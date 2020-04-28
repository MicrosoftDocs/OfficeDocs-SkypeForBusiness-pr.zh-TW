---
title: 使用商務用 Skype Server 部署 Microsoft 團隊聊天室
ms.author: v-lanac
author: lanachin
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
description: 如需如何使用商務用 Skype Server 部署 Microsoft 團隊聊天室的相關資訊，請參閱本主題。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9e827f4d1fc020160b59f26dffde960394c3a69e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905265"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="5564f-103">使用商務用 Skype Server 部署 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="5564f-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="5564f-104">本主題說明當您有單一林內部部署時，如何為 Microsoft 團隊聊天室新增裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="5564f-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="5564f-105">如果您有單一林、內部部署與 Exchange 2013 SP1 或更新版本，以及商務用 Skype Server 2015 或更新版本，則您可以使用隨附的 Windows PowerShell 腳本來建立裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="5564f-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="5564f-106">如果您使用的是多目錄林部署，您可以使用對等的 Cmdlet 來產生相同的結果。</span><span class="sxs-lookup"><span data-stu-id="5564f-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="5564f-107">本節將說明這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5564f-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="5564f-108">開始部署 Microsoft 團隊聊天室之前，請確定您具備適當的許可權來執行相關的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5564f-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="5564f-109">請注意，$strExchangeServer 是 Exchange 伺服器的完整功能變數名稱（FQDN），而 $strLyncFQDN 是商務用 Skype Server 部署的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5564f-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="5564f-110">建立會話之後，您可以建立新的信箱並將其設為 RoomMailboxAccount，或變更現有會議室信箱的設定。</span><span class="sxs-lookup"><span data-stu-id="5564f-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="5564f-111">這可讓帳戶針對 Microsoft 團隊聊天室進行驗證。</span><span class="sxs-lookup"><span data-stu-id="5564f-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="5564f-112">如果您要變更現有的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="5564f-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="5564f-113">如果您要建立新的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="5564f-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="5564f-114">您可以在裝置帳戶上設定各種 Exchange 屬性來改善人員的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="5564f-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="5564f-115">您可以在 [Exchange 屬性] 區段中查看需要設定哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="5564f-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="5564f-116">如果您決定將密碼不要到期，您也可以使用 Windows PowerShell Cmdlet 來設定密碼。</span><span class="sxs-lookup"><span data-stu-id="5564f-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="5564f-117">如需詳細資訊，請參閱密碼管理。</span><span class="sxs-lookup"><span data-stu-id="5564f-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="5564f-118">在 Active Directory 中啟用帳戶，以便將其驗證至 Microsoft 團隊聊天室。</span><span class="sxs-lookup"><span data-stu-id="5564f-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="5564f-119">在商務用 Skype 伺服器池中啟用 Microsoft 團隊聊天室 Active Directory 帳戶，以啟用商務用 Skype Server 的裝置帳戶：</span><span class="sxs-lookup"><span data-stu-id="5564f-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="5564f-120">您需要使用會話初始通訊協定（SIP）位址與專案的網網域控制站</span><span class="sxs-lookup"><span data-stu-id="5564f-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="5564f-121">**可選.**</span><span class="sxs-lookup"><span data-stu-id="5564f-121">**Optional.**</span></span> <span data-ttu-id="5564f-122">您也可以透過針對您的帳戶啟用企業語音，來允許 Microsoft 團隊聊天室撥打及接聽公用交換電話網絡（PSTN）電話。</span><span class="sxs-lookup"><span data-stu-id="5564f-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="5564f-123">企業語音並非 Microsoft 團隊聊天室的需求，但如果您想要使用 Microsoft 團隊聊天室用戶端的 PSTN 撥號功能，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5564f-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="5564f-124">同樣地，您必須以您自己的資訊取代所提供的網網域控制站和電話號碼範例。</span><span class="sxs-lookup"><span data-stu-id="5564f-124">Again, you'll need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="5564f-125">參數值 $true 保持不變。</span><span class="sxs-lookup"><span data-stu-id="5564f-125">The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="5564f-126">範例： Exchange 和商務用 Skype Server 內部部署中的房間帳戶設定</span><span class="sxs-lookup"><span data-stu-id="5564f-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="5564f-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="5564f-127">Related topics</span></span>

[<span data-ttu-id="5564f-128">設定 Microsoft 團隊聊天室的帳戶</span><span class="sxs-lookup"><span data-stu-id="5564f-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="5564f-129">規劃 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="5564f-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="5564f-130">部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="5564f-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="5564f-131">設定 Microsoft Teams 會議室主控台</span><span class="sxs-lookup"><span data-stu-id="5564f-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="5564f-132">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="5564f-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
