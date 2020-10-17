---
title: Lync Server 2013：公用立即訊息支援
description: Lync Server 2013：公用立即訊息支援。
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
ms.openlocfilehash: 1e071e8b79be82d865a85a9488e48dd0a4264c7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565569"
---
# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="b4ec1-103">Lync Server 2013 中的公用立即訊息支援</span><span class="sxs-lookup"><span data-stu-id="b4ec1-103">Public instant messaging support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4ec1-104">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b4ec1-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b4ec1-105">Lync Server 2013 支援使用已授權的公用立即訊息 (IM) 連線提供者，以及使用可擴展郵件和顯示狀態通訊協定 (XMPP) ，以執行一種特殊類型的同盟，讓 Lync Server 能夠使用 Lync 2013 用戶端來存取已設定的 XMPP 網域協力廠商。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-105">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="b4ec1-106">公用 IM 連線供應商支援</span><span class="sxs-lookup"><span data-stu-id="b4ec1-106">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="b4ec1-107">目前支援的公用立即訊息連線協力廠商包括：</span><span class="sxs-lookup"><span data-stu-id="b4ec1-107">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="b4ec1-108">America Online</span><span class="sxs-lookup"><span data-stu-id="b4ec1-108">America Online</span></span>

  - <span data-ttu-id="b4ec1-109">Windows Live</span><span class="sxs-lookup"><span data-stu-id="b4ec1-109">Windows Live</span></span>

  - <span data-ttu-id="b4ec1-110">雅虎\!</span><span class="sxs-lookup"><span data-stu-id="b4ec1-110">Yahoo\!</span></span>

<span data-ttu-id="b4ec1-111">若要與 Windows Live 使用者進行通訊，Lync Server 2013 支援對等 IM 和音訊和視頻通話。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-111">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="b4ec1-112">若要使用 AOL 和 Yahoo 進行通訊 \! ，Lync Server 2013 支援對等 IM。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-112">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="b4ec1-113">通訊方面，nm-server-w15-long 可支援對等 IM，但可能需要個別的授權。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-113">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="b4ec1-114">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-114">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="b4ec1-115">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="b4ec1-115">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="b4ec1-116">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-116">Messenger until the service shut down date.</span></span> <span data-ttu-id="b4ec1-117">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="b4ec1-117">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b4ec1-118">已宣告。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-118">has been announced.</span></span> <span data-ttu-id="b4ec1-119">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-119">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b4ec1-120">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="b4ec1-120">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="b4ec1-121">信使。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-121">Messenger.</span></span> <span data-ttu-id="b4ec1-122">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-122">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="b4ec1-123">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-123">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b4ec1-124">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-124">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="b4ec1-125">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="b4ec1-125">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="b4ec1-126">XMPP 同盟支援</span><span class="sxs-lookup"><span data-stu-id="b4ec1-126">XMPP Federation Support</span></span>

<span data-ttu-id="b4ec1-p105">XMPP 同盟可支援 Lync 使用者和設定好的 XMPP 網域使用者 (其使用 GTalk 之類的公用供應商) 進行通訊。這些使用者可進行的通訊包括以下：</span><span class="sxs-lookup"><span data-stu-id="b4ec1-p105">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk. Communications with these users can include the following:</span></span>

  - <span data-ttu-id="b4ec1-129">對等 IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="b4ec1-129">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="b4ec1-130">在 Lync 用戶端中建立 XMPP 同盟連絡人</span><span class="sxs-lookup"><span data-stu-id="b4ec1-130">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

