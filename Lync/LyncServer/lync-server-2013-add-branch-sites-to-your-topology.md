---
title: Lync Server 2013：將分支網站新增至您的拓撲
description: Lync Server 2013：將分支網站新增至您的拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c7a12373c6a60a2902ee451d39c99f756e2b2f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544569"
---
# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="b7e4b-103">將分支網站新增至您在 Lync Server 2013 中的拓撲</span><span class="sxs-lookup"><span data-stu-id="b7e4b-103">Add branch sites to your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7e4b-104">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="b7e4b-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b7e4b-105">分支網站代表透過 WAN 連結連線至您的主要辦公室的實體分支辦公室。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-105">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="b7e4b-106">若要將分支網站新增至您的 Lync 拓撲，請在中央網站執行此程式。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-106">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="b7e4b-107">若要將分支網站新增至拓撲</span><span class="sxs-lookup"><span data-stu-id="b7e4b-107">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="b7e4b-108">依序按一下 [ **開始**]、[ **所有程式**] 及 [ **Microsoft lync server**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b7e4b-109">在主控台樹中，展開中央網站，以滑鼠右鍵按一下 [ **分支網站**]，然後按一下 [ **新增分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-109">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="b7e4b-110">在 [ **定義新的分支網站** ] 對話方塊中，按一下 [ **名稱**]，然後輸入分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-110">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="b7e4b-111"> (選用) 按一下 [ **描述**]，然後為分支網站輸入有意義的描述。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-111">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="b7e4b-112">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-112">Click **Next**.</span></span>

6.  <span data-ttu-id="b7e4b-113"> (選用) 在下一個 [ **定義新的分支網站** ] 對話方塊中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b7e4b-113">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="b7e4b-114">按一下 [ **城市**]，然後輸入分支網站所在位置的城市名稱。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-114">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="b7e4b-115">按一下 [ **省/地區**]，然後輸入分支網站所在位置的省或地區名稱。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-115">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="b7e4b-116">按一下 [ **國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數呼叫碼。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-116">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="b7e4b-117">按 **[下一步]**，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="b7e4b-117">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="b7e4b-118">如果您是在此網站使用 Survivable 分支裝置或伺服器，請確定已選取 [ **當此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊，按一下 **[完成**]，然後依照所開啟之嚮導中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-118">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="b7e4b-119">如需有關 [嚮導專案] 的詳細資訊，請參閱 [在 Lync Server 2013 中定義 Survivable Branch 裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-119">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="b7e4b-120">如果您未使用此網站的 Survivable 分支裝置或伺服器，請清除 [在 **此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-120">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="b7e4b-121">針對您要新增至拓撲的每一個分支網站重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="b7e4b-121">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="b7e4b-122">**下一步：**</span><span class="sxs-lookup"><span data-stu-id="b7e4b-122">**Next step:**</span></span>

<span data-ttu-id="b7e4b-123">針對 Survivable 分支裝置或伺服器： [定義 Lync Server 2013 中的 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="b7e4b-123">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="b7e4b-124">若為無復原的 PSTN 連線： [在 lync server 2013 中定義分支網站的 PSTN 閘道](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)，在 [lync server 2013 中使用媒體旁路設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)，或在 [lync server 2013 中設定無媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="b7e4b-124">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

