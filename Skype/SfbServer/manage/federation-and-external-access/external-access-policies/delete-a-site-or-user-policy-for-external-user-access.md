---
title: 刪除外部使用者存取的網站或使用者原則
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以刪除 skype for Business Server Control Panel 列在 [外部存取原則] 頁面上任何網站或使用者原則。
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041232"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="13cb5-103">刪除外部使用者存取的網站或使用者原則</span><span class="sxs-lookup"><span data-stu-id="13cb5-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="13cb5-104">如果您已建立或設定不想再使用的外部使用者存取原則，則可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="13cb5-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="13cb5-105">刪除任何已建立的網站或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="13cb5-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="13cb5-p101">將全域原則重設為預設設定。預設全域原則設定拒絕任何外部使用者存取。全域原則無法刪除。</span><span class="sxs-lookup"><span data-stu-id="13cb5-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="13cb5-109">您可以刪除 skype for Business Server Control Panel 列在 [**外部存取原則**] 頁面上任何網站或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="13cb5-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="13cb5-110">刪除全域原則並不是實際加以刪除，只是將它重設為不支援任何外部使用者存取選項的預設設定。</span><span class="sxs-lookup"><span data-stu-id="13cb5-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="13cb5-111">如需重設全域原則的詳細資訊，請參閱[重設外部使用者存取的全域原則](reset-the-global-policy-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="13cb5-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="13cb5-112">刪除外部使用者存取的網站或使用者原則</span><span class="sxs-lookup"><span data-stu-id="13cb5-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="13cb5-113">從使用者帳戶是 RTCUniversalServerAdmins 群組成員 （或具有相等使用者權限），或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="13cb5-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13cb5-114">開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Skype for Business Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="13cb5-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="13cb5-115">按一下 **[外部使用者存取]**，並按一下 **[外部存取原則]**。</span><span class="sxs-lookup"><span data-stu-id="13cb5-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="13cb5-116">在 **[外部存取原則]** 索引標籤上，按一下想要刪除的網站或使用者原則，並按一下 **[編輯]**，然後按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="13cb5-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="13cb5-117">系統提示確認刪除時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="13cb5-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="13cb5-118">使用 Windows PowerShell Cmdlet 移除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="13cb5-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="13cb5-119">使用 Windows PowerShell 和 Remove-csexternalaccesspolicy cmdlet 可刪除外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="13cb5-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="13cb5-120">可以執行此 cmdlet，從 Skype for Business Server 管理命令介面或 Windows PowerShell 的遠端工作階段。</span><span class="sxs-lookup"><span data-stu-id="13cb5-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="13cb5-121">若要移除的特定外部存取原則</span><span class="sxs-lookup"><span data-stu-id="13cb5-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="13cb5-122">此命令會移除套用至 Redmond 網站的外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="13cb5-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="13cb5-123">若要移除所有外部存取原則套用至個別使用者範圍</span><span class="sxs-lookup"><span data-stu-id="13cb5-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="13cb5-124">此命令會移除在個別使用者範圍內設定的外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="13cb5-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="13cb5-125">若要移除其中已停用外部使用者存取的所有外部存取原則</span><span class="sxs-lookup"><span data-stu-id="13cb5-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="13cb5-126">此命令會刪除已停用外部使用者存取的所有外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="13cb5-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="13cb5-127">如需詳細資訊，請參閱[Remove-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="13cb5-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
