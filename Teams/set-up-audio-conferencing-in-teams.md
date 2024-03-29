---
title: 設定 Microsoft Teams 的音訊會議
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '瞭解如何為企業中需要使用電話加入電話會議的人員設定撥入或音訊會議。 '
ms.openlocfilehash: 5f9912b005061461aa2309fb0faa54b4455214ea
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584154"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>設定 Microsoft Teams 的音訊會議

貴組織內的人員有時會需要透過電話來加入會議。 Microsoft Teams 所包含的音訊會議功能正是為了這種情況所準備的！ 人員可以透過電話加入 Teams 會議，而不必在行動裝置或電腦上透過 Teams 應用程式來參加。
  
您只需要為打算排程或主持會議的人員設定音訊會議即可。 撥入的會議出席者不需獲得任何指派的授權或進行其他設定。
  
如需有關音訊會議的常見問題，請參閱[音訊會議常見問題](audio-conferencing-common-questions.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>步驟 1：了解您的國家/地區是否提供音訊會議

移至[音訊會議與通話方案的適用國家和地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)，選取您的國家或地區，以取得有關音訊會議的提供資訊，以及電話系統、通話方案、付費和免付費電話號碼、通訊點數等資訊。

## <a name="step-2-get-and-assign-licenses"></a>步驟 2：取得和指派授權

1. 若要使用音訊會議，您需要設定撥入會議每位使用者的授權。 若要了解需要購買哪些授權及其售價，請參閱 [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

    >[!NOTE]
    > 音訊會議包含在 Office 365 企業版 E5 授權中的附加元件。

2. 購買音訊會議授權之後，您必須將授權指派給組織中要排程或主持會議的人員。 請參閱[將您購買的 Microsoft 365 或商務Office 365授權指派給](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)組織中即將排程或主持會議的人員。

3. 我們也建議您將通訊點數授權 (不需付費) 指派給您在在上一個步驟中指派授權的人員。 若要了解如何設定通訊點數，請參閱[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md)。

   > [!NOTE]
   > 您也可以設定[按分鐘計費的音訊會議](audio-conferencing-pay-per-minute.md)。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>步驟 3：取得會議橋接器的服務號碼

音訊會議不能使用一般的使用者電話號碼，您必須取得服務號碼。 您可以為您的會議橋接器取得付費或免費的服務號碼。 有三種方法可以取得付費和免付費服務號碼：
  
- **使用 Microsoft Teams 系統管理中心**。 針對某些國家/地區，您可以使用 Microsoft Teams 系統管理中心為您的會議橋接器取得服務號碼。 請參閱[取得服務電話號碼](./getting-service-phone-numbers.md)。

- **轉移現有的服務號碼**。 若要將現有號碼從您目前的服務提供者或電信業者移轉至 Microsoft 365 或Office 365。 如需詳細資訊，請參閱[將電話號碼轉移至 Teams ](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)或[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，協助您完成此作業。  
  
- **使用表單要求新號碼**。 有時候 (視您的國家/地區而定) 您無法使用 Microsoft Teams 系統管理中心取得新的服務號碼，或者您將需要特定的電話號碼或區碼。 若是如此，您將需要下載表單並將它傳送給我們。 如需詳細資訊，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>步驟 4：指派服務號碼給會議橋接器

當您為您的會議橋接器取得您的免費和/或免付費電話號碼後，必須指派電話號碼，以便在會議邀請中使用。  

按照以下步驟將新電話號碼指派給音訊會議橋接器。

 **使用 Microsoft Teams 系統管理中心**：

 1. 從 [常用] 移至 **[語音**  >  **電話號碼]**。
 2. 選取電話號碼，然後按一下 [指派]。

如需詳細資訊，請參閱[變更音訊會議橋接器的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>步驟 5：設定會議橋接器的預設和替代語言

 接下來，您想要[為 Microsoft Teams 的語音會議設定自動語音應答語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)，會議自動語音應答在撥入音訊會議的電話號碼時，會使用此語言用向來電者打招呼。

 **使用 Microsoft Teams 系統管理中心**：

1. 從 [常用] 移至 **[會議]**  >  **橋接器**。
2. 選取 [會議橋接電話號碼]，按一下 [編輯]，然後選擇預設語言。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>步驟 6：會議橋接器設定

設定會議橋接器後，請確認預設設定 (例如，進入/退出通知、PIN 長度) 就是您要使用的設定。如果不是，可以變更。

 **使用 Microsoft Teams 系統管理中心**：

1. 從 [常用] 移至 **[會議]**  >  **橋接器**。
2. 選取 [橋接器設定]。 會開啟 [橋接器設定] 窗格。

如需詳細資訊，請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>步驟 7：為主持會議的使用者指派撥入電話號碼

請參閱 [在 Microsoft Teams 中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。

> [!NOTE]
> 您也可以將電話號碼新增至 *TeamsAudioconferencingpolicy* ，並將原則指派給使用者，藉此設定電話號碼。 新增到原則的付費和免付費電話號碼會優先于透過音訊會議設定窗格個別為使用者設定的電話號碼。 如果未將電話號碼新增至 *Teamsaudioconferencingpolicy*，則透過音訊會議設定窗格個別為使用者設定的電話號碼將會顯示在 Microsoft Teams 會議邀請中。 [付費和免付費電話號碼的音訊會議原則設定](audio-conferencing-toll-free-numbers-policy.md) 有更多資訊。

> [!IMPORTANT]
> 指派的電話號碼最多可能需要 24 小時，才會顯示在您的會議邀請上。 如果您沒有看到更新號碼出現，請等候至少 24 小時，然後再連絡支援服務。

## <a name="step-8-set-up-meeting-invitations-optional"></a>步驟 8：設定會議邀請 (選用)

系統會自動將為使用者設定的撥入號碼新增到傳送給會議出席者的會議邀請。 不過，如果您想要的話，您可以新增自己的說明和合法連結、文字訊息和小型公司圖形。 請參閱[自訂會議邀請](meeting-settings-in-teams.md#customize-meeting-invitations)。

## <a name="related-topics"></a>相關主題

[音訊會議的常見問題](audio-conferencing-common-questions.md)
  
[Microsoft Teams 音訊會議的電話號碼](phone-numbers-for-audio-conferencing-in-teams.md)
  
[設定線上會議和電話會議的選項](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
