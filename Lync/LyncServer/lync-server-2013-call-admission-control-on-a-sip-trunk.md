---
title: Lync Server 2013：SIP 主幹上的通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36734aa67e350b6c6f5ea5e9da57ce47f57e3d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="27100-102">Lync Server 2013 中的 SIP 主幹上的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="27100-102">Call admission control on a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27100-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="27100-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="27100-104">若要在 SIP 主幹上部署呼叫許可控制（CAC），您需要建立網路網站來代表網際網路電話服務提供者（ITSP）。</span><span class="sxs-lookup"><span data-stu-id="27100-104">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP).</span></span> <span data-ttu-id="27100-105">若要在 SIP 主幹上套用頻寬原則值，您可以在企業中的網路網站和您建立用以代表 ITSP 的網路網站之間建立站間原則。</span><span class="sxs-lookup"><span data-stu-id="27100-105">To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="27100-106">下圖顯示 SIP 主幹上的 CAC 部署範例。</span><span class="sxs-lookup"><span data-stu-id="27100-106">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="27100-107">**SIP 幹線上的 CAC 配置**</span><span class="sxs-lookup"><span data-stu-id="27100-107">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="27100-108">![呼叫許可控制 Sip 中繼圖表](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "通話許可控制 sip 中繼圖表")</span><span class="sxs-lookup"><span data-stu-id="27100-108">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="27100-109">若要在 SIP 主幹上設定 CAC，您必須在 CAC 部署期間執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="27100-109">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="27100-110">建立代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="27100-110">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="27100-111">將網路網站與合適的網路區域建立關聯，並為此網路網站的音訊和影片分配零頻寬。</span><span class="sxs-lookup"><span data-stu-id="27100-111">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="27100-112">如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定 CAC 的網路網站](lync-server-2013-configure-network-sites-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="27100-112">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="27100-113">針對 ITSP，此網路網站設定無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="27100-113">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="27100-114">在步驟2中實際會套用頻寬原則值。</span><span class="sxs-lookup"><span data-stu-id="27100-114">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="27100-115">使用您在步驟1中建立的網站相關參數值，為 SIP 幹線建立站間連結。</span><span class="sxs-lookup"><span data-stu-id="27100-115">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="27100-116">例如，在企業中使用網路網站的名稱做為 NetworkSiteID1 參數的值，並使用 ITSP network 網站作為 NetworkSiteID2 參數的值。</span><span class="sxs-lookup"><span data-stu-id="27100-116">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="27100-117">如需詳細資訊，請參閱部署檔中的[Lync Server 2013 中的建立網路站間原則](lync-server-2013-create-network-intersite-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="27100-117">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="27100-118">另請參閱適用于新版 CsNetworkInterSitePolicy Cmdlet 的 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="27100-118">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="27100-119">從您的 ITSP 取得會話邊界控制器（SCB）媒體終止點的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="27100-119">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="27100-120">將具有子網路遮罩32的 IP 位址新增至代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="27100-120">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="27100-121">如需詳細資訊，請參閱[在 Lync Server 2013 中將子網與網路網站建立關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="27100-121">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

