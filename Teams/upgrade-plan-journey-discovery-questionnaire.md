---
title: Microsoft 團隊升級 |環境評估、探索問題
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 使用本指導方針，瞭解如何正確評估您目前的環境以升級至團隊的需求。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3d1349cf32e652cc308bb85c187db90303aa959
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808953"
---
# <a name="discovery-questionnaire---evaluate-your-environment"></a>探索問卷-評估您的環境

下列表格清單可協助您在 [升級至團隊之前先評估您的環境](upgrade-plan-journey-evaluate-environment.md)：

- [Microsoft 365 或 Office 365 組織詳細資料](#microsoft-365-or-office-365-organization-details)
- [現有的共同作業平臺摘要](#existing-collaboration-platform-summary)
- [共同作業平臺部署詳細資料](#collaboration-platform-deployment-details)
- [網路和存取 Microsoft 365 或 Office 365 服務](#networking-and-access-to-microsoft-365-or-office-365-services)
- [端點](#endpoints)
- [營運](#operations)
- [採納與準備](#adoption-and-readiness)

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 或 Office 365 組織詳細資料

我們強烈建議您在使用問卷時，擁有有效的 Microsoft 365 或 Office 365 組織。 如果您尚未啟用或設定 Microsoft 365 或 Office 365 組織，請參閱 [規劃 microsoft 365 for business 的設定](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

使用下表來捕獲 Microsoft 365 或 Office 365 組織的相關資訊。

> | 關鍵字 | 自動回應 | 註解 |
> |---|---|---|
> | 請注意生產 Microsoft 365 或 Office 365 組織 <br>[回答] 欄中的名稱和識別碼 <br/>如果您有一個以上的租使用者 <br>與您的組織相關聯， <br>請注意所有 Id。 | 租使用者名稱： <br/>租使用者識別碼：| |
> | 在哪些地區部署承租人？| | |
> | 這些承租人是 Microsoft 365 或 Office 365 多租戶或 <br>負責? | <input type="checkbox"> 多<br/> <input type="checkbox"> 負責 | |
> | 目前使用的是哪些 Microsoft 線上產品？ <br/>請注意每個啟用的使用者數目 <br>[批註] 欄中的 [服務]。 | <input type="checkbox"> Microsoft 團隊 <br/> <input type="checkbox"> 商務用 Skype <br>&nbsp;&nbsp; &nbsp;Online <br/> <input type="checkbox"> Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox"> 商務用 OneDrive <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> 換句話說| |
> | 啟用哪些授權層級 Skype <br>商務用 Online 使用者？ | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 <br/> <input type="checkbox"> 獨立 | 使用者數量 <br>針對每個 SKU： |
> | 什麼是目前的 Active Directory 目錄林 <br>在環境中的功能層級？ <br/>如果有一個以上的目錄林，請注意詳細資料 <br>在 [批註] 欄中。 | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox"> Windows Server 2012 <br/> <input type="checkbox"> Windows Server 2012 R2 <br/> <input type="checkbox"> Windows Server 2016| |
> | 您使用的目錄是什麼 <br>要立即同步處理嗎？ |<input type="checkbox"> (僅限雲端同步)  <br/> <input type="checkbox"> Azure Active Directory <br>&nbsp;&nbsp; &nbsp;至 <br/> <input type="checkbox"> 其他 (指定 <br>&nbsp;&nbsp; &nbsp;[批註] 欄。 ) | |
> | 目前是否已部署聯盟身分識別？ <br/> (Active Directory Federation Services 或 <br>協力廠商)  | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果您使用的是聯盟身分識別， <br>同盟基礎結構？ | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> 協力廠商同盟 <br>&nbsp;&nbsp; &nbsp; 閘道 <br>&nbsp;&nbsp; &nbsp; (請注意，中的詳細資料 <br>&nbsp;&nbsp; &nbsp;[批註] 欄。 )  | |
> | 如果您目前正在維護有效的 Microsoft 365 或 Office 365 <br>租使用者，是您的 SMTP/SIP 網域 <br>與租使用者相關聯的目標使用者？ | <input type="checkbox"> 不適用–無 Microsoft 365 或 Office 365 <br>&nbsp;&nbsp; &nbsp; 租使用者 <br/> <input type="checkbox"> 否，使用者的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 網域沒有關聯 <br>&nbsp;&nbsp; &nbsp; 中的任何租使用者 <br>&nbsp;&nbsp; &nbsp;Microsoft 365 或 Office 365 <br/> <input type="checkbox"> 是，使用者的 SMTP/SIP <br>&nbsp;&nbsp; &nbsp; 網域相關聯 <br>&nbsp;&nbsp; &nbsp; 與現有租使用者 <br>&nbsp;&nbsp; &nbsp; 在 Microsoft 365 或 Office 365 中 | |
> | 使用者 Upn 是否符合其主要 SMTP 位址？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 不一致 | |

## <a name="existing-collaboration-platform-summary"></a>現有的共同作業平臺摘要

使用下表來捕獲現有共同作業平臺部署的相關資訊。

> | 關鍵字 | 自動回應 | 註解 |
> |---|---|---|
> | 已部署 Microsoft 團隊嗎？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 商務用 Skype 是否已部署？ <br/>針對內部部署和混合式部署，請確定 <br>您會注意到版本和累積更新 (CU)  <br>[批註] 欄中的詳細資料。 | <input type="checkbox"> 是，Microsoft 365 或 Office 365 <br/> <input type="checkbox"> 是，使用 Microsoft 365 或 Office 365 的混合式 ()  <br/> <input type="checkbox"> 是，內部部署 <br/> <input type="checkbox"> 是、線上、專用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是、託管、專用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 是、託管、共用 (協力廠商)  <br/> <input type="checkbox"> 否，其他 | |
> | Exchange 是否已部署？ <br/>針對內部部署和混合式部署，請確定 <br>您會注意到批註中的版本與 CU 詳細資料 <br>左欄. | <input type="checkbox"> 是，Microsoft 365 或 Office 365 <br/> <input type="checkbox"> 是，使用 Microsoft 365 或 Office 365 的混合式 ()  <br/> <input type="checkbox"> 是，內部部署 <br/> <input type="checkbox"> 是、線上、專用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是、託管、專用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 是、託管、共用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 否，其他 | |
> | 已部署 SharePoint 嗎？ <br/>針對內部部署和混合式部署，請確定 <br>您會注意到批註中的版本與 CU 詳細資料 <br>左欄. | <input type="checkbox"> 是，Microsoft 365 或 Office 365 <br/> <input type="checkbox"> 是，使用 Microsoft 365 或 Office 365 的混合式 ()  <br/> <input type="checkbox"> 是，內部部署 <br/> <input type="checkbox"> 是、線上、專用 <br>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是、託管、專用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 是、託管、共用 <br>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否已部署 Microsoft 365 或 Office 365 商務用 OneDrive？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您是否已部署任何其他協力廠商平臺 <br>現在還在使用中嗎？ 如果是，請記下的使用者數目 <br>這些平臺和批註中的使用詳細資料 <br>左欄. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> 寬 <br/> <input type="checkbox"> 批註中指定的其他 ( <br>&nbsp;[ &nbsp; &nbsp; 欄]。 )  | 使用者數目： <br/>詳細資料|
> | 您是否計畫將使用者從這些協力廠商移動 <br>是團隊的平臺嗎？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 目前的電話與會議解決方案是什麼？ <br>在此方案的範圍內的使用者？ | | |
> | 您的 SBCs 是否支援針對此方案範圍內的辦公室部署 [直接路由](direct-routing-plan.md#supported-session-border-controllers-sbcs) ？ <br>如果是，請記下 [批註] 欄中的詳細資料。| <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||

## <a name="collaboration-platform-deployment-details"></a>共同作業平臺部署詳細資料

### <a name="microsoft-teams-if-applicable"></a>Microsoft 團隊 (（如果適用）) 

如有需要，請使用下面的範例表格來捕獲團隊部署的詳細資料。 如果您尚未部署團隊，請略過此區段。

> | 關鍵字 | 自動回應 | 註解 |
> |---|---|---|
> | 針對團隊啟用哪些類型的使用者？ | <input type="checkbox"> 組織中的所有使用者 <br/> <input type="checkbox"> 特定使用者/使用者群組 <br>&nbsp;&nbsp; &nbsp; ([批註] 欄中的 [指定])  ||
> | 哪些團隊功能和形式正在使用中？ | <input type="checkbox"> 頻道式交談 <br/> <input type="checkbox"> 私人聊天 <br/> <input type="checkbox"> 來賓存取 <br/> <input type="checkbox"> 頻道會議 <br/> <input type="checkbox"> 私人會議 <br/> <input type="checkbox"> 私人通話 <br/> <input type="checkbox"> 點對點通道頻道 <br/> <input type="checkbox"> 會議中的影片 <br/> <input type="checkbox"> 會議中的螢幕共用 <br/> <input type="checkbox"> 音訊會議 <br/><input type="checkbox"> 應用程式 (應用程式) <br> &nbsp;&nbsp; &nbsp;<input type="checkbox">索引標籤<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">Bot <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">連接線<br><input type="checkbox"> 自訂雲端儲存整合 <br>&nbsp;&nbsp; &nbsp;Dropbox、Box、ShareFile、Google Drive、Egnyte <br/> <input type="checkbox"> 通道電子郵件整合 <br/> <input type="checkbox"> 其他 (在 [批註] 欄中指定。 )  | |
> | 您已將哪些應用程式部署至團隊？ | | |
> | 您是否已明確封鎖任何團隊功能？ <br/>如果是，請記下 [批註] 欄中的詳細資料。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 哪些團隊客戶在使用中？ | <input type="checkbox"> 網站 <br/> <input type="checkbox"> 時間 <br/> <input type="checkbox"> 版 <br/> <input type="checkbox"> 且 <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | 誰有權建立團隊？ | <input type="checkbox"> 組織中的所有人 <br>&nbsp;&nbsp; &nbsp; (這是預設設定)  <br/> <input type="checkbox"> 特定人員 <br>&nbsp;&nbsp; &nbsp; ([批註] 欄中的 [指定]。 )  | |
> | 您是否在團隊中使用安全性與合規性功能？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-online-if-applicable"></a>商務用 Skype Online (（如果適用）) 

如有需要，請使用下面的範例表格來捕獲商務用 Skype Online 部署的詳細資料。 如果您尚未部署商務用 Skype Online 部署，請略過此區段。

> | 關鍵字 | 自動回應 | 註解 |
> |---|---|---|
> | 啟用 Skype 的使用者類型 <br>商務用 Online？ | <input type="checkbox"> 組織中的所有使用者 <br/> <input type="checkbox"> 特定使用者/使用者群組 <br>&nbsp;&nbsp; &nbsp; ([批註] 欄中的 [指定])  | |
> | 目前的形式及功能 <br>目前正在使用中嗎？ | <input type="checkbox"> 立即訊息和目前狀態 (IM/P) <br/> <input type="checkbox"> 舉行 <br/> <input type="checkbox"> 聯盟 <br/> <input type="checkbox"> 會議錄製 <br/> <input type="checkbox"> Microsoft 音訊會議 <br/> <input type="checkbox"> 協力廠商音訊會議 <br>&nbsp;&nbsp; &nbsp; (記下 [批註] 欄中的詳細資料。 )  <br/> <input type="checkbox"> 呼叫方案 (先前的 PSTN 通話)  <br/> <input type="checkbox"> 組織自動語音應答 <br/> <input type="checkbox"> 通話佇列 | |
> | 您已明確封鎖任何 Skype <br>商務用的線上功能 <br>如果是，請記下 [批註] 欄中的詳細資料。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您使用的是哪一種方法，或打算使用它來 <br>將電話系統 (先前的雲端 PBX) 連線至 <br>PSTN？ <br/>選取 [所有適用的]。 | <input type="checkbox"> 呼叫方案 (先前的 PSTN 通話)  <br/> <input type="checkbox"> (利用現有的內部部署 PSTN 連線能力 <br>&nbsp;&nbsp; &nbsp;商務用 Skype 2015 或 Lync Server 2013 <br>&nbsp;&nbsp; &nbsp; 部署)  <br/> <input type="checkbox"> 使用雲端連接器 (內部部署 PSTN 連線)  | |
> | 您是否已將任何電話號碼移植至 Microsoft？ <br/>這適用于通話方案和音訊 <br>會議功能。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>商務用 Skype 內部部署 (（如果適用的話）) 

如果適用的話，請使用下表中的範例資料表，來捕獲商務用 Skype 部署的詳細資料。 如果您尚未部署商務用 Skype 內部部署，請略過此區段。

> | 關鍵字 | 自動回應 | 註解 |
> |---|---|---|
> | 目前所用的 Lync 或商務用 Skype 版本 <br>部署于內部部署？ | <input type="checkbox"> Office 通訊伺服器 2007 "R1" <br/> <input type="checkbox"> Office 通訊伺服器 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> 商務用 Skype Server 2015 <br/> <input type="checkbox"> 商務用 Skype Server 2019 <br/> <input type="checkbox"> 商務用 Skype 雲端連接器版本 | |
> | 是否與設定的商務用 Skype Online 混合？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 此環境是由協力廠商託管及管理嗎？ <br/>如果是，請記下 [批註] 欄中的詳細資料。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 目前使用的形式和功能 <br>即刻? | <input type="checkbox"> 立即訊息和目前狀態 (IM/P)  <br/> <input type="checkbox"> 舉行 <br/> <input type="checkbox"> 聯盟 <br/> <input type="checkbox"> 會議錄製 <br/> <input type="checkbox"> 持續聊天/群組聊天 <br/> <input type="checkbox"> Microsoft 音訊會議 <br>&nbsp;&nbsp; &nbsp; 在您的電腦上 (先前的電話撥入式會議)  <br>&nbsp;&nbsp; &nbsp; 內部部署 Lync Server 或 <br>&nbsp;&nbsp; &nbsp;商務用 Skype 部署 <br/> <input type="checkbox"> 協力廠商音訊會議 <br>&nbsp;&nbsp; &nbsp; (記下 [批註] 欄中的詳細資料)  <br/> <input type="checkbox"> 使用內部部署 PSTN 的企業語音 <br>&nbsp;&nbsp; &nbsp; 連通性 <br/> <input type="checkbox"> 先前的 PSTN 呼叫方案 (以前的 PSTN) 透過 <br>&nbsp;&nbsp; &nbsp;與商務用 Skype Online 混合使用 | |
> | 您已部署 (s) 哪個版本的邊緣伺服器？ | <input type="checkbox"> Office 通訊伺服器 2007 "R1" <br/> <input type="checkbox"> Office 通訊伺服器 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> 商務用 Skype Server 2015 <br/> <input type="checkbox"> 商務用 Skype Server 2019 | |
> | 您是否已部署 Lync 或商務用 Skype Edge <br>在多個資料中心中？ <br/>如果是，請記下 [批註] 欄中的詳細資料。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 選取您的邊緣角色所提供的 [服務]。 | <input type="checkbox"> 外部使用者存取 (公司使用者)  <br/> <input type="checkbox"> 遠端使用者存取 (匿名外部 <br>&nbsp;&nbsp; &nbsp; 會議參與者)  <br/> <input type="checkbox"> 聯盟 <br/> <input type="checkbox"> 媒體轉送 | |
> | 下列哪一項語音通話功能可供您 <br>目前有相依性嗎？ <br/>在批註中記錄任何其他的相依性 <br>左欄. | <input type="checkbox"> 忙碌選項 <br/> <input type="checkbox"> 通話駐留 <br/> <input type="checkbox"> 呼叫裝貨或群組通話提貨 <br/> <input type="checkbox"> 常見的區域電話或「熱 desking」 <br/> <input type="checkbox"> 回應群組或查尋群組 <br/> <input type="checkbox"> 共用線外觀 <br/> <input type="checkbox"> 私人線路 <br/> <input type="checkbox"> 語音信箱 <br/> <input type="checkbox"> 透過公司通話 <br/> <input type="checkbox"> 緊急或資訊號碼 <br>&nbsp;&nbsp; &nbsp; (911、811、411)  <br/> <input type="checkbox"> 擴充撥號 <br/> <input type="checkbox"> 自動語音應答 <br/> <input type="checkbox"> 訂閱者存取 <br/> <input type="checkbox"> 類比裝置 <br/> <input type="checkbox"> 傳入 <br/> <input type="checkbox"> 本機號碼遮罩或變更 <br/> <input type="checkbox"> 以位置為基礎的路由 <br/> <input type="checkbox"> 最低成本的路由 <br/> <input type="checkbox"> 電梯電話 | |

## <a name="networking-and-access-to-microsoft-365-or-office-365-services"></a>網路和存取 Microsoft 365 或 Office 365 服務

您可以使用下表來捕獲貴組織的網路詳細資料，以及您的使用者 (或) 連線至 Microsoft 365 或 Office 365 服務的方式。

> | 關鍵字 | 自動回應 | 註解 |
> |---|---|---|
> | 如何 (或如何) 遷移範圍中的使用者 <br>在 office 中時存取團隊？ <br/>選取 [所有適用的]。 | <input type="checkbox"> 路由 NAT 連線 <br/> <input type="checkbox"> Proxy 伺服器 <br/> <input type="checkbox"> 公用 Wi-Fi <br/> <input type="checkbox"> 受管理的 (不是公用) Wi-Fi <br/> <input type="checkbox"> ExpressRoute (Microsoft 對等)  ||
> | 如果您是透過 proxy 伺服器存取 Microsoft 365 或 Office 365，就是 <br>您可以用任何方式來避開 proxy？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 目前是否使用 ExpressRoute？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 否，但仍在規劃中 | |
> | 您是否已執行網路就緒評估？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 使用者在連線至時，是否需要使用 VPN <br>您遠端的公司資源？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果您使用的是 VPN，就可以將團隊流量排除在 <br>直接存取 Microsoft 365 或 Office 365 服務的 VPN？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您的網路是否支援 QoS？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您可以為小組的音訊和視頻流量進行優先順序排序 <br>若要推動高品質的體驗嗎？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 在區域內的所有位置都有網際網路出口， <br>或是針對整個區域集中進行網際網路出口？ | <input type="checkbox"> 地區對網際網路的存取權 <br/> <input type="checkbox"> 集中存取網際網路 | |

## <a name="endpoints"></a>端點

使用下表來捕獲所使用之用戶端與端點的詳細資料。

> | 關鍵字 | 自動回應 | 註解 |
> |---|---|---|
> | 使用者使用的是哪些桌面作業系統？ | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox"> Windows 8 <br/> <input type="checkbox"> Windows 10 <br/> <input type="checkbox"> Mac (在 [批註] 欄中指定版本。 )  <br/> <input type="checkbox"> Linux (在 [批註] 欄中指定散佈。 )  <br/> <input type="checkbox"> 其他 (請注意 [批註] 欄中的詳細資料。 )  | |
> | 部署的 Microsoft Office 版本 <br>在這些裝置上？ | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox"> Mac 版 Office 2011 <br/> <input type="checkbox"> Mac 版 Office 2016 <br/> <input type="checkbox"> 其他 (請注意 [批註] 欄中的詳細資料。 )  | |
> | 使用的是哪一種 Office 部署技術 <br>在您的組織中？ | <input type="checkbox"> .MSI <br/> <input type="checkbox"> 隨選即用 | |
> | 允許和支援的行動裝置 <br>使用中的平臺？ <br/>選取 [所有適用的]。 | <input type="checkbox"> 時間 <br/> <input type="checkbox"> 電話 <br/> <input type="checkbox"> 且 <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> 其他 (請注意 [批註] 欄中的詳細資料。 )  | |
> | 行動裝置的提供方式為何？ <br/>選取 [所有適用的]。 | <input type="checkbox"> 公司裝置 <br/> <input type="checkbox"> 攜帶您自己的裝置 | |
> | 使用者目前用來存取的裝置 <br>語音和會議服務 <br> (話機、耳機、手機、視頻) ？ | | |

## <a name="operations"></a>營運

您可以使用下表來捕獲環境中運作方面的詳細資料。

> | 關鍵字 | 自動回應 | 註解 |
> |---|---|---|
> | Lync Server 的操作模型是什麼？ <br>商務用 Skype Server、Microsoft 365 或 Office 365 部署 <br>即刻? | | |
> | 您可以將目前的支援方案大綱 <br>Lync Server、商務用 Skype Server、Microsoft 365 或 Office 365？ | | |
> | 如果您要部署至多個國家或地區， <br>每個國家/地區都有自己的 IT/電話 <br>要使用或集中管理此專案的員工嗎？ | <input type="checkbox"> 地區作業與支援 <br/> <input type="checkbox"> 集中式作業及支援 | |
> | 您遵循 [通話品質方法](quality-of-experience-review-guide.md)嗎？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您已將個別或團隊指派給 <br>共同作業平臺的品質擁護者角色 <br>使用中？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 如何監視 Lync Server、Skype <br>商務伺服器、Microsoft 365 或 Office 365 部署？ | | |
> | 您是否遇到通話品質問題？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 您如何以及何時提供訓練給您 <br>支援人員的新服務和功能 | | |

## <a name="adoption-and-readiness"></a>採納與準備

使用下表，並捕獲貴組織目前的採用及準備狀態。

>
> | 關鍵字 | 自動回應 | 註解 |
> |---|---|---|
> | 您目前的使用方式 <br>商務用 Skype？ | **__** % 總作用中使用者與已啟用的使用者 | |
> | 貴組織的使用方式 <br>商務用 Skype？ | 1:1 交談 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">傳遞 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">通話 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">正在<br> 會議 <br>&nbsp;&nbsp; &nbsp;<input type="checkbox">會談<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">正在<br>&nbsp;&nbsp; &nbsp;<input type="checkbox">通話 | |
> | 貴組織是否已採用使用者 <br>並變更管理團隊？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 您目前如何衡量技術的成功 <br>像商務用 Skype 這樣的部署？ | | |
> | 您所說的使用者群百分比是 <br>採用商務用 Skype 嗎？ | | |
> | 商務用 Skype 的使用者觀點是什麼？ | <input type="checkbox"> 良好 <br/> <input type="checkbox"> 通用 <br/> <input type="checkbox"> 壞事 | |
> | 下列哪一項最恰當地描述推出 <br>商務用 Skype 所用的策略 <br>部署? | <input type="checkbox"> 廣泛使用：電子郵件行銷活動 <br>&nbsp;&nbsp; &nbsp; 訓練的連結 <br/> <input type="checkbox"> 已展開：廣泛延伸以及多種 <br>&nbsp;&nbsp; &nbsp; (海報的認知活動 <br>&nbsp;&nbsp; &nbsp; 事件、擁護) 與訓練 <br>&nbsp;&nbsp; &nbsp; (影片、使用者指南、人員內)  <br/> <input type="checkbox"> 量身定制：擴充，加上目標 <br>&nbsp;&nbsp; &nbsp; 依角色進行訊息與訓練 <br/> <input type="checkbox"> 換句話說 <br>&nbsp;&nbsp; &nbsp; (記下 [批註] 欄中的詳細資料。 )  | |


