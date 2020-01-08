---
title: Lync Server 2013：刪除存檔原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f151a940958273509191b35ed817409ba52b6dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="4b31b-102">刪除 Lync Server 2013 中的存檔原則</span><span class="sxs-lookup"><span data-stu-id="4b31b-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b31b-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4b31b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4b31b-104">您可以刪除使用者原則或網站原則。</span><span class="sxs-lookup"><span data-stu-id="4b31b-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="4b31b-105">無法移除全域原則。</span><span class="sxs-lookup"><span data-stu-id="4b31b-105">The global policy cannot be removed.</span></span> <span data-ttu-id="4b31b-106">如果您嘗試刪除全域原則，Lync Server 2013 會自動將原則重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="4b31b-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b31b-107">如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="4b31b-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="4b31b-108">如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="4b31b-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="4b31b-109">刪除使用者或網站原則以進行封存</span><span class="sxs-lookup"><span data-stu-id="4b31b-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="4b31b-110">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4b31b-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b31b-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4b31b-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4b31b-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="4b31b-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4b31b-113">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。</span><span class="sxs-lookup"><span data-stu-id="4b31b-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="4b31b-114">在歸檔原則清單中，按一下您要刪除的使用者或網站原則，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4b31b-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="4b31b-115">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b31b-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4b31b-116">使用 Windows PowerShell Cmdlet 移除存檔原則</span><span class="sxs-lookup"><span data-stu-id="4b31b-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4b31b-117">您可以使用 Windows PowerShell 和**CsArchivingPolicy** Cmdlet 來刪除存檔原則。</span><span class="sxs-lookup"><span data-stu-id="4b31b-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="4b31b-118">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="4b31b-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4b31b-119">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="4b31b-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="4b31b-120">移除指定的存檔原則</span><span class="sxs-lookup"><span data-stu-id="4b31b-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="4b31b-121">舉例來說， **Remove-CsArchivingPolicy**會刪除具有身分識別網站：雷德蒙的原則。</span><span class="sxs-lookup"><span data-stu-id="4b31b-121">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="4b31b-122">請注意，當您在網站範圍中設定原則時，系統會自動使用全域存檔原則來控制先前由網站原則管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="4b31b-122">Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead.</span></span> <span data-ttu-id="4b31b-123">下列命令會移除套用至雷德蒙者網站的存檔：</span><span class="sxs-lookup"><span data-stu-id="4b31b-123">The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="4b31b-124">若要移除所有套用至每個使用者範圍的存檔原則</span><span class="sxs-lookup"><span data-stu-id="4b31b-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="4b31b-125">這個命令會移除所有套用至每個使用者範圍的存檔原則：</span><span class="sxs-lookup"><span data-stu-id="4b31b-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="4b31b-126">若要移除所有停用內部歸檔的歸檔原則</span><span class="sxs-lookup"><span data-stu-id="4b31b-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="4b31b-127">這個命令會移除已停用內部封存的所有存檔原則：</span><span class="sxs-lookup"><span data-stu-id="4b31b-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="4b31b-128">如需詳細資訊，請參閱[Remove CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="4b31b-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b31b-129">請參閱</span><span class="sxs-lookup"><span data-stu-id="4b31b-129">See Also</span></span>


[<span data-ttu-id="4b31b-130">在 Lync Server 2013 中管理內部和外部通訊的存檔</span><span class="sxs-lookup"><span data-stu-id="4b31b-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

