---
title: 使用 商務用 Skype Server 部署Microsoft Teams 會議室
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
- Teams_ITAdmin_Rooms
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 如需如何使用商務用 Skype Server部署Microsoft Teams 會議室的相關資訊，請閱讀本主題。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 53903052efe28a85400ba8b418bd8869ef2dec4e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271678"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>使用 商務用 Skype Server 部署Microsoft Teams 會議室
  
本主題說明當您擁有單一森林內部部署時，如何新增Microsoft Teams 會議室的資源帳戶。
  
如果您使用 Exchange 2013 SP1 或更新版本及 2015 年 商務用 Skype Server 或更新版本的單一森林內部部署，則可以使用提供的Windows PowerShell腳本來建立裝置帳戶。 如果您使用多林部署，可以使用同等的 Cmdlet 來產生相同的結果。 本節說明這些 Cmdlet。
  
開始部署Microsoft Teams 會議室之前，請確定您擁有執行相關聯 Cmdlet 的正確許可權。
  

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

   請注意，$strExchangeServer是 Exchange 伺服器 (FQDN) 的完整功能變數名稱，而 $strLyncFQDN 是您商務用 Skype Server部署的 FQDN。

2. 建立會話之後，您將建立新的信箱並將其啟用為 RoomMailboxAccount，或是變更現有會議室信箱的設定。 這可讓帳戶驗證以Microsoft Teams 會議室。

    如果您要變更現有的資源信箱：

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   如果您要建立新的資源信箱：

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 您可以在Teams 會議室資源帳戶上設定各種 Exchange 屬性，以改善人員的會議體驗。 您可以在 [Exchange 屬性] 區段中查看需要設定哪些屬性。

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. 關閉資源帳戶的密碼到期。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. 在 Active Directory 中啟用資源帳戶，以便驗證以Microsoft Teams 會議室。

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. 在商務用 Skype Server集區上啟用Microsoft Teams 會議室 Active Directory 帳戶，以商務用 Skype Server啟用資源帳戶：

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    `-DomainController`將和 `-RegistrarPool` 屬性變更為適合您環境的值。

7. **選。** 您也可以允許Microsoft Teams 會議室啟用帳戶的企業語音， (PSTN) 電話撥打和接聽公用交換電話網路。 企業語音不是Microsoft Teams 會議室的需求，但如果您想要 PSTN 撥號功能以供Microsoft Teams 會議室使用，以下是啟用方式：

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   同樣地，您必須以自己的資訊取代提供的網域控制站和電話號碼範例。 參數值$true保持不變。 您也需要取代語音原則和撥號對應表原則名稱。

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>範例：Exchange 和 商務用 Skype Server 內部部署中的會議室帳戶設定

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

[設定Microsoft Teams 會議室帳戶](rooms-configure-accounts.md)

[規劃 Microsoft Teams 會議室](rooms-plan.md)
  
[部署 Microsoft Teams 會議室](rooms-deploy.md)
  
[設定 Microsoft Teams 會議室主控台](console.md)
  
[管理 Microsoft Teams 會議室](rooms-manage.md)
