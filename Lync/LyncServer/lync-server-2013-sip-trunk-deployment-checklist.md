---
title: 'Lync Server 2013: SIP 主幹部署檢查表'
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
ms.openlocfilehash: 7260397f219ad3dac8e666431693f59caf51729c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="97532-102">Lync Server 2013 的 SIP 主幹部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="97532-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97532-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="97532-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="97532-104">您可以部署 SIP 主幹之前，您和您的服務提供者必須各自的 SIP 主幹端點相關交換了某些基本連線資訊。</span><span class="sxs-lookup"><span data-stu-id="97532-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="97532-105">取得每個要連接的 ITSP 閘道的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="97532-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="97532-106">IP 位址</span><span class="sxs-lookup"><span data-stu-id="97532-106">IP address</span></span>

  - <span data-ttu-id="97532-107">網域全名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="97532-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97532-108">服務提供者可能會要求您連接到一個以上的 ITSP 閘道。</span><span class="sxs-lookup"><span data-stu-id="97532-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="97532-109">在此情況下，您必須在集區設定的每個 ITSP 閘道與每個中繼伺服器之間的連線。</span><span class="sxs-lookup"><span data-stu-id="97532-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="97532-110">您提供給服務供應商的資訊取決於您的 SIP 主幹連線類型：</span><span class="sxs-lookup"><span data-stu-id="97532-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="97532-111">對於多重通訊協定標籤切換 (MPLS) 或私人網路連線，授與 ITSP 可公開路由的 IP 位址的路由器在周邊網路 （也稱為 DMZ、 非軍事區和遮蔽式子網路）。</span><span class="sxs-lookup"><span data-stu-id="97532-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="97532-112">確認閘道或工作階段界限控制器 (SBC) 在 ITSP 可以連線到這個地址。</span><span class="sxs-lookup"><span data-stu-id="97532-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="97532-113">也可讓 ITSP 中繼伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="97532-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="97532-114">對於虛擬私人網路 (VPN) 連線，可讓 ITSP VPN 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="97532-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="97532-115">憑證考量</span><span class="sxs-lookup"><span data-stu-id="97532-115">Certificate Considerations</span></span>

<span data-ttu-id="97532-116">若要判斷您是否需要憑證，SIP 主幹，請洽詢 ITSP 有關通訊協定支援：</span><span class="sxs-lookup"><span data-stu-id="97532-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="97532-117">如果 ITSP 僅支援傳輸控制通訊協定 (TCP)，您不需要憑證。</span><span class="sxs-lookup"><span data-stu-id="97532-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="97532-118">如果 ITSP 支援傳輸層安全性 (TLS)，則 ITSP 必須提供您的憑證。</span><span class="sxs-lookup"><span data-stu-id="97532-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97532-119">SIP 適用於搭配即時傳輸通訊協定 (RTP) 或安全即時傳輸通訊協定 (SRTP)，管理中 Voice over Internet Protocol (VoIP) 通話的實際語音資料的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="97532-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="97532-120">部署程序</span><span class="sxs-lookup"><span data-stu-id="97532-120">Deployment Process</span></span>

<span data-ttu-id="97532-121">若要實作 SIP 主幹連線的 Lync 伺服器端，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="97532-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="97532-122">使用 Lync Server 拓撲產生器]，建立及設定的 SIP 網域拓撲。</span><span class="sxs-lookup"><span data-stu-id="97532-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="97532-123">如需詳細資訊，請參閱[定義和設定拓撲在拓撲產生器中的 Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)部署文件中。</span><span class="sxs-lookup"><span data-stu-id="97532-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="97532-124">使用 Lync Server Control Panel，設定新的 SIP 網域的語音路由。</span><span class="sxs-lookup"><span data-stu-id="97532-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="97532-125">如需詳細資訊，請參閱部署文件中的[Lync Server 2013 中的 Configuring trunks](lync-server-2013-configuring-trunks.md) 。</span><span class="sxs-lookup"><span data-stu-id="97532-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="97532-126">使用**Test-cspstnoutboundcall**指令程式，以測試連線。</span><span class="sxs-lookup"><span data-stu-id="97532-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="97532-127">如需詳細資訊，請參閱 Lync Server 管理命令介面文件或適用於 Lync Server 管理命令介面的協助。</span><span class="sxs-lookup"><span data-stu-id="97532-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

