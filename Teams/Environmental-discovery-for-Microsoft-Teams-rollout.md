---
title: 環境相容性 - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 如何執行詳細的環境探索，以規劃您從商務用 Skype到Microsoft Teams。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d0c5339fd2782ffaa268705aee161256c9aa04e4
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234308"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>推出新Microsoft Teams環境探索

探索是規劃您進行探索之旅時，首先採取的重要Microsoft Teams。

您可以執行環境的詳細探索，以進一步瞭解其目前狀態，並揭露任何困難，或甚至進一步說明執行您的部署Teams障礙。

## <a name="discovery-questionnaire"></a>探索問卷

下列問卷範例會引導您完成一組問題，以確認貴組織已準備好在 Teams 中成功推出音訊會議電話系統通話方案功能。

所有與現有的共同作業基礎結構Microsoft 365組織Office 365網路、端點、作業，以及採用與準備相關的事項，都包含在環境探索問卷中。

問卷分為多個區段，以確認貴組織在幾個主要Teams部署準備就緒。 請與專案小組合作，盡可能提供要求的資訊，以利規劃活動。

> [!TIP]
> 首先，您可以將問卷複製到Microsoft Word檔中。 嘗試回答所有問題，並捕獲所有詳細資料。

### <a name="project-team"></a>Project小組

收集您專案推出專案的重要專案關係人Teams詳細資訊。 請注意，一個人可以在整個專案中扮演數個角色。

> | 角色 | 名稱、電子郵件地址、電話號碼 | 位置、時區 | 註解 |
> |---|---|---|---|
> | 執行贊助人 | | | |
> | Project導致 | | | |
> | 共同合作主管/架構 | | | |
> | 顧問 | | | |
> | Project經理 | | | |
> | 變更管理/採用專家 | | | |
> | 網路潛在客戶 | | | |
> | 安全性潛在客戶 | | | |
> | 電話潛在客戶 | | | |
> | 桌面潛在客戶 | | | |
> | 支援/服務台潛在客戶 | | | |
> | 部署潛在客戶 | | | |
> | 服務擁有者 | | | |
> | 設施潛在客戶 | | | |
> | 影片小組潛在客戶 | | | |
> | 業務單位潛在客戶 | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365或Office 365組織詳細資料

我們強烈建議您在處理此問卷時Microsoft 365或Office 365組織。 如果您尚未啟用或設定組織Microsoft 365或Office 365，請參閱規劃商務Microsoft 365[的設定](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)。

使用下表來捕獲組織或Microsoft 365 Office 365相關資訊。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 請注意生產Microsoft 365<br/>或Office 365組織名稱和識別碼<br/>在答案欄中。 如果您有更多<br/>與一個租使用者相關聯的<br/>請記下貴組織的所有 ID。 | 租使用者名稱： <br/>租使用者識別碼：| |
> | 在哪些區域部署租使用者？| | |
> | 請記下這些Microsoft 365或 <br/>Office 365租使用者。 它們是否多重租戶 <br/>或專用？ | <input type="checkbox"> 多租戶<br/> <input type="checkbox"> 專用 | |
> | 目前使用哪些 Microsoft Online 產品？ <br/>請注意，每個使用者啟用的使用者數目 <br/>服務。 | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">商務用 Skype <br/>&nbsp;&nbsp; &nbsp;線上 <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint線上 <br/> <input type="checkbox">商務用 OneDrive <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> 其他| |
> | 針對哪些使用者啟用Skype等級 <br/>Business Online 使用者？ | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | 使用者數目 <br/>每個 SKU： |
> | 什麼是目前的 Active Directory 樹林 <br/>環境中的功能層級？ <br/>如果有一多個樹林，請記下詳細資料 <br/>在批註欄中。 | <input type="checkbox">WindowsServer 2000 <br/> <input type="checkbox">WindowsServer 2003 <br/> <input type="checkbox">WindowsServer 2008<br/> <input type="checkbox">WindowsServer 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012R 2 <br/> <input type="checkbox">Windows Server 2016| |
> | 您用於目錄的是什麼 <br/>同步處理嗎？ |<input type="checkbox"> 只有雲端 (同步)  <br/> <input type="checkbox">Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; 連線 <br/> <input type="checkbox"> 其他 (指定于 <br/>&nbsp;&nbsp; &nbsp;批註欄.) | |
> | 目前是否部署聯合身分識別？ <br/> (Active Directory Federation Services 或 <br/>協力廠商)  | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果您使用的是聯合身分識別，什麼是 <br/>聯合基礎結構？ | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> 協力廠商聯盟 <br/>&nbsp;&nbsp; &nbsp; 閘道 (記錄詳細資料 <br/>&nbsp;&nbsp; &nbsp; 在批註欄中.)  | |
> | 如果您目前維持使用中Microsoft 365<br/>或 Office 365租使用者，是 SMTP/SIP 網域的 <br/>與租使用者相關聯的目標使用者？ | <input type="checkbox">N/A – Microsoft 365或<br/>&nbsp;&nbsp; &nbsp; Office 365租使用者就地 <br/> <input type="checkbox"> 否，使用者的 SMTP/SIP <br/>&nbsp;&nbsp; &nbsp; 網域未關聯 <br/>&nbsp;&nbsp; &nbsp; 任何租使用者 <br/>&nbsp;&nbsp; &nbsp; Microsoft 365或Office 365<br/> <input type="checkbox"> 是，使用者的 SMTP/SIP <br/>&nbsp;&nbsp; &nbsp; 網域已關聯 <br/>&nbsp;&nbsp; &nbsp; 現有租使用者 <br/>&nbsp;&nbsp; &nbsp; Microsoft 365或Office 365 | |
> | 使用者 UPNs 是否符合其主要 SMTP 位址？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 不一致 | |

## <a name="existing-collaboration-platform-summary"></a>現有的共同合作平臺摘要

使用下表來捕獲現有共同平臺部署的資訊。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 是否Microsoft Teams部署？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否商務用 Skype部署？ <br/>針對內部部署和混合式部署，請確定 <br/>請注意 CU 版本和累積更新 (CU)  <br/>批註欄中的詳細資訊。 | <input type="checkbox">是、Microsoft 365或 <br/>&nbsp; &nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> 是，混合式 ( <br/>&nbsp;&nbsp; &nbsp; Microsoft 365或 <br/>&nbsp;&nbsp; &nbsp; Office 365)  <br/> <input type="checkbox"> 是，內部部署 <br/> <input type="checkbox"> 是，線上，專用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，託管，專用 <br/>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 是、託管、共用 <br/>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否Exchange部署？ <br/>針對內部部署和混合式部署，請確定 <br/>請注意批註中的版本和 CU 詳細資料 <br/>列。 | <input type="checkbox">是，Microsoft 365 <br/> <input type="checkbox"> 是，混合式 ( <br/>&nbsp;&nbsp; &nbsp; Microsoft 365或 <br/>&nbsp;&nbsp; &nbsp; Office 365)  <br/> <input type="checkbox"> 是，內部部署 <br/> <input type="checkbox"> 是，線上，專用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，託管，專用 <br/>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 是、託管、共用 <br/>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否SharePoint部署？ <br/>針對內部部署和混合式部署，請確定 <br/>請注意批註中的版本和 CU 詳細資料 <br/>列。 | <input type="checkbox">是，Microsoft 365 <br/> <input type="checkbox"> 是，混合式 ( <br/>&nbsp;&nbsp; &nbsp; Microsoft 365或 <br/>&nbsp;&nbsp; &nbsp; Office 365)  <br/> <input type="checkbox"> 是，內部部署 <br/> <input type="checkbox"> 是，線上，專用 <br/>&nbsp;&nbsp; &nbsp; (Microsoft)  <br/> <input type="checkbox"> 是，託管，專用 <br/>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 是、託管、共用 <br/>&nbsp;&nbsp; &nbsp; (協力廠商)  <br/> <input type="checkbox"> 否，其他 | |
> | 是否商務用 OneDrive部署？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您是否已部署任何其他協力廠商平臺 <br/>今天使用中？ 如果是這樣，請注意 <br/>這些平臺以及 <br/>批註欄。 | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> 鬆弛 <br/> <input type="checkbox"> 其他 (指定于 <br/>&nbsp;&nbsp; &nbsp;批註欄.)  | 使用者數目： <br/>細節：|
> | 您是否打算將使用者從這些協力廠商移轉 <br/>要Teams？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 什麼是目前的電話和會議解決方案 <br/>此計畫適用範圍的使用者？ | | |
> | 您是否有[支援直接路由部署的 SBC](./direct-routing-plan.md#supported-session-border-controllers-sbcs) <br/>適用于本計畫範圍中的辦公室？ 如果是，請<br/>記下批註欄中的詳細資訊。| <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||

## <a name="collaboration-platform-deployment-details"></a>共同合作平臺部署詳細資料

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (若適用，) 

如果適用，使用下列範例Teams捕獲部署詳細資料。 如果您尚未部署Teams，請略過本節。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 啟用哪些類型的使用者Teams？ | <input type="checkbox"> 組織中所有使用者 <br/> <input type="checkbox"> 特定使用者/使用者群組 <br/>&nbsp;&nbsp; &nbsp; (批註欄中指定。)  ||
> | 目前Teams哪些功能與模式？ | <input type="checkbox"> 頻道型交談 <br/> <input type="checkbox"> 私人聊天 <br/> <input type="checkbox"> 來賓存取 <br/> <input type="checkbox"> 頻道會議 <br/> <input type="checkbox"> 私人會議 <br/> <input type="checkbox"> 私人通話 <br/> <input type="checkbox"> 臨時通道會議 <br/> <input type="checkbox"> 會議中影片 <br/> <input type="checkbox"> 會議中的螢幕畫面共用 <br/> <input type="checkbox"> 音訊會議 <br/><input type="checkbox"> 應用程式 (應用程式) <br/> &nbsp;&nbsp; &nbsp;<input type="checkbox">標籤<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">機器人 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">連接<br/><input type="checkbox"> 自訂雲端儲存空間整合 <br/>&nbsp;&nbsp; &nbsp; Dropbox、Box、ShareFile、Google <br/>&nbsp;&nbsp; &nbsp;雲端硬碟，Egnyte <br/> <input type="checkbox"> 頻道電子郵件整合 <br/> <input type="checkbox"> 其他 (批註欄中指定。)  | |
> | 您部署哪些應用程式Teams？ | | |
> | 您是否已特別封鎖任何Teams功能？ <br/>如果是，請記下批註欄中的詳細資訊。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 哪些Teams用戶端使用中？ | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows移動 | |
> | 神秘建立團隊的許可權嗎？ | <input type="checkbox"> 組織中所有人 <br/>&nbsp;&nbsp; &nbsp; (這是預設設定)  <br/> <input type="checkbox"> 特定人員 <br/>&nbsp;&nbsp; &nbsp; (批註欄中指定。)  | |
> | 您是否在 Teams 使用安全性與合規性Teams？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-online-if-applicable"></a>商務用 Skype線上 (若適用) 

若適用，使用下列範例商務用 Skype線上部署詳細資料。 如果您尚未在線上部署商務用 Skype，請略過本節。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 啟用哪些類型的使用者Skype <br/>商務用 Online？ | <input type="checkbox"> 組織中所有使用者 <br/> <input type="checkbox"> 特定使用者/使用者群組 <br/>&nbsp;&nbsp; &nbsp; (批註欄中指定。)  | |
> | 目前採用什麼模式和功能 <br/>今天使用中？ | <input type="checkbox"> 立即訊息和目前狀態 (IM/P) <br/> <input type="checkbox"> 會議 <br/> <input type="checkbox"> 聯合會 <br/> <input type="checkbox"> 會議錄製 <br/> <input type="checkbox"> Microsoft 音訊會議 <br/> <input type="checkbox"> 協力廠商音訊會議 (筆記<br/>&nbsp;&nbsp; &nbsp; 批註欄中的詳細資訊。)  <br/> <input type="checkbox"> 通話方案 (PSTN 通話)  <br/> <input type="checkbox"> 組織自動助理 <br/> <input type="checkbox"> 通話佇列 | |
> | 您是否特別封鎖任何Skype <br/>Business Online 功能？ <br/>如果是，請記下批註欄中的詳細資訊。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您用或打算使用什麼方法 <br/>將電話系統 (前雲端 PBX)  <br/>PSTN？ <br/>選取所有適用專案。 | <input type="checkbox"> 通話方案 (PSTN 通話)  <br/> <input type="checkbox"> 內部部署 PSTN 連接 <br/>&nbsp;&nbsp; &nbsp; (利用現有Skype <br/>&nbsp;&nbsp; &nbsp;Business 2015 或 Lync Server <br/>&nbsp;&nbsp; &nbsp; 2013 部署)  <br/> <input type="checkbox"> 內部部署 PSTN 連接 <br/>&nbsp;&nbsp; &nbsp; (雲端連接器)  | |
> | 您是否將任何電話號碼移植到 Microsoft？ <br/>這適用于通話方案與音訊 <br/>會議功能。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |

### <a name="skype-for-business-on-premises-if-applicable"></a>商務用 Skype內部部署 (內部部署) 

如果適用，請用下列範例商務用 Skype捕獲部署詳細資料。 如果您尚未在內部部署商務用 Skype，請略過本節。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | Lync 或 商務用 Skype <br/> 目前部署于內部部署？ | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">商務用 Skype Server 2015 <br/> <input type="checkbox">商務用 Skype Server 2019 <br/><input type="checkbox">商務用 Skype雲端連接器 <br/>&nbsp;&nbsp; &nbsp;版 | |
> | 是否已商務用 Skype線上的混合式？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 此環境是由協力廠商託管和管理嗎？ <br/>党？ 如果是，請記下 <br/>批註欄。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 目前使用的模式和功能 <br/>今天？ | <input type="checkbox"> 立即訊息和目前狀態 (IM/P)  <br/> <input type="checkbox"> 會議 <br/> <input type="checkbox"> 聯合會 <br/> <input type="checkbox"> 會議錄製 <br/> <input type="checkbox"> 永久聊天/ 群組聊天 <br/> <input type="checkbox"> Microsoft 音訊會議 <br/>&nbsp;&nbsp; &nbsp; (電話撥入會議) 您的 <br/>&nbsp;&nbsp; &nbsp; 內部部署 Lync Server 或 <br/>&nbsp;&nbsp; &nbsp; 商務用 Skype部署 <br/> <input type="checkbox"> 協力廠商音訊會議 <br/>&nbsp;&nbsp; &nbsp; (批註中記下詳細資料 <br/>&nbsp;&nbsp; &nbsp; column.)  <br/> <input type="checkbox">企業語音使用內部部署 <br/>&nbsp; &nbsp; &nbsp;PSTN 連線能力 <br/> <input type="checkbox"> 通話方案 (PSTN 通話) 透過 <br/>&nbsp;&nbsp; &nbsp;與 商務用 Skype Online 的混合式 | |
> | 您 () 部署哪些版本的 Edge Server？ | <input type="checkbox">OfficeCommunications Server 2007 "R1" <br/> <input type="checkbox">OfficeCommunications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">商務用 Skype Server 2015 <br/> <input type="checkbox">商務用 Skype Server 2019| |
> | 您是否擁有 Lync 或 商務用 Skype Edge <br/>部署至多個資料中心？ <br/>如果是，請記下批註欄中的詳細資訊。 | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 選取您的 Edge 角色今天提供的服務。 | <input type="checkbox"> 外部使用者存取 (企業使用者)  <br/> <input type="checkbox"> 遠端使用者存取 (匿名 <br/>&nbsp;&nbsp; &nbsp; 外部會議參與者)  <br/> <input type="checkbox"> 聯合會 <br/> <input type="checkbox"> 媒體轉場 | |
> | 您擁有下列哪些語音通話功能 <br/>目前是否具有相依性？ <br/>請注意批註中任何其他相依性 <br/>列。 | <input type="checkbox"> 忙碌選項 <br/> <input type="checkbox"> 通話停駐 <br/> <input type="checkbox"> 呼叫代答或群組呼叫代答 <br/> <input type="checkbox"> 常用區域電話或「熱電話機」 <br/> <input type="checkbox"> 回應群組或搜尋群組 <br/> <input type="checkbox"> 共用線條外觀 <br/> <input type="checkbox"> 私人線路 <br/> <input type="checkbox"> 語音 信箱 <br/> <input type="checkbox"> 透過公司通話 <br/> <input type="checkbox"> 緊急或資訊號碼 <br/>&nbsp;&nbsp; &nbsp; (911、811、411)  <br/> <input type="checkbox"> 分機撥號 <br/> <input type="checkbox"> 自動助理 <br/> <input type="checkbox"> 訂閱者存取 <br/> <input type="checkbox"> 類比裝置 <br/> <input type="checkbox"> 傳真 <br/> <input type="checkbox"> 本機號碼遮罩或變更 <br/> <input type="checkbox"> 位置型路由 <br/> <input type="checkbox"> 最低成本路由 <br/> <input type="checkbox"> 電話通話 | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>網路和存取Microsoft 365 Office 365服務

使用下表來捕獲貴組織的網路詳細資料，以及使用者 (或) 與Microsoft 365 Office 365方式。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 如何 (移) 範圍中的使用者 <br/>當他們Teams時，可以存取嗎？ <br/>選取所有適用專案。 | <input type="checkbox"> 路由 NAT 連接 <br/> <input type="checkbox"> Proxy 伺服器 <br/> <input type="checkbox"> 公用Wi-Fi <br/> <input type="checkbox"> 管理 (非公用) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (Microsoft 對等)  ||
> | 如果存取Microsoft 365或Office 365是透過<br/>Proxy 伺服器，有任何方法可以忽略 Proxy 嗎？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 今天是否使用 ExpressRoute？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 <br/> <input type="checkbox"> 否，但正在規劃中 | |
> | 您是否已執行網路就緒性評定？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 使用者是否須使用 VPN 才能連接到 <br/>遠端公司資源？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 如果使用 VPN，Teams流量排除在 <br/>VPN 以直接存取Microsoft 365 Office 365服務？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您的網路是否支援 QoS？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您能否優先Teams音訊和視Teams流量 <br/>以提升高品質的體驗？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 是否一個地區的所有位置都有網際網路出口， <br/>或網際網路出口是否集中到整個地區？ | <input type="checkbox"> 地區網際網路存取權 <br/> <input type="checkbox"> 集中存取 <br/>&nbsp;&nbsp; &nbsp; 網際網路 | |

## <a name="endpoints"></a>端點

使用下表來捕獲使用中的用戶端和端點詳細資料。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 使用者使用的是哪些桌面作業系統？ | <input type="checkbox">WindowsXp <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (在批註欄中指定版本。)  <br/> <input type="checkbox"> Linux (在批註欄中指定發佈。)  <br/><input type="checkbox"> 其他 (在批註欄中記下詳細資料。)  | |
> | 已部署Microsoft Office版本 <br/>這些裝置？ | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">2013 Office月 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Mac 版 Office 2011 <br/> <input type="checkbox">Mac 版 Office 2016 <br/> <input type="checkbox"> 其他 (在批註欄中記下詳細資料。)  | |
> | 使用Office部署技術 <br/>在貴組織中？ | <input type="checkbox"> 微星 <br/> <input type="checkbox"> 按一下以執行 | |
> | 允許和支援的行動電話是什麼 <br/>使用中的平臺？ <br/>選取所有適用專案。 | <input type="checkbox">Windows <br/> <input type="checkbox"> 移動 <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> 其他 (在批註欄中記下詳細資料。)  | |
> | 行動裝置如何提供？ <br/>選取所有適用專案。 | <input type="checkbox"> 公司裝置 <br/> <input type="checkbox"> 攜帶您自己的裝置 | |
> | 使用者目前用於存取的裝置 <br/>語音和會議服務 <br/> (聽筒、耳機、電話、視) ？ | | |

## <a name="operations"></a>營運

使用下表來捕獲您環境的操作層面詳細資料。

> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 您的 Lync Server 操作模型是什麼， <br/>商務用 Skype Server，Microsoft 365部署， <br/>或Office 365部署？ | | |
> | 您可以概述目前支援安排 <br/>Lync Server、商務用 Skype Server、Microsoft 365、 <br/>或Office 365？ | | |
> | 如果您要部署至多個國家/地區， <br/>每個國家/地區都有自己的 IT/電話 <br/>教職員要合作，或這會集中管理嗎？ | <input type="checkbox"> 地區營運與支援 <br/> <input type="checkbox"> 集中式作業和支援 | |
> | 您是否遵循通話品質方法？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 | |
> | 您是否將個人或小組指派給 <br/>共同合作平臺的品質促進者角色 <br/>使用中？ | <input type="checkbox"> 是的 <br/> <input type="checkbox"> 不 ||
> | 如何監控 Lync Server，Skype <br/>Business Server、Microsoft 365部署，或 <br/>Office 365部署？ | | |
> | 您遇到通話品質問題嗎？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 如何及何時提供訓練 <br/>新服務和功能的技術服務人員？ | | |

## <a name="adoption-and-readiness"></a>採用與準備

使用下表，並捕獲貴組織目前的採用和準備狀態。

>
> | 問題 | 回答 | 註解 |
> |---|---|---|
> | 您目前使用中的使用方式 <br/>商務用 Skype？ | **__** 使用中使用者總數與啟用使用者百分比 | |
> | 貴組織如何使用 <br/>商務用 Skype？ | 1：1 交談 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">我 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">叫 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共用<br/> 會議 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">會議<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">共用<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox">叫 | |
> | 您的組織是否擁有使用者採用 <br/>以及變更管理團隊？ | <input type="checkbox"> 是的<br/> <input type="checkbox"> 不 | |
> | 您目前如何衡量技術的成功 <br/>推出類似 商務用 Skype？ | | |
> | 您說的使用者基礎百分比 <br/>已商務用 Skype？ | | |
> | 使用者對於您商務用 Skype？ | <input type="checkbox"> 好 <br/> <input type="checkbox"> 中性 <br/> <input type="checkbox"> 壞 | |
> | 下列哪一項最能說明推出 <br/>適用于您的商務用 Skype <br/>部署？ | <input type="checkbox"> 廣泛覆蓋：電子郵件行銷活動 <br/>&nbsp;&nbsp; &nbsp; 訓練連結 <br/> <input type="checkbox"> 已展開：廣泛覆蓋及各種 <br/>&nbsp;&nbsp; &nbsp; 宣傳 (海報， <br/>&nbsp;&nbsp; &nbsp; 活動、) 和訓練 <br/>&nbsp;&nbsp; &nbsp; (影片、使用者指南、個人)  <br/> <input type="checkbox"> 量身訂做：已展開，加上已鎖定目標 <br/>&nbsp;&nbsp; &nbsp; 按人員傳送訊息與訓練 <br/> <input type="checkbox"> 其他 <br/>&nbsp;&nbsp; &nbsp; (請注意批註欄中的詳細資訊。)  | |
