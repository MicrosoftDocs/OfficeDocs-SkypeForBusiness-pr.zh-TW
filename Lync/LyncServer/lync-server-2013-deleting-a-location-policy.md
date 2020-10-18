---
title: Lync Server 2013：刪除位置原則
description: Lync Server 2013：刪除位置原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88935c00a60de377c9812a4d119708fd610338ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575839"
---
# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="e7ef7-103">在 Lync Server 2013 中刪除位置原則</span><span class="sxs-lookup"><span data-stu-id="e7ef7-103">Deleting a location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7ef7-104">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e7ef7-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="e7ef7-105">在 Lync Server 2013 中，您可以使用位置原則，套用與增強型 9-1-1 (E9-1-1) 功能及使用者或連絡人的位置設定相關的設定。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-105">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="e7ef7-106">位置原則會判斷使用者是否已啟用 E9-1-1，如果是，則會決定緊急電話的行為。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-106">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="e7ef7-107">例如，您可以使用位置原則來定義組成緊急電話的數字 (例如，在美國為 911)、是否應自動告知公司的安全部門，以及應如何路由傳送來電。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-107">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="e7ef7-108">您可以在 Lync Server 2013 [控制台] 中的 [ **網路** 設定] 群組設定位置原則。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-108">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="e7ef7-109">從 Lync Server 控制台，您可以查看、建立、修改或刪除位置原則。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-109">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="e7ef7-110">使用下列程式會刪除位置原則。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-110">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="e7ef7-111">如需建立或修改位置原則的詳細資訊，請參閱 [在 Lync Server 2013 中建立或修改位置原則](lync-server-2013-creating-or-modifying-a-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-111">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="e7ef7-112">刪除位置原則</span><span class="sxs-lookup"><span data-stu-id="e7ef7-112">To delete a location policy</span></span>

1.  <span data-ttu-id="e7ef7-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e7ef7-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e7ef7-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e7ef7-116">在左導覽列中按一下 **[網路設定]**，然後按一下 **[位置原則]**。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-116">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="e7ef7-117">在 [ **位置原則** ] 頁面上，選取您要刪除的位置原則。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-117">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7ef7-118">您可以一次刪除一個以上的位置原則。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-118">You can delete more than one location policy at a time.</span></span> <span data-ttu-id="e7ef7-119">若要執行此動作，請按住 CTRL 鍵並選取多個原則，並按住 CTRL 鍵。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-119">To do this, press CTRL and select multiple policies while holding down the CTRL key.</span></span> <span data-ttu-id="e7ef7-120">或者，若要選取所有原則，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-120">Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="e7ef7-121">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="e7ef7-122">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-122">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7ef7-123">您無法刪除全域位置原則。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-123">You cannot delete the Global location policy.</span></span> <span data-ttu-id="e7ef7-124">如果您嘗試刪除通用原則，您會收到警告訊息，而且該原則會重設為其預設值。</span><span class="sxs-lookup"><span data-stu-id="e7ef7-124">If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7ef7-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e7ef7-125">See Also</span></span>


[<span data-ttu-id="e7ef7-126">在 Lync Server 2013 中建立或修改位置原則</span><span class="sxs-lookup"><span data-stu-id="e7ef7-126">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="e7ef7-127">在 Lync Server 2013 中查看位置原則資訊</span><span class="sxs-lookup"><span data-stu-id="e7ef7-127">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

