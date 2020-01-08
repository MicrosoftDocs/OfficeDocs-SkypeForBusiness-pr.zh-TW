---
title: Lync Server 2013：設定聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08b7cb0146f96b151af021a63ef97a485a0a9dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="ae995-102">在 Lync Server 2013 中設定聊天室</span><span class="sxs-lookup"><span data-stu-id="ae995-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae995-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ae995-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ae995-104">設定持續性聊天室通常是由使用者或其他中心團隊使用 Windows PowerShell 命令列介面來處理;系統管理員通常不會管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="ae995-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="ae995-105">不過，如果您必須建立及管理聊天室，您可以使用 Windows PowerShell 命令列介面，或將自己新增為聊天室的成員，然後使用 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="ae995-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="ae995-106">如需使用 Windows PowerShell 命令列介面來設定聊天室的詳細資料，請參閱[使用 Windows powershell Cmdlet 來設定持久聊天伺服器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的「會議室管理」。</span><span class="sxs-lookup"><span data-stu-id="ae995-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="ae995-107">管理聊天室中的資料</span><span class="sxs-lookup"><span data-stu-id="ae995-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="ae995-108">持續聊天伺服器可讓使用者透過將訊息張貼到持久聊天室來共同作業。</span><span class="sxs-lookup"><span data-stu-id="ae995-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="ae995-109">資料會保留在伺服器上，而聊天室的成員可以存取資料，包括歷史資料。</span><span class="sxs-lookup"><span data-stu-id="ae995-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="ae995-110">不過，擁有不同角色的使用者會有不同的方式存取永久性資料，如下列清單所述。</span><span class="sxs-lookup"><span data-stu-id="ae995-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="ae995-111">系統管理員可以從任何聊天室刪除較舊的內容（例如，在特定日期之前發佈的內容），讓資料庫不會變得太大。</span><span class="sxs-lookup"><span data-stu-id="ae995-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="ae995-112">或者，他們可以移除或取代被視為不適用於特定聊天室的郵件。</span><span class="sxs-lookup"><span data-stu-id="ae995-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="ae995-113">使用者（包括郵件作者）無法刪除任何聊天室中的內容。</span><span class="sxs-lookup"><span data-stu-id="ae995-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="ae995-114">聊天室管理員可以停用會議室，但無法刪除會議室。</span><span class="sxs-lookup"><span data-stu-id="ae995-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="ae995-115">只有系統管理員才能在已建立聊天室後刪除聊天室。</span><span class="sxs-lookup"><span data-stu-id="ae995-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="ae995-116">刪除郵件時，您無法復原該動作。</span><span class="sxs-lookup"><span data-stu-id="ae995-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="ae995-117">不過，如果有備份，就可以還原已刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="ae995-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="ae995-118">如果啟用持續性聊天規範伺服器，舊的訊息會保留在合規性資料庫中。</span><span class="sxs-lookup"><span data-stu-id="ae995-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae995-119">此聊天室資料使用量適用于 Lync Server 2013、持續聊天伺服器 API 應用程式，但涉及管理員角色的情況除外。</span><span class="sxs-lookup"><span data-stu-id="ae995-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="ae995-120">永久聊天伺服器 API 無法用來執行任何管理員的操作。</span><span class="sxs-lookup"><span data-stu-id="ae995-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="ae995-121">您必須在 Lync Server 管理命令介面中執行這些作業。</span><span class="sxs-lookup"><span data-stu-id="ae995-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

