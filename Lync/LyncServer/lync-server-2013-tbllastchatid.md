---
title: Lync Server 2013： tblLastChatId
description: Lync Server 2013： tblLastChatId。
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
ms.openlocfilehash: 69e80a735e70c8a03441038f5e58eb93e0af1f82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547599"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="f949b-103">Lync Server 2013 中的 tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="f949b-103">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f949b-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f949b-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f949b-105">tblLastChatId 表格包含為每個使用者產生 (且用於 tblChat 表格) 的最後一個交談 ID。</span><span class="sxs-lookup"><span data-stu-id="f949b-105">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="f949b-106">Columns</span><span class="sxs-lookup"><span data-stu-id="f949b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f949b-107">欄</span><span class="sxs-lookup"><span data-stu-id="f949b-107">Column</span></span></th>
<th><span data-ttu-id="f949b-108">類型</span><span class="sxs-lookup"><span data-stu-id="f949b-108">Type</span></span></th>
<th><span data-ttu-id="f949b-109">描述</span><span class="sxs-lookup"><span data-stu-id="f949b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f949b-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="f949b-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f949b-111">int，非 null</span><span class="sxs-lookup"><span data-stu-id="f949b-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f949b-112">節點識別碼 (僅聊天室類型)。</span><span class="sxs-lookup"><span data-stu-id="f949b-112">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f949b-113">lastChatID</span><span class="sxs-lookup"><span data-stu-id="f949b-113">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="f949b-114">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="f949b-114">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f949b-115">最後一個使用的交談 ID。</span><span class="sxs-lookup"><span data-stu-id="f949b-115">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f949b-116">索引鍵</span><span class="sxs-lookup"><span data-stu-id="f949b-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f949b-117">欄</span><span class="sxs-lookup"><span data-stu-id="f949b-117">Column</span></span></th>
<th><span data-ttu-id="f949b-118">描述</span><span class="sxs-lookup"><span data-stu-id="f949b-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f949b-119">&lt;nodeID，lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="f949b-119">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="f949b-120">主索引鍵 (處理時僅有 nodeID 已足夠)。</span><span class="sxs-lookup"><span data-stu-id="f949b-120">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f949b-121">nodeID</span><span class="sxs-lookup"><span data-stu-id="f949b-121">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f949b-122">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="f949b-122">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="f949b-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f949b-123">See Also</span></span>


[<span data-ttu-id="f949b-124">Lync Server 2013 中的 tblChat</span><span class="sxs-lookup"><span data-stu-id="f949b-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

