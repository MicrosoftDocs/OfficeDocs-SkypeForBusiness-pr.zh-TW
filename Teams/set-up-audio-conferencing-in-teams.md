---
title: 為 Microsoft 團隊設定音訊會議
ms.author: tonysmit
author: tonysmit
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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: '瞭解如何為您企業中需要使用手機加入電話會議的人員設定撥入或音訊會議。 '
ms.openlocfilehash: d630f6f149f61609209cc4ead23ed7232647cb08
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2019
ms.locfileid: "37925364"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>為 Microsoft 團隊設定音訊會議

有時候貴組織中的人員必須使用電話撥入會議。 Microsoft 團隊只有在這種情況下才包含音訊會議功能！ 使用者可以使用電話撥入團隊會議，而不是在行動裝置或電腦上使用 [小組] 應用程式。 
  
您只需要為打算排程或主持會議的人員設定音訊會議即可。 在撥入的會議出席者不需要獲指派任何授權或其他設定。
  
如需音訊會議的常見問題，請參閱[音訊會議常見問題](audio-conferencing-common-questions.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>步驟1：瞭解您的國家/地區是否提供音訊會議
<a name="__top"> </a>

移至[適用于音訊會議與通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)，然後選取您的國家或地區以取得音訊會議的可用性資訊，以及電話系統、通話方案、免付費電話和免付費電話的相關資訊。號碼和通訊點數。 
 
## <a name="step-2-get-and-assign-licenses"></a>步驟2：取得並指派授權
 
1. 對於音訊會議，您需要每個將會設定撥入會議的使用者授權。 若要瞭解您需要購買哪些授權才能進行音訊會議，以及需要多少成本，請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

    >[!NOTE] 
    > 音訊會議包含在 Office 365 企業版 E5 授權和附加元件中。
        
2. 購買音訊會議授權之後，您必須將他們指派給組織中將要排程或領導會議的人員。 若要將授權指派給您組織中要排程或領導會議的人員，請參閱[在商務用 Office 365 中指派授權給使用者](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
    
3. 我們也建議您在上一個步驟中指派通訊信用權（不需要支付任何費用）給您指派授權的人員。 若要瞭解如何設定通訊點數，請參閱為[您的組織設定通訊點數](set-up-communications-credits-for-your-organization.md)。
    
> [!NOTE]
> 您也可以設定[每分鐘付費的音訊會議](audio-conferencing-pay-per-minute.md)。

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>步驟3：取得會議橋的服務號碼
<a name="__top"> </a>

對於音訊會議，您無法將電話號碼用於使用者;您將需要取得服務號碼。 您可以取得會議橋的付費或免費服務號碼。 有三種方法可以取得付費和免付費服務號碼： 
  
- **使用 Microsoft 團隊系統管理中心**。 在某些國家/地區，您可以使用 Microsoft 團隊系統管理中心取得會議橋的服務號碼。 請參閱[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)。
    
- **移植現有的服務號碼**。 從目前的服務提供者或電話轉接至 Office 365，將現有的號碼移植或轉移至 Office。 如需詳細資訊，請參閱將[電話號碼傳送給團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)或[管理您組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，以協助您執行此動作。  
  
- **針對新號碼使用要求表單**。 有時候（視您的國家/地區而定）您無法使用 Microsoft 團隊系統管理中心取得新的服務號碼，或者您需要特定的電話號碼或區功能變數代碼。 如果是這樣，您將需要下載表單並將它傳送給我們。 如需詳細資訊，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>步驟4：將服務號碼指派給會議橋
<a name="__top"> </a>

當您為您的會議橋接器取得付費和/或免付費電話號碼之後，您必須指派編號，才能在會議邀請中使用。  

請按照這些步驟，將新的電話號碼指派給您的音訊會議橋。

![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示：

 1. 移至**Microsoft 365 管理中心** > **管理中心** > **小組** > **舊版入口網站**。
 2. 選取 [**語音** > **電話號碼**]。
 3. 選取電話號碼，然後按一下 [**指派**]。

如需詳細資訊，請參閱[在音訊會議橋中變更電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>步驟5：設定會議橋接器的預設及備用語言
<a name="__top"></a>接下來，您想要[在 Microsoft 團隊中設定音訊會議的自動助理語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)，會議自動語音應答會在撥入電話號碼以進行音訊會議時，用來向來電者。 

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 microsoft 團隊標誌的圖示：

1. 從 [儀表板] 移至 [**會議** > **會議橋**]。
2. 選取 [會議橋接電話號碼]，按一下 [**編輯**]，然後選擇預設語言。

## <a name="step-6-set-your-conferencing-bridge-settings"></a>步驟6：設定您的會議橋設定
<a name="__top"> </a>
    
在設定您的會議橋接器之後，請確認您要使用的預設設定（例如 [進入/結束通知] 和 [PIN 長度]）。如果不是，您可以變更它們。 

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 microsoft 團隊標誌的圖示：

1. 從 [儀表板] 移至 [**會議** > **會議橋**]。
2. 選取 [**橋接器設定**]。 這將會開啟 [**橋設定**] 窗格。 

如需詳細資訊，請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>步驟7：為領導會議的使用者指派撥入電話號碼

建立音訊會議橋接器之後，您必須為使用者設定付費和免付費電話號碼。

您必須針對組織中負責領導或排程會議的所有人員執行此動作。 

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 microsoft 團隊標誌的圖示：

1. 從儀表板中，按一下 [**使用者**]，從清單中選取使用者，然後選取 [**編輯**]。
2. 選取 [**音訊會議**] 旁的 [**編輯**]，然後在 [**音訊會議**] 窗格中，選擇 [**付費電話號碼**] 和 [**免付費電話**號碼] 清單中的數位。

如果您需要更多詳細資料，請參閱[將 Microsoft 指派為音訊會議提供者](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。


## <a name="step-8-set-up-meeting-invitations-optional"></a>步驟8：設定會議邀請（選用）
<a name="__top"> </a>
 
為使用者設定的撥入號碼會自動新增至傳送給會議出席者的會議邀請中。 不過，如果您想要的話，您也可以新增自己的說明與法律連結、文字訊息及小型公司圖形。 請參閱[自訂會議邀請](meeting-settings-in-teams.md#customize-meeting-invitations)。
   
## <a name="related-topics"></a>相關主題

[音訊會議的常見問題](audio-conferencing-common-questions.md)
  
[Microsoft 團隊中音訊會議的電話號碼](phone-numbers-for-audio-conferencing-in-teams.md)
  
[設定線上會議和電話會議的選項](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
