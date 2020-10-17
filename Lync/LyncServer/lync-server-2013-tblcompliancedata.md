---
title: Lync Server 2013： tblComplianceData
description: Lync Server 2013： tblComplianceData。
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
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568099"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="443b8-103">Lync Server 2013 中的 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="443b8-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="443b8-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="443b8-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="443b8-105">tblComplianceData 包含法規相符性介面卡尚未處理的規範事件。</span><span class="sxs-lookup"><span data-stu-id="443b8-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="443b8-106">Columns</span><span class="sxs-lookup"><span data-stu-id="443b8-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="443b8-107">欄</span><span class="sxs-lookup"><span data-stu-id="443b8-107">Column</span></span></th>
<th><span data-ttu-id="443b8-108">類型</span><span class="sxs-lookup"><span data-stu-id="443b8-108">Type</span></span></th>
<th><span data-ttu-id="443b8-109">描述</span><span class="sxs-lookup"><span data-stu-id="443b8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="443b8-110">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="443b8-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="443b8-111">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="443b8-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="443b8-112">事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="443b8-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="443b8-113">entryDate</span><span class="sxs-lookup"><span data-stu-id="443b8-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="443b8-114">smalldatetime，非 null</span><span class="sxs-lookup"><span data-stu-id="443b8-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="443b8-115">插入時間 (若是 cmplType=9，則可能是未來很久以後，因為此項目在此情況下只是預留位置)。</span><span class="sxs-lookup"><span data-stu-id="443b8-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="443b8-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="443b8-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="443b8-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="443b8-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="443b8-118">規範事件的類型：</span><span class="sxs-lookup"><span data-stu-id="443b8-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="443b8-119">1: 聊天</span><span class="sxs-lookup"><span data-stu-id="443b8-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="443b8-120">2: 對話</span><span class="sxs-lookup"><span data-stu-id="443b8-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="443b8-121">3: 檔案下載</span><span class="sxs-lookup"><span data-stu-id="443b8-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="443b8-122">4: 檔案上傳</span><span class="sxs-lookup"><span data-stu-id="443b8-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="443b8-123">9: 暫時性檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="443b8-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="443b8-124">10: 聊天刪除 (及取代)</span><span class="sxs-lookup"><span data-stu-id="443b8-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="443b8-125">11: 聊天清除</span><span class="sxs-lookup"><span data-stu-id="443b8-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="443b8-126">cmplTime</span><span class="sxs-lookup"><span data-stu-id="443b8-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="443b8-127">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="443b8-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="443b8-128">事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="443b8-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="443b8-129">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="443b8-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="443b8-130">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="443b8-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="443b8-131">通道統一資源識別項 (URI)。</span><span class="sxs-lookup"><span data-stu-id="443b8-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="443b8-132">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="443b8-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="443b8-133">Bigint</span><span class="sxs-lookup"><span data-stu-id="443b8-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="443b8-134">聊天識別碼 (對應至 tblChat.chatId 表格)。</span><span class="sxs-lookup"><span data-stu-id="443b8-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="443b8-135">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="443b8-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="443b8-136">int，非 null</span><span class="sxs-lookup"><span data-stu-id="443b8-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="443b8-137">發佈者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。</span><span class="sxs-lookup"><span data-stu-id="443b8-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="443b8-138">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="443b8-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="443b8-139">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="443b8-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="443b8-140">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="443b8-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="443b8-141">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="443b8-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="443b8-142">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="443b8-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="443b8-143">訊息 (編碼取決於 cmplType)。</span><span class="sxs-lookup"><span data-stu-id="443b8-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="443b8-144">索引鍵</span><span class="sxs-lookup"><span data-stu-id="443b8-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="443b8-145">欄</span><span class="sxs-lookup"><span data-stu-id="443b8-145">Column</span></span></th>
<th><span data-ttu-id="443b8-146">描述</span><span class="sxs-lookup"><span data-stu-id="443b8-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="443b8-147">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="443b8-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="443b8-148">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="443b8-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

