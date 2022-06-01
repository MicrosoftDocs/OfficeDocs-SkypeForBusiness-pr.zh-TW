---
title: 設定貴組織的 [通訊點數]
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: '瞭解如何為使用者和組織設定通訊點數 (PSTN 消費) 帳單授權。 '
ms.openlocfilehash: 9cbd49ed35b3bd52c7b00decf67cab0e01d0a320
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823594"
---
# <a name="set-up-communications-credits-for-your-organization"></a>設定貴組織的 [通訊點數]

如果您想要搭配商務用 Skype和Microsoft Teams使用免付費電話號碼，您將需要設定通訊點數。 此外，建議您設定通話方案的通訊點數 (國內或國際) ，以及音訊會議需要撥出到 **任何目的地** 的使用者。 我們包含了許多國家/地區，但部分目的地可能不包含在您的通話方案或音訊會議訂閱中。 如果您未設定通訊點數計費，並指派 **通訊點** 數授權給使用者，而且貴組織 (根據您國家/地區的通話方案或音訊會議方案) ，則這些使用者將無法撥打電話或從音訊會議會議撥出。 您可以閱讀[什麼是通訊點數](what-are-communications-credits.md)，取得詳細資訊，包括建議的金額。
  
> [!NOTE]
> 若要瞭解費用， [請參閱這裡的費率](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>步驟 1：指派音訊會議或通話方案授權給使用者

當您註冊時，您會根據您的國家/地區取得特定的分鐘數。 您可以在 [[國家或地區可用性] 清單中搜尋您的國家或地區，以取得音訊會議和通話方案](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization)，以查看您會收到的通話分鐘數。 使用這些通話分鐘之後，通話就會中斷連線。 若要避免這種情況發生，您必須設定通訊點數。
  
若要這麼做，**您必須指派音訊會議或電話系統授權** 給使用者。 對於已指派這兩個授權或兩者之一的使用者，可以啟用通訊點數。
  
- 指派 **音訊會議** 授權給您的使用者。 請參閱[指派Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
    指派此授權之後，您將需要設定音訊會議。 如需逐步指示，請參閱[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)。
    
- 指派 **電話系統** 以及 **國內或國內及國際** 通話方案授權給使用者。 請參閱[指派Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
    > [!NOTE]
    > 雖然通訊點數不需要，但您仍然需要指派 **國內通話方案** 或 **國內及國際通話方案** 授權。
  
    指派這些授權之後，您必須為組織取得電話號碼，然後將這些號碼指派給組織中的人員。 如需逐步指示，請參閱 [設定通話方案](set-up-calling-plans.md)。
    
如需詳細資訊，請參[閱Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>步驟 2：為貴組織設定通訊點數

1. 使用公司或學校帳戶[登入Microsoft 365 系統管理中心](https://portal.office.com/Adminportal)。
    
2. 在Microsoft 365 系統管理中心左側導覽中，移至 **帳單**  >  **購買服務**。

3. 在 **附加組** 件類別底下尋找 **通訊點** 數，或在 [**搜尋所有產品類別**] 搜尋方塊中搜尋「通訊點數」，然後選取 [**詳細資料]**。
    
4. 檢閱服務資訊，然後選取 **[購買]**。  (注意：每筆訂單都會自動選取固定數量的通訊點數授權。) 

5. 在 [結帳] 頁面上，輸入您的付款資訊並填寫必要資訊：
    
   - **新增資金** 輸入您要存入帳戶的金額。 如果您不啟用自動加值功能，當這些資金失效後，使用通訊點數啟用的通話功能將會中斷 (例如輸入免付費服務) 。 為了避免每次餘額達到 0 (零) 時，都需要手動補充您的通訊點數餘額，建議您啟用自動加值功能。
    
   - **自動加值** 啟用自動加值會在餘額低於您設定的閾值時自動重新填入您的帳戶。
    
     建議您使用 **自動加值** 設定，以避免在通訊點數餘額達到 0 (零) 時中斷服務。 當加值交易成功、加值交易失敗 (例如信用卡) 到期，以及您的通訊點數餘額達到 0 (零時，系統會傳送電子郵件給您) 。
    
   - **加值金額** 在達到以下觸發金額後，在 [ **加值** ] 方塊中輸入您要加值到帳戶的金額。
    
   - **觸發金額** 在 [ **餘額低於]** 方塊中輸入金額，該方塊會用來「 *觸發*  」自動加值。 一旦您的餘額低於此金額，加值金額就會自動加到您的帳戶中。

      > [!NOTE]
     > 資金只會在使用服務時，以 Microsoft 發佈的費率套用至通訊點數。 在購買日期的 12 個月內未使用的任何資金將會過期並失效。 
     > 
     > 使用自動加值函數時，會在達到觸發金額且處理充電交易時產生通訊點數發票。 通訊點數會先用到。 若要瞭解如何檢查您的每月使用量，請閱讀[Microsoft Teams PSTN 使用方式報告](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)。
    
6. 選 **取 [下單]**。
    >[!IMPORTANT]
    >如果您是大量授權客戶，建議您使用企業合約付款。 如果您想要這樣做，請開啟頂級支援案例以啟用此功能。 如果您有多個企業合約編號，您可以選取要用來付款的企業合約。 一旦支援啟用此功能) ，您也有機會指定要與企業合約編號建立關聯的採購單編號 (。
    
每個組織都會有不同的通話方案音量和費率來考慮。 您必須向目前的服務提供者取得這種類型的使用狀況資料。 已經使用 商務用 Skype Online 或 Microsoft Teams 做為其服務提供者的組織，可以在 Microsoft Teams **系統管理中心**  >  **分析&報告** 使用方式 **報告**  >   >  **PSTN，簡訊 (預覽) 使用** 情況報告來取得使用狀況資料。
  
當您設定通訊點數時，您必須調查貴組織的通話使用狀況，以判斷您需要的金額。 您可以檢閱 **PSTN 和簡訊 (預覽) 使用** 情況報告，以取得通話使用狀況資訊。 如果您需要儲存資料或建立自訂報告，此報告可讓您將通話資料記錄匯出至Excel。 若要瞭解如何查看使用方式，請閱讀[Microsoft Teams PSTN 使用方式報告](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>步驟 3：指派通訊點數授權給使用者

1. 使用公司或學校帳戶[登入Microsoft 365 系統管理中心](https://portal.office.com/Adminportal)。
    
2. 在Microsoft 365 系統管理中心左側導覽中，移至 [**使用者**  >  **作用中使用者]**，然後從清單中選取使用者。
    
3. 選擇 **[授權與應用程式]**。
    
4. 將 **[通訊點數** ] 切換為 [ **開啟** ] 以指派此授權，然後選取 [ **儲存]**。
    
    > [!NOTE]
    > 即使您已指派 **Enterprise E5** 授權的使用者，還是建議您這麼做。

    > [!TIP]
    > 您可以使用 [Powershell](/powershell/module/skype/?view=skype-ps&preserve-view=true) ，以單一命令將授權和應用程式指派給多位使用者。
  
## <a name="want-to-know-about-plans-and-pricing"></a>想知道方案和價格嗎？

您可以流覽下列其中一個連結來查看方案和價格：
  
- [通話方案](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [音訊會議方案](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [電話系統方案](https://go.microsoft.com/fwlink/?LinkId=799763)
    
您也可以登入Microsoft 365 系統管理中心，然後移 [至](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) **[計費**  >  **訂閱**  >  新增 **訂閱**] 來查看資訊。
  
若要查看每個功能所需的授權或授權資料表，請參[閱Microsoft Teams附加元件授權。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="related-topics"></a>相關主題

- [設定商務用 Skype Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [設定雲端語音信箱 - 管理說明](set-up-phone-system-voicemail.md)
    
- [設定 Microsoft 365](set-up-calling-plans.md) [或 Office 365 的通話方案和通話方案](calling-plans-for-office-365.md)
    
- [加值和管理通訊點數](add-funds-and-manage-communications-credits.md)
    
  
