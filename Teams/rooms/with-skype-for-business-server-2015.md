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
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="1ef79-103">使用 Microsoft Teams 會議室 部署商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="1ef79-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="1ef79-104">本主題說明如何在您擁有單一Microsoft Teams 會議室部署時新增裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="1ef79-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="1ef79-105">如果您有使用 Exchange 2013 SP1 或更新版及 商務用 Skype Server 2015 或更新版的單一林內部部署，則您可以使用提供的 Windows PowerShell 腳本來建立裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="1ef79-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="1ef79-106">如果您使用的是多林部署，您可以使用會產生相同結果的對等 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ef79-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="1ef79-107">本節將說明這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ef79-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="1ef79-108">在您開始部署Microsoft Teams 會議室，請確定您擁有執行關聯的 Cmdlet 的許可權。</span><span class="sxs-lookup"><span data-stu-id="1ef79-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="1ef79-109">請注意$strExchangeServer是 (伺服器) Exchange FQDN) ，而 $strLyncFQDN 是您 商務用 Skype Server 部署的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1ef79-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="1ef79-110">建立會話之後，您可以建立新信箱，並啟用為 RoomMailboxAccount，或變更現有會議室信箱的設定。</span><span class="sxs-lookup"><span data-stu-id="1ef79-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="1ef79-111">這會允許帳戶驗證Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="1ef79-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="1ef79-112">如果您要變更現有的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="1ef79-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="1ef79-113">如果您要建立新資源信箱：</span><span class="sxs-lookup"><span data-stu-id="1ef79-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="1ef79-114">您可以在裝置帳戶Exchange各種資訊屬性，以改善人員的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="1ef79-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="1ef79-115">您可以在屬性區段查看需要設定哪些Exchange屬性。</span><span class="sxs-lookup"><span data-stu-id="1ef79-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="1ef79-116">如果您決定密碼不會過期，您也可以使用 Cmdlet Windows PowerShell設定密碼。</span><span class="sxs-lookup"><span data-stu-id="1ef79-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="1ef79-117">請參閱密碼管理以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="1ef79-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="1ef79-118">啟用 Active Directory 中的帳戶，以便驗證Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="1ef79-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="1ef79-119">在資料商務用 Skype Server上啟用Microsoft Teams 會議室 Active Directory 帳戶，以啟用商務用 Skype Server帳戶：</span><span class="sxs-lookup"><span data-stu-id="1ef79-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="1ef79-120">您必須使用會話初始通訊協定 (SIP) 位址和網域控制站Project</span><span class="sxs-lookup"><span data-stu-id="1ef79-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="1ef79-121">**選。**</span><span class="sxs-lookup"><span data-stu-id="1ef79-121">**Optional.**</span></span> <span data-ttu-id="1ef79-122">您也可以為您的帳戶Microsoft Teams 會議室 PSTN (PSTN) 公用電話交換企業語音網路。</span><span class="sxs-lookup"><span data-stu-id="1ef79-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="1ef79-123">企業語音並非 Microsoft Teams 會議室的一項需求，但如果您想要為 Microsoft Teams 會議室 用戶端提供 PSTN 撥號功能，請執行以下方式：</span><span class="sxs-lookup"><span data-stu-id="1ef79-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="1ef79-124">同樣，您必須以您自己的資訊取代所提供的網域控制站和電話號碼範例。</span><span class="sxs-lookup"><span data-stu-id="1ef79-124">Again, you'll need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="1ef79-125">參數值$true保持相同。</span><span class="sxs-lookup"><span data-stu-id="1ef79-125">The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="1ef79-126">範例：內部部署Exchange商務用 Skype Server會議室帳戶設定</span><span class="sxs-lookup"><span data-stu-id="1ef79-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="1ef79-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="1ef79-127">Related topics</span></span>

[<span data-ttu-id="1ef79-128">設定帳戶Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="1ef79-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="1ef79-129">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="1ef79-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="1ef79-130">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="1ef79-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="1ef79-131">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="1ef79-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="1ef79-132">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="1ef79-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
