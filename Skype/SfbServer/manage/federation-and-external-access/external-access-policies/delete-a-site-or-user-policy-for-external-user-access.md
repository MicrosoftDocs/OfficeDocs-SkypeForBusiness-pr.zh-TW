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
description: 您可以刪除 [外部存取原則] 頁面上的 [商務用 Skype Server] 控制台中所列的任何網站或使用者原則。
ms.openlocfilehash: 2472058009622834e20a1657167c7061b9706579
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818284"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="85cb0-103">刪除外部使用者存取的網站或使用者原則</span><span class="sxs-lookup"><span data-stu-id="85cb0-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="85cb0-104">如果您已建立或設定您不想再使用的外部使用者存取原則，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="85cb0-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="85cb0-105">刪除您建立的任何網站或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="85cb0-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="85cb0-106">將全域原則重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="85cb0-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="85cb0-107">預設全域原則設定會拒絕任何外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="85cb0-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="85cb0-108">無法刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="85cb0-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="85cb0-109">您可以刪除 [**外部存取原則**] 頁面上的 [商務用 Skype Server] 控制台中所列的任何網站或使用者原則。</span><span class="sxs-lookup"><span data-stu-id="85cb0-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="85cb0-110">刪除全域原則並不會真正將它刪除，但只會將其重設為預設設定，而不包含任何外部使用者存取選項的支援。</span><span class="sxs-lookup"><span data-stu-id="85cb0-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="85cb0-111">如需重設全域原則的詳細資訊，請參閱[重設外部使用者存取的全域原則](reset-the-global-policy-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="85cb0-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="85cb0-112">刪除網站或使用者原則供外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="85cb0-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="85cb0-113">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="85cb0-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85cb0-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="85cb0-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="85cb0-115">按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="85cb0-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="85cb0-116">在 [**外部存取原則**] 索引標籤上，按一下您要刪除的網站或使用者原則，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="85cb0-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="85cb0-117">當系統提示您確認刪除時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="85cb0-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="85cb0-118">使用 Windows PowerShell Cmdlet 移除 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="85cb0-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="85cb0-119">您可以使用 Windows PowerShell 與 Remove CsExternalAccessPolicy Cmdlet 來刪除外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="85cb0-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="85cb0-120">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85cb0-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="85cb0-121">移除特定外部存取原則</span><span class="sxs-lookup"><span data-stu-id="85cb0-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="85cb0-122">這個命令會移除已套用至雷德蒙者網站的外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="85cb0-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="85cb0-123">若要移除所有套用至每個使用者範圍的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="85cb0-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="85cb0-124">這個命令會移除在每個使用者作用中設定的所有外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="85cb0-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="85cb0-125">若要移除所有外部存取原則（在禁止外部使用者存取的情況下）</span><span class="sxs-lookup"><span data-stu-id="85cb0-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="85cb0-126">這個命令會刪除已停用使用者存取的所有外部存取原則：</span><span class="sxs-lookup"><span data-stu-id="85cb0-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="85cb0-127">如需詳細資訊，請參閱[Remove CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="85cb0-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
