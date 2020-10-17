---
title: Lync Server 2013：查看執行 Lync Server 2013 的電腦清單
description: Lync Server 2013：查看執行 Lync Server 2013 的電腦清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of computers running Lync Server 2013
ms:assetid: 44eeec27-8b99-44f0-b0bd-622c12393d34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520987(v=OCS.15)
ms:contentKeyID: 48184030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baeb2d8e926b1597c463259378332e0c9f50268f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567179"
---
# <a name="view-a-list-of-computers-running-lync-server-2013"></a><span data-ttu-id="d4fe7-103">查看執行 Lync Server 2013 的電腦清單</span><span class="sxs-lookup"><span data-stu-id="d4fe7-103">View a list of computers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4fe7-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d4fe7-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d4fe7-105">您可以使用 Lync Server 2013 控制台，以查看拓撲中所有執行 Lync Server 2013 的電腦清單，並查看每個電腦的服務狀態。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-105">You can use Lync Server 2013 Control Panel to view a list of all the computers that are running Lync Server 2013 in your topology and see the service status of each.</span></span> <span data-ttu-id="d4fe7-106">您可以依電腦、集區或網站來排序清單。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-106">You can sort the list by computer, pool, or site.</span></span>

<div>

## <a name="to-view-a-list-of-computers-running-lync-server"></a><span data-ttu-id="d4fe7-107">若要檢視執行 Lync Server 的電腦清單</span><span class="sxs-lookup"><span data-stu-id="d4fe7-107">To view a list of computers running Lync Server</span></span>

1.  <span data-ttu-id="d4fe7-108">從指派給 Lync Server 2013 的任何預先定義管理角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-108">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="d4fe7-109">如需 Lync Server 2013 中可用的預先定義管理角色的詳細資訊，請參閱 [在 Lync server 2013 中規劃以角色為基礎的存取控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-109">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="d4fe7-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4fe7-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4fe7-112">在左導覽列中，按一下 **[拓撲]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-112">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="d4fe7-113">在 **[狀態]** 頁面上，視需要執行下列任何動作：</span><span class="sxs-lookup"><span data-stu-id="d4fe7-113">On the **Status** page, do any of the following as needed:</span></span>
    
      - <span data-ttu-id="d4fe7-114">按一下 **[電腦]**、**[集區]** 或 **[網站]** 欄標題，然後按一下向上箭頭或向下箭頭來排序清單。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-114">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    
      - <span data-ttu-id="d4fe7-115">按一下 **[重新整理]** 檢視最新清單。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-115">Click **Refresh** to view the most up-to-date list.</span></span>
    
      - <span data-ttu-id="d4fe7-116">在搜尋欄位中輸入電腦名稱來搜尋特定電腦。</span><span class="sxs-lookup"><span data-stu-id="d4fe7-116">Search for a specific computer by typing the computer name in the search field.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4fe7-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4fe7-117">See Also</span></span>


[<span data-ttu-id="d4fe7-118">管理 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="d4fe7-118">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

