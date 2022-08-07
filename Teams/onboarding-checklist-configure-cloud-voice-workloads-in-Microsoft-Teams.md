---
title: 上線檢查清單 - 設定雲端語音工作負載 - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille
description: 當您在 Teams 中設定雲端語音工作負載時，請遵循此檢查清單中的核心待辦事項工作和活動。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.collection:
- M365-voice
ms.openlocfilehash: 45e4259003730ea53240b7481dfe63bc7c15175f
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269888"
---
# <a name="configure-cloud-voice-workloads-in-microsoft-teams"></a>在 Microsoft Teams 中設定雲端語音工作負載

## <a name="audio-conferencing"></a>音訊會議

| 否 | 活動或工作 | 描述 | 完成？ | 其他資訊 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 判斷貴組織所在地區是否可使用音訊會議 | Microsoft 提供跨國家/地區和城市的音訊會議。 請參閱其他 **資訊** 欄中的指導方針，以瞭解涵蓋的最新國家與地區清單。 <br/><br/> 您可以選取國家或地區來查看哪些 Teams 語音工作負載可用。 | | [音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 確認啟用音訊會議的使用者清單和部署頻率    | 請檢查您是否有 Teams 音訊會議範圍內的商務單位或網站清單。 使用目標和關鍵結果模型，找出哪些使用者將位於範圍中。 我們建議您逐網站工作，以便集中資源。<br/><br/> 在您的啟用計畫中，識別您將啟用哪些使用者，以及何時 (試驗、網站 1、網站 2 等) 。 | | [音訊會議想像](./audio-conferencing-in-office-365.md)|
| 3  | 取得電話號碼 | 瞭解可搭配 Teams 音訊會議工作負載使用的服務號碼。<br/><br/> 從 Microsoft 取得新的電話號碼，或為網站排程音訊會議橋接器號碼的號碼移轉。<br/><br/> 針對音訊會議，您可能也會移轉現有的免付費電話號碼，或是從 Microsoft 取得新的免付費電話號碼。<br/><br/> 若要取得服務號碼，如果列出您的國家或地區，但商務用 Skype系統管理中心沒有服務號碼，請在 <ptn@microsoft.com> (傳送適用于美國) 或 <ptneu@microsoft.com> 美國) 以外國家/地區的 (的新電話號碼要求。 如需詳細資訊，請參閱其他 **資訊** 欄中連結的「管理貴組織的電話號碼」指引。 <br/><br/>**注意：** 視服務提供者而定，號碼移轉程式最多可能需要 30 天。 請務必在規劃中將此事項納入考慮。 | | [通話方案所用的不同電話號碼](/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[取得新的使用者電話號碼要求表單](/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[為您的使用者取得電話號碼](./getting-phone-numbers-for-your-users.md) <br/><br/>[將電話號碼移轉至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[移轉電話號碼的常見問題](/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理貴組織的電話號碼](/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 設定您的預設會議橋接器電話號碼 | 您可以設定貴組織的預設會議橋接器電話號碼，這是指派給已啟用但未明確指派會議橋接器電話號碼的使用者。 預設數位應該會對齊貴組織的中心位置。 | | [設定邀請中包含的電話號碼](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) |
| 5  | 設定會議橋接器電話號碼的語言 | 為會議橋接器電話號碼設定主要和次要語言。 <br/><br/>確認已將地區會議橋接器電話號碼指派為適當的語言，以支援您的使用者。 | | [設定音訊會議的自動語音應答語言](/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) |
| 6  | 設定會議橋接器設定 | 設定會議加入體驗、PIN 長度，以及會議進入/結束宣告設定。 將這些會議橋接器設定與貴組織的目標對齊。 | | [變更音訊會議橋接器的設定](/SkypeForBusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge) |
| 7  | 自訂會議邀請 | 身為系統管理員，您可以在會議邀請中包含連結至 [說明] 或法律資訊的 URL。 您也可以更新標誌，並在邀請中新增頁尾文字。 | | [自訂會議邀請](/SkypeForBusiness/set-up-skype-for-business-online/customize-meeting-invitations) |
| 8  | 設定撥號對應表 | 撥號對應表可讓使用者以慣用的方式撥打電話號碼，例如省略當地通話的區碼、省略國內通話的國家/地區代碼，或甚至使用簡短數位撥號在會議期間撥出給其他使用者。 <br/><br/>服務撥號對應表是預設值，是根據使用者的 Microsoft 365 或Office 365使用位置而定，無法變更。 <br/><br/>如果預設服務撥號對應表不符合您的需求，您可以在租使用者或使用者層級設定租使用者撥號對應表。 | | [Microsoft Teams 音訊會議中的撥號對應表](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) <br/><br/>[Microsoft 365 和 Office 365 通話方案撥號對應表](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 9  | 指派會議號碼和 PIN 給使用者 | 根據預設，會議號碼會根據 Teams 系統管理員選取的預設號碼指派給使用者。 初始使用者 PIN 是根據 PIN 原則隨機產生。<br/><br/> 使用者會在電子郵件中收到會議號碼和 PIN。 使用者可以變更其 PIN。 <br/><br/>身為系統管理員，您可以讓撥入式使用者使用與預設號碼和本機不同于其位置的會議號碼。 | | |
| 10 | 準備並執行使用者接受度測試 | 準備並執行使用者接受度測試，包括撥入和撥出案例。 | | [音訊會議測試方案](./deploy-audio-conferencing-teams-landing-page.md) |
| 11 | 報告使用方式、健康情況、關鍵成功指標和品質 | 根據您在 [想像] 階段中定義的使用方式、健康情況、KSI 和品質報告。 | | [操作指南](./1-drive-value-operate-my-service.md) |

## <a name="calling-plans"></a>通話方案

| 否 | 活動或工作 | 描述 | 完成？ | 其他資訊 |
|----|---------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 判斷貴組織的位置是否可使用通話方案功能 | Microsoft 提供電話系統與適用于多個國家/地區和城市的通話方案。 <br/><br/>如需通話方案涵蓋之國家與地區的最新清單，請參閱 **其他資訊** 欄中的指引。 您可以選取國家或地區，查看通話方案和通訊點數是否可用。 | | [音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 確認啟用通話方案的使用者清單和部署頻率 | 請檢查您是否有 Teams 通話方案範圍內的業務單位或網站清單。 使用目標和關鍵結果模型，找出哪些使用者將處於通話方案的範圍。 我們建議您逐網站工作，以便集中資源。<br/><br/> 做為啟用計畫的一部分，請在 (試驗、網站 1、網站 2 等) 時識別您將啟用哪些使用者。 | | [具有通話方案的電話系統](calling-plan-landing-page.md) |
| 3  | 取得電話號碼 | 瞭解您可以搭配 Teams 通話方案使用的訂閱者號碼。 <br/><br/>從 Microsoft 取得新的電話號碼，或排程使用者電話號碼的號碼移轉。 <br/><br/>如果您要從 Microsoft 取得新的訂閱者號碼，請決定要要求地理或非地理位置號碼。 <br/><br/>**注意：** 視服務提供者而定，號碼移轉程式最多可能需要 30 天。 請務必在規劃中將此事項納入考慮。 | | [通話方案所用的不同電話號碼](/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[取得新的使用者電話號碼要求表單](/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[為您的使用者取得電話號碼](./getting-phone-numbers-for-your-users.md) <br/><br/>[將電話號碼移轉至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[移轉電話號碼的常見問題](/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理貴組織的電話號碼](/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 設定撥號對應表 | 撥號對應表可讓使用者以慣用的方式撥打電話號碼，例如省略當地通話的區碼、省略國內通話的國家/地區代碼，或甚至使用簡短數位撥號在會議期間撥出其他使用者。 <br/><br/>服務撥號對應表是預設值，是根據使用者的 Microsoft 365 或Office 365使用位置而定，無法變更。 <br/><br/>如果預設服務方案不符合您的需求，您可以在租使用者或使用者層級設定租使用者撥號對應表。 檢查您是否已完成音訊會議的這個步驟。 | | [具有通話方案的電話系統](calling-plan-landing-page.md) <br/><br/>[Microsoft 365 和 Office 365 通話方案撥號對應表](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 5  | 設定緊急位置 | 若要將號碼指派給語音使用者，您也必須將緊急位置指派給他們，以供 E.911 使用。 <br/><br/>建議您使用 PowerShell 自動化位置服務的建立。| | [緊急位置、位址和通話路由](what-are-emergency-locations-addresses-and-call-routing.md) |
| 6  | 指派授權、電話號碼、租使用者使用者撥號對應表，以及緊急位置給使用者 | 指派 E5 授權給使用者。 如果您使用 E3/E4 SKU，請將電話系統附加元件指派給使用者。 <br/><br/>指派授權之後，請繼續指派電話號碼、撥號對應表和緊急位置。 使用使用者啟用腳本，一次輕鬆設定多個使用者。 | | |
| 7  | 設定 Azure 語音信箱 | 如果您的使用者信箱裝載于Exchange Online，系統會自動布建使用者的語音信箱。 <br/><br/>不過，若要進行內部部署的Exchange Server，您必須確定您擁有支援的版本和拓撲。 依照 [ **其他資訊** ] 欄中的步驟進行。 您可以為組織開啟或關閉語音信箱轉譯。| | [Azure PBX 語音信箱支援 Exchange Server](https://support.microsoft.com/help/3195158/customer-issues-between-exum-and-azure-voicemail) <br/><br/>[設定 [雲端語音信箱]](/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) |
| 8  | 選用：針對來電和撥出電話設定來電識別碼 | 根據預設，所有撥出電話都會使用指派的電話號碼來撥打身分識別 (來電號碼) 。 <br/><br/>您可以選擇性地變更或封鎖使用者的本機號碼。 <br/><br/>**注意：** 緊急電話一律會將使用者的電話號碼作為來電者識別碼傳送。 | | [如何在貴組織中使用來電者識別碼？](./how-can-caller-id-be-used-in-your-organization.md) <br/><br/>[設定使用者的來電顯示](./set-the-caller-id-for-a-user.md)|
| 9  | 選用：使用 商務用 Skype 設定互通性 | 如果您的組織從 商務用 Skype 移轉到 Teams，請設定互通性原則。 <br/><br/>互通性可讓商務用 Skype和 Teams 使用者彼此聊天及通話。 <br/><br/>您現有的部署和 Teams 的預定推行策略將會影響您的計畫。 檢閱互通性選項、需求和限制，並據此設定原則。 <br/><br/>**注意：** 只有當貴組織仍然在 商務用 Skype Online 上主機使用者時，才適用這些步驟。 | | [Microsoft Teams 和商務用 Skype互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br/><br/>[快速入門手冊：設定 Microsoft Teams 中的通話方案](./configuring-teams-calling-quickstartguide.md) |
| 10 | 準備並執行使用者接受度測試 | 準備並執行使用者接受度測試，包括撥入和撥出案例。 | | [手機系統測試方案](./cloud-voice-landing-page.md) |
| 11 | 報告使用方式、健康情況、關鍵成功指標和品質 | 根據您在 [想像] 階段中定義的使用方式、健康情況、KSI 和品質報告。 | | [操作指南](./1-drive-value-operate-my-service.md) |

## <a name="next-steps"></a>後續步驟

完成此檢查清單之後，您將成功地將語音功能新增至您的 Teams 部署。

在下一個步驟中，使用 [Voice (Playbook 的網站啟用播放簿) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 來協助您在每一個網站上設定使用者，並協助確保您規劃和執行重要的網站特定活動。