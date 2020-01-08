---
title: Lync Server 2013：針對 CAC 設定網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678cab0ea8b473e6ea33ab5db951b105a11fa78
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40977088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="bb6ba-102">在 Lync Server 2013 中設定 CAC 的網路網站</span><span class="sxs-lookup"><span data-stu-id="bb6ba-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb6ba-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="bb6ba-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="bb6ba-104">如果您已為 E9 （1-1 或媒體旁路）建立網路網站，您可以使用<STRONG>CsNetworkSite</STRONG> Cmdlet 來修改現有的網路網站，以套用頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="bb6ba-105">如需如何修改網路網站的範例，請參閱<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中建立或修改網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="bb6ba-106">*Network sites*是呼叫許可控制（CAC）、E9-1 及媒體旁路部署的每個網路區域內的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="bb6ba-107">使用下列程式來建立網路網站，以在 CAC 的範例網路拓撲中與網路網站對齊。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="bb6ba-108">這些程式示範如何建立和設定受 WAN 頻寬限制的網路網站，因此需要頻寬原則來限制即時音訊或視頻流量流程。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="bb6ba-109">在範例 CAC 部署中，北美地區有六個網站。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="bb6ba-110">這些網站中有三個是受 WAN 頻寬的限制： Reno、Albuquerque 及。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="bb6ba-111">*不*受 WAN 頻寬限制的其他三個網站：北京、芝加哥及底特律。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="bb6ba-112">如需如何建立或修改其他網路網站的範例，請參閱[在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-create-or-modify-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="bb6ba-113">若要查看範例網路拓撲，請參閱在規劃檔中[收集 Lync Server 2013 的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="bb6ba-114">在下列程式中，Lync Server 管理命令介面是用來建立網路網站。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="bb6ba-115">如需使用 Lync Server [控制台] 建立網路網站的詳細資料，請參閱<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync server 2013 中建立或修改網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="bb6ba-116">建立通話許可控制的網路網站</span><span class="sxs-lookup"><span data-stu-id="bb6ba-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="bb6ba-117">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bb6ba-118">執行**新的 CsNetworkSite** Cmdlet 來建立網路網站，並將適當的頻寬原則設定檔套用至每個網站。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="bb6ba-119">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="bb6ba-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="bb6ba-120">若要為整個範例拓撲完成建立網路網站，請針對 EMEA 與 APAC 區域中的頻寬限制網路網站，重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="bb6ba-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

