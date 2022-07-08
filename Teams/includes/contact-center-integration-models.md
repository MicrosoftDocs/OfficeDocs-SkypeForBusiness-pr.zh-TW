## <a name="integration-models-for-solution-providers"></a>解決方案提供者的整合模型

<a name="steps"></a>

身為連絡人中心解決方案提供者，您可以選擇三種將連線的連絡人中心解決方案整合至 Teams 的模型：

- 如果您想要使用通過認證的 SBC 和直接路由將連絡人中心解決方案連線至 Teams，請參閱 [連線模型](?tabs=connect#steps)。

- 如果您想要使用 Azure Bot 和 Microsoft Graph Communication API 來啟用解決方案提供者來建立 Teams 應用程式，請參閱 [延伸模型](?tabs=extend#steps)。

- 如果您想要使用 SDK，讓解決方案提供者在他們的應用程式中注入原生 Teams 體驗，請參閱 [電源模型](?tabs=power#steps)。 當 SDK 可用時，就可以使用電源解決方案。 即將推出。

### <a name="the-connect-model"></a>[**連線模型**](#tab/connect)

連線模型使用 Microsoft 認證的 SBC 和直接路由，將連絡人中心解決方案連線到 Teams 電話系統基礎結構，啟用增強的路由、設定和系統深入解析。

專員可以設定自動化虛擬助理和技能型路由佇列，以收集資訊，並與主題專家聯繫客戶。

**功能重點：**

雖然這些功能並非此整合模型的完整功能清單，但重點領域包括：

- Office 365驗證專員從其整合的 CCaaS 用戶端連線到他們的 Microsoft 租使用者

- 查看 Teams 何時提供專員

- Teams 的轉接和群組通話支援

- Teams 圖形 API 和雲端通訊 API 與 Teams 整合

- 多租使用者 SIP 主控功能可在解決方案提供者的 SBC 上支援多個客戶。

- 解決方案提供者使用[ <span class="underline">Microsoft 認證會話框線控制器 (SBC) </span>](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**延伸模型**](#tab/extend)

延伸模型與 Teams 用戶端整合，使用 Microsoft Graph 中 [Teams 用戶端平臺](/microsoftteams/platform/overview)、 [Teams 圖形 API](/graph/api/resources/teams-api-overview) 和 [雲端通訊 API](/graph/api/resources/communications-api-overview)。 延伸模式也會針對所有連絡人中心通話和通話控制體驗使用 Teams 電話系統，而聯繫中心解決方案提供者會同時做為電話語音電信業者與 Microsoft 365 一起運作。

代理商可以使用 Teams 進行內部共同作業和外部通訊，而且在開始參與之前，可以從多個系統中相互關聯的動態內容筆記獲益，然後避免成本高昂的關係切換。

組織可以設計工作流程和進階路由設定，直至個別，並測量其系統和互動的品質。

**功能重點：**

雖然這些功能並非此整合模型的完整功能清單，但重點領域包括：

- Teams 圖形 API 和雲端通訊 API 與 Teams 整合

- 適用于專員體驗的 Teams 型應用程式

- Teams 做為專員的主要通話端點

- 所有通話控制項的 Teams 用戶端通話

- Teams Web 和行動用戶端的代理程式體驗應用程式

- Teams 中的 CCaaS 應用程式中的分析、工作流程管理、代理程式角色式體驗

- 與 Teams 用戶端整合的聊天和共同作業體驗

- 在所有應用程式中保留 Teams 用戶端體驗的效能和品質

> [!NOTE]
> 專員 Bot 不需要電話系統授權。 Teams 使用者確實需要電話系統授權和電話號碼。

### <a name="the-power-model"></a>[**電源模型**](#tab/power)

Power 模型可讓解決方案提供者使用 Teams 通話基礎結構和用戶端平臺建立原生 Azure 語音應用程式，以提供現代化的智慧型解決方案，以共同作業客戶和代理商連線。 Power 模型的目標是提供單一應用程式的單螢幕連絡人中心體驗。


> [!NOTE]
> 即將推出。
