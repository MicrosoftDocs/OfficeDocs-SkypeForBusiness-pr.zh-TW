---
title: 針對 Microsoft 團隊設定網路小組的 [加入檢查清單]
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您為團隊設定您的網路時，請遵循此檢查清單中的核心、執行任務和活動。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cf45acd7053864dbb92e58444cdcc4b162cec9b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573340"
---
# <a name="configure-networking"></a>設定網路

| 不 | 活動或任務 | 說明 | 完畢? | 其他資訊 |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| sr-1  | 審查小組的網路需求 | 在進入網路的詳細資料之前，請先對您的網路需求進行全面瞭解。 | | [為 Microsoft 團隊準備貴組織的網路](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| pplx-2  | 提供網路就緒研討會 | 執行網路就緒評估。 | |  |
| 3  | 使用網路 Planner | 執行網路頻寬規劃。 | | |
| 4  | 驗證使用者連線所需的 NAT 池大小 | 確保已將足夠的公用 IP 位址指派給 NAT 池，以避免埠耗盡。 埠耗盡會影響內部使用者和裝置無法連線至 Office 365 服務的情況。 <br/><br/>連線問題是使用者對雲端服務的感覺問題的主要原因。 | | [使用 Office 365 的 NAT 支援](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 500  | 實施最有效率的路由至 Microsoft 資料中心 | 找出可使用當地或地區出口點數盡可能高效地連線至 Microsoft 網路的位置。 <br/><br/>[**其他資訊**] 欄中的文章說明用戶端如何利用 Office 365 名稱解析中的功能，以及如何有效地將 IP 路由連接至最接近的地區資料中心。 | | [Office 365 用戶端連線](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | 設定連接至團隊連線所需的防火牆埠 | 查看 Office 365 Url 和 Ip，找出並測試內部部署用戶端與伺服器與 Office 365 服務之間連線所需的防火牆埠。 <br/><br/>在支援的環境中，您必須開啟防火牆上的所有埠。 無法開啟某些埠或範圍會對使用者體驗造成負面影響。 根據 [**其他資訊**] 欄中的指示，在防火牆上設定媒體埠。 | | [Office 365 Url 與 IP 位址– Microsoft 團隊](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| utf-7  | 設定 proxy 伺服器 | 設定您的環境，讓 proxy 伺服器遭到略過，而且您可以使用 UDP 直接將使用者連線到 Office 365，以獲得最佳的音訊和視頻品質。 當即時媒體強制遍歷 proxy 伺服器時，小組中的媒體堆疊會強制容錯回復到 TCP，這會對品質造成負面影響。 <br/><br/>為了獲得最高品質的使用者體驗，您總是傾向于 TCP 使用 UDP。 | | [規劃服務管理和品質](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) |
| 型  | 設定分割隧道 VPN | 我們建議您為小組通信量（通常稱為*分割隧道 VPN*）提供備用路徑。 分割隧道表示 Office 365 的流量不會穿過 VPN，但會直接進入 Office 365。 這項變更會對品質產生正面的影響，但也會提供減少 VPN 裝置與組織網路負載的次要優點。 | | 若要實現分割隧道 VPN，請諮詢您的 VPN 供應商以取得設定詳細資料。 |
| 9  | 使用 QoS 設定資料包優先順序 | QoS 應該在受管理的網路的所有區段上執行。 即使已針對頻寬充分提供網路，QoS 也會在事件發生時，在發生意外的網路事件時，降低風險。 當您實現 QoS 時，會優先排列語音流量，以免這些意外的事件不會對品質造成負面影響。 | | [規劃服務管理和品質](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[Microsoft 團隊中的服務品質](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 第 | 針對品質與效能優化 Wi-fi 網路 | 當您優化 Wi-fi 網路時，有幾個因素會發揮作用： <ul><li>實施 QoS 或 Wi-fi 多媒體（WMM），以確保已確定透過 Wi-fi 網路媒體流量的優先順序。</li><li>規劃及優化 Wi-fi 區段和存取點位置。 根據存取點的位置，2.4 GHz 範圍可能會提供足夠的效能。</li></ul> 請諮詢您的 Wi-fi 轉銷商以取得特定指導方針。 | | [端點的 wi-fi 建議](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#wi-fi-recommendations-for-endpoints) |
| 11 | 使用網路評估工具驗證網路連通性 | 使用商務用 Skype 和小組的網路評量工具，測試與商務用 Skype Online 與團隊通話及會議中使用的所有 IP 位址和埠的連線性。 下載工具並查看用法 .docx，以取得如何使用工具及解讀測試結果的詳細資料。 我們建議您在使用團隊的每個位置，在用戶端電腦上執行該工具。 | | [商務用 Skype 和小組網路評估工具](https://go.microsoft.com/fwlink/?linkid=855799) |
