---
title: Lync Server 2013：管理類別、聊天室及增益集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f9281b7987bea7425589efc649c1c29a8482770
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505870"
---
# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="5d927-102">在 Lync Server 2013 中管理類別、聊天室及增益集</span><span class="sxs-lookup"><span data-stu-id="5d927-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d927-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5d927-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5d927-104">在 [Lync Server 2013 控制台] 中，或是使用 Windows PowerShell Cmdlet 時，Persistent Chat 系統管理員可以使用 [ **持續聊天** ] 頁面來建立類別和增益集。若要管理 Persistent 聊天室，系統管理員可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5d927-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5d927-105">或者，如果該 Persistent Chat 系統管理員也 SIP-enabled，則可以使用 Lync 用戶端來啟動網頁，以建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="5d927-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="5d927-106">下列主題說明如何建立及使用類別和聊天室。</span><span class="sxs-lookup"><span data-stu-id="5d927-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5d927-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="5d927-107">In This Section</span></span>

  - [<span data-ttu-id="5d927-108">在 Lync Server 2013 中建立或編輯新類別</span><span class="sxs-lookup"><span data-stu-id="5d927-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="5d927-109">在 Lync Server 2013 中建立或編輯新聊天室</span><span class="sxs-lookup"><span data-stu-id="5d927-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="5d927-110">在 Lync Server 2013 中為聊天室建立新的增益集</span><span class="sxs-lookup"><span data-stu-id="5d927-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="5d927-111">在 Lync Server 2013 中設定可以在視聽中心聊天室中張貼訊息的人員</span><span class="sxs-lookup"><span data-stu-id="5d927-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="5d927-112">在 Lync Server 2013 中停用或啟用聊天室</span><span class="sxs-lookup"><span data-stu-id="5d927-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="5d927-113">在 Lync Server 2013 中將聊天室從某個類別移到另一個類別</span><span class="sxs-lookup"><span data-stu-id="5d927-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="5d927-114">在 Lync Server 2013 中刪除聊天室或類別</span><span class="sxs-lookup"><span data-stu-id="5d927-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="5d927-115">在 Lync Server 2013 中刪除訊息或清除過時的訊息</span><span class="sxs-lookup"><span data-stu-id="5d927-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

