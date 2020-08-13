---
title: Lync Server 2013：建立或修改頻寬原則設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c46ec104972eff34f73825fbb384259fc6eb4ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="fe25f-102">在 Lync Server 2013 中建立或修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="fe25f-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe25f-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="fe25f-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="fe25f-104">頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="fe25f-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="fe25f-105">在 Microsoft Lync Server 2013 中，只有音訊和影片形式可以獲指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="fe25f-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="fe25f-106">您可以設定整體頻寬限制和工作階段限制。</span><span class="sxs-lookup"><span data-stu-id="fe25f-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="fe25f-107">您可以使用 Lync Server 控制台建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="fe25f-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="fe25f-108">每個頻寬原則設定檔可以與一或多個網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="fe25f-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="fe25f-109">請使用下列程序來建立或修改頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="fe25f-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="fe25f-110">若要刪除頻寬原則設定檔，請參閱[刪除 Lync Server 2013 中的網路頻寬原則設定檔](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="fe25f-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="fe25f-111">若要建立新的頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="fe25f-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="fe25f-112">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="fe25f-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fe25f-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="fe25f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe25f-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fe25f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe25f-115">在左導覽列中，按一下 [網路設定]\*\*\*\*，然後按一下 [頻寬原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fe25f-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="fe25f-116">在「頻寬原則」\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fe25f-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="fe25f-p103">在 **[新增頻寬原則設定檔]** 的 **[名稱]** 欄位中輸入名稱。在所有頻寬原則設定檔中，此名稱必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="fe25f-p103">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="fe25f-p104">在 **[音訊限制]** 欄位中輸入數值。此值是要配置給所有音訊連線的最大頻寬數量 (以 kbps 表示)。</span><span class="sxs-lookup"><span data-stu-id="fe25f-p104">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="fe25f-p105">在 **[音訊工作階段限制]** 欄位中輸入數值。此值是要配置給個別音訊連線的最大頻寬數量 (以 kbps 表示)。此值必須為 40 或更大。</span><span class="sxs-lookup"><span data-stu-id="fe25f-p105">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="fe25f-p106">在 **[視訊限制]** 欄位中輸入數值。此值是要配置給所有視訊連線的最大頻寬數量 (以 kbps 表示)。</span><span class="sxs-lookup"><span data-stu-id="fe25f-p106">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="fe25f-p107">在 **[視訊工作階段限制]** 欄位中輸入數值。此值是要配置給個別視訊連線的最大頻寬數量 (以 kbps 表示)。此值必須為 100 或更大。</span><span class="sxs-lookup"><span data-stu-id="fe25f-p107">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="fe25f-129">(選用) 在 **[描述]** 欄位中輸入值，以提供更多有關此頻寬原則設定檔 (無法單獨以名稱表示) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="fe25f-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="fe25f-130">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="fe25f-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe25f-131">建立新的頻寬原則設定檔並不會自動強制頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="fe25f-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="fe25f-132">您必須先讓原則設定檔與網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="fe25f-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="fe25f-133">如需如何關聯原則設定檔與網站的詳細資訊，請參閱<A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中建立或修改網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="fe25f-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="fe25f-134">若要修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="fe25f-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="fe25f-135">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="fe25f-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fe25f-136">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="fe25f-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe25f-137">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fe25f-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe25f-138">在左導覽列中，按一下 [網路設定]\*\*\*\*，然後按一下 [頻寬原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fe25f-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="fe25f-139">在「頻寬原則」\*\*\*\* 頁面上，按一下您要修改的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="fe25f-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="fe25f-140">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="fe25f-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="fe25f-141">在 **[編輯頻寬原則設定檔]** 頁面上，視需要修改欄位 (如需詳細資訊，請參閱本主題中前面的＜若要建立頻寬原則設定檔＞一節)。</span><span class="sxs-lookup"><span data-stu-id="fe25f-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="fe25f-142">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="fe25f-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe25f-143">當您修改頻寬原則設定檔時，將會立即更新與此頻寬原則設定檔關聯的所有網路網站的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="fe25f-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe25f-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fe25f-144">See Also</span></span>


[<span data-ttu-id="fe25f-145">在 Lync Server 2013 中刪除網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="fe25f-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="fe25f-146">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="fe25f-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="fe25f-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="fe25f-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="fe25f-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="fe25f-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="fe25f-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="fe25f-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

