---
title: Lync Server 2013： 設定 CAC 的網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f449d26515c6790ec8582676ca57ed897f12dc40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="b0944-102">設定 Lync Server 2013 中的 CAC 的網路網站</span><span class="sxs-lookup"><span data-stu-id="b0944-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0944-103">_**主題上次修改日期：** 2012年-09-05_</span><span class="sxs-lookup"><span data-stu-id="b0944-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b0944-104">如果您已經建立網路網站的 E9-1-1 或媒體旁路，您可以修改現有的網路網站，以使用<STRONG>Set-csnetworksite</STRONG> cmdlet 來套用頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="b0944-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="b0944-105">如需如何修改網路網站的範例，請參閱<A href="lync-server-2013-create-or-modify-a-network-site.md">建立或修改 Lync Server 2013 中的網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="b0944-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b0944-106">*網路站台*是辦公室或位置內的每個網路地區通話許可控制 (CAC)、 E9-1-1 和媒體旁路的部署。</span><span class="sxs-lookup"><span data-stu-id="b0944-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="b0944-107">使用下列程序來建立對齊 CAC 的範例網路拓撲中的網路網站的網站。</span><span class="sxs-lookup"><span data-stu-id="b0944-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="b0944-108">這些程序顯示如何建立並設定受到 WAN 頻寬限制的網路網站，並因此需要限制即時的音訊或視訊流量的頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="b0944-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="b0944-109">在 CAC 部署範例中，北美地區有六個網站。</span><span class="sxs-lookup"><span data-stu-id="b0944-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="b0944-110">這些網站的三種會受限於 WAN 頻寬： 雷諾、 波特蘭，與阿布。</span><span class="sxs-lookup"><span data-stu-id="b0944-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="b0944-111">其他三個站台，也就是*不*受限制的 WAN 頻寬： 紐約、 芝加哥與底特律。</span><span class="sxs-lookup"><span data-stu-id="b0944-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="b0944-112">如需如何建立或修改這些其他網路網站的範例，請參閱[建立或修改 Lync Server 2013 中的網路網站](lync-server-2013-create-or-modify-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="b0944-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="b0944-113">若要檢視範例網路拓撲，請參閱[範例： 收集您的 Lync Server 2013 中的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)中規劃文件。</span><span class="sxs-lookup"><span data-stu-id="b0944-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="b0944-114">下列程序，Lync Server 管理命令介面用來建立網路網站。</span><span class="sxs-lookup"><span data-stu-id="b0944-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="b0944-115">如需使用 Lync Server 控制台建立網路網站的詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-a-network-site.md">建立或修改 Lync Server 2013 中的網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="b0944-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="b0944-116">若要建立通話許可控制的網路網站</span><span class="sxs-lookup"><span data-stu-id="b0944-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="b0944-117">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="b0944-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b0944-118">執行**New-csnetworksite** cmdlet 建立網路網站，並將適當的頻寬原則設定檔套用至每個網站。</span><span class="sxs-lookup"><span data-stu-id="b0944-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="b0944-119">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="b0944-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="b0944-120">若要完成建立整個範例拓撲的網站，請針對 EMEA 和 APAC 地區中受頻寬限制的網站重複步驟 2。</span><span class="sxs-lookup"><span data-stu-id="b0944-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

