---
title: Lync Server 2013： SIP 主幹上的通話許可控制
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
ms.openlocfilehash: f60a868a4a77259b358f8ab9d4042bf33c56b044
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="e7860-102">Lync Server 2013 的 SIP 主幹上的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="e7860-102">Call admission control on a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7860-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="e7860-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="e7860-p101">若要在 SIP 主幹上部署通話許可控制 (CAC)，您必須建立代表網際網路電話語音服務提供者 (ITSP) 的網路網站。若要在 SIP 主幹上套用頻寬原則值，您可以在企業中的網路網站與您建立以代表 ITSP 的網路網站之間，建立網站間原則。</span><span class="sxs-lookup"><span data-stu-id="e7860-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="e7860-106">下圖顯示在 SIP 主幹上部署 CAC 的範例。</span><span class="sxs-lookup"><span data-stu-id="e7860-106">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="e7860-107">**SIP 主幹上的 CAC 組態**</span><span class="sxs-lookup"><span data-stu-id="e7860-107">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="e7860-108">![通話許可控制 SIP 主幹圖表](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "通話許可控制 SIP 主幹圖表")</span><span class="sxs-lookup"><span data-stu-id="e7860-108">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="e7860-109">若要在 SIP 主幹上設定 CAC，您必須在 CAC 部署期間執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="e7860-109">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="e7860-110">建立代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="e7860-110">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="e7860-111">讓此網路網站與適當的網路地區相關聯，並為此網路網站的音訊與視訊功能配置零的頻寬。</span><span class="sxs-lookup"><span data-stu-id="e7860-111">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="e7860-112">如需詳細資訊，請參閱部署檔中的 [Configure In Lync Server 2013 中的 CAC 的網路網站](lync-server-2013-configure-network-sites-for-cac.md) 。</span><span class="sxs-lookup"><span data-stu-id="e7860-112">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7860-113">對 ITSP 而言，此網路網站組態沒有作用。</span><span class="sxs-lookup"><span data-stu-id="e7860-113">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="e7860-114">頻寬原則值實際是在步驟 2 套用。</span><span class="sxs-lookup"><span data-stu-id="e7860-114">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="e7860-115">針對您在步驟 1 建立的網站使用相關的參數值，建立 SIP 主幹的網站間連結。</span><span class="sxs-lookup"><span data-stu-id="e7860-115">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="e7860-116">例如，您可以使用企業中網路網站的名稱作為 NetworkSiteID1 參數的值，並以 ITSP 網路網站作為 NetworkSiteID2 參數的值。</span><span class="sxs-lookup"><span data-stu-id="e7860-116">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="e7860-117">如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中建立網路網站間原則](lync-server-2013-create-network-intersite-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="e7860-117">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="e7860-118">另請參閱 Lync Server 管理命令介面檔，以瞭解 CsNetworkInterSitePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e7860-118">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="e7860-119">從 ITSP 取得會話邊界控制器的 (SCB) 媒體端接點的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e7860-119">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="e7860-120">將該子網路遮罩為32的 IP 位址，新增至代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="e7860-120">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="e7860-121">如需詳細資訊，請參閱 [在 Lync Server 2013 中建立子網與網路網站的關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="e7860-121">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

