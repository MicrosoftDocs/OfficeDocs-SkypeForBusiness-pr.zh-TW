## <a name="integration-models-for-solution-providers"></a>解決方案提供者的整合模型

<a name="steps"></a>

作為聯絡中心解決方案提供者，您可以選擇三種模式，將已連接的聯絡人中心解決方案整合至 Teams：

- 如果您想要使用認證 SBCs 和直接路由將聯絡中心解決方案連結至 Teams，請參閱 [連接模型](?tabs=connect#steps)。

- 如果您想要使用 Azure Bot 和 Microsoft Graph 通訊 API 來啟用解決方案提供者建立 Teams 應用程式，請參閱 [延伸模型](?tabs=extend#steps)。

- 如果您想要使用可讓解決方案提供者在 App 中內安裝原生 Teams 體驗的 SDK，請參閱 [Power 模型](?tabs=power#steps)。 在 2021 年底提供 SDK 時，將可以使用 Power Solutions。

### <a name="the-connect-model"></a>[**連接模型**](#tab/connect)

Connect 模型使用 Microsoft 認證的 SBCs 和直接路由，將聯絡人中心解決方案連接到 Teams 電話系統基礎結構，啟用增強的路由、組配置和系統深入見解。

代理人可以設定自動化虛擬助理員和技能型路由佇列，以收集資訊，並讓客戶與主題專家聯繫。

**功能重點：**

雖然這些功能不是此整合模型的功能全面清單，但焦點區域包括：

  - 適用于代理人的 Office 365 authN，以從整合的 CCaaS 用戶端連接到其 Microsoft 租使用者 

  - 查看 Teams 何時可以使用代理程式

  - Teams 的轉接和群組通話支援 

  - 與 Teams 整合的 Teams Graph API 和雲端通訊 API 

  - 多租使用者 SIP 主幹，可支援解決方案提供者 SBC 上的多個客戶。  

  - 解決方案提供者使用 [<span class="underline">Microsoft 認證的會話邊界控制器 (SBC) </span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**延伸模型**](#tab/extend)

擴充模型會使用 Microsoft Graph 中的 [Teams](/microsoftteams/platform/overview)用戶端平臺 [、Teams Graph API](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 和雲端通訊 API 與 [Teams 用戶端整合](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)。 延伸模式也會使用 Teams 電話系統，以用於所有聯絡中心通話和通話控制體驗，而聯絡中心解決方案提供者會和 Microsoft 365 一起做為電話業者。

代理人可以使用 Teams 進行內部共同合作和外部通訊，而且可以在開始進行互動之前，從多個系統的資料相互關聯的動態關聯性筆記獲益，然後避免成本昂貴的上下文切換。

組織可以向下設計工作流程和進位路由組組，並測量其系統與互動的品質。

**功能重點：**

雖然這些功能不是此整合模型的功能全面清單，但焦點區域包括：

  - 與 Teams 整合的 Teams Graph API 和雲端通訊 API 

  - 適用于代理人體驗的 Teams 型應用程式 

  - Teams 是代理程式的主要通話端點 

  - 所有通話控制項的 Teams 用戶端通話

  - Teams Web 和行動用戶端的 Agent 體驗應用程式

  - Teams 中 CCaaS 應用程式中的代理人分析、工作流程管理、角色型體驗

  - 與 Teams 用戶端整合的聊天和共同合作體驗 

  - 在所有應用程式中保留 Teams 用戶端體驗的績效和品質  

### <a name="the-power-model"></a>[**Power 模型**](#tab/power)

Power 模型可讓解決方案提供者使用 Teams 通話基礎結構和用戶端平臺建立原生 Azure 語音應用程式，以提供現代化智慧型解決方案，以用於共同操作的客戶和代理人員連接。 Power 模型的目標是提供單一應用程式、單螢幕聯絡中心體驗。

**功能重點：**

雖然這些功能不是此整合模型的功能全面清單，但焦點區域包括：

  - 正式代理體驗原生啟用，透過 Teams SDK 進行全通道通訊 

  - 使用 Teams 共同服務進行代理人共同合作和客戶互動  

  - 快速部署雲端服務，隨時隨地部署 

  - 在 Teams 交談期間直接進行交談控制及與使用者互動 

>[!NOTE]
> Power 模型將于 2021 年底提供。
