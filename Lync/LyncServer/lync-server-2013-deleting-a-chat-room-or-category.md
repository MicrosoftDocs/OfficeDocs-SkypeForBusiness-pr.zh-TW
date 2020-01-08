---
title: Lync Server 2013：刪除聊天室或類別
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f64b89abd0b3266d2be52e300458ceabf3f9b915
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="27e6d-102">在 Lync Server 2013 中刪除聊天室或類別</span><span class="sxs-lookup"><span data-stu-id="27e6d-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27e6d-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="27e6d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="27e6d-104">您可以刪除持久的聊天室。</span><span class="sxs-lookup"><span data-stu-id="27e6d-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="27e6d-105">如果您有不再使用的聊天室，您可以將它停用。</span><span class="sxs-lookup"><span data-stu-id="27e6d-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="27e6d-106">如需詳細資訊，請參閱[在 Lync Server 2013 中停用或啟用](lync-server-2013-disabling-or-enabling-a-chat-room.md)聊天室。</span><span class="sxs-lookup"><span data-stu-id="27e6d-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="27e6d-107">持續性聊天管理員可以查詢停用的聊天室，而且可以使用 Windows PowerShell Cmdlet 來定期清除及永久刪除聊天室，請**CsPersistentChatRoom**。</span><span class="sxs-lookup"><span data-stu-id="27e6d-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="27e6d-108">您可以刪除類別。</span><span class="sxs-lookup"><span data-stu-id="27e6d-108">Categories can be deleted.</span></span> <span data-ttu-id="27e6d-109">不過，若要刪除類別，您必須先刪除其底下的所有聊天室，或將聊天室移至新的類別，並將空的類別刪除。</span><span class="sxs-lookup"><span data-stu-id="27e6d-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="27e6d-110">持續聊天伺服器不允許您刪除包含聊天室的類別。</span><span class="sxs-lookup"><span data-stu-id="27e6d-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="27e6d-111">如需詳細資訊，請參閱[在 Lync Server 2013 將聊天室從一個類別移至另一個類別](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)。</span><span class="sxs-lookup"><span data-stu-id="27e6d-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="27e6d-112">如需使用 Windows PowerShell 命令列介面刪除空類別的詳細資訊，請參閱[使用 Windows powershell Cmdlet 來設定持久聊天伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。</span><span class="sxs-lookup"><span data-stu-id="27e6d-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="27e6d-113">如需聊天室和類別的詳細資訊，請參閱在[Lync server 2013 中設定會議室](lync-server-2013-configure-rooms.md)，並在部署檔中[設定 lync server 2013](lync-server-2013-configure-categories.md)中的類別。</span><span class="sxs-lookup"><span data-stu-id="27e6d-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

