---
title: 在 Office 365 中預配 Skype 會議室系統帳戶
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 請閱讀本主題，以瞭解如何在 Office 365 中預配 Skype 室系統帳戶。
ms.openlocfilehash: d247983647641c91376c99bed3a13606027a7e11
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775387"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="89496-103">在 Office 365 中預配 Skype 會議室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="89496-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="89496-104">請閱讀本主題，以瞭解如何在 Office 365 中預配 Skype 室系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="89496-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="89496-105">下節涵蓋 Office 365 租使用者的 Skype 會議室系統帳戶配置。</span><span class="sxs-lookup"><span data-stu-id="89496-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="89496-106">Office 365 先決條件</span><span class="sxs-lookup"><span data-stu-id="89496-106">Office 365 prerequisites</span></span>

<span data-ttu-id="89496-107">您的線上租使用者必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="89496-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="89496-108">Office 365 方案必須包含商務用 Skype Online 方案2，或 Office 365 E1、E3 或 E5。</span><span class="sxs-lookup"><span data-stu-id="89496-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="89496-109">如需商務用 Skype Online 方案的詳細資料，請參閱[商務用 Skype Online 服務說明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="89496-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="89496-110">您的租使用者必須具備啟用商務用 Skype 的會議功能。</span><span class="sxs-lookup"><span data-stu-id="89496-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="89496-111">您的租使用者必須啟用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="89496-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="89496-112">您的租使用者遠端系統管理員必須具備下列 PowerShell 存取權：</span><span class="sxs-lookup"><span data-stu-id="89496-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="89496-113">Exchange 遠端 PowerShell 存取</span><span class="sxs-lookup"><span data-stu-id="89496-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="89496-114">商務用 Skype Online 遠端 PowerShell 存取</span><span class="sxs-lookup"><span data-stu-id="89496-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="89496-115">適用于 Windows PowerShell 的 windows Azure Active Directory 模組以存取 Office 365 目錄存取權</span><span class="sxs-lookup"><span data-stu-id="89496-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="89496-116">若是 Skype 室帳戶，則需要下列授權：</span><span class="sxs-lookup"><span data-stu-id="89496-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="89496-117">需要商務用 Skype Online 方案2或 Office 365 E1 或 E3 授權，才能啟用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="89496-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="89496-118">若要使用企業語音功能 entitle 會議室，讓會議室可以使用電話號碼來啟用，必須有手機系統授權或 Office 365 E5 的商務用 Skype Online 方案2（1）。</span><span class="sxs-lookup"><span data-stu-id="89496-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="89496-119">如果您需要來自會議的撥入功能，您將需要音訊會議和電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="89496-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="89496-120">如果您需要來自會議的撥出功能，您需要國內或國內和國際通話方案。</span><span class="sxs-lookup"><span data-stu-id="89496-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="89496-121">Skype 室帳戶不需要 Exchange Online 授權，因為應該將帳戶設定為資源信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="89496-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="89496-122">提供概覽</span><span class="sxs-lookup"><span data-stu-id="89496-122">Provisioning overview</span></span>

<span data-ttu-id="89496-123">下圖提供 Office 365 中 Skype 室系統帳戶置備流程的概覽。</span><span class="sxs-lookup"><span data-stu-id="89496-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 版 Skype 會議室系統的提供步驟](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="89496-125">找出新的會議室</span><span class="sxs-lookup"><span data-stu-id="89496-125">Identify a new conference room</span></span>

<span data-ttu-id="89496-126">您可能已經在 Exchange 中有一個資源室信箱提供排程功能，或者您可能會在第一次建立資源信箱來協助 Skype 室系統部署。</span><span class="sxs-lookup"><span data-stu-id="89496-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="89496-127">在任何情況下，您都必須找出要在租使用者中使用的聊天室帳戶。</span><span class="sxs-lookup"><span data-stu-id="89496-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="89496-128">Exchange Online 的 [設定] 和 [商務用 Skype] 設定區段提供這兩種帳戶的指導方針。</span><span class="sxs-lookup"><span data-stu-id="89496-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="89496-129">例如，假設您有下列兩個房間，而您想要為兩者部署 Skype 室系統：</span><span class="sxs-lookup"><span data-stu-id="89496-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="89496-130">現有的資源信箱帳戶： confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="89496-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="89496-131">新的資源信箱帳戶： confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="89496-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="89496-132">Exchange Online 配</span><span class="sxs-lookup"><span data-stu-id="89496-132">Exchange Online provisioning</span></span>

<span data-ttu-id="89496-133">首先，請依照主題中的[[連線至 Exchange Online Powershell]](https://go.microsoft.com/fwlink/p/?LinkId=396554)中的指示，連線至 Exchange online powershell。</span><span class="sxs-lookup"><span data-stu-id="89496-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="89496-134">若要為 Skype 會議室系統設定現有的資源會議室信箱帳戶，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="89496-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="89496-135">若要為 Skype 會議室系統建立新的 Exchange 資源信箱帳戶，請在 Exchange Online PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="89496-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="89496-136">先前的命令會啟用帳戶，為 Skype 室系統使用量設定或建立新的 Exchange 資源信箱帳戶。</span><span class="sxs-lookup"><span data-stu-id="89496-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="89496-137">建立信箱之後，您可以在 Exchange Online PowerShell 中使用 CalendarProcessing Cmdlet 來設定信箱。</span><span class="sxs-lookup"><span data-stu-id="89496-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="89496-138">如需詳細資訊，請參閱單一目錄林內部部署的步驟3到6</span><span class="sxs-lookup"><span data-stu-id="89496-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="89496-139">指派商務用 Skype Online 授權</span><span class="sxs-lookup"><span data-stu-id="89496-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="89496-140">現在，您可以使用 Office 365 管理入口網站（如[指派或移除商務用 office 365](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)或[商務用 Skype 附加元件的授權）來指派或移除商務用 Skype online （方案2）或商務用 Skype online （方案3）授權。授權](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。</span><span class="sxs-lookup"><span data-stu-id="89496-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="89496-141">在您指派商務用 Skype Online 的授權之後，您就可以登入並驗證該帳戶是使用任何商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="89496-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="89496-142">商務用 Skype Online 的提供</span><span class="sxs-lookup"><span data-stu-id="89496-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="89496-143">如先前所示建立並啟用資源室信箱帳戶之後，且您已取得商務用 Skype Online 帳戶的授權，帳戶將會從 Exchange Online 林同步處理到商務用 Skype Online 樹林，方法是使用Windows Azure Active Directory 林。</span><span class="sxs-lookup"><span data-stu-id="89496-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="89496-144">若要在商務用 Skype Online 池中預配 Skype 室系統帳戶，必須執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="89496-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="89496-145">針對現有的資源信箱帳戶或新建立的帳戶（confrm1 或 confrm2），這些步驟都是相同的，因為 Exchange Online 中啟用這兩個帳戶後，就能以同樣的方式同步處理到商務用 Skype Online：</span><span class="sxs-lookup"><span data-stu-id="89496-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="89496-146">建立遠端 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="89496-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="89496-147">請注意，您需要下載商務用 Skype Online 連接器模組與 Microsoft Online Services 登入小幫手，並確認您的電腦已設定。</span><span class="sxs-lookup"><span data-stu-id="89496-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="89496-148">如需詳細資訊，請參閱[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="89496-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="89496-149">若要啟用商務用 Skype 的 Skype 會議室系統帳戶，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="89496-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="89496-150">您可以使用下列命令來傳回這個屬性，以取得商務用 Skype 使用者從您現有的帳戶中駐留的 RegistrarPool 位址：</span><span class="sxs-lookup"><span data-stu-id="89496-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="89496-151">密碼到期日</span><span class="sxs-lookup"><span data-stu-id="89496-151">Password expiration</span></span>

<span data-ttu-id="89496-152">在 Office 365 中，除非您設定不同的密碼過期原則，否則所有使用者帳戶的預設密碼過期原則都會是90天。</span><span class="sxs-lookup"><span data-stu-id="89496-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="89496-153">若是 Skype 室系統帳戶，您可以使用下列步驟選取 [密碼永不過期] 設定。</span><span class="sxs-lookup"><span data-stu-id="89496-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="89496-154">使用您的租使用者全域系統管理員認證建立 Windows Azure Active Directory 會話。</span><span class="sxs-lookup"><span data-stu-id="89496-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="89496-155">針對先前使用下列命令建立的 Skype 會議室系統房間帳戶，設定 [密碼永不過期] 設定：</span><span class="sxs-lookup"><span data-stu-id="89496-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="89496-156">如需詳細資訊，請參閱[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="89496-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="89496-157">核實</span><span class="sxs-lookup"><span data-stu-id="89496-157">Validate</span></span>

<span data-ttu-id="89496-158">針對驗證，您應該能夠使用任何商務用 Skype 用戶端登入您所建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="89496-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

