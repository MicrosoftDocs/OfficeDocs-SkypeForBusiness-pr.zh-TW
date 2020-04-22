---
title: 在 Office 365 語音信箱中為使用者啟用企業語音線上和電話系統
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
description: 瞭解如何在 Office 365 語音服務中為您的商務用 Skype 使用者啟用電話系統。
ms.openlocfilehash: 8ed04e3926adfecb2f0022d12c783f6c3e83d763
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780722"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="a9010-103">在 Office 365 語音信箱中為使用者啟用企業語音線上和電話系統</span><span class="sxs-lookup"><span data-stu-id="a9010-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="a9010-104">瞭解如何在 Office 365 語音服務中為您的商務用 Skype 使用者啟用電話系統。</span><span class="sxs-lookup"><span data-stu-id="a9010-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="a9010-105">在 Office 365 中使用內部部署 PSTN 連線部署電話系統的最後一個步驟，就是讓您的使用者能夠在 Office 365 和語音信箱中使用電話系統。</span><span class="sxs-lookup"><span data-stu-id="a9010-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="a9010-106">若要啟用這些功能，您必須是具有全域系統管理員角色的使用者，而且能夠執行遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a9010-106">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="a9010-107">您必須針對尚未啟用商務用 Skype Online 的 Enterprise Voice 的所有使用者帳戶，遵循此主題中的步驟。</span><span class="sxs-lookup"><span data-stu-id="a9010-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="a9010-108">在 Office 365 語音服務中啟用電話系統</span><span class="sxs-lookup"><span data-stu-id="a9010-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="a9010-109">若要讓使用者在 Office 365 語音及語音信箱中啟用電話系統，您必須執行一些初始步驟，例如檢查您的伺服器上是否已部署商務用 Skype Online 連接器，以及是否允許使用者裝載語音信箱。</span><span class="sxs-lookup"><span data-stu-id="a9010-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="a9010-110">在 Office 365 語音及語音信箱中為您的使用者啟用電話系統</span><span class="sxs-lookup"><span data-stu-id="a9010-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="a9010-111">開始之前，請先檢查您的前端伺服器上是否已部署商務用 Skype Online 連接器（Windows PowerShell 模組）。</span><span class="sxs-lookup"><span data-stu-id="a9010-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="a9010-112">如果不是，您可以從[[下載中心](https://www.microsoft.com/download/details.aspx?id=39366)] 下載。</span><span class="sxs-lookup"><span data-stu-id="a9010-112">If it's not, you can download it from [the download center](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="a9010-113">您可以在設定[您的電腦以進行商務用 Skype Online 管理](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx)時，找到使用此模組的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a9010-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="a9010-114">以系統管理員身分啟動 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a9010-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="a9010-115">輸入下列專案，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="a9010-115">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="a9010-116">輸入下列專案，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="a9010-116">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="a9010-117">按 Enter 後，您應該會看到 [Windows PowerShell 認證] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="a9010-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="a9010-118">輸入您的租使用者管理員使用者名稱和密碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a9010-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="a9010-119">在 [PowerShell] 視窗中，輸入下列專案，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="a9010-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="a9010-120">輸入下列 Cmdlet 以匯入會話：</span><span class="sxs-lookup"><span data-stu-id="a9010-120">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="a9010-121">在商務用 Skype 伺服器上執行 PowerShell 時，當您開啟 PowerShell 時，已載入本機商務用 Skype Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9010-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="a9010-122">您必須指定-AllowClobber 參數以允許線上 Cmdlet 覆寫具有相同名稱的內部部署 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9010-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="a9010-123">使用 Set-CsUser Cmdlet，將 $EnterpriseVoiceEnabled 和 $HostedVoiceMail 屬性指派給您的使用者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a9010-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="a9010-124">例如：</span><span class="sxs-lookup"><span data-stu-id="a9010-124">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="a9010-125">您也可以指定使用者的 SIP 位址、使用者主體名稱（UPN）、功能變數名稱和使用者名稱（網域 \ 使用者名稱），以及 Active Directory 中的顯示名稱（「Bob 凱利」）。</span><span class="sxs-lookup"><span data-stu-id="a9010-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="a9010-126">針對 Office 365 中已啟用電話系統的使用者更新行 URI 和撥號對應表</span><span class="sxs-lookup"><span data-stu-id="a9010-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="a9010-127">本節說明如何針對 Office 365 中已啟用電話系統的使用者，更新行 URI 和撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="a9010-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="a9010-128">更新行 URI</span><span class="sxs-lookup"><span data-stu-id="a9010-128">To update the Line URI</span></span>

1. <span data-ttu-id="a9010-129">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="a9010-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a9010-130">使用「開始」功能表或桌面快捷方式，開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a9010-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a9010-131">您也可以開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a9010-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="a9010-132">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="a9010-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a9010-133">在 [**搜尋使用者**] 方塊中，輸入您要啟用之使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員（SAM）帳戶名稱、SIP 位址或線路統一資源識別元（URI）的全部或第一部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a9010-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="a9010-134">在表格中，按一下您要變更行 URI 的商務用 Skype 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a9010-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="a9010-135">按一下 [**行 URI**]，然後輸入唯一的標準化電話號碼（例如電話： + 14255550200）。</span><span class="sxs-lookup"><span data-stu-id="a9010-135">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="a9010-136">然後按一下 [**認可**]。</span><span class="sxs-lookup"><span data-stu-id="a9010-136">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="a9010-137">使用內部部署 Windows PowerShell Cmdlet 更新撥號對應表</span><span class="sxs-lookup"><span data-stu-id="a9010-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a9010-138">您可以將每一使用者撥號對應表指派給 Windows PowerShell 和[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9010-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="a9010-139">您可以從商務用 Skype Server 2015 或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a9010-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="a9010-140">將每一使用者撥號對應表指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="a9010-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="a9010-141">使用[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)指令程式，將個別使用者撥號對應表 RedmondDialPlan 指派給使用者 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="a9010-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="a9010-142">將每一使用者撥號對應表指派給多位使用者</span><span class="sxs-lookup"><span data-stu-id="a9010-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="a9010-143">下列命令會將每位使用者的撥號對應表 RedmondDialPlan 指派給 Redmond 的城市中所有工作的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9010-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="a9010-144">如需此命令中所使用之 LdapFilter 參數的詳細資訊，請參閱[Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) Cmdlet 的檔：</span><span class="sxs-lookup"><span data-stu-id="a9010-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="a9010-145">您可以針對線上使用者使用通用或使用者撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="a9010-145">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="a9010-146">無法使用網站撥號對應表，只適用于裝載內部部署並指派給內部部署網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9010-146">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="a9010-147">取消指派個別使用者撥號對應表</span><span class="sxs-lookup"><span data-stu-id="a9010-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="a9010-148">使用[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet 取消指派先前指派給 Ken Myer 的任何個別使用者撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="a9010-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="a9010-149">未指派每個使用者的撥號對應表後，Ken Myer 將會透過使用全域撥號對應表或指派給其註冊機構或 PSTN 閘道的服務範圍撥號對應表，來進行管理。</span><span class="sxs-lookup"><span data-stu-id="a9010-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="a9010-150">服務範圍撥號對應表優先于全域撥號對應表：</span><span class="sxs-lookup"><span data-stu-id="a9010-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="a9010-151">使用內部部署 Windows PowerShell Cmdlet 更新語音路由原則</span><span class="sxs-lookup"><span data-stu-id="a9010-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a9010-152">本節說明如何為 Office 365 中啟用電話系統的使用者更新語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="a9010-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="a9010-153">Office 365 中的電話系統使用者必須將語音路由原則指派給他們，來電才能成功路由傳送。</span><span class="sxs-lookup"><span data-stu-id="a9010-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="a9010-154">這與需要將語音原則指派給他們以允許通話成功路由的內部部署商務語音使用者不同。</span><span class="sxs-lookup"><span data-stu-id="a9010-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="a9010-155">語音路由原則應包含 PSTN 使用方式，以定義 Office 365 使用者中的電話系統的授權呼叫和路由。</span><span class="sxs-lookup"><span data-stu-id="a9010-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="a9010-156">您可以將這些 PSTN 使用方式從現有的語音原則複製到新的語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="a9010-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="a9010-157">如需詳細資訊，請參閱[New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a9010-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9010-158">Office 365 使用者中的所有電話系統都被指派了名為 BusinessVoice 的相同線上語音原則，以定義允許的呼叫功能;例如，允許同時振鈴。</span><span class="sxs-lookup"><span data-stu-id="a9010-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="a9010-159">將每一使用者的語音路由原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="a9010-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="a9010-160">使用[Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)指令程式將每位使用者的語音路由原則 RedmondVoiceRoutingPolicy 指派給使用者 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="a9010-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="a9010-161">將每一使用者的語音路由原則指派給多位使用者</span><span class="sxs-lookup"><span data-stu-id="a9010-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="a9010-162">下一個命令會將每位使用者的語音路由原則 RedmondVoiceRoutingPolicy 指派給在 Redmond 的城市中工作的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a9010-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="a9010-163">如需此命令中所用 LdapFilter 參數的詳細資訊，請參閱[Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a9010-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="a9010-164">您可以針對線上使用者使用通用或使用者語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="a9010-164">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="a9010-165">無法使用網站語音路由策略，因為這些原則只適用于內部部署所主控且指派給內部部署網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9010-165">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="a9010-166">取消指派個別使用者的語音路由原則</span><span class="sxs-lookup"><span data-stu-id="a9010-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="a9010-167">使用 Grant-CsVoiceRoutingPolicy 取消指派先前指派給 Ken Myer 的任何個別使用者語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="a9010-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="a9010-168">未指派每位使用者的語音路由原則之後，將會使用通用語音路由原則來管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="a9010-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="a9010-169">如需詳細資訊，請參閱[Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a9010-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

