---
title: Skype 會議室系統房間設定腳本
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a66067d2-22b0-48f1-a5d0-e0cd0ece2e5a
description: 請閱讀本主題, 找出提供 Skype 室系統帳戶的範例腳本。
ms.openlocfilehash: e4b146346d7afe69746cf7046c0ee156ee9ff0da
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192046"
---
# <a name="skype-room-system-room-setup-scripts"></a>Skype 會議室系統房間設定腳本
 
請閱讀本主題, 找出提供 Skype 室系統帳戶的範例腳本。
  
本節說明可用於提供 Skype 室系統帳戶的範例腳本。 這些腳本只是為了說明目的, 只在諮詢 IT 專家或網域管理員之後才會使用。
  
## <a name="example-setup-script-skype-for-business-and-exchange-server-on-premises"></a>範例設定腳本: 商務用 Skype 與 Exchange Server (內部部署)

```
# On Exchange 
Set-Mailbox -Identity confroom@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a 
Lync Meeting to take advantage of enhanced meeting experience from LRS"

Set-CalendarProcessing -id confroom@contoso.com -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse 
$true -AdditionalResponse "This is an LRS room!" -DeleteSubject $false -AutomateProcessing AutoAccept 
# The following is used to preserve the Lync Meeting invitations - so create these based on your Lync Federated partners# Per Lync Federated Partner as a Recommended Practice to ensure Meetings show in Lync with Join#New-RemoteDomain -DomainName Microsoft.com -Name Microsoft$true#Set-RemoteDomain -Identity Microsoft -TNEFEnabled $true
Set-ADAccountPassword -Identity "conference room"# Paste the next command on its own. Enter a blank password first, then enter the new password "password" twiceEnable-ADAccount -Identity "confroom"# On LyncEnable-CsMeetingRoom -SipAddress "sip:confroom@contoso.com" -RegistrarPool cie-srv-02.contoso.com -Identity 'conference room' 
Set-CsMeetingRoom -Identity "conference room" -LineURI "tel:+14255551669;ext=1669" -EnterpriseVoiceEnabled $true
```

## <a name="example-setup-script-skype-for-business-and-exchange-server-online"></a>範例設定腳本: 商務用 Skype 與 Exchange Server Online

在執行腳本前, 請確定您已複習下列先決條件:
  
- 適用于 IT 專業人員的 Microsoft Online Services 登入小幫手
    
- 適用于 Windows PowerShell 的 windows Azure Active Directory 模組 (64 位版本) 或 (32 位版本)
    
- Lync Online 的 Windows PowerShell 模組
    
- 視需要重新開機
    
```
# Note you have to enter each command one at a time and update any bold fields for your environment
$rm="LyncRoom"
$org='YourTenantName.onmicrosoft.com'
$rmURI="$rm@$org"$newpass='MyPass@word1'# This Section Signs into Remote PowerShell
$cred=Get-Credential admin@$org
$sess=New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication basic -ConnectionUri https://ps.outlook.com/powershell
Import-PSSession $sess
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred
Import-PSSession $cssess -AllowClobber
Connect-MsolService -Credential $cred# This Section Create the Calendar Mailbox and Enables it for Lync
New-Mailbox -MicrosoftOnlineServicesID $rmURI -room -Name $rm -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
 -EnableRoomMailboxAccount $true

Set-CalendarProcessing -Identity $rmURI -DeleteSubject $false -AutomateProcessing AutoAccept 
Set-CalendarProcessing -Identity $rmURI -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse $true -AdditionalResponse
 "This is an LRS room!"# Configure the Account to Not Expire
Set-MsolUser -UserPrincipalName $rm -PasswordNeverExpires $true# You need to detect your Lync Pool Registrar name. Using a normal Offic365/LyncOnline user account from your tenant, run the next command and update the RegistrarPool value for the second command coming up
Get-CsOnlineUser -Identity 'admin@YourTenantName.onmicrosoft.com' | fl *registrar*# Update with above result
Enable-CsMeetingRoom -Identity $rmURI -RegistrarPool "sippoolsn20a07.infra.lync.com" -SipAddressType EmailAddress
# If the previous command fails with an error regarding the account name not being found you might need to wait and try again in a few minutes. If you wait too long, you'll need to sign in again to remote PowerShell as detailed above.
```


