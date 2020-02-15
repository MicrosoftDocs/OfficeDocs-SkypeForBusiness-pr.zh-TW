---
title: Lync Server 2013： 管理類別、 聊天室及增益集
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
ms.openlocfilehash: 6c1fcd4422ca855e7247c57d07887b9df20ea695
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="9d326-102">管理類別、 聊天室及 Lync Server 2013 中增益集</span><span class="sxs-lookup"><span data-stu-id="9d326-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d326-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="9d326-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9d326-104">在 Lync Server 2013 控制台中，或使用 Windows PowerShell cmdlet，常設聊天室系統管理員可以使用 [**常設聊天室**] 頁面上建立類別和增益集。管理常設聊天室，系統管理員可以使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9d326-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="9d326-105">或者，如果常設聊天室系統管理員也是已啟用 SIP 的他們可以使用 Lync 用戶端啟動網頁以建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="9d326-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="9d326-106">下列主題說明如何建立及使用類別和聊天室。</span><span class="sxs-lookup"><span data-stu-id="9d326-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9d326-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="9d326-107">In This Section</span></span>

  - [<span data-ttu-id="9d326-108">建立或編輯 Lync Server 2013 中新的類別</span><span class="sxs-lookup"><span data-stu-id="9d326-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="9d326-109">建立或編輯新聊天室 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="9d326-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="9d326-110">在 Lync Server 2013 中建立新的增益集為聊天室</span><span class="sxs-lookup"><span data-stu-id="9d326-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="9d326-111">設定可以在 Lync Server 2013 中視聽中心聊天室中張貼訊息</span><span class="sxs-lookup"><span data-stu-id="9d326-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="9d326-112">停用或啟用 Lync Server 2013 中的聊天室</span><span class="sxs-lookup"><span data-stu-id="9d326-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="9d326-113">將聊天室從某個類別移至 Lync Server 2013 中的另一個</span><span class="sxs-lookup"><span data-stu-id="9d326-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="9d326-114">刪除聊天室或 Lync Server 2013 中的類別</span><span class="sxs-lookup"><span data-stu-id="9d326-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="9d326-115">刪除訊息或清除過時 Lync Server 2013 中的訊息</span><span class="sxs-lookup"><span data-stu-id="9d326-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

