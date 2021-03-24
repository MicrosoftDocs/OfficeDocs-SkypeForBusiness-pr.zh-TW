---
title: 上機檢查清單 - 設定雲端語音工作負載 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille
description: 當您在 Teams 中設定雲端語音工作負載時，請遵循此檢查清單的核心、任務和活動。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c9c22190a5a4237eaa61ede4c7aa82e7a7cee94
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098049"
---
# <a name="configure-cloud-voice-workloads-in-microsoft-teams"></a>在 Microsoft Teams 中設定雲端語音工作負載

## <a name="audio-conferencing"></a>音訊會議

| 否 | 活動或工作 | 說明 | 完成？ | 其他資訊 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 判斷音訊會議是否適用于貴組織的位置 | Microsoft 在多個國家/地區及城市提供音訊會議。 請參閱其他 **資訊列中的** 指南，瞭解涵蓋的最新國家/地區清單。 <br/><br/> 您可以選取某個國家/地區，以查看哪些 Teams 語音工作負載可供使用。 | | [音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 驗證您的使用者清單和啟用音訊會議部署步頻    | 檢查您是否有適用于 Teams 音訊會議之業務單位或網站的清單。 使用目標與關鍵結果模型，找出哪些使用者將適用範圍。 建議您以網站為基礎工作，這樣您才能專注于資源。<br/><br/> 在啟用計畫中，找出您將啟用的使用者，以及何時 (試驗、網站 1、網站 2 等等) 。 | | [音訊會議構想](./audio-conferencing-in-office-365.md)|
| 3  | 取得電話號碼 | 瞭解可與 Teams 音訊會議工作負載一起使用的服務號碼。<br/><br/> 從 Microsoft 取得新電話號碼，或為網站的音訊會議橋接器號碼排程號碼移植。<br/><br/> 針對音訊會議，您也可以轉移現有的免付費號碼，或者，從 Microsoft 取得新的免付費號碼。<br/><br/> 若要取得服務號碼，如果您的國家/地區已列出，但商務用 Skype 系統管理中心沒有服務號碼，請于 (傳送美國) 或 (美國以外的國家/地區的新電話號碼 <ptn@microsoft.com> <ptneu@microsoft.com> 要求) 。 若要詳細資訊，請參閱連結至其他資訊列中的「管理貴組織的電話號碼 **」指引。** <br/><br/>**注意：** 根據服務提供者的不同，號碼移植程式最多可能需要 30 天。 請務必在規劃中考慮到這一點。 | | [用於通話方案的各種電話號碼](/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[取得新的使用者電話號碼要求表單](/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[為您的使用者取得電話號碼](./getting-phone-numbers-for-your-users.md) <br/><br/>[將電話號碼移轉至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[移轉電話號碼的常見問題](/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理貴組織的電話號碼](/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 設定您的預設會議橋接器電話號碼 | 您可以設定貴組織的預設會議橋接器電話號碼，此號碼會指派給已啟用但並未明確指派會議橋接器電話號碼的使用者。 預設號碼應該會與貴組織的中心位置對齊。 | | [設定邀請中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) |
| 5  | 設定會議橋接器電話號碼的語言 | 為會議橋接器電話號碼設定主要和次要語言。 <br/><br/>確認地區會議橋接器電話號碼已指派適當的語言來支援您的使用者。 | | [設定音訊會議的自動語音應答語言](/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) |
| 6  | 設定會議橋接器設定 | 設定會議加入體驗、PIN 長度，以及會議進入/離開公告設定。 讓這些會議橋接器設定與貴組織的目標保持一致。 | | [變更音訊會議橋接器的設定](/SkypeForBusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge) |
| 7  | 自訂會議邀請 | 作為系統管理員，您可以在會議邀請中加入 URL，連結至説明或法律資訊。 您也可以更新標誌，並新增頁腳文字至邀請。 | | [自訂會議邀請](/SkypeForBusiness/set-up-skype-for-business-online/customize-meeting-invitations) |
| 8  | 設定撥號方案 | 撥號方案可讓使用者以他們習慣的方式撥打電話號碼，例如省略當地電話的區碼、省略國內通話的國家/地區代碼，或甚至使用短數位撥號在會議期間撥出給其他使用者。 <br/><br/>預設服務撥號方案是以使用者的 Microsoft 365 或 Office 365 使用位置為基礎，無法變更。 <br/><br/>如果預設服務撥號方案不符合您的需求，您可以設定租使用者或使用者層級的租使用者撥號方案。 | | [Microsoft Teams 音訊會議中的撥號方案](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) <br/><br/>[Microsoft 365 和 Office 365 通話方案撥號方案](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 9  | 指派會議號碼和 PIN 給使用者 | 根據預設，會議號碼會依照已選取的預設號碼 Teams 系統管理員指派給使用者。 初始使用者 PIN 是根據 PIN 策略隨機產生的。<br/><br/> 使用者將會收到電子郵件中的會議號碼和 PIN。 使用者可以變更其 PIN。 <br/><br/>做為系統管理員，您可以啟用撥入使用者使用與預設號碼和當地號碼不同的會議號碼。 | | |
| 10 | 準備並執行使用者接受度測試 | 準備並執行使用者接受度測試，包括撥入和撥出案例。 | | [音訊會議測試計劃](./deploy-audio-conferencing-teams-landing-page.md) |
| 11 | 報告使用方式、健康情況、關鍵成功指示器和品質 | 報告在構想階段定義的使用方式、健康情況、KSIs 和品質。 | | [操作指南](./1-drive-value-operate-my-service.md) |

## <a name="calling-plans"></a>通話方案

| 否 | 活動或工作 | 說明 | 完成？ | 其他資訊 |
|----|---------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 判斷貴組織位置是否提供通話方案功能 | Microsoft 在多個國家/地區及城市提供電話系統與通話方案。 <br/><br/>請參閱其他資訊列中的指南，瞭解通話方案涵蓋的最新國家和地區清單。 您可以選取某個國家/地區，以查看是否提供通話方案及通訊信用額度。 | | [音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 驗證您的使用者清單及啟用通話計畫的部署頻次 | 檢查您是否有適用于 Teams 通話方案之業務單位或網站的清單。 使用目標與關鍵結果模型，找出哪些使用者將適用通話方案。 建議您以網站為基礎工作，這樣您才能專注于資源。<br/><br/> 在啟用計畫中，找出您將啟用的使用者， (試驗、網站 1、網站 2 等專案) 。 | | [具有通話方案的電話系統](calling-plan-landing-page.md) |
| 3  | 取得電話號碼 | 瞭解您可以與 Teams 通話方案一起使用的訂閱者號碼。 <br/><br/>從 Microsoft 取得新電話號碼，或排程使用者電話號碼的號碼移植。 <br/><br/>如果您要從 Microsoft 取得新的訂閱者號碼，請決定要要求地理號碼或非地理號碼。 <br/><br/>**注意：** 根據服務提供者的不同，號碼移植程式最多可能需要 30 天。 請務必在規劃中考慮到這一點。 | | [用於通話方案的各種電話號碼](/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[取得新的使用者電話號碼要求表單](/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[為您的使用者取得電話號碼](./getting-phone-numbers-for-your-users.md) <br/><br/>[將電話號碼移轉至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[移轉電話號碼的常見問題](/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理貴組織的電話號碼](/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 設定撥號方案 | 撥號方案可讓使用者以他們習慣的方式撥打電話號碼，例如省略當地電話的區碼、省略國內通話的國家/地區代碼，或甚至使用短數位撥號在會議期間撥出其他使用者。 <br/><br/>預設服務撥號方案是以使用者的 Microsoft 365 或 Office 365 使用位置為基礎，無法變更。 <br/><br/>如果預設服務方案不符合您的需求，您可以在租使用者或使用者層級設定租使用者撥號方案。 檢查您是否已完成音訊會議此步驟。 | | [具有通話方案的電話系統](calling-plan-landing-page.md) <br/><br/>[Microsoft 365 和 Office 365 通話方案撥號方案](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 5  | 設定緊急位置 | 若要指派號碼給語音使用者，您也必須為語音使用者指派 E.911 的緊急位置。 <br/><br/>我們建議您使用 PowerShell 來自動化位置服務的建立。| | [緊急位置、位址和通話路由](what-are-emergency-locations-addresses-and-call-routing.md) |
| 6  | 指派授權、電話號碼、租使用者撥號方案及緊急位置給使用者 | 指派 E5 授權給使用者。 如果您使用 E3/E4 SKUs，請指派電話系統附加元件給使用者。 <br/><br/>指派授權之後，請繼續指派電話號碼、撥號方案及緊急位置。 使用使用者啟用腳本輕鬆一次設定多個使用者。 | | |
| 7  | 設定 Azure 語音信箱 | 如果您的使用者的信箱是託管在 Exchange Online 上，其語音信箱會自動設定。 <br/><br/>不過，對於 Exchange Server 的內部部署，您必須確定您擁有支援的版本和拓撲。 請遵循其他資訊 **欄中的步驟** 。 您可以為貴組織開啟或關閉語音信箱轉錄功能。| | [Exchange Server 的 Azure PBX 語音信箱支援](https://support.microsoft.com/help/3195158/customer-issues-between-exum-and-azure-voicemail) <br/><br/>[設定 [雲端語音信箱]](/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) |
| 8  | 選擇性：設定來電和撥出來電的本機號碼 | 根據預設，所有外發通話會使用指派的電話號碼進行通話身分識別 (來電) 。 <br/><br/>您可以選擇變更或封鎖使用者的本機號碼。 <br/><br/>**注意：** 緊急電話會一直將使用者的電話號碼傳送為本機號碼。 | | [組織中如何使用本機號碼？](./how-can-caller-id-be-used-in-your-organization.md) <br/><br/>[設定使用者的來電顯示](./set-the-caller-id-for-a-user.md)|
| 9  | 選擇性：設定與商務用 Skype 的互通性 | 如果貴組織從商務用 Skype 遷移到 Teams，請設定互通性原則。 <br/><br/>互通性可讓商務用 Skype 和 Teams 使用者彼此聊天和通話。 <br/><br/>您現有的部署和您針對 Teams 預定的推出策略將會影響您的計畫。 審查互通性選項、需求和限制，並據此設定原則。 <br/><br/>**注意：** 只有在貴組織仍在商務用 Skype Online 上託管使用者時，才適用這些步驟。 | | [Microsoft Teams 與商務用 Skype 互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br/><br/>[快速入門手冊：設定 Microsoft Teams 中的通話方案](./configuring-teams-calling-quickstartguide.md) |
| 10 | 準備並執行使用者接受度測試 | 準備並執行使用者接受度測試，包括撥入和撥出案例。 | | [電話系統的測試方案](./cloud-voice-landing-page.md) |
| 11 | 報告使用方式、健康情況、關鍵成功指示器和品質 | 報告在構想階段定義的使用方式、健康情況、KSIs 和品質。 | | [操作指南](./1-drive-value-operate-my-service.md) |

## <a name="next-steps"></a>後續步驟

完成這份檢查清單之後，您已成功將語音功能新增到您的 Teams 部署中。

下一個步驟是使用 Voice (Playbook) 網站啟用 [Playbook) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 來協助您在每個網站上上手，並有助於確保您規劃並執行重要的網站特定活動。