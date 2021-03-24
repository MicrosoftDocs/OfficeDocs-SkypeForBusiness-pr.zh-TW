---
title: 在 Microsoft 365 和 Office 365 中布建 Skype 室系統帳戶
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 閱讀此主題以瞭解如何在 Microsoft 365 或 Office 365 中布建 Skype 室系統帳戶。
ms.openlocfilehash: 94390effb246a37745d797289c1146ed3d347604
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093517"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="71977-103">在 Microsoft 365 和 Office 365 中布建 Skype 室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="71977-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="71977-104">閱讀此主題以瞭解如何在 Microsoft 365 或 Office 365 中布建 Skype 室系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="71977-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="71977-105">下列章節涵蓋 Skype 會議室系統帳戶布建。</span><span class="sxs-lookup"><span data-stu-id="71977-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="71977-106">Microsoft 365 和 Office 365 必要條件</span><span class="sxs-lookup"><span data-stu-id="71977-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="71977-107">您的線上租使用者必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="71977-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="71977-108">Microsoft 365 或 Office 365 計畫必須包含商務用 Skype Online 方案2或 Office 365 E1，E3 或 E5。</span><span class="sxs-lookup"><span data-stu-id="71977-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="71977-109">如需商務用 Skype Online 方案的詳細資訊，請參閱 [商務用 Skype Online 服務說明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。</span><span class="sxs-lookup"><span data-stu-id="71977-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>
    
- <span data-ttu-id="71977-110">您的租使用者必須已啟用商務用 Skype 的會議功能。</span><span class="sxs-lookup"><span data-stu-id="71977-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="71977-111">您的租使用者必須啟用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="71977-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="71977-112">您的承租人遠端系統管理員必須具備下列 PowerShell 存取權：</span><span class="sxs-lookup"><span data-stu-id="71977-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="71977-113">Exchange 遠端 PowerShell 存取</span><span class="sxs-lookup"><span data-stu-id="71977-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="71977-114">商務用 Skype Online 遠端 PowerShell 存取</span><span class="sxs-lookup"><span data-stu-id="71977-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="71977-115">Windows Azure Active Directory Module for Windows PowerShell，用以存取 Microsoft 365 或 Office 365 目錄存取權</span><span class="sxs-lookup"><span data-stu-id="71977-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="71977-116">若為 Skype 聊天室帳戶，則需要下列授權：</span><span class="sxs-lookup"><span data-stu-id="71977-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="71977-117">需要有商務用 Skype Online 方案2或 Office 365 E1 或 E3 授權，才能啟用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="71977-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="71977-118">若要 entitle 具有 Enterprise Voice 功能的會議室，讓會議室可以使用電話號碼來啟用，則需要使用電話系統許可證或 Office 365 E5 的商務用 Skype Online 方案 2 (1) 。</span><span class="sxs-lookup"><span data-stu-id="71977-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="71977-119">如果您需要來自會議的撥入式功能，您需要音訊會議和電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="71977-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="71977-120">如果您需要從會議撥出的功能，您需要國內或國內和國際通話方案。</span><span class="sxs-lookup"><span data-stu-id="71977-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="71977-121">因為帳戶應該設定為資源信箱帳戶，所以不需要使用 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="71977-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="71977-122">布建概述</span><span class="sxs-lookup"><span data-stu-id="71977-122">Provisioning overview</span></span>

<span data-ttu-id="71977-123">下圖概要說明 Skype 室系統帳戶布建流程。</span><span class="sxs-lookup"><span data-stu-id="71977-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Skype 會議室系統布建步驟](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="71977-125">識別新的會議室</span><span class="sxs-lookup"><span data-stu-id="71977-125">Identify a new conference room</span></span>

<span data-ttu-id="71977-126">在 Exchange 中，您可能已經有可提供排程功能的資源會議室信箱，或者您可能會在第一次協助 Skype 會議室系統部署時建立資源信箱。</span><span class="sxs-lookup"><span data-stu-id="71977-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="71977-127">在任何情況下，您都必須識別要在租使用者中使用的會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="71977-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="71977-128">Exchange Online 布建和商務用 Skype 布建區段提供這兩種帳戶類型的指引。</span><span class="sxs-lookup"><span data-stu-id="71977-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="71977-129">例如，假設您有下列兩個聊天室，而您想要為這兩個聊天室部署 Skype 會議室系統：</span><span class="sxs-lookup"><span data-stu-id="71977-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="71977-130">現有資源信箱帳戶： confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="71977-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="71977-131">新資源信箱帳戶： confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="71977-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="71977-132">Exchange Online 布建</span><span class="sxs-lookup"><span data-stu-id="71977-132">Exchange Online provisioning</span></span>

<span data-ttu-id="71977-133">首先，依照主題的 [連線 [至 Exchange online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)] 主題中的指示，連線至 exchange online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="71977-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
<span data-ttu-id="71977-134">若要為 Skype 室系統設定現有的資源會議室信箱帳戶，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="71977-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="71977-135">若要為 Skype 會議室系統建立新的 Exchange 資源信箱帳戶，請在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="71977-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="71977-136">先前的命令會設定或建立新的 Exchange 資源信箱帳戶，以供啟用該帳戶的 Skype 會議室系統使用。</span><span class="sxs-lookup"><span data-stu-id="71977-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="71977-137">在建立信箱之後，您可以使用 Exchange Online PowerShell 中的 Set-CalendarProcessing Cmdlet 來設定信箱。</span><span class="sxs-lookup"><span data-stu-id="71977-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="71977-138">如需詳細資訊，請參閱單一樹系內部部署的步驟3到6。</span><span class="sxs-lookup"><span data-stu-id="71977-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="71977-139">指派商務用 Skype Online 授權</span><span class="sxs-lookup"><span data-stu-id="71977-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="71977-140">現在您可以指定商務用 Skype Online (Plan 2) 或商務用 Skype Online (Plan 3) 授權365，如 [指派或移除 microsoft 365 for](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) Business 或 [商務用 Skype 附加元件授權](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)中所述。</span><span class="sxs-lookup"><span data-stu-id="71977-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="71977-141">在您指派商務用 Skype Online 的授權後，您就可以使用任何商務用 Skype 用戶端，登入並驗證帳戶是否為作用中。</span><span class="sxs-lookup"><span data-stu-id="71977-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="71977-142">商務用 Skype Online 布建</span><span class="sxs-lookup"><span data-stu-id="71977-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="71977-143">以先前所顯示的方式建立及啟用資源會議室信箱帳戶後，且已授權商務用 Skype Online 帳戶，該帳戶會使用 Windows Azure Active Directory 樹系，從 Exchange Online 樹系同步處理至商務用 Skype Online 樹系。</span><span class="sxs-lookup"><span data-stu-id="71977-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="71977-144">在商務用 Skype Online 集區中布建 Skype 室系統帳戶時，需要進行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="71977-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="71977-145">針對現有資源信箱帳戶或新建立的帳戶 (confrm1 或 confrm2) ，這些步驟都相同，因為在 Exchange Online 中啟用這些帳戶後，這兩個帳戶會以相同方式同步處理至商務用 Skype Online：</span><span class="sxs-lookup"><span data-stu-id="71977-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="71977-146">建立遠端 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="71977-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="71977-147">請注意，您將需要下載 [小組 PowerShell 模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="71977-147">Note that you will need to download [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. <span data-ttu-id="71977-148">若要為商務用 skype 啟用 Skype 會議室系統帳戶，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="71977-148">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="71977-149">您可以使用下列命令來傳回此屬性，以取得商務用 Skype 使用者所在的現有帳戶的 RegistrarPool 位址：</span><span class="sxs-lookup"><span data-stu-id="71977-149">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="71977-150">Skype 室系統帳戶不支援 Multi-Factor 驗證 (MFA) 。</span><span class="sxs-lookup"><span data-stu-id="71977-150">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="71977-151">密碼過期</span><span class="sxs-lookup"><span data-stu-id="71977-151">Password expiration</span></span>

<span data-ttu-id="71977-152">在 Microsoft 365 或 Office 365 中，所有使用者帳戶的預設密碼到期原則都是90天，除非您設定其他密碼到期原則。</span><span class="sxs-lookup"><span data-stu-id="71977-152">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="71977-153">若為 Skype 會議室系統帳戶，您可以使用下列步驟，選取 [密碼永不到期] 設定。</span><span class="sxs-lookup"><span data-stu-id="71977-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="71977-154">使用您的租使用者全域系統管理員認證，建立 Windows Azure Active Directory 會話。</span><span class="sxs-lookup"><span data-stu-id="71977-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="71977-155">使用下列命令，為先前建立的 Skype 聊天室系統房間帳戶設定 [密碼永不到期] 設定：</span><span class="sxs-lookup"><span data-stu-id="71977-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="71977-156">如需詳細資訊，請參閱 [設定您的電腦以進行 Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="71977-156">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="validate"></a><span data-ttu-id="71977-157">驗證</span><span class="sxs-lookup"><span data-stu-id="71977-157">Validate</span></span>

<span data-ttu-id="71977-158">針對驗證，您應該能夠使用任何商務用 Skype 用戶端登入您建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="71977-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>