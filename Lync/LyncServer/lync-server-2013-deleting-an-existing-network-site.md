---
title: Lync Server 2013：刪除現有的網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772d653e0bde803f47a5742a4f3824bdef01c3f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="35239-102">在 Lync Server 2013 中刪除現有的網路網站</span><span class="sxs-lookup"><span data-stu-id="35239-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35239-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="35239-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="35239-104">[網路網站] 是在通話許可控制（CAC）或增強型9-1-1 部署的每個區域中設定的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="35239-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="35239-105">您可以使用 Lync Server 2013 的 [控制台] 來設定網站，並將它們與區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="35239-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="35239-106">例如，北美的網路區域可能會與「芝加哥」、「雷德蒙」和「范與范」等網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="35239-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="35239-107">您必須針對組織中的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制也一樣。</span><span class="sxs-lookup"><span data-stu-id="35239-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="35239-108">您可以從 Lync Server [控制台] 建立、修改及刪除網路網站。</span><span class="sxs-lookup"><span data-stu-id="35239-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="35239-109">使用下列程式刪除現有的網路網站。</span><span class="sxs-lookup"><span data-stu-id="35239-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="35239-110">如需建立或修改網路網站的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="35239-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="35239-111">刪除網路網站</span><span class="sxs-lookup"><span data-stu-id="35239-111">To delete a network site</span></span>

1.  <span data-ttu-id="35239-112">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="35239-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="35239-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="35239-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="35239-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="35239-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="35239-115">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="35239-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="35239-116">在 [**網站**] 頁面上，按一下您要刪除的網站。</span><span class="sxs-lookup"><span data-stu-id="35239-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35239-117">您可以一次刪除一個以上的網站。</span><span class="sxs-lookup"><span data-stu-id="35239-117">You can delete more than one site at a time.</span></span> <span data-ttu-id="35239-118">若要這樣做，請按住 CTRL 並在按住 CTRL 鍵的同時選取多個網站。</span><span class="sxs-lookup"><span data-stu-id="35239-118">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="35239-119">或者，若要選取 [所有網站]，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="35239-119">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="35239-120">在 [**編輯**] 功能表上，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="35239-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="35239-121">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="35239-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="35239-122">如果網路網站與網路子網相關聯，您就無法移除它。</span><span class="sxs-lookup"><span data-stu-id="35239-122">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="35239-123">如果您嘗試移除與子網相關聯的網站，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="35239-123">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="35239-124">若要查看網站是否與任何子網產生關聯，請按一下該網站，然後按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="35239-124">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

