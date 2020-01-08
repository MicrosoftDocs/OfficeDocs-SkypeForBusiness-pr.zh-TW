---
title: 將 Lync Server 2013 Survivable Branch Appliance 分支網站新增至您的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ae19b3683b725db64b2f598eb6fc3d182bac17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="bad31-102">將 Lync Server 2013 Survivable Branch Appliance 分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="bad31-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bad31-103">_**主題上次修改日期：** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="bad31-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="bad31-104">Microsoft Lync Server 2013 Survivable 分支裝置（SBA）無法與 Microsoft Lync Server 2010 前端池（做為備份註冊機構）相關聯。</span><span class="sxs-lookup"><span data-stu-id="bad31-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="bad31-105">SBA 必須與 Microsoft Lync Server 2013 前端池相關聯。</span><span class="sxs-lookup"><span data-stu-id="bad31-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="bad31-106">這些步驟假設 Microsoft Lync Server 2013 SBA。</span><span class="sxs-lookup"><span data-stu-id="bad31-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="bad31-107">在中央網站執行此程式。</span><span class="sxs-lookup"><span data-stu-id="bad31-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="bad31-108">若要將分支網站與 Microsoft Lync Server 2013 SBA 新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="bad31-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="bad31-109">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="bad31-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="bad31-110">在主控台樹中，展開中央網站，展開 [**分支網站**]，然後按一下 [**新增分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="bad31-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="bad31-111">在 [**定義新分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入新分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="bad31-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="bad31-112">可選按一下 [**描述**]，然後為分支網站輸入有意義的描述。</span><span class="sxs-lookup"><span data-stu-id="bad31-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="bad31-113">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bad31-113">Click **Next**.</span></span>

6.  <span data-ttu-id="bad31-114">可選在 [下一步**定義分支網站**] 對話方塊中，執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="bad31-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="bad31-115">按一下 [**城市**]，然後輸入分支網站所在城市的名稱。</span><span class="sxs-lookup"><span data-stu-id="bad31-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="bad31-116">按一下 [**狀態/地區**]，然後輸入分支網站所在的狀態或地區名稱。</span><span class="sxs-lookup"><span data-stu-id="bad31-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="bad31-117">按一下 [**國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bad31-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="bad31-118">按一下 **[下一步]**，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="bad31-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="bad31-119">如果您是在此網站使用 Survivable 分支裝置或 Survivable 分支伺服器，請確定已選取 [**當此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bad31-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="bad31-120">如果您不是在此網站使用 Survivable 分支裝置或 Survivable 分支伺服器，請清除 [**當此嚮導關閉時，開啟新的 Survivable 嚮導]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bad31-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="bad31-121">按一下 **[完成**]，然後依照嚮導中開啟的指示進行。</span><span class="sxs-lookup"><span data-stu-id="bad31-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="bad31-122">如需有關嚮導專案的資訊，請參閱[在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="bad31-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="bad31-123">針對您要新增到拓撲結構中的每個分支網站，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="bad31-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bad31-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="bad31-124">See Also</span></span>


[<span data-ttu-id="bad31-125">在 Lync Server 2013 中定義 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="bad31-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="bad31-126">在 Lync Server 2013 中定義分支網站的 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="bad31-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
<span data-ttu-id="bad31-127">[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="bad31-127">[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span></span>  
[<span data-ttu-id="bad31-128">在 Lync Server 2013 中設定沒有媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="bad31-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

