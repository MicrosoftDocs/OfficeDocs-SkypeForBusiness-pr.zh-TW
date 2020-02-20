---
title: Lync Server 2013： 設定聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3521e533dee1ff995fae417b8a7f29a75a77ac63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="6882d-102">Lync Server 2013 中設定聊天室</span><span class="sxs-lookup"><span data-stu-id="6882d-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6882d-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="6882d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="6882d-104">設定常設聊天室通常用於由使用者或其他中央小組使用 Windows PowerShell 命令列介面;系統管理員通常不會管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="6882d-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="6882d-105">不過，如果您必須建立及管理聊天室，您可以使用 Windows PowerShell 命令列介面，或者將自己新增為成員的聊天室並使用 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="6882d-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="6882d-106">如需使用 Windows PowerShell 命令列介面來設定聊天室的詳細資訊，請參閱[使用 Windows PowerShell cmdlet 的 Configuring Persistent Chat Server](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 「 聊天室管理 」。</span><span class="sxs-lookup"><span data-stu-id="6882d-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="6882d-107">管理聊天室中的資料</span><span class="sxs-lookup"><span data-stu-id="6882d-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="6882d-108">Persistent Chat Server 可讓使用者藉由將訊息張貼到的常設聊天室共同作業。</span><span class="sxs-lookup"><span data-stu-id="6882d-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="6882d-109">將資料保存在伺服器上，和聊天室的成員可以存取資料，包括歷程資料。</span><span class="sxs-lookup"><span data-stu-id="6882d-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="6882d-110">不過，具有不同角色的使用者都有不同的存取權的保存的資料，下列清單中所述。</span><span class="sxs-lookup"><span data-stu-id="6882d-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="6882d-111">系統管理員可以從任何聊天室時亦可讓資料庫變得太大刪除舊內容 （例如，在特定日期之前已張貼的內容）。</span><span class="sxs-lookup"><span data-stu-id="6882d-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="6882d-112">或者，他們可以移除或取代會被視為不適用於特定聊天室的訊息。</span><span class="sxs-lookup"><span data-stu-id="6882d-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="6882d-113">使用者，包括訊息作者無法刪除任何聊天室中的內容。</span><span class="sxs-lookup"><span data-stu-id="6882d-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="6882d-114">聊天室管理員可以停用聊天室，但是無法刪除聊天室。</span><span class="sxs-lookup"><span data-stu-id="6882d-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="6882d-115">已建立之後，只有系統管理員可以刪除聊天室。</span><span class="sxs-lookup"><span data-stu-id="6882d-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="6882d-116">刪除郵件時，您無法復原的動作。</span><span class="sxs-lookup"><span data-stu-id="6882d-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="6882d-117">不過，如果沒有備份，可以還原已刪除的郵件。</span><span class="sxs-lookup"><span data-stu-id="6882d-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="6882d-118">如果啟用常設聊天室規範伺服器，則舊的郵件會保存在規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="6882d-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6882d-119">此聊天室資料使用適用於 Lync Server 2013，Persistent Chat Server API 應用程式，但不包括種情況下，系統管理員角色的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6882d-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="6882d-120">常設聊天室伺服器 API 無法用來執行任何系統管理員的作業。</span><span class="sxs-lookup"><span data-stu-id="6882d-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="6882d-121">您必須在 Lync Server 管理命令介面中執行這些作業。</span><span class="sxs-lookup"><span data-stu-id="6882d-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

