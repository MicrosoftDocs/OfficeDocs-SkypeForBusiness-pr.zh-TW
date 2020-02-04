---
title: Lync Server 2013：SIP 主幹部署檢查表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef670fc4ae9e8a9acba3277a00fc0daf6ff766b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="6b1b4-102">Lync Server 2013 的 SIP 主幹部署檢查表</span><span class="sxs-lookup"><span data-stu-id="6b1b4-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b1b4-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6b1b4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6b1b4-104">您和您的服務提供者必須交換一些有關各 SIP 幹線端點的基本連線資訊，才能部署 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="6b1b4-105">針對您要連接的每個 ITSP 閘道，取得下列資訊：</span><span class="sxs-lookup"><span data-stu-id="6b1b4-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="6b1b4-106">IP 位址</span><span class="sxs-lookup"><span data-stu-id="6b1b4-106">IP address</span></span>

  - <span data-ttu-id="6b1b4-107">完全合格的功能變數名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="6b1b4-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b1b4-108">服務提供者可能會要求您連線到一個以上的 ITSP 閘道。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="6b1b4-109">在這種情況下，您必須在每個 ITSP 閘道與池中的每個轉送伺服器之間設定連線。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="6b1b4-110">您提供給服務提供者的資訊視 SIP 中繼連線類型而定：</span><span class="sxs-lookup"><span data-stu-id="6b1b4-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="6b1b4-111">針對多協定標籤切換（MPLS）或私人網路連線，請為 ITSP 提供周邊網路中路由器的公用路由 IP 位址（也稱為 DMZ、網路隔離區域和遮罩子網）。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="6b1b4-112">確認 ITSP 上的閘道或會話邊界控制器（SBC）可以達到這個位址。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="6b1b4-113">也提供 ITSP 轉送伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="6b1b4-114">針對虛擬私人網路（VPN）連線，請提供 ITSP VPN 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="6b1b4-115">憑證考慮</span><span class="sxs-lookup"><span data-stu-id="6b1b4-115">Certificate Considerations</span></span>

<span data-ttu-id="6b1b4-116">若要判斷您是否需要 SIP 中繼的憑證，請諮詢您的 ITSP 關於通訊協定的支援：</span><span class="sxs-lookup"><span data-stu-id="6b1b4-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="6b1b4-117">如果您的 ITSP 只支援傳輸控制通訊協定（TCP），則不需要證書。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="6b1b4-118">如果您的 ITSP 支援傳輸層安全性（TLS），則 ITSP 必須提供您的憑證。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b1b4-119">SIP 可與即時傳輸通訊協定（RTP）或安全即時傳輸通訊協定（SRTP）搭配使用，以透過網際網路通訊協定（VoIP）通話管理實際語音資料的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="6b1b4-120">部署程式</span><span class="sxs-lookup"><span data-stu-id="6b1b4-120">Deployment Process</span></span>

<span data-ttu-id="6b1b4-121">若要實現 SIP 中繼連線的 Lync Server 端，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6b1b4-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="6b1b4-122">使用 Lync Server 拓撲建立器建立及設定 SIP 網域拓撲。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="6b1b4-123">如需詳細資訊，請參閱在部署檔中，在[Lync Server 2013 的拓撲建立程式中定義及設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="6b1b4-124">使用 Lync Server [控制台] 設定新 SIP 網域的語音路由。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="6b1b4-125">如需詳細資訊，請參閱部署檔中的[Lync Server 2013](lync-server-2013-configuring-trunks.md)中的 [設定 trunks]。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="6b1b4-126">使用**Test CsPstnOutboundCall** Cmdlet 來測試連線性。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="6b1b4-127">如需詳細資訊，請參閱 lync server 管理命令介面檔或 Lync Server 管理命令介面的說明。</span><span class="sxs-lookup"><span data-stu-id="6b1b4-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

