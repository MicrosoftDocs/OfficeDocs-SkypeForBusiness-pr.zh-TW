---
title: Lync Server 2013：設定 CAC 的網路網站
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
ms.openlocfilehash: e24932b23b1a9168ed64279f98db125f06ad0e2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520520"
---
# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="1a54c-102">在 Lync Server 2013 中設定 CAC 的網路網站</span><span class="sxs-lookup"><span data-stu-id="1a54c-102">Configure network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a54c-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="1a54c-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="1a54c-104">如果您已建立 E9-1-1 或媒體旁路的網站，您可以修改現有的網路網站，以使用 <STRONG>Set-CsNetworkSite</STRONG> Cmdlet 來套用頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="1a54c-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="1a54c-105">如需如何修改網路網站的範例，請參閱 <A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中建立或修改網站</A>。</span><span class="sxs-lookup"><span data-stu-id="1a54c-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1a54c-106">*網路網站* 是通話許可控制之每個網路地區內的辦公室或位置 (CAC) 、E9-1-1 和 media 旁路部署。</span><span class="sxs-lookup"><span data-stu-id="1a54c-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="1a54c-107">使用下列程式來建立網路網站，使其對應至 CAC 的範例網路拓撲中的網站。</span><span class="sxs-lookup"><span data-stu-id="1a54c-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="1a54c-108">這些程式示範如何建立及設定受 WAN 頻寬限制的網站，因此需要頻寬原則來限制即時音訊或視頻流量流程。</span><span class="sxs-lookup"><span data-stu-id="1a54c-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="1a54c-109">在範例 CAC 部署中，北美地區包含六個網站。</span><span class="sxs-lookup"><span data-stu-id="1a54c-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="1a54c-110">以下是受 WAN 頻寬限制的三個網站：雷諾、上海及阿布奎基。</span><span class="sxs-lookup"><span data-stu-id="1a54c-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="1a54c-111">其他三個網站 *不* 受 WAN 頻寬限制：紐約、芝加哥和底特律。</span><span class="sxs-lookup"><span data-stu-id="1a54c-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="1a54c-112">如需如何建立或修改其他網路網站的範例，請參閱 [在 Lync Server 2013 中建立或修改網站](lync-server-2013-create-or-modify-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="1a54c-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="1a54c-113">若要查看範例網路拓撲，請參閱規劃檔中的 [範例：在 Lync Server 2013 中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="1a54c-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="1a54c-114">在下列程式中，Lync Server 管理命令介面是用來建立網路網站。</span><span class="sxs-lookup"><span data-stu-id="1a54c-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="1a54c-115">如需使用 Lync Server 控制台建立網路網站的詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync server 2013 中建立或修改網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="1a54c-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="1a54c-116">為通話許可控制建立網路網站</span><span class="sxs-lookup"><span data-stu-id="1a54c-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="1a54c-117">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="1a54c-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1a54c-118">執行 **New-CsNetworkSite** Cmdlet 來建立網路網站，並將適當的頻寬原則設定檔套用至每個網站。</span><span class="sxs-lookup"><span data-stu-id="1a54c-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="1a54c-119">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="1a54c-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="1a54c-120">若要完成整個範例拓撲的建立網站，請對 EMEA 和 APAC 地區的頻寬限制網路網站重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="1a54c-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

