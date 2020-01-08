---
title: Lync Server 2013：tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044a57645a8c49ea74ec4e003f9e12720d0b2268
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="8a027-102">Lync Server 2013 中的 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="8a027-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a027-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8a027-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8a027-104">tblComplianceData 包含尚未由合規性配接器處理的合規性事件。</span><span class="sxs-lookup"><span data-stu-id="8a027-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="8a027-105">分欄</span><span class="sxs-lookup"><span data-stu-id="8a027-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a027-106">左欄</span><span class="sxs-lookup"><span data-stu-id="8a027-106">Column</span></span></th>
<th><span data-ttu-id="8a027-107">類型</span><span class="sxs-lookup"><span data-stu-id="8a027-107">Type</span></span></th>
<th><span data-ttu-id="8a027-108">描述</span><span class="sxs-lookup"><span data-stu-id="8a027-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a027-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="8a027-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="8a027-110">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="8a027-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="8a027-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="8a027-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a027-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="8a027-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="8a027-113">Smalldatetime，not null</span><span class="sxs-lookup"><span data-stu-id="8a027-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="8a027-114">插入的時間（對於 cmplType = 9，未來可能是目前的時間），因為該專案只是該案例中的預留位置。</span><span class="sxs-lookup"><span data-stu-id="8a027-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a027-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="8a027-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="8a027-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="8a027-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a027-117">合規性事件的類型：</span><span class="sxs-lookup"><span data-stu-id="8a027-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="8a027-118">1：聊天</span><span class="sxs-lookup"><span data-stu-id="8a027-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="8a027-119">2： Backchat</span><span class="sxs-lookup"><span data-stu-id="8a027-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="8a027-120">3：檔案下載</span><span class="sxs-lookup"><span data-stu-id="8a027-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="8a027-121">4：檔案上傳</span><span class="sxs-lookup"><span data-stu-id="8a027-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="8a027-122">9：暫存檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="8a027-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="8a027-123">10：聊天刪除（使用 [取代]）</span><span class="sxs-lookup"><span data-stu-id="8a027-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="8a027-124">11：聊天清除</span><span class="sxs-lookup"><span data-stu-id="8a027-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a027-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="8a027-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="8a027-126">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="8a027-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="8a027-127">事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="8a027-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a027-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="8a027-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="8a027-129">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="8a027-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="8a027-130">通道統一資源識別項（URI）。</span><span class="sxs-lookup"><span data-stu-id="8a027-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a027-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="8a027-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="8a027-132">Bigint</span><span class="sxs-lookup"><span data-stu-id="8a027-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="8a027-133">聊天識別碼（對應至 tblChat chatId 表）。</span><span class="sxs-lookup"><span data-stu-id="8a027-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a027-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="8a027-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="8a027-135">int，not null</span><span class="sxs-lookup"><span data-stu-id="8a027-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8a027-136">海報的主體識別碼（對應至 tblPrincipal prinID）。</span><span class="sxs-lookup"><span data-stu-id="8a027-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a027-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="8a027-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="8a027-138">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="8a027-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="8a027-139">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="8a027-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a027-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="8a027-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="8a027-141">Nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="8a027-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="8a027-142">訊息（編碼依據 cmplType）。</span><span class="sxs-lookup"><span data-stu-id="8a027-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="8a027-143">機碼</span><span class="sxs-lookup"><span data-stu-id="8a027-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a027-144">左欄</span><span class="sxs-lookup"><span data-stu-id="8a027-144">Column</span></span></th>
<th><span data-ttu-id="8a027-145">描述</span><span class="sxs-lookup"><span data-stu-id="8a027-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a027-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="8a027-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="8a027-147">主鍵。</span><span class="sxs-lookup"><span data-stu-id="8a027-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

