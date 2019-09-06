---
title: Skype 會議室系統單一林內部部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 若要瞭解如何在單一目錄林內部部署環境中部署 Skype 會議室系統，請閱讀本主題。
ms.openlocfilehash: 2d73ee2313088c653f4362139cb431e55d92015b
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775261"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype 會議室系統單一林內部部署
 
若要瞭解如何在單一目錄林內部部署環境中部署 Skype 會議室系統，請閱讀本主題。
  
本節概述在 Exchange Server 上提供 Skype 室系統帳戶的步驟，以及在單一目錄林內部部署中託管的商務用 Skype 伺服器。
  
## <a name="single-forest-on-premises-deployments"></a>單一目錄林內部部署

如果您已經有會議室的資源信箱，可以使用該帳戶。 否則，您將需要建立一個新的。 您可以使用 Exchange 管理命令介面（PowerShell）或 Exchange 管理主控台來建立新的資源信箱帳戶。 我們建議您使用新的（刪除舊信箱，並重新建立） Skype 會議室系統資源信箱。 請務必先備份信箱資料，然後再將其匯出為使用 Outlook 用戶端重新建立的信箱（如需詳細資訊，請參閱匯出或備份郵件、行事曆、工作及連絡人）。 若要透過刪除信箱來還原遺失的會議，請參閱[連接或還原已刪除的信箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。 
  
若要使用現有的資源信箱帳戶（例如，LRS-01），請遵循下列步驟：
  
1. 執行下列 Exchange 管理 PowerShell 命令：
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 如果您打算建立新的信箱，請針對單一的林內部部署 Exchange 組織，執行下列命令：
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   上述範例會在 Active Directory 中建立已啟用的使用者帳戶，以及內部部署 Exchange 組織中會議室的會議室信箱。 RoomMailboxPassword 參數會指定使用者帳戶的密碼。
    
3. 將帳戶設定為透過接受/拒絕會議來自動解決衝突。 Exchange 中的 Skype 會議室系統隨附的會議室帳戶可由個人管理，但請注意，直到個別人接受會議時，才會顯示在 Skype 會議室系統的主畫面行事曆上。
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   如需可用的完整命令集，請參閱設定 CalendarProcessing。
    
   若要提醒會議召集人在 Outlook 中讓會議成為線上商務用 Skype 會議，請執行下列命令來設定新帳戶的寄件提醒： 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 使用下列命令來設定當地語系化的字串。 如果您的組織需要，您也可以新增自訂翻譯： 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. [選用]：設定會議接受文字，為使用者供應商務用 Skype 會議室的相關資訊，以及在排程及加入會議時預期的情況。 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>檢查 Active Directory 中的資源信箱帳戶

上述步驟1中由 Exchange 所建立的會議室信箱帳戶可能是 Active Directory 中已停用的使用者物件。 如果 Active Directory 中的帳戶已停用，Skype 會議室系統就無法使用 Kerberos/NTLM 驗證登入或進行驗證。 Skype 聊天室系統用戶端必須能夠針對 Exchange Web 服務進行驗證，以取得行事曆設定，而且也必須能夠使用白板內容傳送電子郵件。 
  
因此，如果帳戶已停用，您必須執行下列動作，才能在 Active Directory 中啟用這個帳戶： 
  
1. 在 Active Directory 中，執行下列命令以啟用帳戶登入： 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   執行此命令時，系統會提示您輸入目前的密碼，然後重新輸入密碼兩次以進行確認。
    
2. 設定密碼之後，請執行下列命令以啟用帳戶： 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>啟用商務用 Skype 的 Skype 會議室系統帳戶

本節概述針對您的會議室帳戶啟用商務用 Skype 所需的步驟，將會在 Skype 會議室系統上設定。 
  
在您為會議室建立資源信箱帳戶之後，請使用商務用 Skype Server Management Shell 來啟用商務用 Skype 服務的 Skype 會議室系統帳戶。
  
> [!NOTE]
> 下列程式假設您已在 Active Directory 中啟用 Skype 會議室系統帳戶。 
  
1. 執行下列命令，在商務用 Skype 伺服器池中啟用 Skype 會議室系統帳戶：
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. [選用]：允許此帳戶透過啟用企業語音帳戶來撥打和接聽 PSTN 電話。 Skype 室系統不需要企業版語音，但如果您不啟用企業語音，Skype 聊天室系統用戶端將無法提供 PSTN 撥號功能：
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果您為 Skype 會議室系統會議室帳戶啟用企業版語音，請務必設定適合您組織的受限制語音原則。 如果商務用 Skype 會議室是公開提供的資源，任何人都可以使用它來加入會議（無論是排程的或點對點的）。 加入會議之後，該人員就可以撥出任何號碼。 在商務用 Skype Server 中，「從會議撥出」功能會使用使用者的語音原則，在此案例中，用來加入會議的 Skype 房間系統帳戶。 在舊版的 Lync Server 中，會使用召集人的語音原則。 因此，如果舊版 Lync Server 的使用者排程會議室，並邀請 Skype 會議室系統房間帳戶，任何人都可以使用商務用 Skype 會議室加入會議，而且可以撥打電話給任何國家/地區或國際電話[數位]，只要允許召集人撥打這些號碼即可。 
  

