---
title: Lync Server 2013 IM 和目前狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18eb3d4a7fa5daaa59817d2eefde7af3a8e3f494
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="618f9-102">Lync Server 2013 中的 IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="618f9-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="618f9-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="618f9-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="618f9-104">[立即訊息（IM）] 和 [目前狀態] 會自動安裝在任何 Lync Server 部署中。</span><span class="sxs-lookup"><span data-stu-id="618f9-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="618f9-105">目前*狀態*資訊可讓使用者在適當的時間以適當的溝通方式來處理同事，以提高工作環境的效率。</span><span class="sxs-lookup"><span data-stu-id="618f9-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="618f9-106">使用者的目前狀態是資訊的集合，包括可用性、溝通意願、其他記事（例如位置與狀態），以及如何聯繫使用者。</span><span class="sxs-lookup"><span data-stu-id="618f9-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="618f9-107">Lync Server 中的目前狀態會隨著圖片、位置資訊以及豐富的目前狀態，包括「已提供」、「請勿打擾」和「立即返回」等基本狀態（例如「可用」、「忙碌」」和「在會議中」）。</span><span class="sxs-lookup"><span data-stu-id="618f9-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="618f9-108">系統管理員也可以定義自訂的組織特定的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="618f9-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="618f9-109">連絡人管理與使用者存取選項可讓使用者控制其他人可以看到的資訊。</span><span class="sxs-lookup"><span data-stu-id="618f9-109">Contact management and user access options enable users to control what information others can see.</span></span> <span data-ttu-id="618f9-110">使用者可以設定不同層級的連絡人，每一個都可以查看不同層級的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="618f9-110">Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="618f9-111">只要查看連絡人清單，使用者就能一目了然地找到他們需要瞭解的所有專案。</span><span class="sxs-lookup"><span data-stu-id="618f9-111">By simply looking at a Contacts list, users can find everything they need to know at a glance.</span></span> <span data-ttu-id="618f9-112">簡單的彩色圖示會指出其他使用者的目前狀態，同時也會顯示圖片和位置。</span><span class="sxs-lookup"><span data-stu-id="618f9-112">Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="618f9-113">隨著 Lync Server 與其他產品（例如 Outlook 與 SharePoint）之間的整合，只要出現連絡人的名稱（例如在電子郵件訊息中或在小組網站上），也會顯示狀態和連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="618f9-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="618f9-114">此外，如果您部署 Exchange 2013，Lync Server 和 Exchange 2013 可以共用整合的連絡人存放區，這可由任何一種產品的用戶端存取。</span><span class="sxs-lookup"><span data-stu-id="618f9-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="618f9-115">在 Lync Server 中使用立即訊息，使用者就可以使用及時的資訊彼此快速地傳送訊息。</span><span class="sxs-lookup"><span data-stu-id="618f9-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="618f9-116">如果您想要的話，您的使用者也可以與公用 IM 網路（例如 MSN/Windows Live、Yahoo\!和 AOL）的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="618f9-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="618f9-117">請注意，對於使用 Windows Live、AOL 和 Yahoo 的公用 IM 連線，可能需要個別的授權\!</span><span class="sxs-lookup"><span data-stu-id="618f9-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="618f9-118">Lync 伺服器也包括可擴展的訊息和目前狀態通訊協定（XMPP）相容性，因此您的使用者可以與 Google 交談等 XMPP 服務的使用者交換 IM 訊息和目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="618f9-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="618f9-119">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="618f9-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="618f9-120">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="618f9-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="618f9-121">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="618f9-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="618f9-122">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="618f9-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="618f9-123">已公佈。</span><span class="sxs-lookup"><span data-stu-id="618f9-123">has been announced.</span></span> <span data-ttu-id="618f9-124">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="618f9-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="618f9-125">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="618f9-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="618f9-126">名單.</span><span class="sxs-lookup"><span data-stu-id="618f9-126">Messenger.</span></span> <span data-ttu-id="618f9-127">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="618f9-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="618f9-128">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="618f9-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="618f9-129">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="618f9-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="618f9-130">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="618f9-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="618f9-131">[交談記錄] 可讓使用者追蹤舊的 IM 交談，並檢索可能已透過 IM 月前訊息所傳達的資訊。</span><span class="sxs-lookup"><span data-stu-id="618f9-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="618f9-132">[持續聊天] 功能可讓使用者參與在一段時間內持續存在的多方主題交談。</span><span class="sxs-lookup"><span data-stu-id="618f9-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="618f9-133">張貼到聊天室的訊息（討論論壇）可能是永久性的（也就是隨著時間提供），因此來自不同位置和部門的人員都可以參與，即使他們不是同時在線上。</span><span class="sxs-lookup"><span data-stu-id="618f9-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="618f9-134">如果您的組織必須遵循合規性規範，您可以部署郵件封存功能，以封存您組織中所有使用者的立即訊息內容，或只針對您指定的特定使用者封存立即訊息的內容。</span><span class="sxs-lookup"><span data-stu-id="618f9-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="618f9-135">如果您同時部署 Exchange 2013，您的 IM 封存可以與 Exchange 的就地保留功能整合，為您的合規性提供單一的管理體驗。</span><span class="sxs-lookup"><span data-stu-id="618f9-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

