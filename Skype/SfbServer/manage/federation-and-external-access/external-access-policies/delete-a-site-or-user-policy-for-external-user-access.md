---
title: 刪除外部使用者存取的網站或使用者原則
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以刪除 [外部存取原則] 頁面上的 [商務用 Skype Server] 控制台中所列的任何網站或使用者原則。
ms.openlocfilehash: 407e90af201055f371dc92485ab258bac851a258
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099019"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="f82d8-103">刪除外部使用者存取的網站或使用者原則</span><span class="sxs-lookup"><span data-stu-id="f82d8-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="f82d8-104">如果您已建立或設定不想再使用的外部使用者存取原則，則可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f82d8-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="f82d8-105">刪除任何已建立的網站或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="f82d8-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="f82d8-p101">將全域原則重設為預設設定。預設全域原則設定拒絕任何外部使用者存取。全域原則無法刪除。</span><span class="sxs-lookup"><span data-stu-id="f82d8-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="f82d8-109">您可以刪除 [ **外部存取原則** ] 頁面上的 [商務用 Skype Server] 控制台中所列的任何網站或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="f82d8-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="f82d8-110">刪除全域原則並不是實際加以刪除，只是將它重設為不支援任何外部使用者存取選項的預設設定。</span><span class="sxs-lookup"><span data-stu-id="f82d8-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="f82d8-111">如需重設全域原則的詳細資訊，請參閱 [重設外部使用者存取的全域原則](reset-the-global-policy-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f82d8-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="f82d8-112">刪除外部使用者存取的網站或使用者原則</span><span class="sxs-lookup"><span data-stu-id="f82d8-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="f82d8-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f82d8-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f82d8-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f82d8-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f82d8-115">按一下 **[外部使用者存取]**，並按一下 **[外部存取原則]**。</span><span class="sxs-lookup"><span data-stu-id="f82d8-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="f82d8-116">在 **[外部存取原則]** 索引標籤上，按一下想要刪除的網站或使用者原則，並按一下 **[編輯]**，然後按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="f82d8-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="f82d8-117">系統提示確認刪除時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f82d8-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f82d8-118">使用 Windows PowerShell Cmdlet 移除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="f82d8-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f82d8-119">您可以使用 Windows PowerShell 和 Remove-CsExternalAccessPolicy Cmdlet 刪除外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="f82d8-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="f82d8-120">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f82d8-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="f82d8-121">移除特定的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="f82d8-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="f82d8-122">此命令會移除套用至 Redmond 網站的外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="f82d8-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="f82d8-123">移除所有套用至個別使用者範圍的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="f82d8-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="f82d8-124">此命令會移除在個別使用者範圍內設定的外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="f82d8-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="f82d8-125">移除已停用外部使用者存取的所有外部存取原則</span><span class="sxs-lookup"><span data-stu-id="f82d8-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="f82d8-126">此命令會刪除已停用外部使用者存取的所有外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="f82d8-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="f82d8-127">如需詳細資訊，請參閱 [get-csexternalaccesspolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="f82d8-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>