---
title: Lync Server 2013： 將分支網站新增至您的拓撲
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
ms.openlocfilehash: 1a43d926fcc2883a36a577fd297567da0295a0f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="bfbe6-102">將分支網站新增至您在 Lync Server 2013 中的拓撲</span><span class="sxs-lookup"><span data-stu-id="bfbe6-102">Add branch sites to your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfbe6-103">_**主題上次修改日期：** 2012年-10-05_</span><span class="sxs-lookup"><span data-stu-id="bfbe6-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="bfbe6-104">分支站台代表實體的分公司，透過 WAN 連結連線至您主要的辦公室。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-104">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="bfbe6-105">若要將分支網站新增至您的 Lync 拓樸，執行此程序在中央網站。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-105">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="bfbe6-106">若要將分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="bfbe6-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="bfbe6-107">按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="bfbe6-108">在主控台樹狀目錄中，展開中央網站，以滑鼠右鍵按一下 [**分支網站**]，然後按一下**新的分支網站**。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="bfbe6-109">在 [**定義新的分支網站**] 對話方塊中，按一下 [**名稱**] 中，，然後輸入分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="bfbe6-110">（選用）按一下 [**描述**] 中，，，然後輸入分支網站的有意義描述。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="bfbe6-111">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-111">Click **Next**.</span></span>

6.  <span data-ttu-id="bfbe6-112">（選用）在下的 [**定義新的分支網站**] 對話方塊中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bfbe6-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="bfbe6-113">按一下 [**縣/市**、，然後輸入分支網站所在位置的城市名稱。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="bfbe6-114">按一下 [省/地區\*\*\*\*，然後輸入位置的省或地區的分支網站所在的名稱。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="bfbe6-115">按一下 [**國碼/地區碼**，，，然後輸入分支網站所在國家/地區的兩位數呼叫程式碼。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="bfbe6-116">按一下 [**下一步**，，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bfbe6-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="bfbe6-117">如果您在此網站使用 Survivable Branch Appliance 或 Server，請確定已選取 [**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊、 按一下 [**完成**]，然後遵循開啟精靈] 中的指示操作。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="bfbe6-118">精靈項目的相關資訊，請參閱[定義 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="bfbe6-119">如果您未在此網站使用 Survivable Branch Appliance 或 Server，清除**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊，然後再按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="bfbe6-120">針對每個您想要新增至拓撲的分支網站重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="bfbe6-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="bfbe6-121">**下一個步驟：**</span><span class="sxs-lookup"><span data-stu-id="bfbe6-121">**Next step:**</span></span>

<span data-ttu-id="bfbe6-122">Survivable Branch Appliance 或 Server：[定義 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="bfbe6-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="bfbe6-123">不具彈性的 PSTN 連線：[定義 Lync Server 2013 中的分支網站的 PSTN 閘道](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)，[設定主幹，且媒體旁路 Lync Server 2013 中](lync-server-2013-configure-a-trunk-with-media-bypass.md)，或[設定沒有媒體主幹略過在 Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="bfbe6-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

