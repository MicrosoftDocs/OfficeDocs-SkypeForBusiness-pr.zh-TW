---
title: Lync Server 2013 IM 及顯示狀態
description: Lync Server 2013 IM 及顯示狀態。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d04f0ee6decc03db1a6b5aa44cfedd7515c2d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573279"
---
# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="105e9-103">Lync Server 2013 中的 IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="105e9-103">IM and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="105e9-104">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="105e9-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="105e9-105">立即訊息 (IM) 和目前狀態會自動安裝在任何 Lync Server 部署中。</span><span class="sxs-lookup"><span data-stu-id="105e9-105">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="105e9-106">*「目前狀態」* 資訊可讓使用者在正確的時間使用正確的通訊方式連絡同事，進而產生更具生產力的工作環境。</span><span class="sxs-lookup"><span data-stu-id="105e9-106">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="105e9-107">使用者的目前狀態是資訊的集合，包括顯示狀態、通訊意願、其他記事 (如位置及狀態)，以及使用者的連絡方式。</span><span class="sxs-lookup"><span data-stu-id="105e9-107">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="105e9-108">Lync Server 中的目前狀態已增強，包含圖片、位置資訊，以及豐富的顯示狀態集，除了基本狀態（如「可用」、「忙碌」和「在會議中」）之外，還包括「離線工作」、「請勿打擾」及「是「正確」等基本狀態。</span><span class="sxs-lookup"><span data-stu-id="105e9-108">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="105e9-109">系統管理員也可以定義自訂的組織特有目前狀態。</span><span class="sxs-lookup"><span data-stu-id="105e9-109">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="105e9-p102">連絡人管理及使用者存取選項可讓使用者控制其他人可以看到的資訊。使用者可以設定不同的連絡人層級，而各層級都可以檢視不同的目前狀態資訊層級。</span><span class="sxs-lookup"><span data-stu-id="105e9-p102">Contact management and user access options enable users to control what information others can see. Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="105e9-p103">只要查看連絡人清單，使用者就可以快速找到他們需要知道的所有資訊。簡易彩色圖示可指出其他使用者的目前狀態，也會顯示圖片及位置。</span><span class="sxs-lookup"><span data-stu-id="105e9-p103">By simply looking at a Contacts list, users can find everything they need to know at a glance. Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="105e9-114">透過 Lync Server 與其他產品（如 Outlook 和 SharePoint）之間的整合，每當出現連絡人的名稱時（例如電子郵件訊息或小組網站），也會顯示狀態和連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="105e9-114">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="105e9-115">此外，如果您部署 Exchange 2013，Lync Server 和 Exchange 2013 可以共用統一連絡人存放區，可供任何產品的用戶端存取。</span><span class="sxs-lookup"><span data-stu-id="105e9-115">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="105e9-116">在 Lync Server 中使用立即訊息，使用者就可以透過及時的資訊快速訊息對方。</span><span class="sxs-lookup"><span data-stu-id="105e9-116">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="105e9-117">如果您願意，您的使用者也可以與公用 IM 網路的使用者通訊，例如 MSN/Windows Live、Yahoo \! 和 AOL。</span><span class="sxs-lookup"><span data-stu-id="105e9-117">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="105e9-118">請注意，與 Windows Live、AOL 和 Yahoo 的公用 IM 連線可能需要個別授權\!</span><span class="sxs-lookup"><span data-stu-id="105e9-118">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="105e9-119">Lync Server 也包含可延伸的訊息和顯示狀態通訊協定 (XMPP) 相容性，所以您的使用者可以使用 XMPP 服務（如 Google 交談）的使用者來交換 IM 訊息和目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="105e9-119">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="105e9-120">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="105e9-120">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="105e9-121">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="105e9-121">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="105e9-122">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="105e9-122">Messenger until the service shut down date.</span></span> <span data-ttu-id="105e9-123">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="105e9-123">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="105e9-124">已宣告。</span><span class="sxs-lookup"><span data-stu-id="105e9-124">has been announced.</span></span> <span data-ttu-id="105e9-125">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="105e9-125">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="105e9-126">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="105e9-126">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="105e9-127">信使。</span><span class="sxs-lookup"><span data-stu-id="105e9-127">Messenger.</span></span> <span data-ttu-id="105e9-128">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="105e9-128">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="105e9-129">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="105e9-129">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="105e9-130">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="105e9-130">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="105e9-131">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="105e9-131">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="105e9-132">交談記錄可讓使用者追蹤舊的 IM 交談，以及擷取數月前透過 IM 進行通訊的資訊。</span><span class="sxs-lookup"><span data-stu-id="105e9-132">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="105e9-133">Persistent Chat 功能可讓使用者加入一段時間內的多方、主題型交談。</span><span class="sxs-lookup"><span data-stu-id="105e9-133">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="105e9-134">張貼至聊天室 (討論論壇) 的訊息可以持續存在 (也就是長期可用)，因此來自不同位置和部門的人員都可以參與，即使並非同時在線上。</span><span class="sxs-lookup"><span data-stu-id="105e9-134">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="105e9-135">如果您的組織必須遵循規範要求，則可以部署訊息封存功能來封存組織中所有使用者的 IM 訊息內容，或只封存所指定特定使用者的立即訊息內容。</span><span class="sxs-lookup"><span data-stu-id="105e9-135">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="105e9-136">如果您也部署 Exchange 2013，您的 IM 封存可以與 Exchange 的 In-Place 保留功能整合，為您的相容性提供單一的管理經驗。</span><span class="sxs-lookup"><span data-stu-id="105e9-136">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

