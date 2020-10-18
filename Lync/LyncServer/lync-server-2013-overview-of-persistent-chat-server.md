---
title: Lync Server 2013： Persistent Chat Server 的簡介
description: Lync Server 2013： Persistent Chat Server 的簡介。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbcb396522611aca52bd2093f2fd49f376341356
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577309"
---
# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="8c4da-103">Lync Server 2013 中的 Persistent Chat Server 概述</span><span class="sxs-lookup"><span data-stu-id="8c4da-103">Overview of Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c4da-104">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="8c4da-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="8c4da-105">Lync Server 2013，Persistent Chat Server 可讓使用者加入一段時間內的多方、主題型交談。</span><span class="sxs-lookup"><span data-stu-id="8c4da-105">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="8c4da-106">Persistent Chat Server 可以協助貴組織執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="8c4da-106">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="8c4da-107">改進地理位置分散且跨部門之小組間的通訊。</span><span class="sxs-lookup"><span data-stu-id="8c4da-107">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="8c4da-108">透過使用持續性聊天，小組可以有效率地與其他人共用資訊、想法和決策。</span><span class="sxs-lookup"><span data-stu-id="8c4da-108">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="8c4da-109">張貼至聊天室的郵件 (討論論壇) 可以保留 (也就是在) 的時間內可用，所以來自不同位置和部門的人員可以加入，即使他們不在線上也是一樣。</span><span class="sxs-lookup"><span data-stu-id="8c4da-109">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="8c4da-110">當使用者連線至聊天室時，backchat (會自動載入聊天室的可設定聊天記錄) 郵件的數量，以提供使用者談話的內容。</span><span class="sxs-lookup"><span data-stu-id="8c4da-110">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="8c4da-111">改進資訊傳達方式。</span><span class="sxs-lookup"><span data-stu-id="8c4da-111">Improve information awareness.</span></span> <span data-ttu-id="8c4da-112">透過使用用戶端篩選器，使用者可以定義條件，例如郵件內容中的關鍵字，或郵件中的「寄件者」欄位中的值，以便在持續性聊天立即訊息或聊天室訊息中符合這些條件時，接收通知。</span><span class="sxs-lookup"><span data-stu-id="8c4da-112">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="8c4da-113">這樣一來，使用者就可以隨時掌握最新的內容。</span><span class="sxs-lookup"><span data-stu-id="8c4da-113">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="8c4da-114">改進大企業的通訊。</span><span class="sxs-lookup"><span data-stu-id="8c4da-114">Improve communication with their extended organization.</span></span> <span data-ttu-id="8c4da-115">透過輕鬆地與組織中的其他人合作，並提供共用資訊的持久位置，持續聊天可協助改善通訊。</span><span class="sxs-lookup"><span data-stu-id="8c4da-115">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="8c4da-116">緩和資訊超載的狀況。</span><span class="sxs-lookup"><span data-stu-id="8c4da-116">Reduce information overload.</span></span> <span data-ttu-id="8c4da-117">使用者可以使用用戶端篩選器來追蹤聊天室和最感興趣的訊息，也可以新增想要追蹤其連絡人清單的聊天室。</span><span class="sxs-lookup"><span data-stu-id="8c4da-117">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="8c4da-118">加強重要知識和資訊的傳播。</span><span class="sxs-lookup"><span data-stu-id="8c4da-118">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="8c4da-119">文件和連結可以併入交談中，供整個小組存取。</span><span class="sxs-lookup"><span data-stu-id="8c4da-119">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="8c4da-120">透過張貼問題至更廣大的小組，使用者可以從主題專家的回應中受益。</span><span class="sxs-lookup"><span data-stu-id="8c4da-120">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="8c4da-121">與其他資訊系統整合，可讓重要的組織資料輕鬆地傳遞給大型群組。</span><span class="sxs-lookup"><span data-stu-id="8c4da-121">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="8c4da-122">若要在 Lync Server 2013 中啟用聊天室，請部署 Lync Server 2013 持久聊天。</span><span class="sxs-lookup"><span data-stu-id="8c4da-122">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="8c4da-123">如需啟用聊天室的詳細資訊，請參閱的持續聊天協助 <https://go.microsoft.com/fwlink/p/?linkid=270945> 。</span><span class="sxs-lookup"><span data-stu-id="8c4da-123">For information about enabling chat rooms, see the Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="8c4da-124">如果已啟用 Lync Server 的使用者，且已部署 Lync Server 支援，使用者可以安裝和使用 Lync 2013 持續聊天以提供聊天室支援。</span><span class="sxs-lookup"><span data-stu-id="8c4da-124">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="8c4da-125">如果您的組織需要遵循相容性規定，您可以選擇性地部署 Persistent Chat 合規性服務。</span><span class="sxs-lookup"><span data-stu-id="8c4da-125">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

