---
title: Lync Server 2013：設定 CAC 的網路地區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c029de2a7b6296dc81d365978c55d18c817e0894
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520540"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="c40f7-102">在 Lync Server 2013 中設定 CAC 的網路地區</span><span class="sxs-lookup"><span data-stu-id="c40f7-102">Configure network regions for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c40f7-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c40f7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c40f7-104">如果您已建立 E9-1-1 或媒體旁路的網路地區，您可以使用 <STRONG>Set-CsNetworkRegion</STRONG> 指令程式 (CAC) 新增通話許可控制的特定設定，以修改現有的網路地區。</span><span class="sxs-lookup"><span data-stu-id="c40f7-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="c40f7-105">如需如何修改網路地區的範例，請參閱 <A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中建立或修改網路地區</A>。</span><span class="sxs-lookup"><span data-stu-id="c40f7-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c40f7-106">*網路地區* 是網路中樞或骨幹，用來設定 CAC、E9-1-1 和媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="c40f7-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="c40f7-107">請使用下列程式建立網路地區，以與 CAC 的範例網路拓撲中的網路地區對齊。</span><span class="sxs-lookup"><span data-stu-id="c40f7-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="c40f7-108">若要查看範例網路拓撲，請參閱規劃檔中的 [範例：在 Lync Server 2013 中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="c40f7-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="c40f7-109">CAC 的範例網路拓撲有三個區域：北美、EMEA 和 APAC。</span><span class="sxs-lookup"><span data-stu-id="c40f7-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="c40f7-110">每個地區都有指定的中央網站。</span><span class="sxs-lookup"><span data-stu-id="c40f7-110">Each region has a specified central site.</span></span> <span data-ttu-id="c40f7-111">在北美地區，指定的中央網站命名為芝加哥。</span><span class="sxs-lookup"><span data-stu-id="c40f7-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="c40f7-112">下列程式顯示如何使用 **New-CsNetworkRegion** Cmdlet 來建立北美地區的範例。</span><span class="sxs-lookup"><span data-stu-id="c40f7-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c40f7-113">在下列程式中，Lync Server 管理命令介面是用來建立網路地區。</span><span class="sxs-lookup"><span data-stu-id="c40f7-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="c40f7-114">如需使用 Lync Server 控制台建立網路地區的詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中建立或修改網路地區</A>。</span><span class="sxs-lookup"><span data-stu-id="c40f7-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="c40f7-115">為通話許可控制建立網路地區</span><span class="sxs-lookup"><span data-stu-id="c40f7-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="c40f7-116">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="c40f7-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c40f7-117">針對您需要建立的每個地區，執行 **New-CsNetworkRegion** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c40f7-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="c40f7-118">例如，若要建立北美地區，請執行：</span><span class="sxs-lookup"><span data-stu-id="c40f7-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="c40f7-119">重複步驟2以建立網路地區（EMEA 和 APAC）。</span><span class="sxs-lookup"><span data-stu-id="c40f7-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

