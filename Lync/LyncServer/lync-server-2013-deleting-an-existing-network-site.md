---
title: Lync Server 2013：刪除現有的網路網站
description: Lync Server 2013：刪除現有的網路網站。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cef4774ee71aaf6851757d5b88d30138fc34997
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551069"
---
# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="11b3f-103">在 Lync Server 2013 中刪除現有的網路網站</span><span class="sxs-lookup"><span data-stu-id="11b3f-103">Deleting an existing network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11b3f-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="11b3f-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="11b3f-105">網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="11b3f-105">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="11b3f-106">您可以使用 Lync Server 2013 控制台來設定網站，並將其與區域產生關聯。</span><span class="sxs-lookup"><span data-stu-id="11b3f-106">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="11b3f-107">例如，北美洲的網路區域可能會和 Chicago、Redmond 及 Vancouver 等網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="11b3f-107">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="11b3f-108">您必須為組織內的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="11b3f-108">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="11b3f-109">您可以從 Lync Server 控制台建立、修改和刪除網路網站。</span><span class="sxs-lookup"><span data-stu-id="11b3f-109">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="11b3f-110">使用下列程序刪除現有網路網站。</span><span class="sxs-lookup"><span data-stu-id="11b3f-110">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="11b3f-111">如需建立或修改網站的詳細資訊，請參閱 [在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="11b3f-111">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="11b3f-112">刪除網路網站</span><span class="sxs-lookup"><span data-stu-id="11b3f-112">To delete a network site</span></span>

1.  <span data-ttu-id="11b3f-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="11b3f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11b3f-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="11b3f-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11b3f-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="11b3f-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11b3f-116">在左導覽列中，依序按一下 [網路設定]\*\*\*\* 和 [網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11b3f-116">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="11b3f-117">在 [網站]\*\*\*\* 頁面上，按一下您要刪除的網站。</span><span class="sxs-lookup"><span data-stu-id="11b3f-117">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11b3f-p103">您可以一次刪除多個網站。若要這樣做，請按 CTRL 並在按住 CTRL 鍵的同時選取多個網站。或者，若要選取所有網站，請按一下 [編輯]<STRONG></STRONG> 功能表上的 [全選]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="11b3f-p103">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="11b3f-121">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="11b3f-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="11b3f-122">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="11b3f-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="11b3f-p104">但是如果網站與某個網路子網路相關聯時，則無法移除該網路網站。如果您嘗試移除與子網路相關聯的網站，則會收到錯誤訊息。若要查看網站是否與子網路相關聯，請按一下網站並按一下 [編輯]<STRONG></STRONG> 功能表上的 [顯示詳細資料]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="11b3f-p104">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

