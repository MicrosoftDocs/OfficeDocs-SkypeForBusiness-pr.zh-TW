---
title: 在商務用 Skype 和 Lync 用戶端使用者介面之間切換
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '瞭解如何在或商務用 Skype使用 PowerShell 在用戶端和 Lync 用戶端使用者介面Microsoft 365 Office 365 '
ms.openlocfilehash: 4fad8e0953e95885e9074d62d8eb0c2a59494976
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239578"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="ca9c5-103">在商務用 Skype 和 Lync 用戶端使用者介面之間切換</span><span class="sxs-lookup"><span data-stu-id="ca9c5-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="ca9c5-104">對於 商務用 Skype Online 組織，您可以使用 Microsoft 365 或 Office 365 中的遠端 PowerShell，讓 商務用 Skype 使用者使用 商務用 Skype 用戶端或 商務用 Skype (Lync) 用戶端使用者介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Microsoft 365 or Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="ca9c5-105">預設設定是讓使用者使用用戶端商務用 Skype介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="ca9c5-106">如果您想要使用 Lync 用戶端體驗，您可以遵循本主題稍後的步驟，管理第一次啟動用戶端行為以顯示 Lync 使用者介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca9c5-107">Lync 2013 用戶端體驗不是適用于 2016 商務用 Skype的選項。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-107">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="ca9c5-108">在嘗試將用戶端環境設定為使用 Lync 2013 用戶端之前，請先檢查用戶端版本，以確保該版本不是從數位 16 開始;例如：16.x.x.x.x。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-108">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="ca9c5-109">如果您想要輕鬆切換使用者介面，但不想執行手動步驟，請參閱 Microsoft 下載中心中的 [PowerShell](https://go.microsoft.com/fwlink/?LinkId=532431) 腳本，以簡化操作。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="ca9c5-110">切換商務用 Skype使用者介面</span><span class="sxs-lookup"><span data-stu-id="ca9c5-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="ca9c5-111">Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-111">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="ca9c5-112">此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell Online 模組商務用 Skype[下載](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-112">This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="ca9c5-113">有關其他資訊，請參閱[為](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)線上管理商務用 Skype電腦。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-113">For other information, see [Configuring your computer for Skype for Business Online management](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ca9c5-114">切換  _使用者_ 介面的全域原則設定不會適用于已採用自訂原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-114">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied.</span></span> <span data-ttu-id="ca9c5-115">若要變更使用者介面，您必須針對已應用自訂原則的每個使用者執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-115">To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="ca9c5-116">_ClientPolicyEnableSkypeUI_ 策略會取代使用者現有的自訂策略設定。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="ca9c5-117">若要讓貴組織中所有使用者使用用戶端商務用 Skype，請開啟遠端 PowerShell 並輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="ca9c5-118">如果您正確設定了該政策，就會看到：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-118">If you set the policy right, you will see:</span></span>
  
![PowerShell：SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="ca9c5-120">若要讓貴組織中所有使用者使用 Lync 商務用 Skype (用戶端) ，請開啟遠端 PowerShell 並輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="ca9c5-121">如果您正確設定了該政策，就會看到：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-121">If you set the policy right, you will see:</span></span>
  
![PowerShell：SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="ca9c5-123">若要允許貴組織的單一使用者使用 商務用 Skype用戶端，請開啟遠端 PowerShell 並輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="ca9c5-124">如果您正確設定了該政策，就會看到：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-124">If you set the policy right, you will see:</span></span>
  
![商務用 Skype線上 - 啟用 UI](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="ca9c5-126">若要允許貴組織的單一使用者使用 Lync 商務用 Skype (用戶端) 遠端 PowerShell，然後輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="ca9c5-127">如果您正確設定了該政策，就會看到：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-127">If you set the policy right, you will see:</span></span>
  
![商務用 Skype線上 - UI 已停用](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="ca9c5-129&quot;>若要允許貴組織中多個使用者使用用戶端商務用 Skype，請開啟遠端 PowerShell 並輸入下列專案：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ca9c5-129&quot;>To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```PowerShell
$users = @(&quot;sip:bob@contoso.com&quot;,&quot;sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="ca9c5-130">若要允許貴組織中多個使用者使用 Lync 商務用 Skype (用戶端) ，請開啟遠端 PowerShell 並輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="ca9c5-131">若要允許貴組織的一組使用者使用 商務用 Skype用戶端，請開啟遠端 PowerShell 並輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="ca9c5-132">若要允許貴組織中一組使用者使用 Lync 商務用 Skype (用戶端) 遠端 PowerShell，然後輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="ca9c5-133">使用者的名稱是應該指派該策略的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-133">The user's name is the name of the user's account that the policy should be assigned to.</span></span> <span data-ttu-id="ca9c5-134">使用者的帳戶名稱可以下列其中一種格式輸入：> 使用者> 使用者主體名稱 (UPN) 使用者> Active Directory 顯示名稱的 \\> SIP 位址</span><span class="sxs-lookup"><span data-stu-id="ca9c5-134">The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="ca9c5-135">使用 Windows PowerShell管理 Lync Online</span><span class="sxs-lookup"><span data-stu-id="ca9c5-135">Using Windows PowerShell to manage Lync Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="ca9c5-136">商務用 Skype線上策略設定</span><span class="sxs-lookup"><span data-stu-id="ca9c5-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="ca9c5-137">下表顯示原則第一次適用于使用者的使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="ca9c5-138">**系統管理策略設定**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-138">**Admin policy setting**</span></span>|<span data-ttu-id="ca9c5-139">**顯示的使用者介面**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ca9c5-140">尚未設定該政策。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-140">The policy isn't set.</span></span> |<span data-ttu-id="ca9c5-141">使用者會繼續使用用戶端商務用 Skype介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-141">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|<span data-ttu-id="ca9c5-142">使用者會繼續使用用戶端商務用 Skype介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-142">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|<span data-ttu-id="ca9c5-143">系統將會要求使用者切換到 Lync 商務用 Skype (用戶端) 介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-143">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="ca9c5-144">他們可以稍後切換。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-144">They can switch later.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|<span data-ttu-id="ca9c5-145">使用者將使用用戶端商務用 Skype介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-145">The user will be using the Skype for Business client user interface.</span></span> |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|<span data-ttu-id="ca9c5-146">系統將會要求使用者切換到 Lync 商務用 Skype (用戶端) 介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="ca9c5-147">系統管理員日後可以變更設定，將其切換至用戶端商務用 Skype介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="ca9c5-148">下表顯示變更策略時的使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="ca9c5-149">**系統管理策略設定**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-149">**Admin policy setting**</span></span>|<span data-ttu-id="ca9c5-150">**商務用 Skype (Lync) 使用者介面**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="ca9c5-151">**商務用 Skype使用者介面**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|<span data-ttu-id="ca9c5-152">系統將會要求使用者切換到用戶端商務用 Skype介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="ca9c5-153">使用者會繼續使用用戶端商務用 Skype介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|<span data-ttu-id="ca9c5-154">使用者會繼續使用 Lync 商務用 Skype () 介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="ca9c5-155">系統將會要求使用者切換到 Lync 商務用 Skype (用戶端) 介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="ca9c5-156">尚未設定該政策。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="ca9c5-157">如果使用者未設定商務用 Skype (，) Lync 或用戶端使用者介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="ca9c5-158">他們一定會使用商務用 Skype使用者介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="ca9c5-159">使用者會繼續使用用戶端商務用 Skype介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="ca9c5-160">此表格顯示所有可用的線上自訂策略。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-160">This table shows all the Online custom policies available.</span></span> <span data-ttu-id="ca9c5-161">已建立新政策，可讓系統管理員在切換 EnableSkypeUI 標標時，保留舊的自訂策略。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-161">There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags.</span></span> <span data-ttu-id="ca9c5-162">請使用上方的 Cmdlet，將下列其中一項政策授予您的使用者。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-162">Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="ca9c5-163">**策略名稱**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-163">**Policy name**</span></span>|<span data-ttu-id="ca9c5-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |<span data-ttu-id="ca9c5-165">假</span><span class="sxs-lookup"><span data-stu-id="ca9c5-165">False</span></span>|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |<span data-ttu-id="ca9c5-166">假</span><span class="sxs-lookup"><span data-stu-id="ca9c5-166">False</span></span>|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |<span data-ttu-id="ca9c5-167">假</span><span class="sxs-lookup"><span data-stu-id="ca9c5-167">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |<span data-ttu-id="ca9c5-168">假</span><span class="sxs-lookup"><span data-stu-id="ca9c5-168">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |<span data-ttu-id="ca9c5-169">假</span><span class="sxs-lookup"><span data-stu-id="ca9c5-169">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|<span data-ttu-id="ca9c5-170">假</span><span class="sxs-lookup"><span data-stu-id="ca9c5-170">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |<span data-ttu-id="ca9c5-171">假</span><span class="sxs-lookup"><span data-stu-id="ca9c5-171">False</span></span>|

   
<span data-ttu-id="ca9c5-172">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="ca9c5-173">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca9c5-173">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="ca9c5-174">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="ca9c5-174">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="ca9c5-175">第一次啟動用戶端行為</span><span class="sxs-lookup"><span data-stu-id="ca9c5-175">First launch client behaviors</span></span>

<span data-ttu-id="ca9c5-176">根據預設，當使用者第一次啟動 商務用 Skype 時，他們一定會看到 商務用 Skype 使用者介面，即使您已選取 Lync 用戶端體驗，將用戶端策略設定為 Lync 用戶端體驗 () 如先前所述。 `Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`</span><span class="sxs-lookup"><span data-stu-id="ca9c5-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="ca9c5-177">幾分鐘之後，系統就會要求使用者切換到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="ca9c5-178">如果您想要在使用者第一次啟動 商務用 Skype用戶端時顯示 Lync 使用者介面，請遵循下列步驟，在用戶端更新後第一次啟動用戶端之前：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="ca9c5-179">請遵循本主題之前的步驟，並確認用戶端策略已設定為停用商務用 Skype介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="ca9c5-180">更新使用者電腦上系統登錄。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-180">Update the system registry on the user's computer.</span></span> <span data-ttu-id="ca9c5-181">您應該在使用者第一次啟動用戶端商務用 Skype之前執行此工作，而且應該只執行一次。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-181">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="ca9c5-182">若要瞭解如何建立群組原則物件以更新網域已加入電腦的註冊表，請參閱本主題稍後的一節。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-182">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="ca9c5-183">在 **[HKEY_CURRENT_USER Microsoft \\ \\ Office \\ \\ Lync]** 金鑰中，建立新的 **二進位** 值。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="ca9c5-184">值 **名稱必須是** **EnableSkypeUI，** 且 **值** 資料必須設為 **00 00 00 00 。**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="ca9c5-185">該金鑰看起來應該如下所示：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="ca9c5-186">[HKEY_CURRENT_USER \\軟體 \\ Microsoft \\ Office \\ Lync]</span><span class="sxs-lookup"><span data-stu-id="ca9c5-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="ca9c5-187">"CanSharePptInCollab"=dword：00000001</span><span class="sxs-lookup"><span data-stu-id="ca9c5-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="ca9c5-188">"CanShareOneNoteInCollab"=dword：00000001</span><span class="sxs-lookup"><span data-stu-id="ca9c5-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="ca9c5-189">"CanAppShareInCollab"=dword：00000001</span><span class="sxs-lookup"><span data-stu-id="ca9c5-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="ca9c5-190">"EnableSkypeUI"=十六進位：00，00，00，00，00</span><span class="sxs-lookup"><span data-stu-id="ca9c5-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="ca9c5-191">當使用者第一次啟動用戶端時，商務用 Skype Lync 使用者介面。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="ca9c5-192">控制歡迎畫面教學課程的顯示</span><span class="sxs-lookup"><span data-stu-id="ca9c5-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="ca9c5-193">當使用者開啟 商務用 Skype用戶端時，預設的行為是顯示歡迎畫面，其中包含大多數使用者要求的 *7* 個快速秘訣。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="ca9c5-194">您可以關閉歡迎畫面的顯示，但仍允許使用者在用戶端電腦上新增下列登錄值來存取教學課程：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="ca9c5-195">在 **[HKEY_CURRENT_USER Microsoft \\ \\ Office \\ \\ 15.0 \\ Lync]** 金鑰中，建立新的 DWORD (**32 位) 值**。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-195">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="ca9c5-196">值 **名稱必須是** **IsBasicTutorialSeenByUser，** 且 **值** 資料必須設為 **1。**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-196">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="ca9c5-197">該金鑰看起來應該如下所示：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-197">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="ca9c5-198">關閉用戶端教學課程</span><span class="sxs-lookup"><span data-stu-id="ca9c5-198">Turn off the client tutorial</span></span>

<span data-ttu-id="ca9c5-199">如果您不希望使用者能夠存取教學課程，您可以使用下列登錄值關閉用戶端教學課程：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="ca9c5-200">在 **[HKEY_CURRENT_USER Microsoft \\ \\ Office \\ \\ 15.0 \\ Lync]** 金鑰中，建立新的 DWORD (**32 位) 值**。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-200">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="ca9c5-201">值 **名稱必須是** **TutorialFeatureEnabled，** 且 **值資料** 必須設為 **0。**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-201">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="ca9c5-202">您可以將值資料設定為 **1，** 以重新 **開啟** 教學課程。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="ca9c5-203">建立群組原則物件以修改已加入網域電腦的註冊表</span><span class="sxs-lookup"><span data-stu-id="ca9c5-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="ca9c5-204">使用者第一次啟動 Lync 用戶端體驗的登錄更新商務用 Skype用戶端應該只完成一次。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-204">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="ca9c5-205">如果您使用群組原則物件 (GPO) 更新註冊表，您必須定義物件以建立新值，而不是更新值資料。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-205">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="ca9c5-206">套用 GPO 時，如果新值不存在，GPO 會建立它，並設定值資料為 0。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-206">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="ca9c5-207">下列程式說明如何修改登錄，讓使用者第一次啟動登錄時顯示 Lync 用戶端商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-207">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="ca9c5-208">您也可以使用這個程式來更新註冊表，以停用歡迎畫面教學課程，如先前所述。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-208">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="ca9c5-209">**建立 GPO**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="ca9c5-210">啟動 **群組原則管理主控台**。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="ca9c5-211">若要瞭解如何使用群組原則管理主控台，請參閱 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).</span></span>
    
2. <span data-ttu-id="ca9c5-212">以滑鼠右鍵按一下 **群組原則物件\*\*\*\*節點，然後** 選取功能表上的 [新增。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="ca9c5-213">在 [ **新增 GPO>** 對話方塊中，輸入 GPO 的名稱，例如 MakeLyncDefaultUI，然後按一下 **[確定**。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="ca9c5-214">以滑鼠右鍵按一下您剛剛建立的新 GPO，然後從 **功能表** 選取 [編輯。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="ca9c5-215">在組 **策略管理編輯器** 中，展開 **使用者設定**、展開喜好設定、展開 **Windows 設定，然後** 選取 **登錄節點**。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="ca9c5-216">以滑鼠右鍵按一下 **[註冊表>** 節點，然後選取 **[**  >  **新增登錄機碼目**> 。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="ca9c5-217">在 [ **新增註冊表屬性>** 對話方塊中，更新下列專案：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="ca9c5-218">**領域**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-218">**Field**</span></span>|<span data-ttu-id="ca9c5-219">**要選取或輸入的值**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ca9c5-220">**動作**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-220">**Action**</span></span> <br/> |<span data-ttu-id="ca9c5-221">**創建**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-221">**Create**</span></span> <br/> |
|<span data-ttu-id="ca9c5-222">**蜂巢**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-222">**Hive**</span></span> <br/> | <span data-ttu-id="ca9c5-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="ca9c5-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="ca9c5-224">**金鑰路徑**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-224">**Key Path**</span></span> <br/> |<span data-ttu-id="ca9c5-225">軟體 \\ Microsoft \\ Office \\ Lync</span><span class="sxs-lookup"><span data-stu-id="ca9c5-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="ca9c5-226">**值名稱**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-226">**Value name**</span></span> <br/> |<span data-ttu-id="ca9c5-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="ca9c5-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="ca9c5-228">**數值型別**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-228">**Value type**</span></span> <br/> |<span data-ttu-id="ca9c5-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="ca9c5-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="ca9c5-230">**值資料**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-230">**Value data**</span></span> <br/> |<span data-ttu-id="ca9c5-231">00000000</span><span class="sxs-lookup"><span data-stu-id="ca9c5-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="ca9c5-232">按一下 **[確定** 以儲存您的變更，然後關閉 GPO。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="ca9c5-233">接下來，您必須將您建立 GPO 連結至要指派策略的使用者群組，例如 OU。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="ca9c5-234">**若要使用 GPO 指派策略**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="ca9c5-235">在群組原則管理主控台中，以滑鼠右鍵按一下要指派該策略的 OU，然後選取 [連結 **至現有的 GPO。**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="ca9c5-236">在 [ **選取 GPO」** 對話方塊中，選取您建立 GPO，然後選取 [ **確定**。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="ca9c5-237">在目標使用者的電腦上，開啟命令提示，然後輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="ca9c5-238">**gpupdate /target：user**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="ca9c5-239">訊息「正在更新策略...」。會以 GPO 的適用方式顯示。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-239">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="ca9c5-240">完成後，系統會顯示「使用者策略更新已完成」訊息。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-240">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="ca9c5-241">在命令提示符中，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="ca9c5-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="ca9c5-242">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="ca9c5-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="ca9c5-243">您應該會看到下方顯示「已指派的群組原則物件」，並顯示您建立 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="ca9c5-244">您也可以檢查登錄，確認 GPO 已成功更新使用者電腦上登錄。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-244">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="ca9c5-245">開啟 [登錄編輯程式]，然後流覽至 **[HKEY_CURRENT_USER \\ \\ Microsoft \\ Office \\ Lync]** 鍵。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-245">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key.</span></span> <span data-ttu-id="ca9c5-246">如果 GPO 成功更新登錄，會看到名為 EnableSkypeUI 的值，值為 0。</span><span class="sxs-lookup"><span data-stu-id="ca9c5-246">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ca9c5-247">相關主題</span><span class="sxs-lookup"><span data-stu-id="ca9c5-247">Related topics</span></span>
[<span data-ttu-id="ca9c5-248">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="ca9c5-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="ca9c5-249">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="ca9c5-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
