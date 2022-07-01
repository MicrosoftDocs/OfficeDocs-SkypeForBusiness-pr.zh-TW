---
title: 上線檢查清單 - 設定直接路由 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您在 Teams 中設定直接路由時，請遵循此檢查清單中的核心待辦事項工作和活動。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b25bea2fb2b3e6994259f9f9d606b8bda6fa22c8
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563901"
---
# <a name="configure-direct-routing-in-microsoft-teams"></a>在 Microsoft Teams 中設定直接路由

## <a name="direct-routing"></a>直接路由

| 否 | 活動或工作 | 描述 | 完成？ | 其他資訊 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1|判斷要針對組織位置部署的 PSTN 連線能力|Microsoft 提供替代方法，為使用 Microsoft 365 或 Office 365 電話系統 的使用者提供 PSTN 連線。<ul><li>電話系統與通話方案 (「通話方案」) ：商務用 Skype Online 和 Teams<li>電話系統直接路由 (「直接路由」) ：僅限 Teams<li>具有內部部署 PSTN 連線能力的電話系統：僅限 商務用 Skype Online<li>商務用 Skype Cloud Connector Edition：僅限 商務用 Skype Online</ul>直接路由可讓組織獲得與通話方案相同的權益，但 PSTN 連線是由協力廠商提供者而不是 Microsoft 提供者提供。 這可在無法使用通話方案的國家/地區進行部署，或在需要維護現有 PSTN 服務提供者合約或需要與特定內部部署系統互通性的部署中部署。<br><br>決定最適合貴組織 () 選項。 | |[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br><br>[音訊會議和通話方案的上線檢查清單](./onboarding-checklist-configure-cloud-voice-workloads-in-microsoft-teams.md) |
|2|確認您的使用者清單和啟用直接路由的部署頻率|檢查您是否有商務單位或網站清單，以供 Teams 直接路由使用。 使用目標和關鍵結果模型，找出哪些使用者將處於直接路由的範圍。 我們建議您逐網站工作，以便專注資源。<br><br>做為啟用計畫的一部分，請在 (試驗、網站 1、網站 2 等) 時識別您將啟用哪些使用者。||[直接路由想像](./direct-routing-landing-page.md)|
|3|規劃和取得授權|直接路由使用者必須在 Microsoft 365 或 Office 365 中指派下列授權：<ul><li>商務用 Skype Online (方案 2)<li>Microsoft Phone System<li>Microsoft Teams<li>Microsoft Audio Conferencing</ul>直接路由也支援具有通話方案授權的使用者。 電話系統與通話方案可以使用直接路由介面來路由一些通話。<br><br>若要將外部參與者新增至排定的會議，需要音訊會議授權，方法是向他們撥出電話或提供撥入號碼。||[直接路由授權](direct-routing-plan.md)|
|4|規劃會話框線控制器 (SBC) 功能變數名稱|SBC 功能變數名稱必須來自租使用者「網域」中註冊的其中一個名稱。<br><br>**注意：** 您無法使用 *.onmicrosoft.com 做為 SBC 的完整功能變數名稱 (FQDN) 。<br><br>在規劃每個 SBC 所需的憑證時，SBC 功能變數名稱也很重要。||[SBC 功能變數名稱](direct-routing-plan.md)|
|5|規劃憑證|我們強烈建議您透過產生認證簽署要求 (CSR) ，來要求 SBC 的憑證。<br><br>憑證的主旨、通用名稱或主旨替代名稱欄位中必須有 SBC FQDN。 或者，直接路由支援通用名稱或主旨替代名稱中的萬用字元。<br><br>如需產生 SBC CSR 的特定指示，請參閱 SBC 廠商所提供的檔。<br><br>[ **其他資訊** ] 欄中的文章會列出支援的跟憑證授權單位單位。||[SBC 的公用信任憑證](direct-routing-plan.md)|
|6|規劃及設定防火牆埠|直接路由的連接點為下列三個 FQDN：<ul><li>sip.pstnhub.microsoft.com<li>sip2.pstnhub.microsoft.com<li>sip3.pstnhub.microsoft.com</ul>您公司防火牆必須允許這些連接點和您的 SBC 之間的流量。 設定 SBC 時，您可以定義 SBC 上的 TCP 埠。<br><br>媒體流量是在 UDP 上。 這種類型的流量流經媒體處理器元件。。 您的防火牆也必須允許 SB 和媒體處理器之間的雙向流量。<br><br>**注意：** 媒體處理器具有動態 IP 位址，而靜態 IP 位址則會在稍後提供使用。 請務必允許 [Azure Datacenter IP 範圍](https://www.microsoft.com/download/details.aspx?id=41653)中列出的任何 IP 位址。||[SIP 訊號：FQDN 和防火牆埠](direct-routing-plan.md)<br><br>[媒體流量：IP 位址和埠範圍](direct-routing-plan.md)<br><br>[Azure Datacenter IP 範圍](https://www.microsoft.com/download/details.aspx?id=41653)|
|7|設定 SBC|Microsoft 僅支援通過認證的 SB 與直接路由配對。<br><br>使用廠商專屬的指引及其他 **資訊** 欄中文章中的指示來設定 SBC。||[支援的會話框線控制器 (SBC) ](direct-routing-plan.md)|
|8|將 SBC 與直接路由配對|每個網站中的 SBC 都必須與直接路由配對，才能使用您自己的主幹來提供撥號和 PSTN 通話功能。<br><br>驗證該特定網站中的 SBC 已與直接路由配對，如果之前未執行，請設定配對。<br><br>Microsoft 僅支援經過認證的 SBC 與直接路由配對。 驗證該網站中的 SBC 已通過認證。||[將 SBC 與電話系統的直接路由服務配對](direct-routing-configure.md)|
|9|驗證 SBC 配對|`Get-CsOnlinePSTNGateway`針對您為特定網站配對的每一個 SBC 執行 Cmdlet，並 **確認 Enabled 參數** 顯示 **True 值**。<br><br>使用 SBC 管理介面來確認 SBC 取得 **200 個「確定」**  回應給外寄 SIP 選項。|||
|10|驗證使用者設定|確認使用者帳戶是直接在 Microsoft 365 中建立或同步處理，或使用目錄同步處理Office 365。<br><br>確認已將必要的授權指派給使用者。<br><br>若要使用直接路由進行 PSTN 連線，您的使用者必須在 商務用 Skype Online 中並啟用 Microsoft Teams。||[啟用使用者的直接路由服務](direct-routing-configure.md)|
|11|設定使用者的電話號碼|所有處於直接路由範圍的使用者都必須獲派電話號碼。<br><br> 使用 `Set-CsPhoneNumberAssignment` Cmdlet 將電話號碼指派給使用者。||[設定電話號碼，並啟用企業語音和語音信箱](direct-routing-configure.md)|
|12|設定語音路由|電話系統有一種路由機制，可讓呼叫根據下列專案傳送到特定 SBC：<ul><li>稱為數位模式<li>撥打號碼模式 + 撥打電話的特定使用者</ul>建立以下方法，為使用者設定語音路由：<ul><li>語音路由原則<li>PSTN 使用量<li>語音路由<li>線上 PSTN 閘道</ul>||[設定語音路由](direct-routing-configure.md)|
|13|將 Microsoft Teams 設定為使用者的慣用通話用戶端|使用者在 Microsoft Teams 中看到 [ **通話** ] 索引標籤之前，您必須在 Microsoft Teams 中為租使用者啟用 **私人通話** ，且 Teams 用戶端必須設定為使用者的 **慣用通話客戶** 端。||[啟用 Microsoft Teams 通話](direct-routing-configure.md)<br><br>[將 Microsoft Teams 設定為使用者的慣用通話用戶端](direct-routing-configure.md)|
|14|啟用使用者的直接路由|使用直接路由透過設定的 SBC，將語音路由原則指派給進行 PSTN 通話的使用者。||[啟用使用者的直接路由服務](direct-routing-configure.md)|
|15|準備並執行使用者接受度測試|準備並執行使用者接受度測試，包括撥入和撥出案例。||[在 Teams 中測試雲端語音工作負載](1-onboard-prepare-my-service.md)|
|16|報告使用方式、健康情況 (KSIs) 和品質的重要成功指標|根據您在 [想像] 階段中定義的使用方式、健康情況、KSI 和品質報告。||[操作指南](1-drive-value-operate-my-service.md)|

## <a name="next-steps"></a>後續步驟

完成此檢查清單之後，您就可以成功設定 Teams 部署的直接路由。

在下一個步驟中，使用 [Voice (Playbook 的網站啟用播放簿) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 來協助您在每一個網站上設定使用者，並協助確保您規劃和執行重要的網站特定活動。
