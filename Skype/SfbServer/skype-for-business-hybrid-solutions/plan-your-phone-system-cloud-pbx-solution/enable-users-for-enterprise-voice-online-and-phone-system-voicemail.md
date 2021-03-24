---
title: 為使用者啟用企業語音線上版和電話系統語音信箱
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: 瞭解如何為商務用 Skype 使用者啟用電話系統語音服務。
ms.openlocfilehash: f1c59505073a7113407f28b7ebbe3a323724782e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098569"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="30d61-103">為使用者啟用企業語音線上版和電話系統語音信箱</span><span class="sxs-lookup"><span data-stu-id="30d61-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="30d61-104">在2021年7月31日之後，商務用 Skype Online 將會停用，在此之後將無法再存取服務。</span><span class="sxs-lookup"><span data-stu-id="30d61-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="30d61-105">此外，您的內部部署環境之間的 PSTN 連線，不論是透過商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype Online，都將不再支援。</span><span class="sxs-lookup"><span data-stu-id="30d61-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="30d61-106">瞭解如何使用 [直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="30d61-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="30d61-107">瞭解如何為商務用 Skype 使用者啟用電話系統語音服務。</span><span class="sxs-lookup"><span data-stu-id="30d61-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="30d61-108">使用內部部署 PSTN 連線部署電話系統的最後一個步驟，就是讓您的使用者能夠使用電話系統及語音信箱。</span><span class="sxs-lookup"><span data-stu-id="30d61-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="30d61-109">若要啟用這些功能，您必須是具有全域系統管理員角色的使用者，而且能夠執行遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="30d61-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="30d61-110">您必須針對尚未啟用商務用 Skype Online 的 Enterprise Voice 的所有使用者帳戶，遵循此主題中的步驟。</span><span class="sxs-lookup"><span data-stu-id="30d61-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="30d61-111">啟用電話系統語音服務</span><span class="sxs-lookup"><span data-stu-id="30d61-111">Enable Phone System voice services</span></span>

<span data-ttu-id="30d61-112">若要讓使用者能夠使用電話語音及語音信箱，您必須執行一些初始步驟，例如檢查您的伺服器上是否已部署商務用 Skype Online 連接器，以及是否允許您的使用者主控語音信箱。</span><span class="sxs-lookup"><span data-stu-id="30d61-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="30d61-113">為使用者啟用電話系統語音和語音信箱</span><span class="sxs-lookup"><span data-stu-id="30d61-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="30d61-114">商務用 Skype Online 連接器目前是最新小組 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="30d61-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="30d61-115">如果您使用的是最新的 [小組 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，您不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="30d61-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="30d61-116">開始之前，請先檢查小組 PowerShell 模組是否已安裝在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="30d61-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="30d61-117">如果不是，請使用 [團隊 PowerShell 模組安裝](/microsoftteams/teams-powershell-install)中的指示進行安裝。</span><span class="sxs-lookup"><span data-stu-id="30d61-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="30d61-118">以系統管理員身分啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="30d61-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="30d61-119">輸入下列專案，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="30d61-119">Type the following and press Enter:</span></span>
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. <span data-ttu-id="30d61-120">使用 Set-CsUser Cmdlet，將 $EnterpriseVoiceEnabled 和 $HostedVoiceMail 屬性指派給您的使用者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="30d61-120">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="30d61-121">例如：</span><span class="sxs-lookup"><span data-stu-id="30d61-121">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="30d61-122">您也可以使用使用者的 SIP 位址、使用者主體名稱 (UPN) 、功能變數名稱和使用者名稱 (網域 \ 使用者名稱) 及 Active Directory 中的顯示名稱來指定使用者。 ( 「Bob 凱利」 ) 。</span><span class="sxs-lookup"><span data-stu-id="30d61-122">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="30d61-123">更新啟用電話系統之使用者的行 URI 和撥號對應表</span><span class="sxs-lookup"><span data-stu-id="30d61-123">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="30d61-124">本節說明如何更新啟用電話系統之使用者的行 URI 和撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="30d61-124">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="30d61-125">更新行 URI</span><span class="sxs-lookup"><span data-stu-id="30d61-125">To update the Line URI</span></span>

1. <span data-ttu-id="30d61-126">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="30d61-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="30d61-127">使用「開始」功能表或桌面快捷方式，開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="30d61-127">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="30d61-128">您也可以開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="30d61-128">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="30d61-129">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="30d61-129">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="30d61-130">在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="30d61-130">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="30d61-131">在表格中，按一下您要變更行 URI 的商務用 Skype 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="30d61-131">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="30d61-132">按一下 [ **行 URI**]，然後輸入唯一的標準化電話號碼 (例如電話： + 14255550200) 。</span><span class="sxs-lookup"><span data-stu-id="30d61-132">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="30d61-133">然後按一下 [ **認可**]。</span><span class="sxs-lookup"><span data-stu-id="30d61-133">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="30d61-134">使用內部部署 Windows PowerShell Cmdlet 更新撥號對應表</span><span class="sxs-lookup"><span data-stu-id="30d61-134">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="30d61-135">您可以將每一使用者撥號對應表指派給 Windows PowerShell 和 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="30d61-135">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="30d61-136">您可以從商務用 Skype Server 2015 或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="30d61-136">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="30d61-137">將每一使用者撥號對應表指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="30d61-137">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="30d61-138">使用 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) 指令程式，將個別使用者撥號對應表 RedmondDialPlan 指派給使用者 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="30d61-138">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="30d61-139">將每一使用者撥號對應表指派給多位使用者</span><span class="sxs-lookup"><span data-stu-id="30d61-139">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="30d61-140">下列命令會將每位使用者的撥號對應表 RedmondDialPlan 指派給 Redmond 的城市中所有工作的使用者。</span><span class="sxs-lookup"><span data-stu-id="30d61-140">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="30d61-141">如需此命令中所使用之 LdapFilter 參數的詳細資訊，請參閱 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) Cmdlet 的檔：</span><span class="sxs-lookup"><span data-stu-id="30d61-141">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="30d61-142">您可以針對線上使用者使用通用或使用者撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="30d61-142">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="30d61-143">無法使用網站撥號對應表，只適用于裝載內部部署並指派給內部部署網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="30d61-143">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="30d61-144">取消指派個別使用者撥號對應表</span><span class="sxs-lookup"><span data-stu-id="30d61-144">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="30d61-145">使用 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet 取消指派先前指派給 Ken Myer 的任何個別使用者撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="30d61-145">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="30d61-146">未指派每個使用者的撥號對應表後，Ken Myer 將會透過使用全域撥號對應表或指派給其註冊機構或 PSTN 閘道的服務範圍撥號對應表，來進行管理。</span><span class="sxs-lookup"><span data-stu-id="30d61-146">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="30d61-147">服務範圍撥號對應表優先于全域撥號對應表：</span><span class="sxs-lookup"><span data-stu-id="30d61-147">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="30d61-148">使用內部部署 Windows PowerShell Cmdlet 更新語音路由原則</span><span class="sxs-lookup"><span data-stu-id="30d61-148">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="30d61-149">本節說明如何更新啟用電話系統之使用者的語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="30d61-149">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="30d61-150">電話系統使用者必須具有指派給他們的語音路由原則，來電才能成功路由傳送。</span><span class="sxs-lookup"><span data-stu-id="30d61-150">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="30d61-151">這與需要將語音原則指派給他們以允許通話成功路由的內部部署商務語音使用者不同。</span><span class="sxs-lookup"><span data-stu-id="30d61-151">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="30d61-152">語音路由原則應包含 PSTN 使用方式，以定義電話系統使用者的授權呼叫和路由。</span><span class="sxs-lookup"><span data-stu-id="30d61-152">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="30d61-153">您可以將這些 PSTN 使用方式從現有的語音原則複製到新的語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="30d61-153">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="30d61-154">如需詳細資訊，請參閱 [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="30d61-154">For more information, see [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="30d61-155">所有電話系統使用者都被指派了名為 BusinessVoice 的相同線上語音原則，用來定義允許的呼叫功能;例如，允許同時振鈴。</span><span class="sxs-lookup"><span data-stu-id="30d61-155">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="30d61-156">將每一使用者的語音路由原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="30d61-156">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="30d61-157">使用 [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) 指令程式將每位使用者的語音路由原則 RedmondVoiceRoutingPolicy 指派給使用者 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="30d61-157">Use the [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="30d61-158">將每一使用者的語音路由原則指派給多位使用者</span><span class="sxs-lookup"><span data-stu-id="30d61-158">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="30d61-159">下一個命令會將每位使用者的語音路由原則 RedmondVoiceRoutingPolicy 指派給在 Redmond 的城市中工作的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="30d61-159">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="30d61-160">如需此命令中所用 LdapFilter 參數的詳細資訊，請參閱 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="30d61-160">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="30d61-161">您可以針對線上使用者使用通用或使用者語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="30d61-161">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="30d61-162">無法使用網站語音路由策略，因為這些原則只適用于內部部署所主控且指派給內部部署網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="30d61-162">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="30d61-163">取消指派個別使用者的語音路由原則</span><span class="sxs-lookup"><span data-stu-id="30d61-163">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="30d61-164">使用 Grant-CsVoiceRoutingPolicy 取消指派先前指派給 Ken Myer 的任何個別使用者語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="30d61-164">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="30d61-165">未指派每位使用者的語音路由原則之後，將會使用通用語音路由原則來管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="30d61-165">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="30d61-166">如需詳細資訊，請參閱 [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="30d61-166">For more information, see [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
