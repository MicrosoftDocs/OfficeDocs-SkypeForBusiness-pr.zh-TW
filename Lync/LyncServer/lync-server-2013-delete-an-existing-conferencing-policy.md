---
title: Lync Server 2013：刪除現有的會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 679d88a1d359ea9590262d78e49ab8fa7fbc3906
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="e8a78-102">在 Lync Server 2013 中刪除現有的會議原則</span><span class="sxs-lookup"><span data-stu-id="e8a78-102">Delete an existing conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8a78-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e8a78-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e8a78-104">遵循這些步驟即可刪除使用者層級或網站層級會議原則。</span><span class="sxs-lookup"><span data-stu-id="e8a78-104">Follow these steps to delete a user-level or a site-level conferencing policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8a78-105">您無法刪除全域會議原則。</span><span class="sxs-lookup"><span data-stu-id="e8a78-105">You cannot delete the global conferencing policy.</span></span>



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a><span data-ttu-id="e8a78-106">刪除網站或使用者會議原則</span><span class="sxs-lookup"><span data-stu-id="e8a78-106">To delete a site or user conferencing policy</span></span>

1.  <span data-ttu-id="e8a78-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e8a78-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8a78-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e8a78-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e8a78-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e8a78-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e8a78-110">請在左導覽列中按一下 **[會議]**，然後按一下 **[會議原則]**。</span><span class="sxs-lookup"><span data-stu-id="e8a78-110">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="e8a78-111">在會議原則清單中，按一下您要刪除的網站或使用者原則，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e8a78-111">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e8a78-112">使用 Windows PowerShell Cmdlet 移除會議原則</span><span class="sxs-lookup"><span data-stu-id="e8a78-112">Removing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e8a78-113">您可以使用 Lync Server 管理命令介面和**Remove-CsConferencingPolicy** Cmdlet 來刪除會議原則。</span><span class="sxs-lookup"><span data-stu-id="e8a78-113">You can delete conferencing policies by using Lync Server Management Shell and the **Remove-CsConferencingPolicy** cmdlet.</span></span> <span data-ttu-id="e8a78-114">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e8a78-114">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e8a78-115">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="e8a78-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a><span data-ttu-id="e8a78-116">移除指定的會議原則</span><span class="sxs-lookup"><span data-stu-id="e8a78-116">To remove a specified conferencing policy</span></span>

  - <span data-ttu-id="e8a78-117">下列命令可移除具有 Identity RedmondConferencingPolicy 的會議原則：</span><span class="sxs-lookup"><span data-stu-id="e8a78-117">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="e8a78-118">移除所有套用於個別使用者範圍的會議原則</span><span class="sxs-lookup"><span data-stu-id="e8a78-118">To remove all of the conferencing policies applied to the per-user scope</span></span>

  - <span data-ttu-id="e8a78-119">下列命令可移除所有設定於個別使用者範圍的會議原則：</span><span class="sxs-lookup"><span data-stu-id="e8a78-119">The following command removes all the conferencing policies configured at the per-user scope:</span></span>
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a><span data-ttu-id="e8a78-120">移除所有允許外部使用者錄製的會議原則</span><span class="sxs-lookup"><span data-stu-id="e8a78-120">To remove all of the conferencing polices that allow recording by external users</span></span>

  - <span data-ttu-id="e8a78-121">下列命令可移除任何允許外部使用者錄製會議的會議原則：</span><span class="sxs-lookup"><span data-stu-id="e8a78-121">The following command deletes any conferencing policies that allow external users to record the conference:</span></span>
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

<span data-ttu-id="e8a78-122">如需詳細資訊，請參閱[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy)。</span><span class="sxs-lookup"><span data-stu-id="e8a78-122">For details, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

