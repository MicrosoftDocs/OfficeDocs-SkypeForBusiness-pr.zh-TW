---
title: Lync Server 2013：刪除網路區域連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 158537f2473beba686daa51c5384a45f01432320
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="f3f42-102">刪除 Lync Server 2013 中的 [網路區域] 連結</span><span class="sxs-lookup"><span data-stu-id="f3f42-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3f42-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f3f42-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f3f42-104">您可以設定兩個網路區域之間的連結，作為通話許可控制（CAC）的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3f42-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="f3f42-105">網路中的區域是透過物理廣域網路（WAN）連線來連結。</span><span class="sxs-lookup"><span data-stu-id="f3f42-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="f3f42-106">您可以使用 Lync Server [控制台] 來刪除兩個網路區域之間的現有連結。</span><span class="sxs-lookup"><span data-stu-id="f3f42-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="f3f42-107">如需建立或修改網路區域連結的詳細資料，請參閱[在 Lync Server 2013 中設定網路區域連結](lync-server-2013-configuring-network-region-links.md)。</span><span class="sxs-lookup"><span data-stu-id="f3f42-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="f3f42-108">刪除網路區域連結</span><span class="sxs-lookup"><span data-stu-id="f3f42-108">To delete a network region link</span></span>

1.  <span data-ttu-id="f3f42-109">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f3f42-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3f42-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="f3f42-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f3f42-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f3f42-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f3f42-112">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="f3f42-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="f3f42-113">在 [**地區連結**] 頁面上，按一下您要刪除的區域連結。</span><span class="sxs-lookup"><span data-stu-id="f3f42-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3f42-114">您可以一次刪除一個以上的區域連結。</span><span class="sxs-lookup"><span data-stu-id="f3f42-114">You can delete more than one region link at a time.</span></span> <span data-ttu-id="f3f42-115">若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個區域連結。</span><span class="sxs-lookup"><span data-stu-id="f3f42-115">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="f3f42-116">或者，若要選取所有區域連結，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="f3f42-116">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="f3f42-117">從 [**編輯**] 功能表中，選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="f3f42-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="f3f42-118">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f3f42-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3f42-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="f3f42-119">See Also</span></span>


[<span data-ttu-id="f3f42-120">在 Lync Server 2013 中設定網路區域連結</span><span class="sxs-lookup"><span data-stu-id="f3f42-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

