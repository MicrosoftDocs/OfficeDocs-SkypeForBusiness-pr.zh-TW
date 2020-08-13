---
title: Lync Server 2013：停用網路媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaad239f320f498378498f9b3e373592d487c0c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="ce18b-102">停用 Lync Server 2013 中的網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="ce18b-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce18b-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="ce18b-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="ce18b-104">媒體旁路設定會在 Microsoft Lync Server 2013 部署中全域套用。</span><span class="sxs-lookup"><span data-stu-id="ce18b-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="ce18b-105">媒體旁路允許來電略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce18b-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="ce18b-106">如需有關何時使用媒體旁路的詳細資訊，請參閱規劃區段中的在[Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)。您可以從 Lync Server 控制台停用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="ce18b-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="ce18b-107">如需啟用和設定詞中略過的詳細資訊，請參閱[啟用網路媒體旁路 In Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="ce18b-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="ce18b-108">停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="ce18b-108">To disable media bypass</span></span>

1.  <span data-ttu-id="ce18b-109">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ce18b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce18b-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ce18b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ce18b-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ce18b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ce18b-112">在左導覽列中，按一下 **[網路設定]**，然後按一下 **[全域]**。</span><span class="sxs-lookup"><span data-stu-id="ce18b-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="ce18b-113">在 **[全域]** 頁面上，按一下 **[全域]** 設定。</span><span class="sxs-lookup"><span data-stu-id="ce18b-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="ce18b-114">永遠只有一個設定，而且永遠稱為 Global。</span><span class="sxs-lookup"><span data-stu-id="ce18b-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="ce18b-115">在 [**編輯**] 功能表上，按一下 [**查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ce18b-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="ce18b-116">在 [**編輯通用設定**] 頁面上，清除 [**啟用媒體旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ce18b-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="ce18b-117">按一下 [**認可**] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="ce18b-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce18b-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce18b-118">See Also</span></span>


[<span data-ttu-id="ce18b-119">在 Lync Server 2013 中啟用網路媒體旁路</span><span class="sxs-lookup"><span data-stu-id="ce18b-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

