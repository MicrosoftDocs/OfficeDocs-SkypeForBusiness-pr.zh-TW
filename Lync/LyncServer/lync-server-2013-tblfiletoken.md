---
title: Lync Server 2013：tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146c168e62bd0602a76cd77ab678c84ba5e44da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="284be-102">Lync Server 2013 中的 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="284be-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="284be-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="284be-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="284be-104">tblFileToken 包含臨時權杖以進行檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="284be-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="284be-105">分欄</span><span class="sxs-lookup"><span data-stu-id="284be-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="284be-106">左欄</span><span class="sxs-lookup"><span data-stu-id="284be-106">Column</span></span></th>
<th><span data-ttu-id="284be-107">類型</span><span class="sxs-lookup"><span data-stu-id="284be-107">Type</span></span></th>
<th><span data-ttu-id="284be-108">描述</span><span class="sxs-lookup"><span data-stu-id="284be-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="284be-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="284be-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="284be-110">Nvarchar （50），not null</span><span class="sxs-lookup"><span data-stu-id="284be-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="284be-111">唯一標記（GUID）。</span><span class="sxs-lookup"><span data-stu-id="284be-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="284be-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="284be-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="284be-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="284be-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="284be-114">要轉移檔案之主體的 ID。</span><span class="sxs-lookup"><span data-stu-id="284be-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="284be-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="284be-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="284be-116">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="284be-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="284be-117">聊天室節點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="284be-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="284be-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="284be-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="284be-119">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="284be-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="284be-120">到期時間。</span><span class="sxs-lookup"><span data-stu-id="284be-120">Expiration time.</span></span> <span data-ttu-id="284be-121">（權杖會在30分鐘之後到期，除非已固定（請參閱此欄中的下列描述）。</span><span class="sxs-lookup"><span data-stu-id="284be-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="284be-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="284be-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="284be-123">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="284be-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="284be-124">已傳送檔案的 URL （適用于合規性服務使用）。</span><span class="sxs-lookup"><span data-stu-id="284be-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="284be-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="284be-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="284be-126">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="284be-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="284be-127">已傳送檔案的縮圖 URL （適用于合規性服務使用）。</span><span class="sxs-lookup"><span data-stu-id="284be-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="284be-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="284be-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="284be-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="284be-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="284be-130">實際檔案傳輸作業（適用于合規性服務使用）的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="284be-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="284be-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="284be-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="284be-132">稍微</span><span class="sxs-lookup"><span data-stu-id="284be-132">bit</span></span></p></td>
<td><p><span data-ttu-id="284be-133">如果上傳則為 True;如果下載（適用于相容性服務使用），則為 False。</span><span class="sxs-lookup"><span data-stu-id="284be-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="284be-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="284be-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="284be-135">bit、not null</span><span class="sxs-lookup"><span data-stu-id="284be-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="284be-136">如果權杖已釘選，則為 True。</span><span class="sxs-lookup"><span data-stu-id="284be-136">True if token is pinned.</span></span> <span data-ttu-id="284be-137">它是用來在表格中保留權杖，直到合規性服務有機會從它取得相關欄位為止。</span><span class="sxs-lookup"><span data-stu-id="284be-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="284be-138">鍵</span><span class="sxs-lookup"><span data-stu-id="284be-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="284be-139">左欄</span><span class="sxs-lookup"><span data-stu-id="284be-139">Column</span></span></th>
<th><span data-ttu-id="284be-140">描述</span><span class="sxs-lookup"><span data-stu-id="284be-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="284be-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="284be-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="284be-142">主鍵。</span><span class="sxs-lookup"><span data-stu-id="284be-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="284be-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="284be-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="284be-144">在 tblNode nodeGuid 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="284be-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

