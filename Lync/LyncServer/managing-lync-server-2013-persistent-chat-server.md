---
title: 管理 Lync Server 2013 常設聊天室伺服器
description: 管理 Lync Server 2013，Persistent Chat Server。
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
ms.openlocfilehash: fe5306c79c738d61b70c3dd079fb55650e6fdae9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544579"
---
# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="8febe-103">管理 Lync Server 2013 常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="8febe-103">Managing Lync Server 2013, Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8febe-104">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="8febe-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="8febe-105">您可以使用 Lync Server 2013，Persistent Chat Server，讓多位使用者參與交談，以在其上張貼和存取特定主題的內容，包括文字、連結及檔案。</span><span class="sxs-lookup"><span data-stu-id="8febe-105">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="8febe-106">儘管使用者能在工作階段期間進行即時通訊，但每個工作階段的內容會持續存在，這表示在工作階段結束後內容仍然可供使用。</span><span class="sxs-lookup"><span data-stu-id="8febe-106">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="8febe-107">Persistent 聊天室的內容主要是由簡短文字郵件所組成，雖然它可包含較長的訊息（稱為 *情景*），也包含超連結、圖釋和上傳的檔。</span><span class="sxs-lookup"><span data-stu-id="8febe-107">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8febe-108">Lync 2013 用戶端不支援檔案上傳與下載;不過，Lync Server 2013，Persistent Chat Server 仍然支援此功能。</span><span class="sxs-lookup"><span data-stu-id="8febe-108">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="8febe-109">舊版群組聊天用戶端可以開機自檢及查看檔案，但是如果相同的聊天室是透過 Lync 2013 用戶端來存取，則無法存取檔案。</span><span class="sxs-lookup"><span data-stu-id="8febe-109">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="8febe-110">聊天室的存取權是由成員資格清單控制。</span><span class="sxs-lookup"><span data-stu-id="8febe-110">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="8febe-111">任何成員都能依時間順序檢閱或全文搜尋整個聊天室記錄。</span><span class="sxs-lookup"><span data-stu-id="8febe-111">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="8febe-112">如需使用 Persistent Chat 用戶端的詳細資訊，請參閱規劃檔中的 [規劃 Lync server 2013 中的用戶端](lync-server-2013-planning-for-clients.md) ，以及部署檔中的 [lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md) 。</span><span class="sxs-lookup"><span data-stu-id="8febe-112">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8febe-113">當您為組織設定 Persistent Chat Server 時，請在部署期間指定初始設定。</span><span class="sxs-lookup"><span data-stu-id="8febe-113">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="8febe-114">不過，在某些情況下，您可能想要變更您如何實施 Persistent Chat Server 支援。</span><span class="sxs-lookup"><span data-stu-id="8febe-114">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="8febe-115">例如，您可能需要為組織內的特定小組或群組設定 Persistent Chat Server 支援和控制項的方式不同。</span><span class="sxs-lookup"><span data-stu-id="8febe-115">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="8febe-116">本節提供協助您自訂 Persistent Chat Server 部署的資訊和程式。</span><span class="sxs-lookup"><span data-stu-id="8febe-116">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="8febe-117">如需可針對 Persistent Chat Server 設定之功能的詳細資訊，請參閱規劃檔中的在 [lync server 2013 中定義組織的 Persistent Chat server 需求](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) ，以及在規劃檔、部署檔或作業檔中， [Persistent chat Server 如何在 lync server 2013 中運作](lync-server-2013-how-persistent-chat-server-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="8febe-117">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="8febe-118">如需部署 Lync Server 2013 之持久聊天伺服器的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中部署 Persistent Chat server](lync-server-2013-deploying-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="8febe-118">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8febe-119">本章節內容</span><span class="sxs-lookup"><span data-stu-id="8febe-119">In This Section</span></span>

  - [<span data-ttu-id="8febe-120">在 Lync Server 2013 中，Persistent Chat Server 的運作方式</span><span class="sxs-lookup"><span data-stu-id="8febe-120">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="8febe-121">使用類別管理 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="8febe-121">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="8febe-122">瞭解 Persistent Chat 成員資格</span><span class="sxs-lookup"><span data-stu-id="8febe-122">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="8febe-123">Persistent Chat Server 最佳作法</span><span class="sxs-lookup"><span data-stu-id="8febe-123">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="8febe-124">在 Lync Server 2013 中管理類別、聊天室及增益集</span><span class="sxs-lookup"><span data-stu-id="8febe-124">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="8febe-125">在 Lync Server 2013 中管理 Persistent Chat 使用者存取</span><span class="sxs-lookup"><span data-stu-id="8febe-125">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="8febe-126">在 Lync Server 2013 中運作及維護 Persistent Chat 系統</span><span class="sxs-lookup"><span data-stu-id="8febe-126">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

