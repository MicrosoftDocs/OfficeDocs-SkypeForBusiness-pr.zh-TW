---
title: 'Lync Server 2013: tbllastchatid 表格'
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
ms.openlocfilehash: be10514a933cb6a311d115fbbb011398f2758ef9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="bcdb1-102">Lync Server 2013 中的 tbllastchatid 表格</span><span class="sxs-lookup"><span data-stu-id="bcdb1-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcdb1-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="bcdb1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bcdb1-104">tblLastChatId 表格包含為每個使用者產生 (且用於 tblChat 表格) 的最後一個交談 ID。</span><span class="sxs-lookup"><span data-stu-id="bcdb1-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="bcdb1-105">Columns</span><span class="sxs-lookup"><span data-stu-id="bcdb1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bcdb1-106">欄</span><span class="sxs-lookup"><span data-stu-id="bcdb1-106">Column</span></span></th>
<th><span data-ttu-id="bcdb1-107">類型	</span><span class="sxs-lookup"><span data-stu-id="bcdb1-107">Type</span></span></th>
<th><span data-ttu-id="bcdb1-108">描述</span><span class="sxs-lookup"><span data-stu-id="bcdb1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcdb1-109">節點識別碼</span><span class="sxs-lookup"><span data-stu-id="bcdb1-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="bcdb1-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="bcdb1-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bcdb1-111">節點識別碼 (僅聊天室類型)。</span><span class="sxs-lookup"><span data-stu-id="bcdb1-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcdb1-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="bcdb1-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="bcdb1-113">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="bcdb1-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bcdb1-114">最後一個使用的交談 ID。</span><span class="sxs-lookup"><span data-stu-id="bcdb1-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bcdb1-115">索引鍵</span><span class="sxs-lookup"><span data-stu-id="bcdb1-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bcdb1-116">欄</span><span class="sxs-lookup"><span data-stu-id="bcdb1-116">Column</span></span></th>
<th><span data-ttu-id="bcdb1-117">描述</span><span class="sxs-lookup"><span data-stu-id="bcdb1-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcdb1-118">&lt;節點識別碼 lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="bcdb1-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="bcdb1-119">主索引鍵 (處理時僅有 nodeID 已足夠)。</span><span class="sxs-lookup"><span data-stu-id="bcdb1-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcdb1-120">節點識別碼</span><span class="sxs-lookup"><span data-stu-id="bcdb1-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="bcdb1-121">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="bcdb1-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="bcdb1-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bcdb1-122">See Also</span></span>


[<span data-ttu-id="bcdb1-123">Lync Server 2013 中的 tblChat</span><span class="sxs-lookup"><span data-stu-id="bcdb1-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

