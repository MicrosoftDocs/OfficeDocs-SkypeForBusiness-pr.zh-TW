---
title: 加入檢查清單-設定直接傳送-Microsoft 團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在團隊中設定直接傳送路線時，請遵循此檢查清單中的核心、執行任務和活動。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 176075b9ea5570b7049ae1647dc63cfebfa84194
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139934"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>在 Microsoft 團隊中設定直接路由

## <a name="direct-routing"></a>直接路由

| 否 | 活動或任務 | 描述 | 完畢? | 其他資訊 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|判斷將針對貴組織的位置部署哪些 PSTN 連線性|Microsoft 提供替代方法，為您的使用者使用 Office 365 Phone 系統提供 PSTN 連線能力。<ul><li>含有通話方案的電話系統（「通話方案」）：商務用 Skype Online 與團隊<li>電話系統 Direct 路由（"直接路由"）：僅限團隊<li>具有內部部署 PSTN 連線的電話系統：僅適用于商務用 Skype Online<li>商務用 skype 雲端連接器版本：僅適用于商務用 Skype Online</ul>[直接傳送] 可提供與呼叫方案相同的優點，除了由協力廠商提供者（而不是 Microsoft）來加速 PSTN 連線以外。 這可讓您在無法使用通話方案的國家或地區進行部署，或是在需要維護現有 PSTN 服務提供者合約，或需要與特定內部部署系統進行互通性的部署中進行。<br><br>決定哪一種選項最適合您的組織。 | |[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[音訊會議與通話方案的加入檢查清單](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams) |
|pplx-2|驗證您的使用者清單和部署節奏，以啟用直接路由|確認您在範圍中有與團隊直接路由的商務單位或網站清單。 使用 [目標] 和 [主要結果] 模型，即可完成直接路由作用中的使用者。 我們建議您以網站為基礎，讓您能將資源集中在一起。<br><br>在您的啟用方案中，請依時間（試驗、網站1、網站2等）識別您要啟用的使用者。||[直接路由展望](2-envision-make-my-service-decisions-direct-routing.md)|
|3|規劃及取得授權|直接傳送的使用者必須具備下列 Office 365 中指派的授權：<ul><li>商務用 Skype Online （方案2）<li>Microsoft Phone 系統<li>Microsoft Teams<li>Microsoft 音訊會議</ul>直接路由還支援已授權呼叫方案的使用者。 含有通話方案的電話系統可以使用直接路由介面傳送一些通話。<br><br>若要將外部參與者新增至排程的會議，請撥打電話給他們，或提供撥入號碼，就必須使用音訊會議授權。||[直接路由授權](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements)|
|4|規劃會話邊界控制器（SBC）功能變數名稱|SBC 功能變數名稱必須來自租使用者的「網域」中所註冊的名稱之一。<br><br>**注意：** 您無法針對 SBC 的完整功能變數名稱（FQDN）使用 *. onmicrosoft.com。<br><br>在規劃每個 SBC 所需的憑證時，SBC 網功能變數名稱稱也很重要。||[SBC 網功能變數名稱稱](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sbc-domain-names)|
|500|規劃憑證|我們強烈建議您透過產生認證簽署要求（CSR）來要求 SBC 的憑證。<br><br>憑證必須在 [主旨]、[常見名稱] 或 [subject 替代名稱] 欄位中有 SBC FQDN。 或者，直接路由支援通用名稱或消費者替換名稱中的萬用字元。<br><br>如需針對 SBC 產生 CSR 的特定指示，請參閱您的 SBC 轉銷商提供的檔。<br><br>[**其他資訊**] 欄中的文章會列出支援的根憑證授權單位。||[SBC 公開信任的憑證](https://docs.microsoft.com/microsoftteams/direct-routing-plan#public-trusted-certificate-for-the-sbc)|
|6|規劃及設定防火牆埠|直接路由的連接點是下列三個 Fqdn：<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>這些連接點與您的 SBCs 之間的流量必須在您的企業防火牆上允許。 您可以在設定 SBC 時定義 SBC 上的 TCP 埠。<br><br>媒體流量是在 UDP 上。 此類型的流量會流向媒體處理器元件。 您的防火牆上也必須允許在 SBCs 與媒體處理器之間進行雙向通訊。<br><br>**注意：** 媒體處理器有動態 IP 位址，而且會在稍後提供靜態 IP 位址。 您可以允許[Azure 資料中心 Ip 範圍](https://www.microsoft.com/download/details.aspx?id=41653)中所列的任何 IP 位址，這一點非常重要。||[SIP 信號： Fqdn 和防火牆埠](https://docs.microsoft.com/microsoftteams/direct-routing-plan#sip-signaling-fqdns-and-firewall-ports)<br><br>[媒體流量： IP 位址與埠範圍](https://docs.microsoft.com/microsoftteams/direct-routing-plan#media-traffic-port-ranges)<br><br>[Azure 資料中心 IP 範圍](https://www.microsoft.com/download/details.aspx?id=41653)|
|utf-7|設定 SBCs|Microsoft 只支援驗證的 SBCs 與直接路由配對。<br><br>使用供應商專用的指示，以及 [**其他資訊**] 欄中的文章中的指示來設定 SBCs。||[支援的會話邊界控制器（SBCs）](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)|
|型|使用直接佈線對 SBCs 進行配對|在每個網站中，SBCs 都必須與直接路由搭配使用，以提供撥號音和 PSTN 通話功能（您自己的 trunks）。<br><br>驗證特定網站中的 SBC 已與直接路由配對，或者如果不在之前就進行設定。<br><br>Microsoft 只支援認證的 SBC 與直接路由配對。 驗證該網站中的 SBC 已認證。||[使 SBC 與電話系統的直接路由服務成對](https://docs.microsoft.com/microsoftteams/direct-routing-configure#pair-the-sbc-to-direct-routing-service-of-phone-system)|
|9|驗證 SBC 配對|針對您`Get-CsOnlinePSTNGateway`針對特定網站進行配對的每個 SBC 執行 Cmdlet，並確認**已啟用**參數顯示值**True**。<br><br>使用 SBC 管理介面，確認 SBC 收到**200 「確定**」對傳出 SIP 選項的回應。|||
|第|驗證使用者設定|請確認使用者帳戶是直接在 Office 365 中建立，或是使用目錄同步處理與 Office 365 同步處理。<br><br>確認已指派所需的授權給使用者。<br><br>針對直接路由的 PSTN 連線，您的使用者必須駐留在商務用 Skype Online 中，且已啟用 Microsoft 團隊。||[允許使用者使用直接路由服務](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|11|設定使用者的電話號碼|直接傳送範圍內的所有使用者，都必須獲指派電話號碼和語音信箱。<br><br> 使用`Set-CsUser` Cmdlet 來啟用語音信箱並將電話號碼指派給您的使用者。||[設定電話號碼並啟用企業語音及語音信箱](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)|
|之間|設定語音路由|[電話系統] 有一個路由機制，可讓您根據下列情況，將呼叫傳送到特定的 SBC：<ul><li>名為 [數位模式]<li>撥打電話的電話號碼模式 + 特定使用者</ul>透過建立下列專案來設定使用者的語音路由：<ul><li>語音路由策略<li>PSTN 用法<li>語音路線<li>線上 PSTN 閘道</ul>||[設定語音路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-voice-routing)|
|合|將 Microsoft 團隊設定為使用者的首選呼叫用戶端|在使用者可以在 Microsoft 團隊中看到 [**通話**] 索引標籤之前，您必須先為 microsoft 團隊中的租使用者啟用**私人通話**，而且小組用戶端必須設定為使用者的**首選呼叫客戶**端。||[啟用 Microsoft 團隊通話](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-calling-for-microsoft-teams)<br><br>[將 Microsoft 團隊設定為使用者的首選呼叫用戶端](https://docs.microsoft.com/microsoftteams/direct-routing-configure#set-microsoft-teams-as-the-preferred-calling-client-for-the-users)|
|4|允許使用者直接傳送|將語音路由策略指派給將透過已設定的 SBC 直接路由的使用者，進行撥打電話並取得 PSTN 通話。||[允許使用者使用直接路由服務](https://docs.microsoft.com/microsoftteams/direct-routing-configure#enable-users-for-direct-routing-service)|
|工資|準備及執行使用者接受度測試|準備及執行使用者接受度測試，包括撥入和撥出案例。||[在團隊中測試雲端語音工作負載](https://docs.microsoft.com/MicrosoftTeams/1-onboard-prepare-my-service#test-cloud-voice-workloads-in-teams)|
|位|報告使用量、健康情況、關鍵成功率（KSIs）及品質|在您在構想階段中定義的使用方式、健康情況、KSIs 和品質等報告。||[操作指南](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service)|

## <a name="next-steps"></a>後續步驟

完成此檢查清單後，您就可以成功地設定直接與您的小組部署進行路由。

在下一個步驟中，使用 [[網站啟用行動手冊-語音（行動手冊）](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) ] 協助您在每個網站上為您的使用者進行設計，並協助確保您規劃並執行重要的網站特定活動。
