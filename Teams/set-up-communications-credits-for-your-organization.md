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
description: '瞭解如何設定 PSTN 消費 (訂閱) 使用者和組織帳單授權。 '
ms.openlocfilehash: a7eab97eb3a69c8fd18442a4f8f132ec02cf9671
ms.sourcegitcommit: d9778b925873648213f05e27385255ba66cf8492
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2021
ms.locfileid: "61055554"
---
# <a name="set-up-communications-credits-for-your-organization"></a>設定貴組織的 [通訊點數]

如果您想要將免付費號碼與 商務用 Skype 和 Microsoft Teams。 此外，我們建議您為需要撥出至任何目的地之通話方案 (國內或國際) 和音訊會議使用者設定通訊信用 **額度**。 包含許多國家/地區，但部分目的地可能不包含在通話方案或音訊會議訂閱中。 如果您沒有設定通訊信用額度帳單，並指派通訊信用額度授權給使用者，而貴組織 (會根據您的國家/地區) 的通話方案或音訊會議方案而用完通話分鐘數，這些使用者將無法撥打電話或從音訊會議會議撥出。 您可以閱讀什麼是通訊信用額度，以取得更多資訊，包括建議的基金 [金額？](what-are-communications-credits.md)
  
> [!NOTE]
> 若要瞭解費用， [請參閱這裡的費率](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>步驟 1：指派音訊會議或通話方案授權給使用者

當您註冊時，會根據您的國家/地區獲得特定分鐘數。 您可以在音訊會議與通話方案的國家/地區可用性[](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization)清單中搜尋您的國家/地區，以查看您可獲得的分鐘數。 當您使用這些通話分鐘數後，通話將會中斷。 若要避免發生這種情況，您必須設定通訊信用額度。
  
若要這麼做 **，您必須指派** 音訊會議或電話系統授權給使用者。
  
- 指派 **音訊會議授權** 給使用者。 請參閱[指派Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
    指派此授權之後，您必須設定音訊會議。 有關逐步指示，請參閱在 Microsoft 365 或 Office 365 中試用或[購買音訊Office 365。](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
- 指派 **電話系統** 國內 **或** 國內及國際通話方案授權給使用者。 請參閱[指派Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
    > [!NOTE]
    > 雖然通訊信用額度不一樣，您仍然需要指派國內通話方案或 **國內和國際** 通話方案授權。
  
    指派這些授權之後，您必須取得貴組織的電話號碼，然後將這些號碼指派給貴組織的人。 有關逐步指示，請參閱 [設定通話方案](set-up-calling-plans.md)。
    
詳細資訊，請參閱Microsoft Teams[附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>步驟 2：為貴組織設定通訊信用額度

1. 使用公司[Microsoft 365 系統管理中心](https://portal.office.com/Adminportal)學校帳戶來登錄帳戶。
    
2. 在系統左側導Microsoft 365 系統管理中心，請前往帳單  >  **購買服務**。 向下卷起並選取 **附加元件**。

3. 選取 **通訊信用額度**。
    
4. 在 [**通訊信用額度訂閱**> 頁面上，填入您的資訊，然後按一下 [下 **一步：**
    
   - **新增資金** 輸入要新加到帳戶的金額。 如果您未啟用自動充值功能，一旦這些資金用盡，使用通訊信用額度啟用的通話功能會中斷 (例如免付費服務) 。 為了避免每次餘額達到 0 或零 (時，) 手動補充通訊信用額度餘額，建議您啟用自動充值功能。
    
   - **自動充電** 當餘額低於您設定閾值時，啟用自動加值功能會自動重新填入您的帳戶。
    
     建議您使用自動充值設定，以避免通訊信用額度餘額達到 0 (零) 。 當充值交易成功、充值交易失敗 (例如過期的信用卡) ，以及您的通訊信用額度餘額達到 0 (零) 時，您就會收到電子郵件。
    
   - **充值金額** 在到達下方的觸發金額後，在您想要新加到您帳戶的加值方塊中輸入金額。
    
   - **觸發金額** 在當餘額低於方塊時輸入金額，此方塊會用來'*觸發*'自動充值。 一旦餘額低於此金額，加值金額會自動新加到您的帳戶。

      > [!NOTE]
     > 當服務使用時，資金只會以 Microsoft 發佈費率適用于通訊信用額度。 購買日期後 12 個月內未使用的任何資金將會到期並予以沒收。 
     > 
     > 使用自動充值功能時，當達到觸發金額並處理充值交易時，會針對通訊信用額度產生發票。 通訊信用額度會先以先發的方式使用。 若要瞭解如何檢查每月使用量，請閱讀[PSTN](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)Microsoft Teams報告。
    
5. 輸入您的付款資訊，然後按一下 **[下單**。
    >[!IMPORTANT]
    >如果您是大量授權客戶，您可以選擇要付款的企業協定號碼。 如果您有多個企業協定編號，您可以選取要用於付款的企業協定。 如果適用，您也會有機會指定要與企業 (建立關聯的) 。
    
每個組織都會考慮不同的通話方案使用量和費率。 您必須從目前的服務提供者取得這類使用方式資料。 已經使用 商務用 Skype Online 或 Microsoft Teams 作為服務提供者的組織可以在 **Microsoft Teams** 系統管理中心分析 & 報告使用方式報告  >    >    >  **PSTN** 和簡訊 (預覽) 使用方式報告中，來取得使用方式資料。
  
當您設定通訊信用額度時，您必須調查貴組織的通話使用量，以決定您需要的金額。 您可以查看 PSTN 和簡訊 (**通話) 使用方式** 資訊。 如果您需要儲存資料或建立自訂報表Excel此報表可讓您將通話資料記錄匯出至其他記錄。 若要瞭解如何查看使用方式，請參閱[PSTN](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)Microsoft Teams報告。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>步驟 3：指派通訊信用額度授權給使用者

1. 使用公司[Microsoft 365 系統管理中心](https://portal.office.com/Adminportal)學校帳戶來登錄帳戶。
    
2. 在左側流覽Microsoft 365 系統管理中心，前往 **使用者**  >  **活動使用者**，然後從清單中選取使用者。
    
3. 選擇 **授權與應用程式**。
    
4. 將 **通訊信用額度切換** 為 **開啟** 以指派此授權， **然後選取** 儲存 。
    
    > [!NOTE]
    > 即使您有指派 **E5** 授權Enterprise使用者，仍建議您這麼做。

    > [!TIP]
    > 您可以使用 [Powershell](/powershell/module/skype/?view=skype-ps&preserve-view=true) 以單一命令將授權和應用程式指派給多個使用者。
  
## <a name="want-to-know-about-plans-and-pricing"></a>想要瞭解方案與價格嗎？

您可以流覽下列其中一個連結來查看方案與價格：
  
- [通話方案](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [音訊會議方案](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [電話系統方案](https://go.microsoft.com/fwlink/?LinkId=799763)
    
您也可以以登錄帳戶並進入帳單訂閱 [新增訂閱Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)****  >  **查看**  >  **資訊**。
  
若要查看每個功能所需的授權或授權資料表，請參閱Microsoft Teams[附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
## <a name="related-topics"></a>相關主題

- [設定商務用 Skype Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [設定雲端語音信箱 - 管理說明](set-up-phone-system-voicemail.md)
    
- [設定通話方案](set-up-calling-plans.md)與通話方案[Microsoft 365或Office 365](calling-plans-for-office-365.md)
    
- [加值和管理通訊點數](add-funds-and-manage-communications-credits.md)
    
  
