---
title: Lync Server 2013： SIP 中繼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76907c1868e9fccb1a31e705c73807a8cbe501b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="127f5-102">Lync Server 2013 中的 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="127f5-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="127f5-103">_**主題上次修改日期：** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="127f5-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="127f5-104">會話初始通訊協定（SIP）是用來啟動及管理基本電話語音的語音 IP （VoIP）通訊會話，以及其他即時通訊服務，例如立即訊息、會議、目前狀態偵測及彩信.</span><span class="sxs-lookup"><span data-stu-id="127f5-104">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia.</span></span> <span data-ttu-id="127f5-105">本節提供有關實現*sip trunks*的規劃資訊，這種類型的 sip 連線延伸到您的本機網路邊界以外。</span><span class="sxs-lookup"><span data-stu-id="127f5-105">This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="127f5-106">什麼是 SIP 中繼？</span><span class="sxs-lookup"><span data-stu-id="127f5-106">What is SIP Trunking?</span></span>

<span data-ttu-id="127f5-107">SIP 幹線是一種 IP 連線，可在您的組織與防火牆以外的網際網路電話服務提供者（ITSP）之間建立 SIP 通訊連結。</span><span class="sxs-lookup"><span data-stu-id="127f5-107">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall.</span></span> <span data-ttu-id="127f5-108">通常，SIP 幹線是用來將貴組織的中心網站連線至 ITSP。</span><span class="sxs-lookup"><span data-stu-id="127f5-108">Typically, a SIP trunk is used to connect your organization’s central site to an ITSP.</span></span> <span data-ttu-id="127f5-109">在某些情況下，您也可以選擇使用 SIP 中繼將分支網站連線至 ITSP。</span><span class="sxs-lookup"><span data-stu-id="127f5-109">In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="127f5-110">SIP Trunks 與直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="127f5-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="127f5-111">[*幹線*] 一詞是從電路交換技術衍生而來。</span><span class="sxs-lookup"><span data-stu-id="127f5-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="127f5-112">它是指連接電話交換裝置的專用物理線路。</span><span class="sxs-lookup"><span data-stu-id="127f5-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="127f5-113">就像其前置任務一樣，時間分割複用（TDM） trunks，SIP trunks 是兩個獨立 SIP 網路之間的連線，即 Lync Server 2013 企業版和 ITSP。</span><span class="sxs-lookup"><span data-stu-id="127f5-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="127f5-114">與電路交換 trunks 不同，SIP trunks 是可在任何支援的 SIP 中繼連線類型上建立的虛擬連線。</span><span class="sxs-lookup"><span data-stu-id="127f5-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="127f5-115">如需支援的連線類型的詳細資料，請參閱[如何在 Lync Server 2013 中實現 SIP 中繼？](lync-server-2013-how-do-i-implement-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="127f5-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="127f5-116">另一方面，直接 SIP 連線就是不跨越本機網路邊界的 SIP 連線（也就是，它們會連線到內部網路內的公用交換電話網絡（PSTN）閘道或私人分支 exchange （PBX）。</span><span class="sxs-lookup"><span data-stu-id="127f5-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="127f5-117">如需有關如何將直接 SIP 連線搭配 Lync Server 2013 使用的詳細資訊，請參閱[Lync server 2013 中的直接 sip](lync-server-2013-direct-sip-connections.md)連線。</span><span class="sxs-lookup"><span data-stu-id="127f5-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="127f5-118">本節內容</span><span class="sxs-lookup"><span data-stu-id="127f5-118">In This Section</span></span>

  - [<span data-ttu-id="127f5-119">Lync Server 2013 中的 SIP 主幹連線概觀</span><span class="sxs-lookup"><span data-stu-id="127f5-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="127f5-120">如何在 Lync Server 2013 中實作 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="127f5-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="127f5-121">Lync Server 2013 中的 SIP 主幹連線的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="127f5-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="127f5-122">Lync Server 2013 中的分支網站 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="127f5-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="127f5-123">Lync Server 2013 的 SIP 主幹部署檢查表</span><span class="sxs-lookup"><span data-stu-id="127f5-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

