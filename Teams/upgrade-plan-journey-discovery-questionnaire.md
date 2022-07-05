---
title: Microsoft Teams 升級|環境評估，探索問題
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 請使用此指導方針來瞭解適當評估您目前環境升級至 Teams 的需求。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a72fda2622ab9bcd56520e48db38335d72423e46
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616029"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>探索問卷 - 評估您的環境

下列表格清單問題可協助您 [在升級至 Teams 之前評估您的環境](upgrade-plan-journey-evaluate-environment.md)：

- [Microsoft 365 或Office 365組織詳細資料](#microsoft-365-or-office-365-organization-details)
- [現有的共同作業平臺摘要](#existing-collaboration-platform-summary)
- [共同作業平臺部署詳細資料](#collaboration-platform-deployment-details)
- [Microsoft 365 或 Office 365 服務的網路功能和存取權](#networking-and-access-to-microsoft-365-or-office-365-services)
- [端點](#endpoints)
- [營運](#operations)
- [採用和整備](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 或Office 365組織詳細資料

我們強烈建議您在使用問卷時，擁有有效的 Microsoft 365 或Office 365組織。 如果您尚未啟用或設定 Microsoft 365 或Office 365組織，請參閱[規劃您的商務用 Microsoft 365 設定](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

使用下表擷取 Microsoft 365 或Office 365組織的相關資訊。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 請注意 Microsoft 365 或Office 365組織的生產 <br>[解答] 欄中的名稱和識別碼 <br/>如果您有多個租使用者 <br>[與您的組織相關聯] 底下， <br>記下所有識別碼。 | 租使用者名稱： <br/>租使用者識別碼：| |
> | 在哪些地區部署租使用者？| | |
> | 這些租使用者是 Microsoft 365 或 Office 365 Multitenant 或 <br>專用？ | <input type="checkbox"> 多重元數<br/> <input type="checkbox"> 專用 | |
> | 目前使用哪些 Microsoft Online 產品？ <br/>請注意，每個使用者都已啟用 <br>[批註] 欄中的 [服務]。 | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox">商務用 Skype <br>&nbsp;&nbsp; &nbsp;線上 <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox">商務用 OneDrive <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> 其他| |
> | Skype 的授權層級 <br>商務線上使用者？ | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> 獨立 | 使用者數目 <br>每個 SKU： |
> | 什麼是目前的 Active Directory 樹系 <br>環境中的功能層級？ <br/>如果有一個以上的森林，請注意詳細資料 <br>在 [批註] 欄中。 | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | 您用於目錄的功能 <br>今天同步處理嗎？ |<input type="checkbox"> 僅限雲端 (同步處理)  <br/> <input type="checkbox"> Azure Active Directory <br>&nbsp;&nbsp; &nbsp;連接 <br/> <input type="checkbox"> 其他 (在 <br>&nbsp;&nbsp; &nbsp;批註欄.) | |
> | 同盟身分識別目前是否已部署？ <br/> (Active Directory 同盟服務或 <br>協力廠商)  | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果您使用同盟身分識別，什麼是 <br>同盟基礎結構？ | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> 協力廠商同盟 <br>&nbsp;&nbsp; &nbsp; 閘道 <br>&nbsp;&nbsp; &nbsp; (請注意 <br>&nbsp;&nbsp; &nbsp;批註欄.)  | |
> | 如果您目前維護作用中的 Microsoft 365 或 Office 365 <br>租使用者，是您的 SMTP/SIP 網域 <br>與租使用者相關聯的目標使用者？ | <input type="checkbox">不適用 – 沒有 Microsoft 365 或 Office 365 <br>&nbsp;&nbsp; &nbsp; 租使用者就地 <br/> <input type="checkbox"> 否，使用者的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 網域沒有關聯 <br>&nbsp;&nbsp; &nbsp; 與任何租使用者在 <br>&nbsp;&nbsp; &nbsp;Microsoft 365 或 Office 365 <br/> <input type="checkbox"> 是，使用者的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 網域相關聯 <br>&nbsp;&nbsp; &nbsp; 與現有租使用者 <br>&nbsp;&nbsp; &nbsp; Microsoft 365 或 Office 365 | |
> | 使用者 UPN 是否符合其主要 SMTP 位址？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 不一致 | |

## <a name="existing-collaboration-platform-summary"></a>現有的共同作業平臺摘要

使用下表擷取現有共同作業平臺部署的相關資訊。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 是否已部署 Microsoft Teams？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否已部署商務用 Skype？ <br/>對於內部部署和混合式部署，請確定 <br>您會記下 CU)  (版本和累積更新 <br>[批註] 欄中的詳細資料。 | <input type="checkbox">是，Microsoft 365 或 Office 365 <br/> <input type="checkbox">是，使用 Microsoft 365 或 Office 365) 的混合式 ( <br/> <input type="checkbox"> 是，內部部署 <br/> <input type="checkbox"> 是，線上，專用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，託管，專用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 是、託管、共用 (協力廠商)  <br/> <input type="checkbox"> 否，其他 | |
> | Exchange 是否已部署？ <br/>對於內部部署和混合式部署，請確定 <br>請注意批註中的版本和 CU 詳細資料 <br>列。 | <input type="checkbox">是，Microsoft 365 或 Office 365 <br/> <input type="checkbox">是，使用 Microsoft 365 或 Office 365) 的混合式 ( <br/> <input type="checkbox"> 是，內部部署 <br/> <input type="checkbox"> 是，線上，專用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，託管，專用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 是、託管、共用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 SharePoint？ <br/>對於內部部署和混合式部署，請確定 <br>請注意批註中的版本和 CU 詳細資料 <br>列。 | <input type="checkbox">是，Microsoft 365 或 Office 365 <br/> <input type="checkbox">是，使用 Microsoft 365 或 Office 365) 的混合式 ( <br/> <input type="checkbox"> 是，內部部署 <br/> <input type="checkbox"> 是，線上，專用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，託管，專用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 是、託管、共用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 Microsoft 365 或Office 365 商務用 OneDrive？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您是否已部署任何其他協力廠商平臺 <br>和今天一起使用嗎？ 如果是，請記下 <br>這些平臺和批註中的使用詳細資料 <br>列。 | <input type="checkbox"> Cisco Webex <br/> <input type="checkbox"> 鬆弛 <br/> <input type="checkbox"> 批註中的其他 (指定 <br>&nbsp;&nbsp; &nbsp; column.)  | 使用者數目： <br/>細節：|
> | 您打算從這些協力廠商移動使用者嗎？ <br>要移至 Teams 的平臺嗎？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 什麼是目前的電話語音和會議解決方案 <br>參與此計畫之範圍的使用者？ | | |
> | 您是否有支援針對參與此計畫之範圍之辦公室部署 [之直接路由的 SB](direct-routing-plan.md#supported-session-border-controllers-sbcs) ？ <br>如果是，請記下 [批註] 欄中的詳細資料。| <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||

## <a name="collaboration-platform-deployment-details"></a>共同作業平臺部署詳細資料

### <a name="microsoft-teams-if-applicable"></a>如果適用，Microsoft Teams () 

如果適用，請使用下表範例，擷取 Teams 部署的詳細資料。 如果您尚未部署 Teams，請略過此區段。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | Teams 已啟用哪些類型的使用者？ | <input type="checkbox"> 組織中的所有使用者 <br/> <input type="checkbox"> 特定使用者/使用者群組 <br>&nbsp;&nbsp; &nbsp; (在 [批註] 欄) 中指定 ||
> | 正在使用哪些 Teams 功能和形式？ | <input type="checkbox"> 以頻道為基礎的交談 <br/> <input type="checkbox"> 私人聊天 <br/> <input type="checkbox"> 來賓存取 <br/> <input type="checkbox"> 頻道會議 <br/> <input type="checkbox"> 私人會議 <br/> <input type="checkbox"> 私人通話 <br/> <input type="checkbox"> 臨機操作頻道會議 <br/> <input type="checkbox"> 會議中的影片 <br/> <input type="checkbox"> 會議中的螢幕畫面分享 <br/> <input type="checkbox"> 音訊會議 <br/><input type="checkbox"> 應用程式 (應用程式) <br> &nbsp;&nbsp; &nbsp;<input type="checkbox">標籤<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">機器人 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">連接<br><input type="checkbox"> 自訂雲端儲存整合 <br>&nbsp;&nbsp; &nbsp;Dropbox、Box、ShareFile、Google 雲端硬碟、Egnyte <br/> <input type="checkbox"> 通道電子郵件整合 <br/> <input type="checkbox"> [批註] 欄中的其他 (指定)  | |
> | 您已將哪些應用程式部署到 Teams？ | | |
> | 您是否特別封鎖任何 Teams 功能？ <br/>如果是，請記下 [批註] 欄中的詳細資料。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 正在使用哪個 Teams 用戶端？ | <input type="checkbox"> Web <br/> <input type="checkbox"> 窗戶 <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | 誰有權建立團隊？ | <input type="checkbox"> 組織中的每個人 <br>&nbsp;&nbsp; &nbsp; (這是預設設定)  <br/> <input type="checkbox"> 特定人員 <br>&nbsp;&nbsp; &nbsp; (在 [批註] 欄中指定。)  | |
> | 您是否在 Teams 中使用安全性與合規性功能？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-online-if-applicable"></a>商務用 Skype Online (如果適用) 

如果適用，請使用下表範例，擷取商務用 Skype線上部署的詳細資料。 如果您尚未部署商務用 Skype線上部署，請略過此區段。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | Skype 啟用的使用者類型 <br>商務用 Online？ | <input type="checkbox"> 組織中的所有使用者 <br/> <input type="checkbox"> 特定使用者/使用者群組 <br>&nbsp;&nbsp; &nbsp; (在 [批註] 欄) 中指定 | |
> | 目前是什麼形式和功能 <br>今天使用中？ | <input type="checkbox"> 立即訊息和目前狀態 (IM/P) <br/> <input type="checkbox"> 會議 <br/> <input type="checkbox"> 聯合會 <br/> <input type="checkbox"> 會議錄製 <br/> <input type="checkbox"> Microsoft Audio Conferencing <br/> <input type="checkbox"> 協力廠商音訊會議 <br>&nbsp;&nbsp; &nbsp; (記 [批註] 欄中的詳細資料。)  <br/> <input type="checkbox"> 通話方案 (舊稱 PSTN 通話)  <br/> <input type="checkbox"> 組織自動語音應答 <br/> <input type="checkbox"> 通話佇列 | |
> | 是否已明確封鎖任何 Skype <br>商務線上功能？ <br>如果是，請記下 [批註] 欄中的詳細資料。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您正在使用何種方法，或打算使用什麼方法來 <br>將電話系統 (先前稱為雲端 PBX) 連線至 <br>PSTN？ <br/>選取所有適用的選項。 | <input type="checkbox"> 通話方案 (舊稱 PSTN 通話)  <br/> <input type="checkbox"> 內部部署 PSTN 連線 (運用現有 <br>&nbsp;&nbsp; &nbsp; 商務用 Skype 2015 或 Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; 部署)  <br/> <input type="checkbox"> 使用雲端連接器 (的內部部署 PSTN 連線)  | |
> | 您是否將任何電話號碼移轉到 Microsoft？ <br/>這適用于通話方案和音訊 <br>會議功能。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>如果適用，商務用 Skype內部部署 () 

如果適用，請使用下表範例，擷取商務用 Skype部署的詳細資料。 如果您尚未部署商務用 Skype內部部署，請略過此區段。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 目前 Lync 或 商務用 Skype 的版本 <br>部署在內部部署嗎？ | <input type="checkbox"> Office Communications Server 2007 「R1」 <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">商務用 Skype Server 2015 <br/> <input type="checkbox">商務用 Skype Server 2019 <br/> <input type="checkbox">商務用 Skype Cloud Connector Edition | |
> | 已設定商務用 Skype Online 的混合式？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 這個環境是由協力廠商託管和管理嗎？ <br/>如果是，請記下 [批註] 欄中的詳細資料。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 目前使用何種形式和功能 <br>今天？ | <input type="checkbox"> 立即訊息和目前狀態 (IM/P)  <br/> <input type="checkbox"> 會議 <br/> <input type="checkbox"> 聯合會 <br/> <input type="checkbox"> 會議錄製 <br/> <input type="checkbox"> 常設聊天室 /群組聊天 <br/> <input type="checkbox"> Microsoft Audio Conferencing <br>&nbsp;&nbsp; &nbsp; (先前在您的會議中撥入會議)  <br>&nbsp;&nbsp; &nbsp; 內部部署 Lync Server 或 <br>&nbsp;&nbsp; &nbsp; 商務用 Skype部署 <br/> <input type="checkbox"> 協力廠商音訊會議 <br>&nbsp;&nbsp; &nbsp; (請記下 [批註] 欄) 中的詳細資料 <br/> <input type="checkbox">企業語音使用內部部署 PSTN <br>&nbsp;&nbsp; &nbsp; 連接 <br/> <input type="checkbox"> 通話方案 (舊稱 PSTN 通話) 透過 <br>&nbsp;&nbsp; &nbsp;與 商務用 Skype Online 的混合式 | |
> | 您已部署 Edge Server 的哪個版本 () ？ | <input type="checkbox"> Office Communications Server 2007 「R1」 <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">商務用 Skype Server 2015 <br/> <input type="checkbox">商務用 Skype Server 2019 | |
> | 您是否已部署 Lync 或 商務用 Skype Edge？ <br>進入多個資料中心？ <br/>如果是，請記下 [批註] 欄中的詳細資料。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 選取您 Edge 角色目前提供的服務。 | <input type="checkbox"> 外部使用者存取 (公司使用者)  <br/> <input type="checkbox"> 匿名外部使用者存取 ( <br>&nbsp;&nbsp; &nbsp; 會議參與者)  <br/> <input type="checkbox"> 聯合會 <br/> <input type="checkbox"> 媒體轉送 | |
> | 您可使用下列哪些語音通話功能 <br>目前有相依性嗎？ <br/>請注意批註中的任何其他相依性 <br>列。 | <input type="checkbox"> 忙碌選項 <br/> <input type="checkbox"> 通話駐留 <br/> <input type="checkbox"> 撥號接聽電話或群組通話取貨 <br/> <input type="checkbox"> 常見的區域電話或「熱門桌面電話」 <br/> <input type="checkbox"> 回應群組或搜尋群組 <br/> <input type="checkbox"> 共用線條外觀 <br/> <input type="checkbox"> 私人行 <br/> <input type="checkbox"> 語音 信箱 <br/> <input type="checkbox"> 透過工作撥號 <br/> <input type="checkbox"> 緊急或資訊號碼 <br>&nbsp;&nbsp; &nbsp; (911、811、411)  <br/> <input type="checkbox"> 擴充功能撥號 <br/> <input type="checkbox"> 自動語音應答 <br/> <input type="checkbox"> 訂閱者存取權 <br/> <input type="checkbox"> 類比裝置 <br/> <input type="checkbox"> 傳真 <br/> <input type="checkbox"> 來電者識別碼遮罩或變更 <br/> <input type="checkbox"> 以位置為基礎的路由 <br/> <input type="checkbox"> 成本最低的路由 <br/> <input type="checkbox"> 升降機手機 | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>Microsoft 365 或 Office 365 服務的網路功能和存取權

請使用下表來擷取貴組織的網路詳細資料，以及您的使用者 (或將) 連線至 Microsoft 365 或Office 365服務的方式。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 如何 (或如何) 移轉範圍中的使用者 <br>當他們在辦公室時，可以存取 Teams 嗎？ <br/>選取所有適用的選項。 | <input type="checkbox"> 路由 NAT 連線 <br/> <input type="checkbox"> Proxy 伺服器 <br/> <input type="checkbox"> 公用Wi-Fi <br/> <input type="checkbox"> 受管理 (而非公開) Wi-Fi <br/> <input type="checkbox"> ExpressRoute (Microsoft 對等)  ||
> | 如果存取 Microsoft 365 或 Office 365 是透過 Proxy 伺服器，就在那裡 <br>有任何略過 Proxy 的方法嗎？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 現在是否正在使用 ExpressRoute？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 否，但計畫中 | |
> | 您是否已執行網路整備評估？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 連線到的使用者是否需要使用 VPN <br>遠端公司資源？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果使用 VPN，可以排除 Teams 流量 <br>直接存取 Microsoft 365 或 Office 365 服務的 VPN？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您的網路是否支援 QoS？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您可以排定 Teams 音訊和視訊流量的優先順序嗎？ <br>想要提供高品質的體驗嗎？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 執列區域內的所有位置都有網際網路出口， <br>還是整個地區的網際網路出口集中？ | <input type="checkbox"> 地區網際網路存取權 <br/> <input type="checkbox"> 集中式存取網際網路 | |

## <a name="endpoints"></a>端點

使用下表擷取使用中的用戶端和端點的詳細資料。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 使用者使用的是哪一種桌面作業系統？ | <input type="checkbox"> Windowsxp <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (在 [批註] 欄中指定版本。)  <br/> <input type="checkbox"> Linux (指定 [批註] 欄中的發佈。)  <br/> <input type="checkbox"> 其他 (請記下 [批註] 欄中的詳細資料。)  | |
> | 部署的 Microsoft Office 版本 <br>要使用這些裝置嗎？ | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox">Mac 版 Office 2011 <br/> <input type="checkbox">Mac 版 Office 2016 <br/> <input type="checkbox"> 其他 (請記下 [批註] 欄中的詳細資料。)  | |
> | 正在使用哪個 Office 部署技術 <br>在您的組織中？ | <input type="checkbox"> 微星 <br/> <input type="checkbox"> 隨選即用 | |
> | 行動裝置允許和支援的功能 <br>使用中的平臺？ <br/>選取所有適用的選項。 | <input type="checkbox"> 窗戶 <br/> <input type="checkbox"> 移動 <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> 其他 (請記下 [批註] 欄中的詳細資料。)  | |
> | 如何提供行動裝置？ <br/>選取所有適用的選項。 | <input type="checkbox"> 公司裝置 <br/> <input type="checkbox"> 攜帶您自己的裝置 | |
> | 使用者目前用來存取哪些裝置 <br>語音和會議服務 <br> (話筒、耳機、手機、視訊) ？ | | |

## <a name="operations"></a>營運

使用下表擷取您環境操作層面的詳細資料。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | Lync Server 的操作模型為何， <br>商務用 Skype Server、Microsoft 365 或 Office 365 部署 <br>今天？ | | |
> | 您是否可以為目前的支援安排建立大綱 <br>Lync Server、商務用 Skype Server、Microsoft 365 或 Office 365？ | | |
> | 如果您要部署到多個國家或地區， <br>每個國家/地區都有自己的 IT/電話語音 <br>要與其合作的員工，還是會集中管理？ | <input type="checkbox"> 地區營運及支援 <br/> <input type="checkbox"> 集中式作業和支援 | |
> | 您是否遵循 [通話品質方法](quality-of-experience-review-guide.md)？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您是否已將個人或小組指派給 <br>共同作業平臺的品質冠軍角色 <br>在使用中？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 如何監視您的 Lync Server、Skype for <br>商務伺服器、Microsoft 365 或Office 365部署？ | | |
> | 您是否遇到通話品質問題？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 如何以及何時提供訓練給您的 <br>新服務和功能的技術支援？ | | |

## <a name="adoption-and-readiness"></a>採用和整備

請使用下表，並擷取貴組織目前的採用和整備狀態。

>
> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 您目前的使用狀況 <br>商務用 Skype？ | **__** 作用中使用者總數與啟用使用者的百分比 | |
> | 貴組織如何使用 <br>商務用 Skype？ | 1：1 交談 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">我 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">叫 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共用<br> 會議 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">會議<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">共用<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">叫 | |
> | 您的組織是否擁有使用者採用 <br>和變更管理小組？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 您目前如何衡量科技成功 <br>像商務用 Skype一樣推行？ | | |
> | 您會說什麼百分比的使用者基礎 <br>採用商務用 Skype？ | | |
> | 使用者對於商務用 Skype的情懷為何？ | <input type="checkbox"> 好 <br/> <input type="checkbox"> 中性 <br/> <input type="checkbox"> 壞 | |
> | 下列哪一項最適合說明推出 <br>用於商務用 Skype的策略 <br>部署？ | <input type="checkbox"> 廣泛連絡人：電子郵件行銷活動 <br>&nbsp;&nbsp; &nbsp; 訓練連結 <br/> <input type="checkbox"> 展開：廣寬範圍加上各種 <br>&nbsp;&nbsp; &nbsp; 宣傳活動 (海報， <br>&nbsp;&nbsp; &nbsp; 活動、冠軍) 和訓練 <br>&nbsp;&nbsp; &nbsp; (影片、使用者指南、親自)  <br/> <input type="checkbox"> 量身打造：展開，加上目標 <br>&nbsp;&nbsp; &nbsp; 依角色傳訊和訓練 <br/> <input type="checkbox"> 其他 <br>&nbsp;&nbsp; &nbsp; (記 [批註] 欄中的詳細資料。)  | |


