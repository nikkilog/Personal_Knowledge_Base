# PITFALL_LOG.md

记录已经发生、原因明确、未来可复用的问题。

------------------------------------------------------------------------

# Authentication 与 Secret 管理

## P032｜OAuth Client Secret 生命周期误判

状态：

已确认。

场景：

创建 Google OAuth Client 后，需要保存 client_secret 用于无弹窗认证。

错误表现：

后续无法再次查看完整 secret，误认为凭据丢失。

错误原因：

OAuth Client Secret 通常只在创建阶段完整展示。

正确做法：

创建后立即保存：

-   Client ID
-   Client Secret
-   JSON 文件

如果遗失：

-   创建新的凭据；
-   不覆盖旧配置；
-   新配置验证成功后再切换。

验收：

确认：

-   credentials 可以生成；
-   refresh token 可以工作；
-   API 可以访问。

------------------------------------------------------------------------

## P033｜OAuth JSON 字段含义混淆

状态：

已确认。

场景：

读取 OAuth JSON 时，将 token_uri 与 refresh_token 混淆。

错误表现：

无法建立无弹窗认证。

错误原因：

token_uri：

是 Google Token Endpoint 地址。

refresh_token：

是授权后的长期刷新凭据。

两者用途不同。

正确做法：

明确保存：

    CLIENT_ID
    CLIENT_SECRET
    REFRESH_TOKEN

使用 OAuth Library 管理流程。

验收：

credentials 可以刷新 access token，并成功调用 API。

------------------------------------------------------------------------

## P034｜双 Runtime 不应维护两套业务代码

状态：

已确认。

场景：

同一个自动化任务需要：

-   Colab 运行；
-   VSCode 本地运行。

错误表现：

维护两份逻辑相同但环境不同的代码。

错误原因：

把运行环境差异混入业务逻辑。

正确做法：

保持：

    Business Logic

单一。

通过：

-   Secret Loader
-   Runtime Adapter
-   Environment Config

处理环境差异。

验收：

同一个 Notebook：

-   Colab 可运行；
-   Local Kernel 可运行；
-   输出结果一致。
