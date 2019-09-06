---
title: 使用商務用 Skype Server 部署 Microsoft 團隊聊天室
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 如需如何使用商務用 Skype Server 部署 Microsoft 團隊聊天室的相關資訊，請參閱本主題。
ms.openlocfilehash: 0661a19b3569cbfde5edfb5ceb631fab7282d302
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774943"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>使用商務用 Skype Server 部署 Microsoft 團隊聊天室
  
本主題說明當您有單一林內部部署時，如何為 Microsoft 團隊聊天室新增裝置帳戶。
  
如果您有單一林、內部部署與 Exchange 2013 SP1 或更新版本，以及商務用 Skype Server 2015 或更新版本，則您可以使用隨附的 Windows PowerShell 腳本來建立裝置帳戶。 如果您使用的是多目錄林部署，您可以使用對等的 Cmdlet 來產生相同的結果。 本節將說明這些 Cmdlet。

  
開始部署 Microsoft 團隊聊天室之前，請確定您具備適當的許可權來執行相關的 Cmdlet。
  

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

   請注意，$strExchangeServer 是 Exchange 伺服器的完整功能變數名稱（FQDN），而 $strLyncFQDN 是商務用 Skype Server 部署的 FQDN。

2. 建立會話之後，您可以建立新的信箱並將其設為 RoomMailboxAccount，或變更現有會議室信箱的設定。 這可讓帳戶針對 Microsoft 團隊聊天室進行驗證。

    如果您要變更現有的資源信箱：

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   如果您要建立新的資源信箱：

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 您可以在裝置帳戶上設定各種 Exchange 屬性來改善人員的會議體驗。 您可以在 [Exchange 屬性] 區段中查看需要設定哪些屬性。

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. 如果您決定將密碼不要到期，您也可以使用 Windows PowerShell Cmdlet 來設定密碼。 如需詳細資訊，請參閱密碼管理。

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. 在 Active Directory 中啟用帳戶，以便將其驗證至 Microsoft 團隊聊天室。

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. 在商務用 Skype 伺服器池中啟用 Microsoft 團隊聊天室 Active Directory 帳戶，以啟用商務用 Skype Server 的裝置帳戶：

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    您需要使用會話初始通訊協定（SIP）位址與專案的網網域控制站

7. **可選.** 您也可以透過針對您的帳戶啟用企業語音，來允許 Microsoft 團隊聊天室撥打及接聽公用交換電話網絡（PSTN）電話。 企業語音並非 Microsoft 團隊聊天室的需求，但如果您想要使用 Microsoft 團隊聊天室用戶端的 PSTN 撥號功能，請執行下列動作：

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   同樣地，您必須以您自己的資訊取代所提供的網網域控制站和電話號碼範例。 參數值 $true 保持不變。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>範例： Exchange 和商務用 Skype Server 內部部署中的房間帳戶設定

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

## <a name="see-also"></a>另請參閱

[設定 Microsoft 團隊聊天室的帳戶](room-systems-v2-configure-accounts.md)

[規劃 Microsoft 團隊聊天室](skype-room-systems-v2-0.md)
  
[部署 Microsoft 團隊聊天室](room-systems-v2.md)
  
[設定 Microsoft 團隊聊天室主控台](console.md)
  
[管理 Microsoft 團隊聊天室](skype-room-systems-v2.md)
