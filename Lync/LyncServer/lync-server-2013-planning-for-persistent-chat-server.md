---
title: Lync Server 2013：規劃常設聊天室伺服器
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
ms.openlocfilehash: 363008c910c53f5b1b951bf57ba8663b4d4d970d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="c5e2c-102">在 Lync Server 2013 中規劃常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="c5e2c-102">Planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5e2c-103">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="c5e2c-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="c5e2c-104">您可以使用 Lync Server 2013、持續聊天伺服器來讓多名使用者參與交談，以便在其中張貼及存取特定主題的相關內容，包括文字、連結和檔案。</span><span class="sxs-lookup"><span data-stu-id="c5e2c-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="c5e2c-105">雖然使用者可以在會話中即時進行通訊，但每個會話的內容都是永久性的，這表示在會話結束之後，仍可使用它。</span><span class="sxs-lookup"><span data-stu-id="c5e2c-105">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="c5e2c-106">本節說明 Lync Server 2013 （持久聊天伺服器部署）中的規劃考慮，包括定義需求、識別元件和支援的拓撲，以及部署建議。</span><span class="sxs-lookup"><span data-stu-id="c5e2c-106">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c5e2c-107">本節內容</span><span class="sxs-lookup"><span data-stu-id="c5e2c-107">In This Section</span></span>

  - [<span data-ttu-id="c5e2c-108">Lync Server 2013 中的常設聊天室伺服器概觀</span><span class="sxs-lookup"><span data-stu-id="c5e2c-108">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="c5e2c-109">在 Lync Server 2013 中，持久聊天伺服器的運作方式</span><span class="sxs-lookup"><span data-stu-id="c5e2c-109">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="c5e2c-110">在 Lync Server 2013 中定義組織的常設聊天室伺服器需求</span><span class="sxs-lookup"><span data-stu-id="c5e2c-110">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="c5e2c-111">Lync Server 2013 中持續聊天伺服器的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="c5e2c-111">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="c5e2c-112">Lync Server 2013 中持續聊天伺服器的技術需求</span><span class="sxs-lookup"><span data-stu-id="c5e2c-112">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="c5e2c-113">在 Lync Server 2013 中設定常設聊天室伺服器的系統與基礎結構</span><span class="sxs-lookup"><span data-stu-id="c5e2c-113">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="c5e2c-114">Lync Server 2013 中的常設聊天室伺服器的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="c5e2c-114">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

