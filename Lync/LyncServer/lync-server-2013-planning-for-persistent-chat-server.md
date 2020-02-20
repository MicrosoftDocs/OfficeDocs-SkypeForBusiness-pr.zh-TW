---
title: Lync Server 2013： 規劃常設聊天室伺服器
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
ms.openlocfilehash: cda48e5ab61af965d719298533227c8e473d9a15
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="be22c-102">規劃 Lync Server 2013 中的常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="be22c-102">Planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be22c-103">_**主題上次修改日期：** 2012年-10-11_</span><span class="sxs-lookup"><span data-stu-id="be22c-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="be22c-104">您可以使用 Lync Server 2013，Persistent Chat Server 啟用多位使用者可以加入對話行列他們張貼及存取關於特定主題，包括文字、 連結及檔案的內容。</span><span class="sxs-lookup"><span data-stu-id="be22c-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="be22c-105">雖然使用者可以進行即時通訊工作階段期間，每個工作階段的內容為持續性，這表示它會繼續執行的工作階段結束之後才能使用。</span><span class="sxs-lookup"><span data-stu-id="be22c-105">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="be22c-106">本節說明在 Lync Server 2013，Persistent Chat Server 部署，包括定義需求、 識別元件與支援的拓撲，以及部署建議的規劃考量。</span><span class="sxs-lookup"><span data-stu-id="be22c-106">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="be22c-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="be22c-107">In This Section</span></span>

  - [<span data-ttu-id="be22c-108">在 Lync Server 2013 常設聊天室伺服器的概觀</span><span class="sxs-lookup"><span data-stu-id="be22c-108">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="be22c-109">Persistent Chat Server 在 Lync Server 2013 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="be22c-109">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - <span data-ttu-id="be22c-110">[定義 Lync Server 2013 中的 [for Persistent Chat Server 貴組織的需求](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="be22c-110">[Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)</span></span>

  - [<span data-ttu-id="be22c-111">Persistent Chat Server in Lync Server 2013 的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="be22c-111">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="be22c-112">Persistent Chat Server in Lync Server 2013 的技術需求</span><span class="sxs-lookup"><span data-stu-id="be22c-112">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="be22c-113">Persistent Chat Server in Lync Server 2013 的設定系統與基礎結構</span><span class="sxs-lookup"><span data-stu-id="be22c-113">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="be22c-114">Persistent Chat Server in Lync Server 2013 的部署檢查表</span><span class="sxs-lookup"><span data-stu-id="be22c-114">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

