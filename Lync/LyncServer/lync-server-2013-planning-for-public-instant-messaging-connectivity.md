---
title: Lync Server 2013：規劃公用立即訊息連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="5333e-102">規劃 Lync Server 2013 中的公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="5333e-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5333e-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="5333e-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="5333e-104">公用立即訊息連線是一種聯盟類別，並設定為允許您的內部和外部 Lync Server 2013 使用者從下列任何專案新增連絡人：</span><span class="sxs-lookup"><span data-stu-id="5333e-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="5333e-105">信使連絡人</span><span class="sxs-lookup"><span data-stu-id="5333e-105">Messenger contacts</span></span>

  - <span data-ttu-id="5333e-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="5333e-106">Yahoo\!</span></span> <span data-ttu-id="5333e-107">聯絡</span><span class="sxs-lookup"><span data-stu-id="5333e-107">contacts</span></span>

  - <span data-ttu-id="5333e-108">美洲線上（AOL）連絡人</span><span class="sxs-lookup"><span data-stu-id="5333e-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="5333e-109">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（PIC USL）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="5333e-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="5333e-110">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="5333e-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5333e-111">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="5333e-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="5333e-112">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="5333e-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5333e-113">已公佈。</span><span class="sxs-lookup"><span data-stu-id="5333e-113">has been announced.</span></span> <span data-ttu-id="5333e-114">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="5333e-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="5333e-115">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟所需的每個使用者、每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="5333e-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5333e-116">名單.</span><span class="sxs-lookup"><span data-stu-id="5333e-116">Messenger.</span></span> <span data-ttu-id="5333e-117">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，不會更新的底層合約。</span><span class="sxs-lookup"><span data-stu-id="5333e-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="5333e-118">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="5333e-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5333e-119">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="5333e-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5333e-120">Skype 同盟將會新增到此清單，讓 Lync 使用者能夠透過 IM 和語音來取得成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="5333e-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="5333e-121">此同盟類別需要下列規劃考慮：</span><span class="sxs-lookup"><span data-stu-id="5333e-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="5333e-122">除了立即訊息之外，Windows Live Messenger 使用者也可以與 Lync Server 2013 使用者進行對等音訊/視覺通訊。</span><span class="sxs-lookup"><span data-stu-id="5333e-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="5333e-123">您的邊緣伺服器必須符合特定的埠和通訊協定需求。</span><span class="sxs-lookup"><span data-stu-id="5333e-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="5333e-124">如需詳細資訊，請參閱[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5333e-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="5333e-125">Yahoo [立即訊息] 沒有任何獨特的需求，除了在提供同盟的一般邊緣伺服器規劃和部署中通常所使用的情況。</span><span class="sxs-lookup"><span data-stu-id="5333e-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="5333e-126">美洲線上要求指派給存取邊緣服務的 Edge 伺服器憑證具有用戶端增強型金鑰用法（EKU）。</span><span class="sxs-lookup"><span data-stu-id="5333e-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5333e-127">本節內容</span><span class="sxs-lookup"><span data-stu-id="5333e-127">In This Section</span></span>

  - [<span data-ttu-id="5333e-128">證書摘要-Lync Server 2013 中的公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="5333e-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="5333e-129">埠摘要-Lync Server 2013 中的公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="5333e-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="5333e-130">[DNS 摘要-Lync Server 2013 中的公用立即訊息連線](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5333e-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

