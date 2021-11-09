---
title: Skype會議室系統單一樹系內部部署
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 閱讀此主題以瞭解如何在單一樹系內部部署環境中部署 Skype 的會議室系統。
ms.openlocfilehash: 0f8ab644efc3d832fd5e201bd49517971ba5ba08
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828416"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype會議室系統單一樹系內部部署
 
閱讀此主題以瞭解如何在單一樹系內部部署環境中部署 Skype 的會議室系統。
  
本節概述在單一樹系內部部署中的 Exchange Server 和商務用 Skype Server 上布建 Skype 室系統帳戶的步驟。
  
## <a name="single-forest-on-premises-deployments"></a>單一樹系內部部署

如果您已經有會議室的資源信箱帳戶，您可以使用它。 否則，您將需要建立一個新的。 您可以使用 Exchange 管理命令介面 (PowerShell) 或 Exchange 管理主控台，以建立新的資源信箱帳戶。 建議使用新的 (刪除舊的信箱，然後重新建立) 資源信箱 Skype 的會議室系統。 請務必先備份信箱資料，然後再將其匯出回使用 Outlook 用戶端重新建立的信箱 (如需詳細資訊，請參閱匯出或備份郵件、行事曆、任務及連絡人) 。 若要還原因刪除信箱而遺失的會議，請參閱[連線或還原已刪除的信箱](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。 
  
若要使用現有的資源信箱帳戶 (例如，LRS-01) 請遵循下列步驟：
  
1. 執行下列 Exchange 管理 PowerShell 命令：
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 若要建立新的信箱，請針對單一樹系內部部署 Exchange 組織執行下列命令：
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   在上述範例中，會在 Active Directory 中建立已啟用的使用者帳戶，並在內部部署 Exchange 組織中的會議室建立會議室信箱。 RoomMailboxPassword 參數能指定使用者帳戶的密碼。
    
3. 透過接受/拒絕會議，將帳戶設定為自動解決衝突。 Skype會議室 Exchange 中的會議室帳戶可由個人管理，但請注意，直到個人接受會議時，才不會出現在 Skype 室系統主畫面行事曆上。
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   如需一組完整的可用命令，請參閱 Set-CalendarProcessing。
    
   若要提醒會議召集人在 Outlook 中讓會議成為線上商務用 Skype 會議，請執行下列命令來設定新帳戶的 MailTip： 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 使用下列命令來設定當地語系化的字串。 如果您的組織需要，您也可以新增自訂翻譯： 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. 選用：設定會議接受文字，以提供使用者商務用 Skype 會議室的相關資訊，以及在排程及加入會議時所期望的專案。 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>檢查 Active Directory 中的資源信箱帳戶

在上述步驟1中 Exchange 所建立的會議室信箱帳戶可能是 Active Directory 中已停用的使用者物件。 Skype會議室系統無法使用 Kerberos/NTLM 驗證來登入或驗證，如果在 Active Directory 中停用帳戶。 Skype 的會議室系統用戶端必須能夠對 Exchange Web 服務進行驗證，以取得行事曆設定，也必須能夠使用白板內容傳送電子郵件。 
  
因此，如果停用帳戶，您必須執行下列動作，以在 Active Directory 中啟用此帳戶： 
  
1. 在 Active Directory 中執行下列命令，以啟用帳戶登入： 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   執行此命令時，會提示您輸入目前的密碼，然後重新輸入密碼兩次進行確認。
    
2. 設定密碼後，請執行下列命令來啟用帳戶： 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>為商務用 Skype 啟用 Skype 會議室系統帳戶

本節概述為您的會議室帳戶啟用商務用 Skype 所需的步驟，將在 Skype 會議室系統上進行設定。 
  
在您為會議聊天室建立資源信箱帳戶後，請使用商務用 Skype Server 管理命令介面來啟用商務用 Skype 服務 Skype 會議室系統帳戶。
  
> [!NOTE]
> 下列程式假設您已在 Active Directory 中啟用 Skype 的會議室系統帳戶。 
  
1. 執行下列命令，在商務用 Skype Server 集區上啟用 Skype 的會議室系統帳戶：
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 選用：允許此帳戶啟用企業語音的帳戶，以撥打和接收 PSTN 電話通話。 Skype 會議室系統不需要企業語音，但如果您未啟用企業語音，Skype 的會議室系統用戶端將無法提供 PSTN 撥號功能：
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 如果您為 Skype 會議室系統的會議室帳戶啟用企業語音，請務必設定適用于您組織的受限制語音原則。 如果商務用 Skype 會議室是公開提供的資源，任何人都可以使用該資源加入會議，無論是排程或特殊的。 加入會議之後，使用者可以撥出任何號碼。 在商務用 Skype Server 中，「從會議撥出」功能會使用使用者的語音原則，在此案例中是用來加入會議的 Skype 會議室系統帳戶。 在舊版的 Lync Server 中，會使用召集人的語音原則。 因此，如果舊版 Lync Server 的使用者排程會議室，並邀請 Skype 會議室系統帳戶，任何人都可以使用商務用 Skype 會議室加入會議，而且可以撥打任何國內/地區或國際電話號碼，只要召集人可以撥打這些號碼。 
