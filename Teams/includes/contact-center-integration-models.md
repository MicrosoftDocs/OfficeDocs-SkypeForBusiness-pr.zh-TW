## <a name="integration-models-for-solution-providers"></a>解決方案提供者的整合模型

<a name="steps"></a>

作為連絡人中心解決方案提供者，有三種模式可供選擇，以將已連接的連絡人中心解決方案整合到 Teams:

- 如果您想要使用認證的 SBC 和直接路由將連絡人中心解決方案連結到 Teams，請參閱[連結模型](?tabs=connect#steps)。

- 如果您想要使用 Azure Bot 和 Microsoft Graph 通訊 API 讓解決方案提供者建立 Teams 應用程式，請參閱 [擴充模型](?tabs=extend#steps)。

- 如果您想要使用可讓解決方案提供者在應用程式中安裝原生 Teams 體驗的 SDK，請參閱 [Power 模型](?tabs=power#steps)。 當 SDK 可供使用時 (接近 2021 年底), 將可以使用 Power 解決方案。

### <a name="the-connect-model"></a>[**連結模型**](#tab/connect)

Connect 模型使用 Microsoft 認證的 SBC 和直接路由，將連絡人中心解決方案連接到 Teams 電話系統基礎結構，啟用增強的路由、組態和系統深入解析。

代理程式可以設定自動化的虛擬助理和技能型路由佇列，以收集資訊，並讓客戶與主題專家連結。

**功能重點:**

雖然這些功能不是此整合模型功能完整的清單，但有四個焦點領域包括：

  - 適用於代理程式的 Office 365 authN，以從整合式 CCaaS 用戶端連線到其 Microsoft 租用戶 

  - 查看 Teams 何時提供代理程式

  - Teams 的轉接和群組通話支援 

  - 與 Teams 整合的 Teams Graph API 和雲端通訊 API 

  - 多租用戶 SIP 主幹以支援解決方案提供者 SBC 上的多個客戶。  

  - 解決方案提供者使用 [<span class="underline"> Microsoft 認證會話邊界控制器 (SBC)</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**延伸模型**](#tab/extend)

延伸模型使用 [Teams 用戶端平台](/microsoftteams/platform/overview)，[Teams Graph API](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 和 [Microsoft Graph 中的 Cloud Communications API](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 與 Teams 用戶端整合。 延伸模型也會針對所有連絡人中心通話和通話控制體驗使用 Teams 電話系統，而連絡人中心解決方案提供者則做為電話語音電信業者，與 Microsoft 365 一起。

代理程式可以使用 Teams 進行內部共同作業和外部通訊，而且可以在開始參與之前，從多個系統關聯資料的動態內容相關筆記獲益，然後避免成本昂貴的內容切換。

組織可以設計工作流程和進階路由組態給個人，並測量其系統與互動的品質。

**功能重點:**

雖然這些功能不是此整合模型功能完整的清單，但有四個焦點領域包括：

  - 與 Teams 整合的 Teams Graph API 和雲端通訊 API 

  - 適用於代理程式體驗的 Teams 型應用程式 

  - Teams 做為代理程式的主要呼叫端點 

  - 所有通話控制項的 Teams 用戶端通話

  - Teams Web 和行動用戶端的代理程式體驗應用程式

  - Teams 中 CCaaS 應用程式的代理程式分析、工作流程管理、角色型體驗 

  - 與 Teams 用戶端整合的聊天和共同作業體驗 

  - 在所有應用程式中保留 Teams 用戶端體驗的效能和品質  

### <a name="the-power-model"></a>[**電源模型**](#tab/power)

Power 模型可讓解決方案提供者使用 Teams 通話基礎結構和用戶端平台建立原生 Azure 語音應用程式，以提供現代化、智慧型的解決方案，以用於共同合作的客戶和代理程式連線。 Power 模型的目標是提供單一應用程式、單一螢幕的連絡人中心體驗。

**功能重點:**

雖然這些功能不是此整合模型功能完整的清單，但有四個焦點領域包括：

  - 透過 Teams SDK 針對全通道通訊原生啟用的正式代理程式體驗 

  - 使用 Teams 共同作業服務進行代理程式共同作業和客戶互動  

  - 快速提供雲端服務，隨時隨地部署 

  - 在 Teams 交談期間，直接控制交談並與使用者互動 

>[!NOTE]
> Power 模型將於 2021 年底提供。
