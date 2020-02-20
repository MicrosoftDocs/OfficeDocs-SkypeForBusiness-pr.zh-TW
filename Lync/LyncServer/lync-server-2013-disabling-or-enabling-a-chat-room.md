---
title: Lync Server 2013： 停用或啟用聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96ad55bd6396cdac9b30441eb8b41bebaba834ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="8be12-102">停用或啟用 Lync Server 2013 中的聊天室</span><span class="sxs-lookup"><span data-stu-id="8be12-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8be12-103">_**上次修改主題：** 2014年-02-05_</span><span class="sxs-lookup"><span data-stu-id="8be12-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="8be12-104">如果不再相關主題的常設聊天室，您可以讓聊天室使用者無法使用藉由停用它。</span><span class="sxs-lookup"><span data-stu-id="8be12-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="8be12-105">停用聊天室時，所有成員會立即都中斷連線會議室。</span><span class="sxs-lookup"><span data-stu-id="8be12-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="8be12-106">停用聊天室之後，使用者無法將其重新加入或聊天室搜尋中尋找。</span><span class="sxs-lookup"><span data-stu-id="8be12-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="8be12-107">常設聊天室管理員可以稍後再啟用已停用的聊天室。</span><span class="sxs-lookup"><span data-stu-id="8be12-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="8be12-108">停用聊天室時，其中的成員資格清單與其他設定仍會保留。</span><span class="sxs-lookup"><span data-stu-id="8be12-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="8be12-109">如果您重新啟用會議室，您不需要以手動方式重新建立設定。</span><span class="sxs-lookup"><span data-stu-id="8be12-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="8be12-110">如果仍然存在該聊天室的歷程記錄 （聊天室歷程記錄保存性是選擇性的設定套用至該類別內的所有聊天室類別上; 預設值是它保存，但可以藉由將類別的**啟用聊天歷程記錄**設定為 false 關閉），此內容會保留時已停用聊天室。</span><span class="sxs-lookup"><span data-stu-id="8be12-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="8be12-111">不過，該內容不會出現在搜尋期間聊天室仍會保留在停用狀態的時間。</span><span class="sxs-lookup"><span data-stu-id="8be12-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="8be12-112">如果您稍後啟用該聊天室，使用者可以搜尋聊天室被停用之前已張貼的訊息。</span><span class="sxs-lookup"><span data-stu-id="8be12-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="8be12-113">如需停用，並使用 Windows PowerShell 命令列介面來啟用聊天室的詳細資訊，請參閱[使用 Windows PowerShell cmdlet 的 Configuring Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 「 聊天室管理 」。</span><span class="sxs-lookup"><span data-stu-id="8be12-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="8be12-114">若要停用聊天室，請使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="8be12-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="8be12-115">若要啟用聊天室，請停用屬性設為 False:</span><span class="sxs-lookup"><span data-stu-id="8be12-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="8be12-116">請注意，無法啟用或停用使用 Lync Server Control Panel 聊天室。</span><span class="sxs-lookup"><span data-stu-id="8be12-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="8be12-117">如需設定聊天室的詳細資訊，請參閱部署文件中的[Lync Server 2013 中的 Configure rooms](lync-server-2013-configure-rooms.md) 。</span><span class="sxs-lookup"><span data-stu-id="8be12-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

