---
title: Lync Server 2013：tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fc42a3151b5863885fdb3853ea529503e18a6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="64dcf-102">Lync Server 2013 中的 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="64dcf-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64dcf-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="64dcf-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="64dcf-104">tblLastChatId 包含每位使用者所產生（並在 tblChat 資料表中使用）的最後一個聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="64dcf-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="64dcf-105">分欄</span><span class="sxs-lookup"><span data-stu-id="64dcf-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64dcf-106">左欄</span><span class="sxs-lookup"><span data-stu-id="64dcf-106">Column</span></span></th>
<th><span data-ttu-id="64dcf-107">類型</span><span class="sxs-lookup"><span data-stu-id="64dcf-107">Type</span></span></th>
<th><span data-ttu-id="64dcf-108">說明</span><span class="sxs-lookup"><span data-stu-id="64dcf-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64dcf-109">個</span><span class="sxs-lookup"><span data-stu-id="64dcf-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="64dcf-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="64dcf-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="64dcf-111">[Node ID] （聊天室-僅限類型）。</span><span class="sxs-lookup"><span data-stu-id="64dcf-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dcf-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="64dcf-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="64dcf-113">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="64dcf-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="64dcf-114">上次使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="64dcf-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="64dcf-115">鍵</span><span class="sxs-lookup"><span data-stu-id="64dcf-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64dcf-116">左欄</span><span class="sxs-lookup"><span data-stu-id="64dcf-116">Column</span></span></th>
<th><span data-ttu-id="64dcf-117">說明</span><span class="sxs-lookup"><span data-stu-id="64dcf-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64dcf-118">&lt;lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="64dcf-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="64dcf-119">主鍵（只有一個代表可充分處理）。</span><span class="sxs-lookup"><span data-stu-id="64dcf-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64dcf-120">個</span><span class="sxs-lookup"><span data-stu-id="64dcf-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="64dcf-121">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="64dcf-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="64dcf-122">請參閱</span><span class="sxs-lookup"><span data-stu-id="64dcf-122">See Also</span></span>


[<span data-ttu-id="64dcf-123">Lync Server 2013 中的 tblChat</span><span class="sxs-lookup"><span data-stu-id="64dcf-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

