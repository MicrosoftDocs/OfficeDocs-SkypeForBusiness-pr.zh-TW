---
title: 常設聊天室伺服器的 Lync Server 2013： 概觀
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
ms.openlocfilehash: 2cd18a5943332f8c612ba10b74317666d609d558
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="bb249-102">在 Lync Server 2013 常設聊天室伺服器的概觀</span><span class="sxs-lookup"><span data-stu-id="bb249-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb249-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="bb249-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="bb249-104">Lync Server 2013，Persistent Chat Server 可讓使用者參與多方、 主題型保留一段時間的交談。</span><span class="sxs-lookup"><span data-stu-id="bb249-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="bb249-105">Persistent Chat Server 可協助組織，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="bb249-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="bb249-106">改進地理位置分散且跨部門之小組間的通訊。</span><span class="sxs-lookup"><span data-stu-id="bb249-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="bb249-107">藉由使用常設聊天室，小組可以有效地共用資訊、 想法和決策與另一個。</span><span class="sxs-lookup"><span data-stu-id="bb249-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="bb249-108">張貼至聊天室 （論壇） 的郵件可以保存 （也就是可供使用一段時間），以便從不同的位置和部門的人員可以參與，即使當它們不同時線上。</span><span class="sxs-lookup"><span data-stu-id="bb249-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="bb249-109">當使用者連接至聊天室時，為了讓使用者在內容交談聊天室自動載入討論串 （聊天歷程記錄訊息的可設定數字）。</span><span class="sxs-lookup"><span data-stu-id="bb249-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="bb249-110">改進資訊傳達方式。</span><span class="sxs-lookup"><span data-stu-id="bb249-110">Improve information awareness.</span></span> <span data-ttu-id="bb249-111">藉由使用用戶端篩選，使用者可以定義條件 — 例如關鍵字的郵件內容或在郵件中的 「 發話 」 欄位的值-若要在 [常設聊天室立即訊息或聊天室訊息符合這些條件時收到通知。</span><span class="sxs-lookup"><span data-stu-id="bb249-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="bb249-112">如此一來，使用者可以保持以他們最感興趣的內容。</span><span class="sxs-lookup"><span data-stu-id="bb249-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="bb249-113">改進大企業的通訊。</span><span class="sxs-lookup"><span data-stu-id="bb249-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="bb249-114">輕鬆地共同作業段長時間執行主題與其他人在組織中，並提供持續性的理想的共用資訊，常設聊天室協助改善通訊。</span><span class="sxs-lookup"><span data-stu-id="bb249-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="bb249-115">緩和資訊超載的狀況。</span><span class="sxs-lookup"><span data-stu-id="bb249-115">Reduce information overload.</span></span> <span data-ttu-id="bb249-116">使用者可以追蹤聊天室和郵件的最感興趣使用用戶端篩選，並可以新增他們想要依照其連絡人清單的聊天室。</span><span class="sxs-lookup"><span data-stu-id="bb249-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="bb249-117">加強重要知識和資訊的傳播。</span><span class="sxs-lookup"><span data-stu-id="bb249-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="bb249-118">文件和連結可以併入交談中，供整個小組存取。</span><span class="sxs-lookup"><span data-stu-id="bb249-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="bb249-119">透過張貼問題至更廣大的小組，使用者可以從主題專家的回應中受益。</span><span class="sxs-lookup"><span data-stu-id="bb249-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="bb249-120">與其他資訊系統的整合可讓重要的組織資料，以輕鬆地傳達給至大型群組。</span><span class="sxs-lookup"><span data-stu-id="bb249-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="bb249-121">若要啟用 Lync Server 2013 中的聊天室，請部署 Lync Server 2013 常設聊天室。</span><span class="sxs-lookup"><span data-stu-id="bb249-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="bb249-122">如需啟用聊天室的資訊，請參閱 [常設聊天室說明在<https://go.microsoft.com/fwlink/p/?linkid=270945>。</span><span class="sxs-lookup"><span data-stu-id="bb249-122">For information about enabling chat rooms, see the Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="bb249-123">如果使用者已啟用 Lync Server，並部署 Lync Server 支援，使用者可以安裝並使用 Lync 2013 常設聊天室，提供聊天室支援。</span><span class="sxs-lookup"><span data-stu-id="bb249-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="bb249-124">如果您的組織需要遵循法規合規性，您可以選擇性地部署常設聊天室規範服務。</span><span class="sxs-lookup"><span data-stu-id="bb249-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

