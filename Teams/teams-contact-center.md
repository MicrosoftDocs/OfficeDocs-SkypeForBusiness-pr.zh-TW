---
title: 小組連絡人中心
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: anblak
localization_priority: Normal
f1.keywords:
- NOCSH
description: 整合式連絡人中心作為服務 (CCaaS Microsoft 團隊的) 解決方案
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f0989c8fade3461418e86713dfb758bc7dfbbcc
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424623"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a>Microsoft 團隊的連絡人中心整合

將流行的接觸中心解決方案與 Microsoft 團隊整合，對於部署小組通話功能的客戶來說是一個常見的需求。  本文將說明連絡人中心解決方案如何與 Microsoft 團隊整合，以及參與 Microsoft 團隊連線的連絡人中心認證計畫的合作夥伴解決方案的其他資訊。

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a>什麼是 Microsoft 團隊的連絡人中心整合？

今天的連絡人中心提供的功能比支援更多-它們的作用是使用其中一個主要機動車來進行互動與針對客戶豐富的品牌提供不相關的意見反應。 由於當今客戶想要使用的頻道種類廣泛（例如，手機、電子郵件、文字、社交，以及與當日購買流程相關的觸控點數延伸，許多組織已有兩個額外的現實：

1. 組織中的每一個成員都有可能參與直接吸引客戶，因此需要配備適當的工具。

2. 此延伸的客戶互動範圍需要能協助磁片一致性、持續改進及規模的工具。

Microsoft 團隊支援客戶互動工作資料流程，方法是在其溝通模式（包括聊天、視訊會議和通話）中充當內部和外部客戶連線的中心。 針對某些公司，Microsoft 團隊的 [雲端語音功能](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)，包括 [自動](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) 語音應答和 [通話佇列](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)，提供功能與設定以滿足其需求。

對於那些想要整合解決方案與商務工具及工作流程以推動客戶歷程的人，Microsoft 團隊也會與一些業界主要的連絡人中心整合，做為服務 (CCaaS) 解決方案提供者。

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a>Microsoft 團隊認證計畫的線上連絡人中心

Api 可讓合作夥伴開發並整合小組的 CCaaS 方案。 此外，我們已開發 Microsoft 團隊認證計畫的線上連絡人中心，為客戶提供每個參與合作夥伴的解決方案都經過測試和驗證，以提供他們預期的品質、相容性及可靠性（由 Microsoft 解決方案提供）。

下列合作夥伴正在驗證其 Microsoft 團隊的解決方案，且已準備好參與客戶：

|  Partner                                                                                                                               |  解決方案網站                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Anywhere365 | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| Competella | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| ComputerTalk | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| ContactCenter4All | www.contactcenter4all.com |
| Enghouse Interactive | http://www.enghouseteams.com/                                                       |
| Five9 | https://www.five9.com/products/application-integration/uc-integration                                                   |
| Genesys | https://www.genesys.com/microsoft                                                                                   |
| Landis 技術 | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| Luware | https://luware.com/en/solutions/                                                                                       |
| 好 inContact | https://www.niceincontact.com/microsoft-teams                                                            |
| Tendfor | https://www.tendfor.com/en/                                                                                     |

此清單會隨著更多合作夥伴加入並符合認證準則而更新。

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a>連絡人中心解決方案在 Microsoft 團隊中的運作方式為何？

Microsoft 團隊提供一系列的功能，可支援開發協力廠商語音解決方案，包括：

1. [直接路由連線](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [Microsoft Graph 雲端通訊 Api](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. 團隊平臺與擴充性

4. 團隊 Sdk

總之，這些功能可讓3個整合模型：

  - 透過 [直接路由 **]** 連線 () 

  - 連線**並延伸** (直接路由、圖形 Api 與團隊 app 平臺) 

  -  (將團隊 Sdk 內嵌到原生團隊互動的3p 應用程式中 **，延伸及加電**) 

### <a name="connect"></a>至

此模型會將 CCaaS 合作夥伴與 Microsoft 團隊手機系統基礎結構連線，以增強路由、配置和系統深入瞭解。 在此模型中，[接觸中心] 合作夥伴解決方案也可以為所選的號碼和使用者提供電話語音。

使用在連線模型上建立之解決方案的代理程式可將資訊 & 真知灼見中收集，以及直接將來電轉接至團隊專家，以確保他們的可用性。

組織可以設定自動化的虛擬助手及以技能為基礎的路由佇列，以確保呼叫能傳送到最佳的代理程式。

**功能重點：**

雖然以下不是此整合模型的完整功能清單，但焦點區域包括：

  - 可讓代理從其整合的 CCaaS 用戶端連線至其 Microsoft 租使用者的 Office 365 authN 

  - 來自團隊使用者的目前狀態指示 

  - 透過 [測試方案] 中的指示，透過直接路由 (通話流程)  

  - 支援使用團隊使用者轉移和群組通話 

  - 團隊圖形 Api 和雲端溝通 Api 與團隊整合 

  - 能夠支援多租使用者 SIP 中繼，以支援合作夥伴的 SBC 中的數個客戶。  

  - 要在 SBC 中實現[ <span class="underline">Microsoft 認證會話邊界控制器 (</span>的合作夥伴) ](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers) 

### <a name="connect-and-extend"></a>連接並延伸

此模型透過在 Microsoft Graph 中使用 [團隊用戶端平臺](https://docs.microsoft.com/microsoftteams/platform/overview)、 [團隊圖表 Api](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 和 [雲端通訊 API](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 與團隊用戶端整合，並使用團隊電話系統進行所有聯絡人通話和通話控制體驗，來延伸連絡人中心人員和代理程式體驗。 在此模型中，連絡人中心合作夥伴就像 Microsoft 365 一樣充當電話運營商。

您可以利用連線與擴充的解決方案，從多個系統開始預訂，然後在內部共同作業和外部通訊的小組中，以無成本的內容切換來獲益。

組織可以設計工作流程並將高級路由設定向下移動到個人，並測量其系統品質與互動。

**功能重點：**

雖然以下不是此整合模型的完整功能清單，但它會醒目提示主要重點領域：

  - 團隊圖形 Api 和雲端溝通 Api 與團隊整合 

  - 以團隊為基礎的應用程式經驗 

  - 團隊成為代理的主要呼叫端點 

  - 小組用戶端呼叫所有通話控制

  - 您也可以在 [團隊網頁與行動用戶端] 上使用 [代理經驗] 應用程式

  - 在團隊內的 CCaaS app 中，針對代理程式進行分析、工作流程管理、以角色為基礎的體驗

  - 與團隊用戶端整合的聊天與共同作業體驗 

  - 在所有應用程式中保持效能與團隊用戶端體驗的品質  

### <a name="extend-and-power"></a>延伸及開啟

此模型可讓合作夥伴利用呼叫基礎結構和用戶端平臺的小組，建立以 Azure 為基礎的語音應用程式，以提供共同作業式客戶與代理程式連線的新型智慧型解決方案。 延伸及加電的目的是 stoke 開發人員創造性，並提升客戶的生產力。

透過直接在 Azure 上建立，合作夥伴可以在所有團隊地區與地域中快速部署和提供其解決方案，benefitting 從我們的共用全域通訊網路，然後充分利用 Azure 的儲存空間、計算、分析 & 認知服務。

透過 [延伸] 與 [電源整合] 模型，合作夥伴可提供含全通道通訊體驗的連絡人中心代理程式，同時結合了人工智慧，來自訂參與者或其他服務在使用 [Microsoft Graph 中的雲端通訊 API](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)進行通話的方式和時機。

**功能重點：**

雖然以下不是此整合模型的完整功能清單，但除了連接和延伸模型提供的功能之外，這些醒目提示也是這些功能。

  - 原生代理程式透過團隊 SDK 以本機方式啟用全通道通訊 

  - 針對代理共同作業和客戶互動運用小組共同作業服務  

  - 提供雲端服務的快速資源調配，隨時隨地部署 

  - 在團隊交談期間進行直接交談控制與使用者互動 

### <a name="comparing-connected-contact-center-integration-models"></a>比較連線的連絡人中心整合模型

請參閱下表以取得 Microsoft 團隊支援的整合模型的概覽。

<table>
<thead>
<tr class="header">
<th></th>
<th><strong>團隊語音應用程式</strong></th>
<th><strong>至</strong></th>
<th><strong>Connect + extend</strong></th>
<th><strong>延伸 + power</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>雲端服務模型</td>
<td>Azure</td>
<td>Partner</td>
<td><p>合作夥伴 +</p>
<p>Azure</p></td>
<td>Azure</td>
</tr>
<tr class="even">
<td>誰負責處理解決方案？</td>
<td>Microsoft</td>
<td>Partner</td>
<td>Partner</td>
<td>Partner</td>
</tr>
<tr class="odd">
<td>M365 登入</td>
<td>是</td>
<td>是</td>
<td>是</td>
<td>是</td>
</tr>
<tr class="even">
<td>有團隊通話的使用者？</td>
<td>非正式、SME</td>
<td>非正式、SME</td>
<td>非正式、SME、正式</td>
<td>非正式、SME、正式</td>
</tr>
<tr class="odd">
<td>IW/SME 經驗</td>
<td>Teams</td>
<td>Teams</td>
<td><p>團隊 +</p>
<p>長度</p></td>
<td><p>團隊 +</p>
<p>長度</p></td>
</tr>
<tr class="even">
<td>服務連線能力</td>
<td>平台<br />
 (通話方案 + DR) </td>
<td>直接路由</td>
<td>直接路由</td>
<td>平台<br />
 (通話方案 + DR) </td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a>後續步驟

如果您是尋找加入認證計畫的供應商，請傳送電子郵件給您 <Teamscategorypartner@microsoft.com> 。
