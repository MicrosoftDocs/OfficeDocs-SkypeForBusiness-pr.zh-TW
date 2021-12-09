---
title: 使用 Microsoft Teams 會議室 部署商務用 Skype Server
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 請閱讀本主題，以瞭解如何使用 Microsoft Teams 會議室 部署商務用 Skype Server。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 702eb2128dd37980fd3fc76548638102d45d7af9
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355618"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>使用 Microsoft Teams 會議室 部署商務用 Skype Server
  
本主題說明如何在擁有單一樹Microsoft Teams 會議室部署時新增資源帳戶。
  
如果您有使用 Exchange 2013 SP1 或更新版及 商務用 Skype Server 2015 或更新版的單一林內部部署，則您可以使用提供的 Windows PowerShell 腳本來建立裝置帳戶。 如果您使用的是多林部署，您可以使用會產生相同結果的對等 Cmdlet。 本節將說明這些 Cmdlet。
  
在您開始部署Microsoft Teams 會議室，請確定您擁有執行關聯的 Cmdlet 的許可權。
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   請注意，$strExchangeServer是 (伺服器 FQDN) 的Exchange功能變數名稱，$strLyncFQDN是您部署中的 FQDN 商務用 Skype Server功能變數名稱。

2. 建立會話之後，您可以建立新信箱，並啟用為 RoomMailboxAccount，或變更現有會議室信箱的設定。 這會允許帳戶驗證Microsoft Teams 會議室。

    如果您要變更現有的資源信箱：

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   如果您要建立新資源信箱：

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 您可以在資源帳戶Exchange各種Teams 會議室屬性，以改善人員的會議體驗。 您可以在屬性區段查看需要設定哪些Exchange屬性。

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. 關閉資源帳戶的密碼到期。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. 啟用 Active Directory 中的資源帳戶，以便驗證Microsoft Teams 會議室。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. 在資源商務用 Skype Server上啟用Microsoft Teams 會議室 Active Directory 帳戶，以啟用商務用 Skype Server帳戶：

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    將 `-DomainController` 和 `-RegistrarPool` 屬性變更為適合您環境的值。

7. **選。** 您也可以為您的帳戶Microsoft Teams 會議室 PSTN (PSTN) 公用電話交換企業語音網路。 企業語音不是您所需的Microsoft Teams 會議室，但如果您想要 PSTN 撥號功能Microsoft Teams 會議室，以下是啟用方式：

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   同樣，您必須以您自己的資訊取代所提供的網域控制站和電話號碼範例。 參數值$true保持相同。 您也需要取代語音策略和撥號方案策略名稱。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>範例：內部部署和Exchange商務用 Skype Server會議室帳戶設定

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>相關主題

[設定帳戶Microsoft Teams 會議室](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
