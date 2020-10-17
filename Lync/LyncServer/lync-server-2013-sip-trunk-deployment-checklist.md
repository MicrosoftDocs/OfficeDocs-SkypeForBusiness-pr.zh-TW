---
title: Lync Server 2013： SIP 主幹部署檢查清單
description: Lync Server 2013： SIP 主幹部署檢查清單。
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
ms.openlocfilehash: dbab9647a7146b2478317ab6c020969506f9c0ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559039"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="13b1b-103">Lync Server 2013 的 SIP 主幹部署檢查表</span><span class="sxs-lookup"><span data-stu-id="13b1b-103">SIP trunk deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13b1b-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="13b1b-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="13b1b-105">在您部署 SIP 主幹之前，您和服務提供者必須交換某些有關您各自 SIP 主幹端點的基本連線資訊。</span><span class="sxs-lookup"><span data-stu-id="13b1b-105">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="13b1b-106">針對您要連接的每個 ITSP 閘道取得下列資訊：</span><span class="sxs-lookup"><span data-stu-id="13b1b-106">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="13b1b-107">IP 位址</span><span class="sxs-lookup"><span data-stu-id="13b1b-107">IP address</span></span>

  - <span data-ttu-id="13b1b-108">網域全名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="13b1b-108">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13b1b-109">服務提供者可能要求您連接至多個 ITSP 閘道。</span><span class="sxs-lookup"><span data-stu-id="13b1b-109">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="13b1b-110">在此情況下，您必須設定每個 ITSP 閘道與集區中的每個轉送伺服器之間的連線。</span><span class="sxs-lookup"><span data-stu-id="13b1b-110">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="13b1b-111">您提供給服務提供者的資訊取決於您的 SIP 主幹連線類型：</span><span class="sxs-lookup"><span data-stu-id="13b1b-111">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="13b1b-112">若為多協定標籤切換 (MPLS) 或私人網路絡連線，請將您周邊 (網路中路由器的可公開路由的 IP 位址（也稱為 DMZ、網路隔離區域及遮罩式子網) ）提供給 ITSP。</span><span class="sxs-lookup"><span data-stu-id="13b1b-112">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="13b1b-113">確認 ITSP 中 (SBC) 的閘道或會話邊界控制器可以聯繫至此位址。</span><span class="sxs-lookup"><span data-stu-id="13b1b-113">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="13b1b-114">也為 ITSP 提供轉送伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="13b1b-114">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="13b1b-115">對於虛擬私人網路 (VPN) 連線，請將 VPN 伺服器的 IP 位址提供給 ITSP。</span><span class="sxs-lookup"><span data-stu-id="13b1b-115">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="13b1b-116">憑證考慮</span><span class="sxs-lookup"><span data-stu-id="13b1b-116">Certificate Considerations</span></span>

<span data-ttu-id="13b1b-117">若要判斷您是否需要憑證以進行 SIP 主幹，請與您的 ITSP 相關的通訊協定支援：</span><span class="sxs-lookup"><span data-stu-id="13b1b-117">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="13b1b-118">如果您的 ITSP 只支援傳輸控制通訊協定 (TCP) ，您不需要憑證。</span><span class="sxs-lookup"><span data-stu-id="13b1b-118">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="13b1b-119">如果您的 ITSP 支援傳輸層安全性 (TLS) ，則 ITSP 必須為您提供憑證。</span><span class="sxs-lookup"><span data-stu-id="13b1b-119">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13b1b-120">SIP 可搭配即時傳輸通訊協定 (RTP) 或安全即時傳輸通訊協定 (SRTP) ，用來管理 Voice over Internet Protocol 中實際語音資料的通訊協定 (VoIP) 通話。</span><span class="sxs-lookup"><span data-stu-id="13b1b-120">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="13b1b-121">部署程式</span><span class="sxs-lookup"><span data-stu-id="13b1b-121">Deployment Process</span></span>

<span data-ttu-id="13b1b-122">若要執行 SIP 主幹連線的 Lync Server 端，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="13b1b-122">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="13b1b-123">使用 Lync Server 拓撲產生器，建立及設定 SIP 網域拓撲。</span><span class="sxs-lookup"><span data-stu-id="13b1b-123">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="13b1b-124">如需詳細資訊，請參閱部署檔中的在 [2013 拓撲產生器中定義及設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) 產生器中的拓撲。</span><span class="sxs-lookup"><span data-stu-id="13b1b-124">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="13b1b-125">使用 Lync Server 控制台，設定新 SIP 網域的語音路由。</span><span class="sxs-lookup"><span data-stu-id="13b1b-125">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="13b1b-126">如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013](lync-server-2013-configuring-trunks.md) 中設定主幹。</span><span class="sxs-lookup"><span data-stu-id="13b1b-126">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="13b1b-127">使用 **Test-CsPstnOutboundCall** Cmdlet 來測試連線性。</span><span class="sxs-lookup"><span data-stu-id="13b1b-127">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="13b1b-128">如需詳細資訊，請參閱 lync server 管理命令介面檔或 Lync Server 管理命令介面的說明。</span><span class="sxs-lookup"><span data-stu-id="13b1b-128">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

