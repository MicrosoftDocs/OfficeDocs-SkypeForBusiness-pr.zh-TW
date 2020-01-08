---
title: Lync Server 2013：定義前端伺服器、立即訊息及顯示狀態的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 176b73f6d82c03e3bcdb0f2b0066752cd68f307c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="c696f-102">在 Lync Server 2013 中定義前端伺服器、立即訊息及顯示狀態的需求</span><span class="sxs-lookup"><span data-stu-id="c696f-102">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c696f-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c696f-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c696f-104">規劃 [立即訊息（IM）] 和 [目前狀態] 的主要工作是確保您的使用者擁有足夠的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="c696f-104">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="c696f-105">啟用與外部使用者的通訊</span><span class="sxs-lookup"><span data-stu-id="c696f-105">Enabling Communication with External Users</span></span>

<span data-ttu-id="c696f-106">您可以讓您的使用者與外部使用者通訊，大幅提高您在 Lync 伺服器投資的益處。</span><span class="sxs-lookup"><span data-stu-id="c696f-106">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="c696f-107">外部使用者可以包括：</span><span class="sxs-lookup"><span data-stu-id="c696f-107">External users can include:</span></span>

  - <span data-ttu-id="c696f-108">\*\*\*\*    如果您組織的使用者是在您的防火牆外工作，且正在使用其膝上型電腦或其他 Lync Server 裝置，則可供遠端使用者使用。</span><span class="sxs-lookup"><span data-stu-id="c696f-108">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="c696f-109">**同盟使用者**   與公司合作的使用者，您可與其他人同時執行 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="c696f-109">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="c696f-110">若要讓您的使用者能夠輕鬆地與這些使用者聯繫，您可以建立與這些公司的聯盟關聯。</span><span class="sxs-lookup"><span data-stu-id="c696f-110">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="c696f-111">\*\*\*\*    公用 IM 服務的公用使用者使用者，例如由 Internet 服務、Yahoo\!和 AOL 的 Windows Live 網路所提供的 IM 服務，以及使用可擴展訊息和目前狀態通訊協定（XMPP）的提供者和伺服器（例如 Google 交談）的使用者。</span><span class="sxs-lookup"><span data-stu-id="c696f-111">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c696f-112">請注意，對於使用 Windows Live、AOL 和 Yahoo！的公用 IM 連線，可能需要個別的授權</span><span class="sxs-lookup"><span data-stu-id="c696f-112">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="c696f-113">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="c696f-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="c696f-114">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="c696f-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c696f-115">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="c696f-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="c696f-116">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="c696f-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c696f-117">已公佈。</span><span class="sxs-lookup"><span data-stu-id="c696f-117">has been announced.</span></span> <span data-ttu-id="c696f-118">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="c696f-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="c696f-119">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="c696f-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c696f-120">名單.</span><span class="sxs-lookup"><span data-stu-id="c696f-120">Messenger.</span></span> <span data-ttu-id="c696f-121">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="c696f-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="c696f-122">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="c696f-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c696f-123">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="c696f-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c696f-124">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="c696f-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="c696f-125">若要啟用任何一種或所有案例，您必須部署邊緣伺服器，以協助您在 Lync Server 部署與外部使用者之間進行安全通訊。</span><span class="sxs-lookup"><span data-stu-id="c696f-125">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="c696f-126">貴組織的遠端使用者和聯盟組織中的使用者將能夠彼此查看其目前狀態並使用 IM 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c696f-126">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="c696f-127">如需有關如何啟用與外部使用者的通訊的詳細資訊，請參閱規劃檔中的[Lync Server 2013 規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="c696f-127">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="c696f-128">封存 IM 內容</span><span class="sxs-lookup"><span data-stu-id="c696f-128">Archiving IM Content</span></span>

<span data-ttu-id="c696f-129">如果您的組織必須遵循合規性規範，Lync Server 提供您可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="c696f-129">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="c696f-130">您可以使用 [封存] 來封存貴組織中所有使用者的 IM 訊息內容，或只針對您指定的特定使用者封存 IM 訊息的內容。</span><span class="sxs-lookup"><span data-stu-id="c696f-130">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="c696f-131">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的存檔規劃](lync-server-2013-planning-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="c696f-131">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="c696f-132">如果您也已部署 Microsoft Exchange Server 2013，您可以將 Exchange 資料的存檔與 Lync 伺服器資料的存檔整合，然後使用單一工具來搜尋這兩種類型的已歸檔資料。</span><span class="sxs-lookup"><span data-stu-id="c696f-132">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="c696f-133">如需詳細資訊，請參閱設定[Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 歸檔](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="c696f-133">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

