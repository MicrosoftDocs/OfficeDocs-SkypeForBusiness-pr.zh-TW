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
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 請閱讀本主題，以瞭解如何使用 Microsoft Teams 會議室 部署商務用 Skype Server。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662258"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>使用 Microsoft Teams 會議室 部署商務用 Skype Server
  
本主題說明如何在您擁有單一Microsoft Teams 會議室部署時新增裝置帳戶。
  
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

   請注意$strExchangeServer是 (伺服器) Exchange FQDN) ，而 $strLyncFQDN 是您 商務用 Skype Server 部署的 FQDN。

2. 建立會話之後，您可以建立新信箱，並啟用為 RoomMailboxAccount，或變更現有會議室信箱的設定。 這會允許帳戶驗證Microsoft Teams 會議室。

    如果您要變更現有的資源信箱：

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   如果您要建立新資源信箱：

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 您可以在裝置帳戶Exchange各種資訊屬性，以改善人員的會議體驗。 您可以在屬性區段查看需要設定哪些Exchange屬性。

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. 如果您決定密碼不會過期，您也可以使用 Cmdlet Windows PowerShell設定密碼。 請參閱密碼管理以瞭解更多資訊。

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. 啟用 Active Directory 中的帳戶，以便驗證Microsoft Teams 會議室。

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. 在資料商務用 Skype Server上啟用Microsoft Teams 會議室 Active Directory 帳戶，以啟用商務用 Skype Server帳戶：

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    您必須使用會話初始通訊協定 (SIP) 位址和網域控制站Project

7. **選。** 您也可以為您的帳戶Microsoft Teams 會議室 PSTN (PSTN) 公用電話交換企業語音網路。 企業語音並非 Microsoft Teams 會議室的一項需求，但如果您想要為 Microsoft Teams 會議室 用戶端提供 PSTN 撥號功能，請執行以下方式：

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   同樣，您必須以您自己的資訊取代所提供的網域控制站和電話號碼範例。 參數值$true保持相同。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>範例：內部部署Exchange商務用 Skype Server會議室帳戶設定

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="related-topics"></a>相關主題

[設定帳戶Microsoft Teams 會議室](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
