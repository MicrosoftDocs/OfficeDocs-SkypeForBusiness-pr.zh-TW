---
title: Lync Server 2013：刪除網路頻寬原則設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c33f781e8818dbefa3dc37b3f17c789099e6add
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="bdf63-102">刪除 Lync Server 2013 的網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="bdf63-102">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdf63-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bdf63-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bdf63-104">在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="bdf63-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="bdf63-105">在 Microsoft Lync Server 2013 中，只有音訊和視頻形式可獲指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="bdf63-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="bdf63-106">您可以設定整體頻寬限制及會話限制。</span><span class="sxs-lookup"><span data-stu-id="bdf63-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="bdf63-107">您可以使用 Lync Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="bdf63-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="bdf63-108">使用下列程式刪除網路頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="bdf63-108">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="bdf63-109">如需建立或修改網路頻寬原則設定檔的詳細資料，請參閱[在 Lync Server 2013 中建立或修改頻寬原則設定檔](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf63-109">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="bdf63-110">刪除頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="bdf63-110">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="bdf63-111">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bdf63-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bdf63-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="bdf63-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bdf63-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf63-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bdf63-114">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。</span><span class="sxs-lookup"><span data-stu-id="bdf63-114">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="bdf63-115">在 [**頻寬原則**] 頁面上，按一下您要刪除的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="bdf63-115">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bdf63-116">您可以一次刪除一個以上的設定檔。</span><span class="sxs-lookup"><span data-stu-id="bdf63-116">You can delete more than one profile at a time.</span></span> <span data-ttu-id="bdf63-117">若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個設定檔。</span><span class="sxs-lookup"><span data-stu-id="bdf63-117">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="bdf63-118">或者，若要選取所有設定檔，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="bdf63-118">Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="bdf63-119">在 [**編輯**] 功能表上，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="bdf63-119">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="bdf63-120">您無法刪除與網路網站相關聯的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="bdf63-120">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="bdf63-121">您必須先移除與網路網站的關聯，然後才能刪除設定檔。</span><span class="sxs-lookup"><span data-stu-id="bdf63-121">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="bdf63-122">如需如何修改網路網站的詳細資訊，請參閱<A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中建立或修改網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="bdf63-122">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bdf63-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="bdf63-123">See Also</span></span>


[<span data-ttu-id="bdf63-124">在 Lync Server 2013 中建立或修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="bdf63-124">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="bdf63-125">在 Lync Server 2013 中查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="bdf63-125">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="bdf63-126">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="bdf63-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="bdf63-127">移除-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="bdf63-127">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

