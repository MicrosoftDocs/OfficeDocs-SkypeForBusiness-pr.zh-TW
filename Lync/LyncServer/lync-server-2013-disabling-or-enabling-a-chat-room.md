---
title: Lync Server 2013：停用或啟用聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89862b4f7e38a637fa183641f8cdc75e0491379
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="9f841-102">在 Lync Server 2013 中停用或啟用聊天室</span><span class="sxs-lookup"><span data-stu-id="9f841-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f841-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="9f841-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="9f841-104">如果永久聊天室的主題已不再相關，您可以停用聊天室，讓使用者無法使用該聊天室。</span><span class="sxs-lookup"><span data-stu-id="9f841-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="9f841-105">停用聊天室時，所有成員都會立即中斷與聊天室的連線。</span><span class="sxs-lookup"><span data-stu-id="9f841-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="9f841-106">停用聊天室之後，使用者就無法在聊天室搜尋中重新加入或尋找。</span><span class="sxs-lookup"><span data-stu-id="9f841-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="9f841-107">停用聊天室可在稍後由持續聊天管理員啟用。</span><span class="sxs-lookup"><span data-stu-id="9f841-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="9f841-108">如果聊天室停用，則會保留其成員資格清單及其他設定。</span><span class="sxs-lookup"><span data-stu-id="9f841-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="9f841-109">如果您再次啟用聊天室，就不需要手動重新建立設定。</span><span class="sxs-lookup"><span data-stu-id="9f841-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="9f841-110">如果聊天室的歷程記錄持續存在（聊天室記錄暫留是在類別中套用至所有聊天室的選擇性設定，預設值是它會保留，但若要將類別的 [**啟用聊天記錄**] 設定為 false，則會在停用聊天室時保留該內容。</span><span class="sxs-lookup"><span data-stu-id="9f841-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="9f841-111">不過，在聊天室保持在停用狀態時，搜尋中不會顯示該內容。</span><span class="sxs-lookup"><span data-stu-id="9f841-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="9f841-112">如果您稍後啟用聊天室，使用者就可以搜尋在停用聊天室之前所張貼的訊息。</span><span class="sxs-lookup"><span data-stu-id="9f841-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="9f841-113">如需使用 Windows PowerShell 命令列介面來停用或啟用聊天室的詳細資料，請參閱[使用 Windows powershell Cmdlet 來設定持久聊天伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。</span><span class="sxs-lookup"><span data-stu-id="9f841-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="9f841-114">若要停用聊天室，請使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="9f841-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="9f841-115">若要啟用聊天室，請將 Disabled 屬性設定為 False：</span><span class="sxs-lookup"><span data-stu-id="9f841-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="9f841-116">請注意，您無法使用 Lync Server [控制台] 來啟用或停用聊天室。</span><span class="sxs-lookup"><span data-stu-id="9f841-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="9f841-117">如需有關設定聊天室的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定會議室](lync-server-2013-configure-rooms.md)。</span><span class="sxs-lookup"><span data-stu-id="9f841-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

