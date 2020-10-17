---
title: Lync Server 2013：刪除網路地區連結
description: Lync Server 2013：刪除網路地區連結。
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
ms.openlocfilehash: 5a17c1ec64460e0f7cb447597f94aadd7fd2a9ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545329"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="17efd-103">在 Lync Server 2013 中刪除網路地區連結</span><span class="sxs-lookup"><span data-stu-id="17efd-103">Deleting network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17efd-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="17efd-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="17efd-105">您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="17efd-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="17efd-106">網路中的地區是透過實體廣域網路 (WAN) 連線相連結。</span><span class="sxs-lookup"><span data-stu-id="17efd-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="17efd-107">您可以使用 Lync Server 控制台刪除兩個網路地區之間的現有連結。</span><span class="sxs-lookup"><span data-stu-id="17efd-107">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="17efd-108">如需建立或修改網路地區連結的詳細資訊，請參閱 [在 Lync Server 中設定網路地區連結 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="17efd-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="17efd-109">刪除網路地區連結</span><span class="sxs-lookup"><span data-stu-id="17efd-109">To delete a network region link</span></span>

1.  <span data-ttu-id="17efd-110">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="17efd-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17efd-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="17efd-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="17efd-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="17efd-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="17efd-113">按一下左導覽列中的 [網路設定]\*\*\*\*，然後按一下 [地區連結]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="17efd-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="17efd-114">在 [地區連結]\*\*\*\* 頁面中，按一下要刪除的地區連結。</span><span class="sxs-lookup"><span data-stu-id="17efd-114">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17efd-p103">您可以一次刪除一個以上的地區連結。若要一次刪除一個以上的地區連結，請按住 CTRL 鍵並同時選取多個地區連結。若要選取多個地區，您也可以按一下 [編輯]<STRONG></STRONG> 功能表中的 [全選]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="17efd-p103">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="17efd-118">選取 [編輯]\*\*\*\* 功能表中的 [刪除]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="17efd-118">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="17efd-119">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="17efd-119">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17efd-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17efd-120">See Also</span></span>


[<span data-ttu-id="17efd-121">在 Lync Server 2013 中設定網路地區連結</span><span class="sxs-lookup"><span data-stu-id="17efd-121">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

