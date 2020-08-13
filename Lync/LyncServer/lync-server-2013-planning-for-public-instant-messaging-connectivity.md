---
title: Lync Server 2013：規劃公用立即訊息連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52bc8a563a45e75b01932ee716df90f1cf2ca7da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="1bb9b-102">在 Lync Server 2013 中規劃公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="1bb9b-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bb9b-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="1bb9b-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="1bb9b-104">公用立即訊息連線是同盟的類別，設定為允許您的內部及外部 Lync Server 2013 使用者從下列任何專案新增連絡人：</span><span class="sxs-lookup"><span data-stu-id="1bb9b-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="1bb9b-105">信使連絡人</span><span class="sxs-lookup"><span data-stu-id="1bb9b-105">Messenger contacts</span></span>

  - <span data-ttu-id="1bb9b-106">雅虎\!</span><span class="sxs-lookup"><span data-stu-id="1bb9b-106">Yahoo\!</span></span> <span data-ttu-id="1bb9b-107">接觸</span><span class="sxs-lookup"><span data-stu-id="1bb9b-107">contacts</span></span>

  - <span data-ttu-id="1bb9b-108">北美線上 (AOL) 連絡人</span><span class="sxs-lookup"><span data-stu-id="1bb9b-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="1bb9b-109">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 (PIC USL) 已不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="1bb9b-110">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="1bb9b-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1bb9b-111">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="1bb9b-112">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="1bb9b-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1bb9b-113">已宣告。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-113">has been announced.</span></span> <span data-ttu-id="1bb9b-114">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="1bb9b-115">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的每一使用者、每月訂閱授權。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="1bb9b-116">信使。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-116">Messenger.</span></span> <span data-ttu-id="1bb9b-117">Microsoft 提供此服務的能力已因 Yahoo！的支援而產生，不會更新的基準合約。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="1bb9b-118">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="1bb9b-119">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="1bb9b-120">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以透過 IM 和語音來抵達數百個人的人員。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1bb9b-121">這個同盟類別需要下列規劃考慮：</span><span class="sxs-lookup"><span data-stu-id="1bb9b-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="1bb9b-122">Windows Live Messenger 使用者除了立即訊息之外，還可以與 Lync Server 2013 使用者進行對等音訊/視覺通訊。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="1bb9b-123">您的 Edge Server 必須符合特定埠和通訊協定的需求。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="1bb9b-124">如需詳細資訊，請參閱[決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="1bb9b-125">在規劃及部署提供同盟之典型 Edge Server 的情況下，Yahoo 立即訊息沒有獨特的需求。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="1bb9b-126">北美洲線上要求指派給 Access Edge service 的 Edge Server 憑證具有用戶端增強型金鑰使用方式 (EKU) 。</span><span class="sxs-lookup"><span data-stu-id="1bb9b-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1bb9b-127">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1bb9b-127">In This Section</span></span>

  - [<span data-ttu-id="1bb9b-128">Lync Server 2013 中的憑證摘要-公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="1bb9b-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="1bb9b-129">Lync Server 2013 中的埠摘要-公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="1bb9b-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="1bb9b-130">[Lync Server 2013 中的 DNS 摘要-公用立即訊息連線](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1bb9b-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

