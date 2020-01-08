---
title: Lync Server 2013：常設聊天室伺服器概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a744f4eb251bbbacc8b1b5f4c2a5978a9689f225
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="54655-102">Lync Server 2013 中的常設聊天室伺服器概觀</span><span class="sxs-lookup"><span data-stu-id="54655-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54655-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="54655-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="54655-104">Lync Server 2013，Persistent 聊天伺服器可讓使用者參與多方、依時間保留的、以主題為基礎的交談。</span><span class="sxs-lookup"><span data-stu-id="54655-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="54655-105">持續聊天伺服器可協助您的組織執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="54655-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="54655-106">改善地理位置分散且跨職能團隊之間的溝通。</span><span class="sxs-lookup"><span data-stu-id="54655-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="54655-107">透過使用持續聊天，小組可以高效地與其他人共用資訊、想法和決策。</span><span class="sxs-lookup"><span data-stu-id="54655-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="54655-108">張貼到聊天室（討論論壇）的郵件可以持續（也就是可在一段時間內提供），讓來自不同位置和部門的人員都可以參與，即使他們不在線上也一樣。</span><span class="sxs-lookup"><span data-stu-id="54655-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="54655-109">當使用者連線到聊天室時，系統會自動在聊天室中載入 backchat （可設定的聊天記錄訊息數），為使用者提供交談的內容。</span><span class="sxs-lookup"><span data-stu-id="54655-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="54655-110">改善資訊認識。</span><span class="sxs-lookup"><span data-stu-id="54655-110">Improve information awareness.</span></span> <span data-ttu-id="54655-111">使用者可以使用用戶端篩選器，在郵件內容中定義關鍵字，或在郵件中的「寄件者」欄位值中定義條件，以便在永久聊天立即訊息或聊天室訊息中滿足這些條件時接收通知。</span><span class="sxs-lookup"><span data-stu-id="54655-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="54655-112">如此一來，使用者就能隨時掌握最新感興趣的內容。</span><span class="sxs-lookup"><span data-stu-id="54655-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="54655-113">改善與其延伸組織的溝通。</span><span class="sxs-lookup"><span data-stu-id="54655-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="54655-114">您可以輕鬆地與組織中的其他人員共同作業主題，以及提供共用資訊的持久位置，持續聊天協助改善溝通。</span><span class="sxs-lookup"><span data-stu-id="54655-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="54655-115">減少資訊超載。</span><span class="sxs-lookup"><span data-stu-id="54655-115">Reduce information overload.</span></span> <span data-ttu-id="54655-116">使用者可以使用用戶端篩選來追蹤聊天室和最感興趣的訊息，並可在其連絡人清單中新增他們想要追蹤的聊天室。</span><span class="sxs-lookup"><span data-stu-id="54655-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="54655-117">增加重要知識與資訊的散佈。</span><span class="sxs-lookup"><span data-stu-id="54655-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="54655-118">您可以在交談中加入檔和連結，以供所有團隊存取。</span><span class="sxs-lookup"><span data-stu-id="54655-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="54655-119">透過將問題張貼到更廣泛的小組，使用者可以透過主題專家的回應獲益。</span><span class="sxs-lookup"><span data-stu-id="54655-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="54655-120">與其他資訊系統整合能讓重要的組織資料輕鬆地傳達給大型群組。</span><span class="sxs-lookup"><span data-stu-id="54655-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="54655-121">若要在 Lync Server 2013 中啟用聊天室，請部署 Lync Server 2013 持續聊天。</span><span class="sxs-lookup"><span data-stu-id="54655-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="54655-122">如需啟用聊天室的相關資訊，請參閱持續聊天說明<http://go.microsoft.com/fwlink/p/?linkid=270945>。</span><span class="sxs-lookup"><span data-stu-id="54655-122">For information about enabling chat rooms, see the Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="54655-123">如果使用者已啟用 Lync Server，且已部署 Lync Server 支援，則使用者可以安裝並使用 Lync 2013 持續聊天來提供聊天室支援。</span><span class="sxs-lookup"><span data-stu-id="54655-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="54655-124">如果您的組織必須遵循合規性規範，您可以選擇部署持久的聊天合規性服務。</span><span class="sxs-lookup"><span data-stu-id="54655-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

