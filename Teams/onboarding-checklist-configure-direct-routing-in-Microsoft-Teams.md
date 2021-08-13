---
title: 上線檢查清單 - 設定直接路由 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您在 Teams 中設定直接路由時，請遵循此檢查清單的核心、Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9a6dc19258066efe279e0cc6382839170b2f85c7cb270fda01577d85db25910e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324872"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>在中設定直接路由Microsoft Teams

## <a name="direct-routing"></a>直接路由

| 否 | 活動或工作 | 描述 | 完成？ | 其他資訊 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|決定要針對貴組織的位置部署哪些 PSTN 連接|Microsoft 提供替代方法，以使用或Microsoft 365提供 PSTN Office 365 電話系統。<ul><li>電話系統通話方案 (「通話方案」) ：商務用 Skype線上Teams<li>電話系統直接路由 (「直接路由」) ：Teams路由<li>電話系統內部部署 PSTN 連線：商務用 Skype Online<li>商務用 Skype Cloud Connector Edition：商務用 Skype線上</ul>直接路由為組織提供與通話方案相同的權益，但協力廠商提供者而非 Microsoft 可協助 PSTN 連接。 這可讓部署在未提供通話方案的國家/地區，或需要維護現有 PSTN 服務提供者合約或需要與特定內部部署系統的互通性的部署中。<br><br>決定貴 () 哪一個選項最適合貴組織。 | |[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[音訊會議與通話計畫的上線檢查清單](./onboarding-checklist-configure-cloud-voice-workloads-in-microsoft-teams.md) |
|2|驗證您的使用者清單和啟用直接路由的部署步頻|檢查您是否有適用于直接路由的業務單位或網站Teams。 使用目標與關鍵結果模型，找出哪些使用者會參與直接路由。 我們建議您以網站為基礎工作，這樣您才能專注于資源。<br><br>在啟用計畫中，識別您將啟用的使用者， (試驗、網站 1、網站 2 等等) 。||[直接路由構想](./direct-routing-landing-page.md)|
|3|規劃並取得授權|直接路由的使用者必須在下列授權中指派Microsoft 365或Office 365：<ul><li>商務用 Skype Online (方案 2)<li>Microsoft 電話系統<li>Microsoft Teams<li>Microsoft 音訊會議</ul>直接路由也支援已授權通話方案的使用者。 電話系統通話方案時，您可以使用直接路由介面路由部分通話。<br><br>若要將外部參與者新增到排定的會議，無論是撥出給外部參與者，還是提供撥入號碼，都需要音訊會議授權。||[直接路由授權](direct-routing-plan.md)|
|4|規劃會話邊界控制器 (SBC) 功能變數名稱|SBC 功能變數名稱必須來自租使用者「網域」中註冊的其中一個名稱。<br><br>**注意：** 在 SBC 的 FQDN onmicrosoft.com 中，您 (*.) 功能變數名稱。<br><br>SBC 功能變數名稱對於規劃每個 SBC 所需的憑證也非常重要。||[SBC 功能變數名稱](direct-routing-plan.md)|
|5|規劃憑證|我們強烈建議您要求 SBC 的憑證，在CSR (中) 。<br><br>憑證在主體、通用名稱或主體替代名稱欄位中必須包含 SBC FQDN。 或者，直接路由支援通用名稱或主體替代名稱中的萬用字元。<br><br>有關為 SBC 產生CSR 的特定指示，請參閱 SBC 廠商提供的檔。<br><br>其他資訊 **欄中的文章列出** 支援的根憑證授權單位。||[SBC 的公用信任憑證](direct-routing-plan.md)|
|6|規劃及設定防火牆埠|直接路由的連接點為下列三個 FQDNs：<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>這些連接點和 SBC 之間的流量必須允許在公司防火牆上。 當您設定 SBC 時，您可以在 SBC 上定義 TCP 埠。<br><br>媒體流量位於 UDP 上。 這類流量會流向媒體處理器元件和來自媒體處理器元件。 您的防火牆也必須允許 SBCs 與媒體處理器之間的雙向流量。<br><br>**注意：** 媒體處理器具有動態 IP 位址，靜態 IP 位址稍後會提供。 您必須允許 Azure 資料中心 IP 範圍中列出的任何 [IP 位址](https://www.microsoft.com/download/details.aspx?id=41653)。||[SIP 訊號：FQDNs 和防火牆埠](direct-routing-plan.md)<br><br>[媒體流量：IP 位址和埠範圍](direct-routing-plan.md)<br><br>[Azure 資料中心 IP 範圍](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|設定 SBCs|Microsoft 僅支援經過認證的 SBCs 與直接路由配對。<br><br>Configure SBCs by using vendor-specific guidance and the instructions in the article in the **Additional information** column.||[支援會話邊界控制器 (SBC) ](direct-routing-plan.md)|
|8|將 SBCs 與直接路由配對|每個網站的 SBCs 必須與直接路由配對，以使用您自己的主幹提供撥號音和 PSTN 通話功能。<br><br>驗證該特定網站中的 SBC 已與直接路由配對，或設定配對 ，如果之前未執行。<br><br>Microsoft 僅支援經過認證的 SBC 與直接路由配對。 驗證該網站的 SBC 通過認證。||[將 SBC 與直接路由服務配對電話系統](direct-routing-configure.md)|
|9|驗證 SBC 配對|針對您為特定網站配對的每個 SBC 執行 `Get-CsOnlinePSTNGateway` Cmdlet，並確認參數 **啟用** 會顯示 **值 True**。<br><br>使用 SBC 管理介面來驗證 SBC 是否收到 **200 個 「確定」**  回應給待發 SIP 選項。|||
|10|驗證使用者組組|確認使用者帳戶是直接在中建立，或是使用目錄同步處理Microsoft 365或Office 365同步處理。<br><br>確認已指派必要的授權給使用者。<br><br>針對具有直接路由的 PSTN 連線，您的使用者必須商務用 Skype線上，並啟用 Microsoft Teams。||[啟用使用者進行直接路由服務](direct-routing-configure.md)|
|11|設定使用者的電話號碼|所有在直接路由範圍內的使用者都必須被指派其電話號碼和語音信箱。<br><br> 使用 `Set-CsUser` Cmdlet 啟用語音信箱，並將電話號碼指派給使用者。||[設定電話號碼並啟用企業語音信箱](direct-routing-configure.md)|
|12|設定語音路由|電話系統路由機制，可依據：<ul><li>稱為數位模式<li>呼叫號碼模式 + 撥打通話的特定使用者</ul>建立：為使用者設定語音路由：<ul><li>語音路由策略<li>PSTN 使用量<li>語音路由<li>線上 PSTN 閘道</ul>||[設定語音路由](direct-routing-configure.md)|
|13|將Microsoft Teams設為使用者偏好的通話用戶端|使用者必須先在 Microsoft Teams 中為租使用者啟用私人通話，Teams 用戶端才能在 Microsoft Teams Microsoft Teams 中看見該租使用者。您必須將 Teams 用戶端配置為使用者偏好的通話用戶端。 ||[啟用通話Microsoft Teams](direct-routing-configure.md)<br><br>[將Microsoft Teams設為使用者偏好的通話用戶端](direct-routing-configure.md)|
|14|啟用使用者進行直接路由|透過已配置的 SBC 使用直接路由，將語音路由策略指派給將撥打和接聽 PSTN 通話的使用者。||[啟用使用者進行直接路由服務](direct-routing-configure.md)|
|15|準備並執行使用者接受度測試|準備並執行使用者接受度測試，包括撥入和撥出案例。||[測試雲端語音工作負載Teams](1-onboard-prepare-my-service.md)|
|16|報告使用方式、健康情況、KSIs (關鍵) 及品質|報告在構想階段定義的使用方式、健康情況、KSIs 和品質。||[操作指南](1-drive-value-operate-my-service.md)|

## <a name="next-steps"></a>後續步驟

完成這份檢查清單之後，您已成功在部署中Teams路由。

下一個步驟是使用 Voice (Playbook) 網站啟用 [Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 來協助您在每個網站上上手，並有助於確保您規劃並執行重要的網站特定活動。