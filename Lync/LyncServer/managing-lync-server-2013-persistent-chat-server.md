---
title: 管理 Lync Server 2013 常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 067e24a7e1534e355e39f80b6a3fda90e059be14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="7b925-102">管理 Lync Server 2013 常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="7b925-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b925-103">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="7b925-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="7b925-104">您可以使用 Lync Server 2013、持續聊天伺服器來讓多名使用者參與交談，以便在其中張貼及存取特定主題的相關內容，包括文字、連結和檔案。</span><span class="sxs-lookup"><span data-stu-id="7b925-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="7b925-105">雖然使用者可以在會話中即時進行通訊，但每個會話的內容都是永久性的，這表示在會話結束之後，仍可使用它。</span><span class="sxs-lookup"><span data-stu-id="7b925-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="7b925-106">持久聊天室的內容主要由簡短的文字訊息所組成，雖然它可以包含較長的訊息（稱為*故事*），以及超連結、圖釋和上傳的檔。</span><span class="sxs-lookup"><span data-stu-id="7b925-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b925-107">Lync 2013 用戶端不支援檔案上傳和下載;不過，Lync Server 2013 （持久聊天伺服器）仍支援它。</span><span class="sxs-lookup"><span data-stu-id="7b925-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="7b925-108">舊版群組聊天用戶端可以張貼及查看檔案，但如果是透過 Lync 2013 用戶端存取相同的聊天室，就無法存取檔案。</span><span class="sxs-lookup"><span data-stu-id="7b925-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="7b925-109">聊天室的存取權是由成員資格清單所控制。</span><span class="sxs-lookup"><span data-stu-id="7b925-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="7b925-110">整個聊天室記錄都可供任何成員進行依時間檢查或全文搜尋。</span><span class="sxs-lookup"><span data-stu-id="7b925-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="7b925-111">如需使用持續聊天用戶端的詳細資訊，請參閱在規劃檔中[規劃 Lync server 2013 中的用戶端](lync-server-2013-planning-for-clients.md)，以及在部署檔中的[lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="7b925-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="7b925-112">當您為您的組織設定持續聊天伺服器時，您會在部署期間指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="7b925-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="7b925-113">不過，有時您可能會想要變更實現持久聊天伺服器支援的方式。</span><span class="sxs-lookup"><span data-stu-id="7b925-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="7b925-114">例如，您可能需要為貴組織內的特定團隊或群組設定持續聊天伺服器支援及控制。</span><span class="sxs-lookup"><span data-stu-id="7b925-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="7b925-115">本節提供的資訊和程式可協助您自訂持續聊天伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="7b925-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="7b925-116">如需可針對持久聊天伺服器設定的功能和功能的詳細資訊，請參閱在規劃檔中[定義貴組織在 Lync server 2013 中的持續聊天伺服器需求](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)，以及[永久性聊天伺服器在 lync server 2013 中的運作方式](lync-server-2013-how-persistent-chat-server-works.md)（在規劃檔、部署檔或作業檔中）。</span><span class="sxs-lookup"><span data-stu-id="7b925-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="7b925-117">如需有關部署 Lync Server 2013 持續聊天伺服器的詳細資訊，請參閱部署檔中的[Lync server 2013 中的部署持久聊天伺服器](lync-server-2013-deploying-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7b925-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7b925-118">本節內容</span><span class="sxs-lookup"><span data-stu-id="7b925-118">In This Section</span></span>

  - [<span data-ttu-id="7b925-119">在 Lync Server 2013 中，持久聊天伺服器的運作方式</span><span class="sxs-lookup"><span data-stu-id="7b925-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="7b925-120">使用類別以管理常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="7b925-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="7b925-121">瞭解持續聊天的成員資格</span><span class="sxs-lookup"><span data-stu-id="7b925-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="7b925-122">常設聊天室伺服器最佳做法</span><span class="sxs-lookup"><span data-stu-id="7b925-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="7b925-123">在 Lync Server 2013 中管理類別、聊天室及增益集</span><span class="sxs-lookup"><span data-stu-id="7b925-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="7b925-124">在 Lync Server 2013 中管理常設聊天室使用者存取</span><span class="sxs-lookup"><span data-stu-id="7b925-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="7b925-125">在 Lync Server 2013 中操作和維護常設聊天室系統</span><span class="sxs-lookup"><span data-stu-id="7b925-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

