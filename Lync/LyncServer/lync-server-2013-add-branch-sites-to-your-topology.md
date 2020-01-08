---
title: Lync Server 2013：新增分支網站至拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029627060ff03b804d0d2f76f40fdd4052f0d1c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="d13ee-102">在 Lync Server 2013 中新增分支網站至拓撲</span><span class="sxs-lookup"><span data-stu-id="d13ee-102">Add branch sites to your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d13ee-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d13ee-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d13ee-104">分支網站代表通過 WAN 連結連線到主要辦公室的物理分支辦公室。</span><span class="sxs-lookup"><span data-stu-id="d13ee-104">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="d13ee-105">若要將分支網站新增至您的 Lync 拓撲，請在中央網站執行此程式。</span><span class="sxs-lookup"><span data-stu-id="d13ee-105">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="d13ee-106">在拓撲中新增分支網站</span><span class="sxs-lookup"><span data-stu-id="d13ee-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="d13ee-107">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="d13ee-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d13ee-108">在主控台樹中，展開中央網站，以滑鼠右鍵按一下 [**分支網站**]，然後按一下 [**新增分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="d13ee-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="d13ee-109">在 [**定義新分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="d13ee-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="d13ee-110">可選按一下 [**描述**]，然後為分支網站輸入有意義的描述。</span><span class="sxs-lookup"><span data-stu-id="d13ee-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="d13ee-111">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d13ee-111">Click **Next**.</span></span>

6.  <span data-ttu-id="d13ee-112">可選在 [下一步**定義分支網站**] 對話方塊中，執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="d13ee-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="d13ee-113">按一下 [**城市**]，然後輸入分支網站所在城市的名稱。</span><span class="sxs-lookup"><span data-stu-id="d13ee-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="d13ee-114">按一下 [**狀態/地區**]，然後輸入分支網站所在的狀態或地區名稱。</span><span class="sxs-lookup"><span data-stu-id="d13ee-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="d13ee-115">按一下 [**國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d13ee-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="d13ee-116">按一下 **[下一步]**，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d13ee-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="d13ee-117">如果您是在此網站使用 Survivable 分支裝置或伺服器，請確定已選取 [在**關閉此嚮導時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成**]，然後依照嚮導中開啟的指示進行。</span><span class="sxs-lookup"><span data-stu-id="d13ee-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="d13ee-118">如需有關嚮導專案的資訊，請參閱[在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d13ee-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="d13ee-119">如果您不是在此網站使用 Survivable 分支裝置或伺服器，請清除 [在**關閉此嚮導時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="d13ee-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="d13ee-120">針對您要新增到拓撲結構中的每個分支網站，重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="d13ee-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="d13ee-121">**後續步驟：**</span><span class="sxs-lookup"><span data-stu-id="d13ee-121">**Next step:**</span></span>

<span data-ttu-id="d13ee-122">針對 Survivable 分支裝置或伺服器：[在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="d13ee-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="d13ee-123">針對非復原 PSTN 連線：針對[lync server 2013 中的分支網站定義 PSTN 閘道](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)，請[在 lync server 2013 中使用 [媒體旁路] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)，或在[lync server 2013 中設定不含媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="d13ee-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

