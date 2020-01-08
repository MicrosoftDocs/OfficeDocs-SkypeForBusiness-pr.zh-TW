---
title: Lync Server 2013：管理類別、聊天室及增益集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2870d83d463866e07afdffab7c0a840bb2686928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="76902-102">在 Lync Server 2013 中管理類別、聊天室及增益集</span><span class="sxs-lookup"><span data-stu-id="76902-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76902-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="76902-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="76902-104">在 Lync Server 2013 的 [控制台] 中，或使用 Windows PowerShell Cmdlet 時，持續性聊天系統管理員可以使用**持續性聊天**頁面來建立類別與增益集。若要管理持續聊天室，管理員可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76902-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="76902-105">或者，如果持續性聊天系統管理員也是 SIP 啟用的，他們可以使用 Lync 用戶端來啟動網頁，以建立和管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="76902-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="76902-106">下列主題說明如何建立及使用類別和聊天室。</span><span class="sxs-lookup"><span data-stu-id="76902-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="76902-107">本節內容</span><span class="sxs-lookup"><span data-stu-id="76902-107">In This Section</span></span>

  - [<span data-ttu-id="76902-108">在 Lync Server 2013 中建立或編輯新類別</span><span class="sxs-lookup"><span data-stu-id="76902-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="76902-109">在 Lync Server 2013 中建立或編輯新聊天室</span><span class="sxs-lookup"><span data-stu-id="76902-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="76902-110">在 Lync Server 2013 為聊天室建立新增益集</span><span class="sxs-lookup"><span data-stu-id="76902-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="76902-111">在 Lync Server 2013 中設定能夠在視聽中心聊天室張貼訊息的人員</span><span class="sxs-lookup"><span data-stu-id="76902-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="76902-112">在 Lync Server 2013 中停用或啟用聊天室</span><span class="sxs-lookup"><span data-stu-id="76902-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="76902-113">在 Lync Server 2013 中將聊天室從某個類別移到另一個類別</span><span class="sxs-lookup"><span data-stu-id="76902-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="76902-114">在 Lync Server 2013 中刪除聊天室或類別</span><span class="sxs-lookup"><span data-stu-id="76902-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="76902-115">在 Lync Server 2013 中刪除訊息或清除過時的訊息</span><span class="sxs-lookup"><span data-stu-id="76902-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

