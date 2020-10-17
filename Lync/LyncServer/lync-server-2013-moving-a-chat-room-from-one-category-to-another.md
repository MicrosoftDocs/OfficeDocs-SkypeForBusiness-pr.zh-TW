---
title: Lync Server 2013：將聊天室從某個類別移到另一個類別
description: Lync Server 2013：將聊天室從某個類別移到另一個類別。
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
ms.openlocfilehash: 4066732a90a94414b55d6a567fde0d496e4faf13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541997"
---
# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="f9264-103">在 Lync Server 2013 中將聊天室從某個類別移到另一個類別</span><span class="sxs-lookup"><span data-stu-id="f9264-103">Moving a chat room from one category to another in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9264-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f9264-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f9264-105">建議您在建立聊天室後，不要變更 Persistent 聊天室的類別。</span><span class="sxs-lookup"><span data-stu-id="f9264-105">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="f9264-106">不過，如果聊天室管理員擁有其他類別的「建立者」\*\*\*\* 權限，即可將一個類別中的聊天室移到另一個類別。</span><span class="sxs-lookup"><span data-stu-id="f9264-106">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="f9264-107">未刪除或重新建立聊天室。</span><span class="sxs-lookup"><span data-stu-id="f9264-107">The room is not deleted and recreated.</span></span> <span data-ttu-id="f9264-108">這是與資料庫的關聯出現變更。</span><span class="sxs-lookup"><span data-stu-id="f9264-108">It is a change of association within the database.</span></span>

<span data-ttu-id="f9264-p102">變更聊天室類別的機會應該很少。類別會決定允許的聊天室成員資格，因此，將聊天室移到另一個類別時，將清除新類別不再支援的所有系統存取控制清單 (SACL)。例如，如果使用者原先是聊天室的成員，但不再是新類別中的 **AllowedMember**，將修改聊天室成員資格，並且從聊天室移除該使用者。</span><span class="sxs-lookup"><span data-stu-id="f9264-p102">Changing a chat room category should be done rarely. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="f9264-112">如需使用 Windows PowerShell 命令列介面移動聊天室的詳細資訊，請參閱 [使用 windows PowerShell Cmdlet 設定 Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。</span><span class="sxs-lookup"><span data-stu-id="f9264-112">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="f9264-113">如需有關設定聊天室的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定聊天室](lync-server-2013-configure-rooms.md) 。</span><span class="sxs-lookup"><span data-stu-id="f9264-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

