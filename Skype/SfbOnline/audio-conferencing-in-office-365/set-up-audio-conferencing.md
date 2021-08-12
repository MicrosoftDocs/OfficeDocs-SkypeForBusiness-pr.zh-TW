---
title: 設定音訊會議商務用 Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: '瞭解如何為企業中需要使用電話加入電話會議的人員設定撥入或音訊會議。 '
ms.openlocfilehash: 48ce96b4b2ab6ad87054784bea93d8a7a45638ee6f2d86938cca1be60f30d442
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341089"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>設定音訊會議商務用 Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

貴組織內的人員有時會需要透過電話來加入會議。 商務用 Skype音訊會議功能， 人員可以使用電話商務用 Skype會議，而不是在行動裝置商務用 Skype或 PC 上使用 商務用 Skype應用程式。 
  
您只需要為打算排程或主持會議的人員設定音訊會議即可。 撥入的會議出席者不需獲得任何指派的授權或進行其他設定。
  
如需有關音訊會議的常見問題，請參閱[音訊會議常見問題](/MicrosoftTeams/audio-conferencing-common-questions)。

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>步驟 1：了解您的國家/地區是否提供音訊會議
<a name="__top"> </a>

移至[音訊會議與通話方案的適用國家和地區](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)，選取您的國家或地區，以取得有關音訊會議的提供資訊，以及電話系統、通話方案、付費和免付費電話號碼、通訊點數等資訊。 
 
## <a name="step-2-get-and-assign-licenses"></a>步驟 2：取得和指派授權
 
1. 若要使用音訊會議，您需要設定撥入會議每位使用者的授權。 若要瞭解您需要為音訊會議購買哪些授權，以及需要購買多少授權，[請參閱商務用 Skype授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

    >[!NOTE] 
    > 音訊會議包含在 Office 365 企業版 E5 授權中的附加元件。
        
2. 購買音訊會議授權之後，您必須將授權指派給組織中要排程或主持會議的人員。 請參閱[指派或移除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)您Microsoft 365 Apps 商務版授權給組織中要排程或主導會議的人。
    
3. 我們也建議您將通訊點數授權 (不需付費) 指派給您在在上一個步驟中指派授權的人員。 若要了解如何設定通訊點數，請參閱[設定貴組織的通訊點數](/microsoftteams/set-up-communications-credits-for-your-organization)。
    
> [!NOTE]
> 您也可以設定[按分鐘計費的音訊會議](/microsoftteams/audio-conferencing-pay-per-minute)。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>步驟 3：取得會議橋接器的服務號碼
<a name="__top"> </a>

音訊會議不能使用一般的使用者電話號碼，您必須取得服務號碼。 您可以為您的會議橋接器取得付費或免費的服務號碼。 有三種方法可以取得付費和免付費服務號碼： 
  
- **使用 商務用 Skype 系統管理中心**。 針對部分國家/地區，您可以使用系統管理中心取得會議橋接器商務用 Skype號碼。 請參閱[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)。
    
- **轉移現有的服務號碼**。 從目前的服務提供者或電話電信公司移轉現有號碼至Microsoft 365或Office 365。 如需詳細資訊，請參閱[將電話號碼轉移至 Teams ](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)或[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)，協助您完成此作業。  
  
- **使用表單要求新號碼**。 有時候 (視您的國家/地區) 您將無法使用 商務用 Skype 系統管理中心取得新的服務號碼，或者您需要特定的電話號碼或區碼。 若是如此，您將需要下載表單並將它傳送給我們。 如需詳細資訊，請參閱[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>步驟 4：指派服務號碼給會議橋接器
<a name="__top"> </a>

當您為您的會議橋接器取得您的免費和/或免付費電話號碼後，必須指派電話號碼，以便在會議邀請中使用。  

若要為音訊會議橋接器指派新電話號碼：

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心：**

 1. 移至 [Microsoft 365 系統管理中心]  >  [系統管理中心]  >  [Teams]  >  [舊版入口網站]。
 2. 選取 [語音]  >  [電話號碼]。
 3. 選取電話號碼，然後按一下 [指派]。

有關詳細資料，請參閱 [變更音訊會議橋接器上的電話號碼](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>步驟 5：設定會議橋接器的預設和替代語言
<a name="__top"> </a>

接下來，您想要為音訊會議設定自動 [語音](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) 語音服務語言，當電話撥入音訊會議的電話號碼時，會議自動語音機會用來問候來電者。 

![Microsoft Teams 標誌圖示](../images/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**：

1. 在儀表板中，移至 [會議]  >  [會議橋接器]。
2. 選取 [會議橋接電話號碼]，按一下 [編輯]，然後選擇預設語言。

![使用系統管理中心商務用 Skype ](../images/sfb-logo-30x30.png) **標誌的商務用 Skype圖示**：

1. 請前往系統管理中心>**系統管理中心**  >  **Teams**  >  **舊版入口網站**。
2. 選取 **音訊會議**  >  **Microsoft 橋接器**。 
3. 選取會議橋接器電話號碼，選取設定 **語言**，然後選擇預設語言。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>步驟 6：會議橋接器設定
<a name="__top"> </a>
    
設定會議橋接器後，請確認預設設定 (例如，進入/退出通知、PIN 長度) 就是您要使用的設定。如果不是，可以變更。 

![Microsoft Teams 標誌圖示](../images/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**：

1. 在儀表板中，移至 [會議]  >  [會議橋接器]。
2. 選取 [橋接器設定]。 會開啟 [橋接器設定] 窗格。 

如需詳細資訊，請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心：**

1. 移至 [Microsoft 365 系統管理中心]  >  [系統管理中心]  >  [Teams]  >  [舊版入口網站]。
2. 選取 **音訊會議**  >  **Microsoft 橋接器設定**。 這會開啟 **Microsoft 橋接器設定** 頁面。 

如需詳細資訊，請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>步驟 7：為主持會議的使用者指派撥入電話號碼

在您建立音訊會議橋接器之後，必須為您的使用者設定付費和免付費電話號碼。

您必須為貴組織中負責主持或排程會議的所有人員執行此動作。 

![Microsoft Teams 標誌圖示](../images/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**：

1. 在儀表板中，按一下 [使用者]，從清單中選取使用者，然後選取 [編輯]。
2. 選取 [音訊會議] 旁邊的 [編輯]，然後在 [音訊會議] 窗格中，選擇 [收費電話號碼] 和 [免付費] 電話號碼清單中的電話號碼。

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心：**

1. 前往舊  >  **Microsoft 365 系統管理中心Teams**  >  **入口網站**。
2. 選取 **[音訊會議**  >  **使用者**，然後從清單中選取使用者，然後按一下 [**編輯**。 

如需詳細資訊，請參閱[將 Microsoft 指派為音訊會議提供者](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)。


## <a name="step-8-set-up-meeting-invitations-optional"></a>步驟 8：設定會議邀請 (選用)
<a name="__top"> </a>
 
系統會自動將為使用者設定的撥入號碼新增到傳送給會議出席者的會議邀請。 不過，如果您想要的話，您可以新增自己的說明和合法連結、文字訊息和小型公司圖形。 請參閱[自訂會議邀請](../set-up-skype-for-business-online/customize-meeting-invitations.md)。
   
## <a name="related-topics"></a>相關主題

[音訊會議的常見問題](/MicrosoftTeams/audio-conferencing-common-questions)
  
[設定商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[音訊會議的電話號碼](phone-numbers-for-audio-conferencing.md)
  
[設定線上會議和電話會議的選項](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
