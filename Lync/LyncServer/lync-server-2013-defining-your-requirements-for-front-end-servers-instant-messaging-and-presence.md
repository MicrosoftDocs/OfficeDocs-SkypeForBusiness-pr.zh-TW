---
title: Lync Server 2013：定義前端伺服器、立即訊息及顯示狀態的需求
description: Lync Server 2013：定義前端伺服器、立即訊息及顯示狀態的需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923132b32d5aef80191b19a7b85c3f17276e5946
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545369"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="93b1d-103">在 Lync Server 2013 中定義前端伺服器、立即訊息及顯示狀態的需求</span><span class="sxs-lookup"><span data-stu-id="93b1d-103">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93b1d-104">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="93b1d-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="93b1d-105">規劃立即訊息 (IM) 和目前狀態的主要工作，是要確保您有足夠的前端伺服器供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="93b1d-105">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="93b1d-106">啟用與外部使用者的通訊</span><span class="sxs-lookup"><span data-stu-id="93b1d-106">Enabling Communication with External Users</span></span>

<span data-ttu-id="93b1d-107">您可以讓使用者與外部使用者通訊，以大幅提高在 Lync Server 中投資的效益。</span><span class="sxs-lookup"><span data-stu-id="93b1d-107">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="93b1d-108">外部使用者包括：</span><span class="sxs-lookup"><span data-stu-id="93b1d-108">External users can include:</span></span>

  - <span data-ttu-id="93b1d-109">**遠端使用者**    組織本身的使用者，當他們在防火牆外工作時使用其膝上型電腦或其他 Lync Server 裝置。</span><span class="sxs-lookup"><span data-stu-id="93b1d-109">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="93b1d-110">同盟**使用者**    公司的使用者，您也可以使用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="93b1d-110">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="93b1d-111">為了方便您的使用者輕鬆連絡這些使用者，您可以和這些公司建立同盟關係。</span><span class="sxs-lookup"><span data-stu-id="93b1d-111">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="93b1d-112">**公用使用者**    公用 IM 服務的使用者，例如網際網路服務、Yahoo 和 AOL 的 Windows Live 網路所提供的 IM 服務， \! 以及使用可擴展郵件和顯示狀態通訊協定 (XMPP) （如 Google 交談）的提供者和伺服器使用者。</span><span class="sxs-lookup"><span data-stu-id="93b1d-112">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="93b1d-113">等公用 IM 進行連線可能需要個別授權</span><span class="sxs-lookup"><span data-stu-id="93b1d-113">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="93b1d-114">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="93b1d-114">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="93b1d-115">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="93b1d-115">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="93b1d-116">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="93b1d-116">Messenger until the service shut down date.</span></span> <span data-ttu-id="93b1d-117">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="93b1d-117">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="93b1d-118">已宣告。</span><span class="sxs-lookup"><span data-stu-id="93b1d-118">has been announced.</span></span> <span data-ttu-id="93b1d-119">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="93b1d-119">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="93b1d-120">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="93b1d-120">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="93b1d-121">信使。</span><span class="sxs-lookup"><span data-stu-id="93b1d-121">Messenger.</span></span> <span data-ttu-id="93b1d-122">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="93b1d-122">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="93b1d-123">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="93b1d-123">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="93b1d-124">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="93b1d-124">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="93b1d-125">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="93b1d-125">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="93b1d-126">若要啟用任何或所有上述案例，您必須部署 Edge Server，以協助啟用 Lync Server 部署與外部使用者之間的安全通訊。</span><span class="sxs-lookup"><span data-stu-id="93b1d-126">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="93b1d-127">貴組織的遠端使用者和同盟組織的使用者，將能夠看到彼此的目前狀態，並使用 IM 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="93b1d-127">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="93b1d-128">如需啟用與外部使用者通訊的詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的外部使用者存取](lync-server-2013-planning-for-external-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="93b1d-128">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="93b1d-129">封存 IM 內容</span><span class="sxs-lookup"><span data-stu-id="93b1d-129">Archiving IM Content</span></span>

<span data-ttu-id="93b1d-130">當您的組織必須遵循法規遵從性規定時，Lync Server 會提供您可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="93b1d-130">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="93b1d-131">您可以使用封存為組織中的所有使用者或您指定的特定使用者封存 IM 訊息的內容。</span><span class="sxs-lookup"><span data-stu-id="93b1d-131">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="93b1d-132">如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的](lync-server-2013-planning-for-archiving.md) 封存。</span><span class="sxs-lookup"><span data-stu-id="93b1d-132">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="93b1d-133">如果您也部署 Microsoft Exchange Server 2013，您可以將 Exchange 資料的封存與 Lync Server 資料的封存整合，並使用單一工具來搜尋這兩種類型的封存資料。</span><span class="sxs-lookup"><span data-stu-id="93b1d-133">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="93b1d-134">如需詳細資訊，請參閱設定 [Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="93b1d-134">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

