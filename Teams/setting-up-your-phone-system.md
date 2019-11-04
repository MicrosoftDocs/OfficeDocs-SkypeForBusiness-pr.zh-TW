---
title: 在組織中設定電話系統
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '瞭解如何為您的組織設定電話系統（雲端 PBX）。 '
ms.openlocfilehash: 402ae5f92e72cd1bc7ab759d3706108480a27a7e
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925294"
---
# <a name="setting-up-phone-system-in-your-organization"></a>在組織中設定電話系統

以下是在 Office 365 中設定電話系統的逐步指南。 在每個步驟的結尾，都提供其他詳細資訊的連結。

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>步驟1：確認您的國家或地區有可用的電話系統

1.  首先，請移至[適用于音訊會議與通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)，然後從頁面頂端的清單中選取您的國家或地區。 
2.  在 [**電話系統**] 下，查看功能清單及詳細資料。 
3.  如果有可用的電話系統，請移至步驟2。 

**若要深入瞭解手機系統和音訊會議的地區可用性，請參閱[音訊會議與通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>步驟2：購買並指派電話系統和通話方案授權

若要將電話系統和通話方案授權指派給單一使用者，步驟與指派 Office 365 授權相同。 請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)。 如果您想要大量指派多個使用者，請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步驟3：為您的使用者取得電話號碼

您必須先取得電話號碼，才能將貴組織中的使用者設定為撥打及接聽電話。

您有三種方式可取得使用者的號碼：
- 使用商務用 Skype 系統管理中心來取得新號碼。
- 取得商務用 Skype 系統管理中心無法使用的新號碼。
- 將現有的號碼從目前的服務提供者或電話轉接到 Office 365。

您必須使用 [新增**使用者編號**] 頁面來查看、搜尋、取得及保留這些號碼。 您可以依 [國家/地區]、[省/市] 及 [城市] 進行搜尋，然後輸入使用者所需的電話號碼數量。

### <a name="get-new-user-phone-numbers"></a>取得新使用者的電話號碼 
 
![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示

1. 使用您的公司或學校帳戶登入 Microsoft 365。

2. 移至**Microsoft 365 管理中心** > **商務用 Skype**。
    
3. 在左導覽中，前往 [**語音** > **電話號碼**]，按一下 [**新增號碼** ![] [新增] 按鈕，顯示](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)為加號，然後按一下 [**新增使用者號碼**]。
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>取得商務用 Skype 系統管理中心無法使用的新號碼
  
有時候（視您的國家/地區而定），您將無法使用商務用 Skype 系統管理中心來取得新號碼。 在這種情況下，您將需要下載表單並將它傳送給我們。 請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，瞭解如何要求新的使用者號碼。   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>從服務提供者或電話載波傳送埠或轉移電話號碼
  
- 如果您需要999或更少的使用者電話號碼，您可以使用商務用 Skype 系統管理中心的 [**新的當地號碼埠順序**] 嚮導。 遵循將[電話號碼轉接給小組](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)，以轉接您的電話號碼中找到的步驟。
    
- 如果您需要端口超過999的電話號碼，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以提交埠訂單服務要求或訂單，以將所有這些電話號碼移植到 Office 365。 

**如需取得新電話號碼或轉移現有號碼的詳細資訊，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步驟4：取得服務電話號碼（音訊會議、通話佇列、自動語音應答）

除了從 Office 365 取得使用者的電話號碼之外，您還可以在 [音訊會議] （適用于 [會議室]）、自動語音應答及通話佇列（亦稱為服務號碼）等服務中搜尋和取得付費或免付費電話號碼。 服務電話號碼的並行通話容量比使用者或訂閱者電話號碼要高。 例如，服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。

### <a name="get-new-service-numbers"></a>取得新的服務號碼

![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示


1. 使用您的公司或學校帳戶登入 Office 365。

2. 移至**Microsoft 365 管理中心** > **商務用 Skype**。

3. 在左導覽中，移至 [**語音** > **電話號碼** > ]，**新增號碼**，然後按一下 [**新的服務號碼**]。

    > [!IMPORTANT]
    > 若要在商務用 Skype 系統管理中心的左側導覽中看到 [**語音**] 選項，您必須先購買至少一個**企業版 E5 授權**、一個**電話系統**附加元件授權或一個**音訊會議**附加元件授權。

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>取得商務用 Skype 系統管理中心無法使用的新號碼
  
有時候（視您的國家/地區而定），您將無法使用商務用 Skype 系統管理中心來取得新號碼。 在這種情況下，您將需要下載表單並將它傳送給我們。 請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，瞭解如何要求新號碼。 

### <a name="port-or-transfer-existing-service-numbers"></a>移植或轉移現有的服務號碼

如果您想要從目前的服務提供者或承運人傳送服務號碼，您必須手動將埠訂單提交給 Microsoft。 您必須針對每一種類型的服務號碼（[收費電話]）提交不同的埠順序（免付費電話），您就會使用一份授權函式（LOA）來傳送。 在授權信件（LOA）中，您必須選取正確的服務號碼類型。 當您聯繫 Microsoft 支援時，請確定您已指定要轉移服務號碼（*而非使用者或訂閱者號碼*），或同時進行通話容量可能不足以處理通話量。 如果您想要使用電話號碼傳送電話號碼或進行其他動作，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>步驟5：如果您要設定通話方案

如果您已按照上述步驟進行，就表示您已購買並指派電話系統和授權，以及通話方案（步驟2），以及為使用者取得的電話號碼（步驟3），因此您的通話方案已部分設定。 請依照下列三個程式完成您的通話方案設定。

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>為您的組織新增緊急位址和位置

1. 在 [**語音**] 頁面上，選擇 [**緊急位置** > **新增位址**]。

2. 在 [**新增位址**] 窗格中，輸入您的位址名稱，然後完成剩餘的方塊。
    
     ![[新增位址] 窗格的螢幕擷取畫面](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > 針對英文客戶，如果街道名稱是一個數位，請務必在結尾包含 "st" 或 "th"，如上述圖片所示。

3. 選擇 [**驗證**]。

    如有需要，系統會提示您對位址進行修正。

    > [!CAUTION]
    > 驗證街道或市政位址涉及確認其合法且格式正確。 部分正確的緊急位址（例如，如果您輸了錯誤的城市名稱），可能仍會通過驗證。 即使是拼錯並通過驗證，也會將 [錯誤] 的城市名稱及其他正確的位址部分組合在一起，以將呼叫路由至適當的緊急派單中心。

    > [!TIP]
    > 如果需要針對緊急回應修正位址，就會出現綠色橫幅，通知您位址已更新。

4. 驗證網址之後，請選擇 [**儲存**]。

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>為使用者指派電話號碼和緊急位址

> [!TIP]
> 如果您在執行這個步驟之前，先將其他人新增至您的商務，可能需要**幾個小時的時間**，才會顯示在 [**語音使用者**] 頁面上。 還有一個延隔時間。

1. 在 [**語音使用者**] 頁面上，選取您要指派電話號碼和緊急位址的人員。

2. 在 [動作] 窗格中，按一下 [**指派號碼**]。

3. 在 [**指派號碼**] 頁面上，于 [**選取要指派的號碼**] 清單中，選取使用者的電話號碼。

4. 若要選取緊急位址，請在方塊中輸入城市的名稱，然後選擇 [**搜尋**]。

    > [!IMPORTANT]
    > 如果您在美國以外的地區，您的號碼已經有緊急位址，但您現在可以變更它。 請參閱[指派或變更使用者的緊急位址](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)。 
  
5. 指派電話號碼和緊急位址之後，請選擇 [**儲存**]。

### <a name="tell-your-users-about-their-new-phone-numbers"></a>告訴使用者他們的新電話號碼


我們建議您傳送郵件，或使用您公司的最佳通訊方法，告訴使用者他們的新電話號碼。

以下說明如何在其**商務用 Skype**應用程式中查看電話號碼：

1. 在桌上型電腦上登入商務用 Skype。
    
2. 選擇 [**設定** > **工具** > **選項**]。 
    
     ![[工具] 功能表上選項的螢幕擷取畫面](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 然後選擇 [**電話**]。 
    
    ![商務用 Skype 電話選項的螢幕擷取畫面](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
在**Microsoft 團隊**中，使用者可以按一下左側導覽中的 [**來電**] 來查看他們的電話號碼。 電話號碼會顯示在撥號鍵台的上方。

![按一下 [通話] 後可用選項的螢幕擷取畫面](media/teams-phone-number.png)

**如需設定通話方案所涉及之所有步驟的詳細資訊，請參閱[設定通話方案](set-up-calling-plans.md)。**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>步驟6：如果您想要設定音訊會議

有時候貴組織中的人員必須使用電話撥入會議。 商務用 Skype 和 Microsoft 團隊包括音訊會議功能，只適用于這種情況！ 使用者可以使用電話撥入商務用 Skype 或 Microsoft 團隊會議，而不是在行動裝置或電腦上使用商務用 Skype 或 Microsoft 團隊 app。

您只需要為規劃排程或領導會議的人員設定音訊會議。 在撥入的會議出席者不需要獲指派任何授權或其他設定。
  
如需音訊會議的常見問題，請參閱[音訊會議常見問題](audio-conferencing-common-questions.md)。
    
1. 如果您購買的是 [**音訊會議**附加元件授權] 和 [通訊點數] 授權，也請指派它們。 如需相關指示，請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)。

    決定您的音訊會議提供者。 音訊會議提供者提供音訊會議橋。 [會議橋接] 會設定會議的撥入電話號碼、Pin 及會議 Id。 決定要使用的是 Microsoft 或協力廠商音訊會議提供者：

    > [!NOTE]
    > Microsoft 團隊使用者無法使用者使用協力廠商音訊會議提供者。

    - **Microsoft 作為音訊會議提供者**：如果您想要最簡單的音訊會議方案，請選擇 [Microsoft 作為您的音訊會議提供者]。
    
    - **協力廠商是您的音訊會議提供者**：如果您所在的國家/地區無法使用 Office 365 中的音訊會議，則服務品質不會因位置而無法正常工作，或者您有現有的合同，請選擇協力廠商音訊會議提供者。 若要尋找提供者，請移至[Microsoft 定點](https://go.microsoft.com/fwlink/?LinkId=797530)。
 
2. 將音訊會議提供者指派給領導或排程會議的人員。 請參閱[將 Microsoft 指派為音訊會議提供者](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

3. 設定會議邀請。 下列步驟是選擇性的，但許多管理員都要執行這些步驟： 
  
   1. [在商務用 Skype 中自訂會議邀請](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。 為使用者設定的撥入號碼會自動新增至傳送給出席者的會議邀請中。 不過，您可以新增自己的說明與法律連結、文字訊息及小型公司圖形。
    
   2. 針對[商務用 Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)或[Microsoft 團隊](set-the-phone-numbers-included-on-invites-in-teams.md)中的邀請所包含的會議召集人，設定音訊會議電話號碼。 這是將顯示在使用者排程之會議中的電話號碼。
    
   3. [在商務用 Skype](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing)或[Microsoft 團隊](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中設定音訊會議的自動語音應答語言，當電話撥入音訊會議電話號碼時，音訊會議自動語音應答會用來向來電者。 此步驟僅適用于使用 Microsoft 做為音訊提供者的情況。
    
   4. [在 Microsoft 團隊中](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)設定音訊會議會議的 PIN 長度。
    
      > [!NOTE]
      > 使用中國由世紀運營之 Office 365 的客戶尚不提供此功能。 若要深入瞭解，請參閱[瞭解由世紀運營的 Office 365](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)。

**如需音訊會議的詳細資訊，請參閱[設定 Microsoft 團隊的音訊會議](set-up-audio-conferencing-in-teams.md)。**

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>步驟7：如果您想要設定雲端通話佇列

雲端通話佇列包括某人撥入您組織的電話號碼時所使用的問候語、自動保留通話的功能，以及在通話時搜尋下一個可用的呼叫代理程式來處理通話的功能在暫停時聆聽音樂。 您可以為組織建立單一或多個通話佇列。

您必須先取得或轉讓現有的付費或免付費服務號碼，才能建立及設定通話佇列。 當您收到付費或免付費服務電話號碼之後，就會顯示在商務用**Skype 系統管理中心** > **的語音** > **電話號碼**中，而且列出的**數位類型**將會列為**服務-免付費電話**. 若要取得您的服務號碼，請參閱[取得商務用 Skype 和 Microsoft 團隊的服務電話號碼](/microsoftteams/getting-service-phone-numbers)，或者，如果您想要轉移與現有的服務號碼，請參閱[將電話號碼轉移至團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。
  
> [!NOTE]
> 如果您在美國以外，您就無法使用商務用 Skype 系統管理中心來取得服務號碼。 移至 [[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)]，瞭解如何從美國以外的地區進行。

若要建立新的通話佇列，請**在商務用 Skype 系統管理中心**中，按一下 [**呼叫路由** > **呼叫佇列**]，按一下 [**新增**]，然後依照[建立雲端通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue)的**步驟 3**中的指示進行。

**如需通話佇列的詳細資訊，請參閱[建立雲端通話佇列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。**

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>步驟8：如果您想要設定雲端自動助理

自動語音應答讓撥入您組織的人員，並流覽功能表系統，以取得正確的部門、呼叫佇列、人員或接線員。 您可以使用商務用 Skype 系統管理中心，為您的組織建立自動語音應答。

若要建立新的自動語音應答，請在商務用 Skype 系統管理中心中，按一下 [**呼叫路由** > **自動**語音應答]，按一下 [**新增**]，然後依照建立雲端自動語音應答**之步驟 2**中的每個頁面上的指示進行。 [](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).


**如需雲端自動語音應答的詳細資訊，請參閱[設定雲端自動](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)語音應答。**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步驟9：指派服務電話號碼（音訊會議、通話佇列、自動語音應答）

從**上述步驟 4**獲得您的服務號碼之後，您必須將他們指派給您想要的每一種類型的服務。 例如，如果您需要專用的服務電話號碼（付費或免費付費），您必須將號碼指派給會議橋。

- 在音訊會議中，您可以移至**Microsoft 365 系統管理中心** > **** > 的 [**商務** > 用 Skype**音訊會議**]，將專用號碼指派給會議橋接器，然後按一下您也可以在 [[音訊會議橋] 中查看 [變更付費或免付費號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)]。

- 針對自動語音應答，您可以移至**Microsoft 365 系統管理中心** > **** > ，透過**商務** > 用 Skype**呼叫路由** > 自動語音來將專用號碼指派給自動語音應答**** 然後按一下自動語音應答。 在 [**一般**] 頁面上，您已有的服務號碼會列在 [**電話號碼**] 下拉式清單中。 如需詳細資訊，請參閱[設定雲端自動](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)語音應答。
- 在通話佇列中，您可以移至**Microsoft 365 系統管理中心** > **** > 的 [**商務** > 用 Skype 呼叫**路由** > **呼叫] 佇列**，將專用號碼指派給呼叫佇列，然後按一下在通話佇列中。 在 [**一般**] 頁面上，您已有的服務號碼會列在 [**電話號碼**] 下拉式清單中。 如需詳細資訊，請參閱[建立雲端通話佇列](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)。

**如需取得新服務號碼和移植現有服務號碼的詳細資訊，請參閱[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)。**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>步驟10：為您的組織設定通訊點數

如果您想要在商務用 Skype 和 Microsoft 團隊中使用免付費電話號碼，就必須設定通訊點數。 此外，建議您針對您的通話方案（國內或國際）及需要撥出至**任何目的地**的音訊會議使用者設定通訊點數。 包含許多國家/地區，但某些目的地可能不會包含在您的通話方案或音訊會議訂閱中。 如果您沒有設定通訊信用帳單，並將**通訊點數**授權指派給您的使用者，而您在您的國家/地區的通話方案或音訊會議方案上是您的組織時間，則這些使用者無法從音訊會議會議撥打或撥出電話。 您可以透過閱讀通訊點數來取得詳細資訊（包括建議的融資金額）[嗎？](what-are-communications-credits.md)
  
> [!NOTE]
> 若要瞭解成本多少，請[參閱這裡的速度](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。

### <a name="to-set-up-communications-credits"></a>設定通訊點數

1. 使用您的公司或學校帳戶登入 Microsoft 365。

2. 在系統管理中心的左側導覽中，移至 [**帳單** > **訂閱** > **附加** > **購買附加**元件]，**然後選擇 [** > **立即購買**]。

3. 在 [**通訊點數**訂閱] 頁面上，填入您的資訊，然後按一下 **[下一步]**。

4. 輸入您的付款資訊，然後按一下 [**下單**]。
    >[!IMPORTANT]
    >如果您是大量授權客戶，您可以選擇要付款的企業協定號碼。 如果您有多個企業協定編號，您可以選取要用來進行付款的企業協定。 您也可以指定要與企業協定編號（如果適用）關聯的採購訂單編號的機會。
    
**如需設定通訊點數的詳細資訊，請參閱為[您的組織設定通訊點數](set-up-communications-credits-for-your-organization.md)。**
  
### <a name="assign-a-communications-credits-license-to-users"></a>指派通訊點數授權給使用者

1. 使用您的公司或學校帳戶登入 Office 365。

2. 在 Microsoft 365 系統管理中心的左導覽中，移至 [**使用者** > 作用中的**使用者**]，然後從清單中選取一個或多位使用者。

3. 在 [**產品授權**] 底下的 [動作] 窗格中，按一下 [**編輯**]。

4. 在 [**產品授權**] 頁面上，將 [**通訊點數**] 切換至 [**開啟**] 以指派此授權，然後按一下 [**儲存**]。

    > [!NOTE]
    > 即使您有指派**企業版 E5**授權的使用者，仍建議您這麼做。

**若要深入瞭解指派通訊點數授權的詳細資訊，請參閱[為您的組織設定通訊點數](set-up-communications-credits-for-your-organization.md)。**

## <a name="related-topics"></a>相關主題
[以下是您在 Office 365 中使用電話系統所取得的結果](here-s-what-you-get-with-phone-system.md)

[取得商務用 Skype 和 Microsoft 團隊的服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
