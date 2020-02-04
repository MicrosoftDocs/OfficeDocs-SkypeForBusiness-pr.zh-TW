---
title: Lync Server 2013：Public Instant Messaging 支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e3207d1a7a12f4db379e4d58615cffdfb45036
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="d95aa-102">Lync Server 2013 中的 Public Instant Messaging 支援</span><span class="sxs-lookup"><span data-stu-id="d95aa-102">Public instant messaging support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d95aa-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="d95aa-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="d95aa-104">Lync Server 2013 支援使用授權公用立即訊息（IM）連線提供者，以及使用可擴展訊息和目前狀態通訊協定（XMPP）來實現一種特殊類型的同盟，讓 Lync Server 存取已設定的 XMPP使用 Lync 2013 用戶端的網域合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="d95aa-104">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="d95aa-105">公用 IM 連線提供者支援</span><span class="sxs-lookup"><span data-stu-id="d95aa-105">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="d95aa-106">目前支援的公用立即訊息連線性合作夥伴包括：</span><span class="sxs-lookup"><span data-stu-id="d95aa-106">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="d95aa-107">美洲線上</span><span class="sxs-lookup"><span data-stu-id="d95aa-107">America Online</span></span>

  - <span data-ttu-id="d95aa-108">Windows Live</span><span class="sxs-lookup"><span data-stu-id="d95aa-108">Windows Live</span></span>

  - <span data-ttu-id="d95aa-109">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="d95aa-109">Yahoo\!</span></span>

<span data-ttu-id="d95aa-110">若要與 Windows Live 使用者進行通訊，Lync Server 2013 支援對等 IM 和音訊與視頻通話。</span><span class="sxs-lookup"><span data-stu-id="d95aa-110">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="d95aa-111">若要與 AOL 和 Yahoo\!通訊，Lync Server 2013 支援對等 IM。</span><span class="sxs-lookup"><span data-stu-id="d95aa-111">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="d95aa-112">可能需要個別的授權。</span><span class="sxs-lookup"><span data-stu-id="d95aa-112">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d95aa-113">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="d95aa-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="d95aa-114">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="d95aa-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d95aa-115">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="d95aa-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="d95aa-116">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="d95aa-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d95aa-117">已公佈。</span><span class="sxs-lookup"><span data-stu-id="d95aa-117">has been announced.</span></span> <span data-ttu-id="d95aa-118">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="d95aa-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="d95aa-119">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="d95aa-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d95aa-120">名單.</span><span class="sxs-lookup"><span data-stu-id="d95aa-120">Messenger.</span></span> <span data-ttu-id="d95aa-121">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="d95aa-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="d95aa-122">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="d95aa-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d95aa-123">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="d95aa-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d95aa-124">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="d95aa-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="d95aa-125">XMPP 同盟支援</span><span class="sxs-lookup"><span data-stu-id="d95aa-125">XMPP Federation Support</span></span>

<span data-ttu-id="d95aa-126">XMPP 同盟支援使用公用提供者的已設定 XMPP 網域使用者進行 Lync 使用者通訊（例如 GTalk）。</span><span class="sxs-lookup"><span data-stu-id="d95aa-126">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk.</span></span> <span data-ttu-id="d95aa-127">與這些使用者的通訊可能包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d95aa-127">Communications with these users can include the following:</span></span>

  - <span data-ttu-id="d95aa-128">對等 IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="d95aa-128">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="d95aa-129">在 Lync 用戶端中建立 XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="d95aa-129">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

