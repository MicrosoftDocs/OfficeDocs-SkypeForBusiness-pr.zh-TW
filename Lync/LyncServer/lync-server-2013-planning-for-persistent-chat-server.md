---
title: Lync Server 2013：規劃 Persistent Chat Server
description: Lync Server 2013：規劃 Persistent Chat Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Persistent Chat Server
ms:assetid: 57b2f574-234e-4a5a-bb78-8823369ba79e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398381(v=OCS.15)
ms:contentKeyID: 48184190
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6944437492a1eee718a614369201c3548c95864a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549299"
---
# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="c6f40-103">在 Lync Server 2013 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="c6f40-103">Planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6f40-104">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="c6f40-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="c6f40-105">您可以使用 Lync Server 2013，Persistent Chat Server，讓多位使用者參與交談，以在其上張貼和存取特定主題的內容，包括文字、連結及檔案。</span><span class="sxs-lookup"><span data-stu-id="c6f40-105">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="c6f40-106">雖然使用者可以在會話中即時進行通訊，但每個會話的內容都是持續性的，這表示當會話結束後，它仍可繼續使用。</span><span class="sxs-lookup"><span data-stu-id="c6f40-106">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="c6f40-107">本節說明 Lync Server 2013、Persistent Chat Server 部署的規劃考慮，包括定義需求、識別元件和支援的拓撲，以及部署建議。</span><span class="sxs-lookup"><span data-stu-id="c6f40-107">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6f40-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c6f40-108">In This Section</span></span>

  - [<span data-ttu-id="c6f40-109">Lync Server 2013 中的 Persistent Chat Server 概述</span><span class="sxs-lookup"><span data-stu-id="c6f40-109">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="c6f40-110">在 Lync Server 2013 中，Persistent Chat Server 的運作方式</span><span class="sxs-lookup"><span data-stu-id="c6f40-110">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="c6f40-111">在 Lync Server 2013 中定義組織對 Persistent Chat Server 的需求</span><span class="sxs-lookup"><span data-stu-id="c6f40-111">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="c6f40-112">Lync Server 2013 中持久聊天伺服器的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="c6f40-112">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="c6f40-113">Lync Server 2013 中 Persistent Chat Server 的技術需求</span><span class="sxs-lookup"><span data-stu-id="c6f40-113">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="c6f40-114">在 Lync Server 2013 中設定 Persistent Chat Server 的系統和基礎結構</span><span class="sxs-lookup"><span data-stu-id="c6f40-114">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="c6f40-115">Lync Server 2013 中 Persistent Chat Server 的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="c6f40-115">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

