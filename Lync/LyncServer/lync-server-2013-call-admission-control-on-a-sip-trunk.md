---
title: Lync Server 2013： SIP 主幹上的通話許可控制
description: Lync Server 2013： SIP 主幹上的通話許可控制。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3667ef4608b221a1607b6bbe0d89d390cb1dd402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563155"
---
# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="e565a-103">Lync Server 2013 的 SIP 主幹上的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="e565a-103">Call admission control on a SIP trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e565a-104">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="e565a-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="e565a-p101">若要在 SIP 主幹上部署通話許可控制 (CAC)，您必須建立代表網際網路電話語音服務提供者 (ITSP) 的網路網站。若要在 SIP 主幹上套用頻寬原則值，您可以在企業中的網路網站與您建立以代表 ITSP 的網路網站之間，建立網站間原則。</span><span class="sxs-lookup"><span data-stu-id="e565a-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="e565a-107">下圖顯示在 SIP 主幹上部署 CAC 的範例。</span><span class="sxs-lookup"><span data-stu-id="e565a-107">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="e565a-108">**SIP 主幹上的 CAC 組態**</span><span class="sxs-lookup"><span data-stu-id="e565a-108">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="e565a-109">![通話許可控制 SIP 主幹圖表](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "通話許可控制 SIP 主幹圖表")</span><span class="sxs-lookup"><span data-stu-id="e565a-109">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="e565a-110">若要在 SIP 主幹上設定 CAC，您必須在 CAC 部署期間執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="e565a-110">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="e565a-111">建立代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="e565a-111">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="e565a-112">讓此網路網站與適當的網路地區相關聯，並為此網路網站的音訊與視訊功能配置零的頻寬。</span><span class="sxs-lookup"><span data-stu-id="e565a-112">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="e565a-113">如需詳細資訊，請參閱部署檔中的 [Configure In Lync Server 2013 中的 CAC 的網路網站](lync-server-2013-configure-network-sites-for-cac.md) 。</span><span class="sxs-lookup"><span data-stu-id="e565a-113">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e565a-114">對 ITSP 而言，此網路網站組態沒有作用。</span><span class="sxs-lookup"><span data-stu-id="e565a-114">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="e565a-115">頻寬原則值實際是在步驟 2 套用。</span><span class="sxs-lookup"><span data-stu-id="e565a-115">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="e565a-116">針對您在步驟 1 建立的網站使用相關的參數值，建立 SIP 主幹的網站間連結。</span><span class="sxs-lookup"><span data-stu-id="e565a-116">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="e565a-117">例如，您可以使用企業中網路網站的名稱作為 NetworkSiteID1 參數的值，並以 ITSP 網路網站作為 NetworkSiteID2 參數的值。</span><span class="sxs-lookup"><span data-stu-id="e565a-117">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="e565a-118">如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中建立網路網站間原則](lync-server-2013-create-network-intersite-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="e565a-118">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="e565a-119">另請參閱 Lync Server 管理命令介面檔，以取得 New-CsNetworkInterSitePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e565a-119">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="e565a-120">從 ITSP 取得會話邊界控制器的 (SCB) 媒體端接點的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e565a-120">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="e565a-121">將該子網路遮罩為32的 IP 位址，新增至代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="e565a-121">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="e565a-122">如需詳細資訊，請參閱 [在 Lync Server 2013 中建立子網與網路網站的關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="e565a-122">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

