---
title: Lync Server 2013：將聊天室從某個類別移到另一個類別
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f9774e53321ff6fe667b3b8c8dcfe0e78bcdaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="da6c4-102">在 Lync Server 2013 中將聊天室從某個類別移到另一個類別</span><span class="sxs-lookup"><span data-stu-id="da6c4-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da6c4-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="da6c4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="da6c4-104">我們建議您在建立聊天室之後，不要變更持續聊天室的類別。</span><span class="sxs-lookup"><span data-stu-id="da6c4-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="da6c4-105">不過，如果聊天室管理員有其他類別的建立**者**許可權，他/她就可以將會議室從一個類別移到另一個類別。</span><span class="sxs-lookup"><span data-stu-id="da6c4-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="da6c4-106">不會刪除並重新建立聊天室。</span><span class="sxs-lookup"><span data-stu-id="da6c4-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="da6c4-107">變更是資料庫中的關聯。</span><span class="sxs-lookup"><span data-stu-id="da6c4-107">It is a change of association within the database.</span></span>

<span data-ttu-id="da6c4-108">變更聊天室類別時，請不要這麼做。</span><span class="sxs-lookup"><span data-stu-id="da6c4-108">Changing a chat room category should be done rarely.</span></span> <span data-ttu-id="da6c4-109">類別會決定聊天室的允許成員資格，因此當聊天室移至另一個類別時，新類別不再支援的所有系統存取控制清單（Sacl）都將清除。</span><span class="sxs-lookup"><span data-stu-id="da6c4-109">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="da6c4-110">例如，如果使用者是聊天室的成員，且已不再是新類別中的**AllowedMember** ，則會修改聊天室成員資格，並將該使用者從聊天室中移除。</span><span class="sxs-lookup"><span data-stu-id="da6c4-110">For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="da6c4-111">如需使用 Windows PowerShell 命令列介面移動聊天室的詳細資料，請參閱[使用 Windows powershell Cmdlet 來設定持久聊天伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。</span><span class="sxs-lookup"><span data-stu-id="da6c4-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="da6c4-112">如需有關設定聊天室的詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定會議室](lync-server-2013-configure-rooms.md)。</span><span class="sxs-lookup"><span data-stu-id="da6c4-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

