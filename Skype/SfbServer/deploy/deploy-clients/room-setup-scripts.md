---
title: Skype 會議室系統房間設定腳本
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a66067d2-22b0-48f1-a5d0-e0cd0ece2e5a
description: 請閱讀本主題，找出提供 Skype 室系統帳戶的範例腳本。
ms.openlocfilehash: b2a6d0ce02e233492ac04a198c2bf2220f4de998
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003003"
---
# <a name="skype-room-system-room-setup-scripts"></a><span data-ttu-id="6acd4-103">Skype 會議室系統房間設定腳本</span><span class="sxs-lookup"><span data-stu-id="6acd4-103">Skype Room System room setup scripts</span></span>
 
<span data-ttu-id="6acd4-104">請閱讀本主題，找出提供 Skype 室系統帳戶的範例腳本。</span><span class="sxs-lookup"><span data-stu-id="6acd4-104">Read this topic to find sample scripts for provisioning Skype Room System accounts.</span></span>
  
<span data-ttu-id="6acd4-105">本節說明可用於提供 Skype 室系統帳戶的範例腳本。</span><span class="sxs-lookup"><span data-stu-id="6acd4-105">This section illustrates sample scripts that can be used to provision Skype Room System accounts.</span></span> <span data-ttu-id="6acd4-106">這些腳本只是為了說明目的，只在諮詢 IT 專家或網域管理員之後才會使用。</span><span class="sxs-lookup"><span data-stu-id="6acd4-106">These scripts are for illustrative purposes only and should be used only after consulting with your IT expert or domain administrator.</span></span>
  
## <a name="example-setup-script-skype-for-business-and-exchange-server-on-premises"></a><span data-ttu-id="6acd4-107">範例設定腳本：商務用 Skype 與 Exchange Server （內部部署）</span><span class="sxs-lookup"><span data-stu-id="6acd4-107">Example Setup Script: Skype for Business and Exchange Server (On Premises)</span></span>

```powershell
# On Exchange 
Set-Mailbox -Identity confroom@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a 
Lync Meeting to take advantage of enhanced meeting experience from LRS"

Set-CalendarProcessing -id confroom@contoso.com -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse 
$true -AdditionalResponse "This is an LRS room!" -DeleteSubject $false -AutomateProcessing AutoAccept 
# The following is used to preserve the Lync Meeting invitations - so create these based on your Lync Federated partners# Per Lync Federated Partner as a Recommended Practice to ensure Meetings show in Lync with Join#New-RemoteDomain -DomainName Microsoft.com -Name Microsoft$true#Set-RemoteDomain -Identity Microsoft -TNEFEnabled $true
Set-ADAccountPassword -Identity "conference room"# Paste the next command on its own. Enter a blank password first, then enter the new password "password" twiceEnable-ADAccount -Identity "confroom"# On LyncEnable-CsMeetingRoom -SipAddress "sip:confroom@contoso.com" -RegistrarPool cie-srv-02.contoso.com -Identity 'conference room' 
Set-CsMeetingRoom -Identity "conference room" -LineURI "tel:+14255551669;ext=1669" -EnterpriseVoiceEnabled $true
```

## <a name="example-setup-script-skype-for-business-and-exchange-server-online"></a><span data-ttu-id="6acd4-108">範例設定腳本：商務用 Skype 與 Exchange Server Online</span><span class="sxs-lookup"><span data-stu-id="6acd4-108">Example Setup Script: Skype for Business and Exchange Server Online</span></span>

<span data-ttu-id="6acd4-109">在執行腳本前，請確定您已複習下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="6acd4-109">Make sure you've reviewed the following prerequisites before running the script:</span></span>
  
- <span data-ttu-id="6acd4-110">適用于 IT 專業人員的 Microsoft Online Services 登入小幫手</span><span class="sxs-lookup"><span data-stu-id="6acd4-110">Microsoft Online Services Sign-In Assistant for IT Professionals BETA</span></span>
    
- <span data-ttu-id="6acd4-111">適用于 Windows PowerShell 的 windows Azure Active Directory 模組（64位版本）或（32位版本）</span><span class="sxs-lookup"><span data-stu-id="6acd4-111">Windows Azure Active Directory Module for Windows PowerShell (64-bit version) or (32-bit version)</span></span>
    
- <span data-ttu-id="6acd4-112">Lync Online 的 Windows PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="6acd4-112">Windows PowerShell Module for Lync Online</span></span>
    
- <span data-ttu-id="6acd4-113">視需要重新開機</span><span class="sxs-lookup"><span data-stu-id="6acd4-113">Reboot if needed</span></span>
    
```powershell
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


