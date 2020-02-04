---
title: Lync Server 2013：刪除現有的網路區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57af552f82dfb3ca30943fd68c348cd5315b969b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="7be8c-102">在 Lync Server 2013 中刪除現有的網路區域</span><span class="sxs-lookup"><span data-stu-id="7be8c-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7be8c-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7be8c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7be8c-104">網路區域跨多個地理區域互連網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="7be8c-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="7be8c-105">每個網路區域都必須與一個中央網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="7be8c-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="7be8c-106">中央網站是在其上執行呼叫許可控制（CAC）頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="7be8c-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="7be8c-107">您可以使用 Lync Server [控制台] 來設定網路區域。</span><span class="sxs-lookup"><span data-stu-id="7be8c-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="7be8c-108">網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。</span><span class="sxs-lookup"><span data-stu-id="7be8c-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="7be8c-109">在 Lync Server [控制台] 中，您可以建立、修改或刪除網路區域。</span><span class="sxs-lookup"><span data-stu-id="7be8c-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="7be8c-110">使用本主題刪除現有的網路區域。</span><span class="sxs-lookup"><span data-stu-id="7be8c-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="7be8c-111">如需建立或修改現有網路區域的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路區域](lync-server-2013-creating-or-modifying-network-regions.md)。</span><span class="sxs-lookup"><span data-stu-id="7be8c-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="7be8c-112">刪除網路區域</span><span class="sxs-lookup"><span data-stu-id="7be8c-112">To delete a network region</span></span>

1.  <span data-ttu-id="7be8c-113">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="7be8c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7be8c-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="7be8c-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7be8c-115">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="7be8c-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7be8c-116">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。</span><span class="sxs-lookup"><span data-stu-id="7be8c-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="7be8c-117">在 [**地區**] 頁面上，按一下您要刪除的地區。</span><span class="sxs-lookup"><span data-stu-id="7be8c-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7be8c-118">您可以一次刪除一個以上的區域。</span><span class="sxs-lookup"><span data-stu-id="7be8c-118">You can delete more than one region at a time.</span></span> <span data-ttu-id="7be8c-119">若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個區域。</span><span class="sxs-lookup"><span data-stu-id="7be8c-119">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="7be8c-120">或者，若要選取所有區域，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="7be8c-120">Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="7be8c-121">在 [**編輯**] 功能表上，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="7be8c-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="7be8c-122">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7be8c-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="7be8c-123">如果網路區域與網路網站相關聯，則無法移除。</span><span class="sxs-lookup"><span data-stu-id="7be8c-123">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="7be8c-124">如果您嘗試移除與網站相關聯的區域，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7be8c-124">If you attempt to remove a region associated with a site you will receive an error message.</span></span> <span data-ttu-id="7be8c-125">若要查看某個地區是否與任何網站相關聯，請選取該區域，然後按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="7be8c-125">To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7be8c-126">請參閱</span><span class="sxs-lookup"><span data-stu-id="7be8c-126">See Also</span></span>


[<span data-ttu-id="7be8c-127">在 Lync Server 2013 中建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="7be8c-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

