---
title: '[加入檢查清單]-設定雲端語音工作負載-Microsoft 團隊'
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille
description: 當您在小組中設定雲端語音工作負載時，請遵循此檢查清單中的核心、執行任務和活動。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8116a5aaac0db346929c9e312350e84521f756ff
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/24/2020
ms.locfileid: "49730991"
---
# <a name="configure-cloud-voice-workloads-in-microsoft-teams"></a>在 Microsoft 團隊中設定雲端語音工作負載

## <a name="audio-conferencing"></a>音訊會議

| 否 | 活動或任務 | 描述 | 完畢? | 其他資訊 |
|----|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 判斷您組織的位置是否有可用的音訊會議 | Microsoft 可在多個國家/地區和城市中提供音訊會議。 請參閱 [ **其他資訊** ] 欄中所涵蓋之最新國家和地區清單的指導方針。 <br/><br/> 您可以選取國家或地區，以查看語音工作負載可供使用的團隊。 | | [音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 驗證您的使用者清單和部署節奏以啟用音訊會議    | 檢查您是否有與團隊進行音訊會議的商務單位或網站清單。 使用 [目標] 和 [主要結果] 模型，即可完成範圍中的使用者。 我們建議您以網站為基礎，讓您能夠將資源集中在一起。<br/><br/> 在您的啟用方案中，請找出您要啟用的使用者，以及 (試生產、網站1、網站2等) 。 | | [音訊會議展望](https://docs.microsoft.com/MicrosoftTeams/audio-conferencing-in-office-365)|
| 3  | 取得電話號碼 | 瞭解可與團隊音訊會議工作負荷搭配使用的服務號碼。<br/><br/> 從 Microsoft 取得新的電話號碼，或為網站的音訊會議橋接器編號排程編號移植。<br/><br/> 對於音訊會議，您也可以轉移現有的免付費電話號碼，或者，或者，從 Microsoft 取得新的免付費電話號碼。<br/><br/> 若要取得服務號碼，如果列出您的國家或地區，但在商務用 Skype 系統管理中心中不提供任何服務號碼，請傳送新的電話號碼要求給我們的 <ptn@microsoft.com> 美國 () 或 (的美國 <ptneu@microsoft.com>) 以外的國家/地區。 如需詳細資訊，請參閱連結至 [ **其他資訊** ] 欄中的 [管理貴組織的電話號碼] 指導方針。 <br/><br/>**注意：** 視服務提供者而定，號碼移植處理常式可能需要長達30天的時間。 在您的規劃中，請務必考慮這一點。 | | [通話方案所用的不同類型的電話號碼](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[[取得新的使用者電話號碼] 要求表單](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[為您的使用者取得電話號碼](/microsoftteams/getting-phone-numbers-for-your-users) <br/><br/>[將電話號碼移轉至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[移轉電話號碼的常見問題](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理貴組織的電話號碼](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 設定您的預設會議橋電話號碼 | 您可以設定貴組織的預設會議橋電話號碼，指派給已啟用但未明確指派會議橋接電話號碼的使用者。 預設的數位應該與貴組織的中心位置相符。 | | [設定邀請中包含的電話號碼](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) |
| 500  | 設定會議橋接器電話號碼的語言 | 針對您的橋接器電話號碼設定主要和次要語言。 <br/><br/>確認地區會議橋接電話號碼已獲指派適當的語言以支援您的使用者。 | | [設定音訊會議的自動語音應答語言](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) |
| 6  | 設定會議橋接器設定 | 設定會議加入體驗、PIN 長度及會議進入/結束宣告設定。 將這些會議橋接器的設定與貴組織的目標對齊。 | | [變更音訊會議橋接器的設定](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge) |
| utf-7  | 自訂會議邀請 | 就像管理員一樣，您可以在會議邀請中加入 Url，連結至 [說明] 或 [法律資訊]。 您也可以更新標誌，並將頁尾文字新增至邀請。 | | [自訂會議邀請](https://docs.microsoft.com/SkypeForBusiness/set-up-skype-for-business-online/customize-meeting-invitations) |
| 型  | 設定撥號方案 | 撥號計畫可讓使用者以其使用的方式撥打電話號碼（例如省略當地電話的區號、省略國內通話的國家/地區碼），或甚至使用短數位撥號在會議期間撥出給其他使用者。 <br/><br/>[服務撥號方案] （預設值）是以使用者的 Microsoft 365 或 Office 365 使用位置為基礎，且無法變更。 <br/><br/>如果預設的服務撥號方案不符合您的需求，您可以在租使用者或使用者層級設定租使用者撥號方案。 | | [Microsoft 團隊音訊會議中的撥號方案](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) <br/><br/>[Microsoft 365 和 Office 365 通話方案撥號方案](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 9  | 指派會議號碼和 Pin 給使用者 | 根據預設，會議號碼會根據選取的預設 [團隊管理員] 指派給使用者。 根據 PIN 原則，隨機產生初始使用者 Pin。<br/><br/> 使用者會在電子郵件中接收會議號碼和 Pin。 使用者可以變更其針腳。 <br/><br/>如果您是系統管理員，您可以讓撥入使用者使用不同于預設號碼的會議號碼，並將其位置設為本機號碼。 | | |
| 第 | 準備及執行使用者接受度測試 | 準備及執行使用者接受度測試，包括撥入和撥出案例。 | | [音訊會議的測試方案](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-audio-conferencing) |
| 11 | 報告使用量、健康情況、金鑰成功指示器及品質 | 在您在構想階段中定義的使用方式、健康情況、KSIs 和品質等報告。 | | [操作指南](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service) |

## <a name="calling-plans"></a>通話方案

| 否 | 活動或任務 | 描述 | 完畢? | 其他資訊 |
|----|---------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 判斷您組織的位置是否有可用的通話方案功能 | Microsoft 會在多個國家/地區與城市之間提供通話方案的電話系統。 <br/><br/>請參閱 [ **其他資訊** ] 欄中的指導方針，以取得通話方案所涵蓋之國家和地區的最新清單。 您可以選取國家或地區，以查看通話方案，以及通訊點數是否可供使用。 | | [音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) |
| 2  | 驗證您的使用者清單和部署節奏，以啟用呼叫方案 | 檢查您是否有與團隊通話方案之範圍內的商務單位或網站清單。 使用 [目標] 和 [主要結果] 模型，即可判斷哪些使用者將在通話方案範圍內。 我們建議您以網站為基礎，讓您能夠將資源集中在一起。<br/><br/> 在您的啟用方案中，請根據 (試生產、網站1、網站2等) ，找出您要啟用的使用者。 | | [具有通話方案的電話系統](calling-plan-landing-page.md) |
| 3  | 取得電話號碼 | 瞭解可與團隊通話方案搭配使用的訂閱者號碼。 <br/><br/>從 Microsoft 取得新的電話號碼，或為使用者電話號碼排程編號移植。 <br/><br/>如果您要從 Microsoft 取得新的訂閱者號碼，請決定您是否要要求地理或非地理位置號碼。 <br/><br/>**注意：** 視服務提供者而定，號碼移植處理常式可能需要長達30天的時間。 在您的規劃中，請務必考慮這一點。 | | [通話方案所用的不同類型的電話號碼](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans) <br/><br/>[[取得新的使用者電話號碼] 要求表單](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/get-new-user-phone-numbers-request-forms) <br/><br/>[為您的使用者取得電話號碼](/microsoftteams/getting-phone-numbers-for-your-users) <br/><br/>[將電話號碼移轉至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) <br/><br/>[移轉電話號碼的常見問題](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions) <br/><br/>[管理貴組織的電話號碼](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) |
| 4  | 設定撥號方案 | 撥號方案可讓使用者以其使用的方式撥打電話號碼（例如省略當地電話的區號、省略國內通話的國家/地區碼），或甚至使用短數位撥號在會議期間撥出其他使用者。 <br/><br/>[服務撥號方案] （預設值）是以使用者的 Microsoft 365 或 Office 365 使用位置為基礎，且無法變更。 <br/><br/>如果預設服務方案不符合您的需求，您可以在租使用者或使用者層級設定租使用者撥號方案。 檢查您是否已完成此步驟以進行音訊會議。 | | [具有通話方案的電話系統](calling-plan-landing-page.md) <br/><br/>[Microsoft 365 和 Office 365 通話方案撥號方案](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) |
| 500  | 設定緊急位置 | 若要將號碼指派給語音使用者，您也必須為其指派一個緊急位置，以進行 E. 911。 <br/><br/>我們建議使用 PowerShell 來自動化位置服務的建立。| | [緊急位置、位址及呼叫路由](what-are-emergency-locations-addresses-and-call-routing.md) |
| 6  | 指派授權、電話號碼、租使用者撥號方案，以及使用者的緊急位置 | 將 E5 授權指派給您的使用者。 如果您使用的是 E3/E4 Sku，請將電話系統附加元件指派給最終使用者。 <br/><br/>指派授權之後，請依指派電話號碼、撥號方案及緊急位置來繼續進行。 使用使用者啟用腳本輕鬆地設定多個使用者。 | | |
| utf-7  | 設定 Azure 語音信箱 | 如果您的使用者信箱是託管在 Exchange Online 上，系統會自動預配其語音信箱。 <br/><br/>不過，對於 Exchange Server 的內部部署，您必須確認您有受支援的版本和拓撲。 遵循 [ **其他資訊** ] 欄中的步驟進行。 您可以針對您的組織開啟或關閉語音信箱。| | [Exchange Server 的 Azure PBX 語音信箱支援](https://support.microsoft.com/help/3195158/customer-issues-between-exum-and-azure-voicemail) <br/><br/>[設定雲端語音信箱](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) |
| 型  | 選用：針對來電和呼出通話設定本機號碼 | 根據預設，所有出站通話都使用指派的電話號碼來呼叫身分識別 (來電者識別碼) 。 <br/><br/>您可以選擇性地變更或封鎖使用者的本機號碼。 <br/><br/>**注意：** 緊急通話總是以本機號碼方式傳送使用者的電話號碼。 | | [如何在您的組織中使用本機號碼？](/microsoftteams/how-can-caller-id-be-used-in-your-organization) <br/><br/>[設定使用者的來電顯示](/microsoftteams/set-the-caller-id-for-a-user)|
| 9  | 選用：使用商務用 Skype 設定互通性 | 如果您的組織是從商務用 Skype 遷移至團隊，請設定互通性原則。 <br/><br/>互通性能讓商務用 Skype 與團隊使用者聊天，並彼此通話。 <br/><br/>您現有的部署與團隊的預期推出戰略將會影響您的方案。 查看互通性選項、需求與限制，並據此設定原則。 <br/><br/>**注意：** 只有在您的組織仍在商務用 Skype Online 中託管使用者時，才適用這些步驟。 | | [Microsoft 團隊和商務用 Skype 的互通性](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) <br/><br/>[快速入門手冊：設定 Microsoft Teams 中的通話方案](https://docs.microsoft.com/MicrosoftTeams/configuring-teams-calling-quickstartguide) |
| 第 | 準備及執行使用者接受度測試 | 準備及執行使用者接受度測試，包括撥入和撥出案例。 | | [電話系統的測試方案](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-phone-system) |
| 11 | 報告使用量、健康情況、金鑰成功指示器及品質 | 在您在構想階段中定義的使用方式、健康情況、KSIs 和品質等報告。 | | [操作指南](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service) |

## <a name="next-steps"></a>後續步驟

完成此檢查清單後，您將會成功地在小組部署中新增語音功能。

在下一個步驟中，使用 [ [網站啟用行動手冊] 來取得語音 (行動手冊) ](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) ，協助您規劃並執行重要的網站特定活動。
