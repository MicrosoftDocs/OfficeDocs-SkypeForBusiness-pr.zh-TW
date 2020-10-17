---
title: Lync Server 2013： tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 162676768c3cb358db436dc2ba40ce378a31ba6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509450"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="6f030-102">Lync Server 2013 中的 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="6f030-102">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f030-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6f030-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6f030-104">tblComplianceData 包含法規相符性介面卡尚未處理的規範事件。</span><span class="sxs-lookup"><span data-stu-id="6f030-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="6f030-105">Columns</span><span class="sxs-lookup"><span data-stu-id="6f030-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f030-106">欄</span><span class="sxs-lookup"><span data-stu-id="6f030-106">Column</span></span></th>
<th><span data-ttu-id="6f030-107">類型</span><span class="sxs-lookup"><span data-stu-id="6f030-107">Type</span></span></th>
<th><span data-ttu-id="6f030-108">描述</span><span class="sxs-lookup"><span data-stu-id="6f030-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f030-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="6f030-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="6f030-110">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="6f030-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="6f030-111">事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="6f030-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f030-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="6f030-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="6f030-113">smalldatetime，非 null</span><span class="sxs-lookup"><span data-stu-id="6f030-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="6f030-114">插入時間 (若是 cmplType=9，則可能是未來很久以後，因為此項目在此情況下只是預留位置)。</span><span class="sxs-lookup"><span data-stu-id="6f030-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f030-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="6f030-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="6f030-116">int，非 null</span><span class="sxs-lookup"><span data-stu-id="6f030-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6f030-117">規範事件的類型：</span><span class="sxs-lookup"><span data-stu-id="6f030-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="6f030-118">1: 聊天</span><span class="sxs-lookup"><span data-stu-id="6f030-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="6f030-119">2: 對話</span><span class="sxs-lookup"><span data-stu-id="6f030-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="6f030-120">3: 檔案下載</span><span class="sxs-lookup"><span data-stu-id="6f030-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="6f030-121">4: 檔案上傳</span><span class="sxs-lookup"><span data-stu-id="6f030-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="6f030-122">9: 暫時性檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="6f030-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="6f030-123">10: 聊天刪除 (及取代)</span><span class="sxs-lookup"><span data-stu-id="6f030-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="6f030-124">11: 聊天清除</span><span class="sxs-lookup"><span data-stu-id="6f030-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f030-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="6f030-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="6f030-126">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="6f030-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="6f030-127">事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="6f030-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f030-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="6f030-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="6f030-129">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="6f030-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="6f030-130">通道統一資源識別項 (URI)。</span><span class="sxs-lookup"><span data-stu-id="6f030-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f030-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="6f030-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="6f030-132">Bigint</span><span class="sxs-lookup"><span data-stu-id="6f030-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="6f030-133">聊天識別碼 (對應至 tblChat.chatId 表格)。</span><span class="sxs-lookup"><span data-stu-id="6f030-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f030-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="6f030-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="6f030-135">int，非 null</span><span class="sxs-lookup"><span data-stu-id="6f030-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6f030-136">發佈者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。</span><span class="sxs-lookup"><span data-stu-id="6f030-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f030-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="6f030-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="6f030-138">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="6f030-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="6f030-139">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="6f030-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f030-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="6f030-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="6f030-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="6f030-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="6f030-142">訊息 (編碼取決於 cmplType)。</span><span class="sxs-lookup"><span data-stu-id="6f030-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="6f030-143">索引鍵</span><span class="sxs-lookup"><span data-stu-id="6f030-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f030-144">欄</span><span class="sxs-lookup"><span data-stu-id="6f030-144">Column</span></span></th>
<th><span data-ttu-id="6f030-145">描述</span><span class="sxs-lookup"><span data-stu-id="6f030-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f030-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="6f030-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="6f030-147">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="6f030-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

