---
title: Lync Server 2013：tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b469b79e680c202654024d1ac20a55b9929e4b10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="bc10a-102">Lync Server 2013 中的 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="bc10a-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc10a-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bc10a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bc10a-104">tblFileToken 包含臨時權杖以進行檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="bc10a-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="bc10a-105">分欄</span><span class="sxs-lookup"><span data-stu-id="bc10a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc10a-106">左欄</span><span class="sxs-lookup"><span data-stu-id="bc10a-106">Column</span></span></th>
<th><span data-ttu-id="bc10a-107">類型</span><span class="sxs-lookup"><span data-stu-id="bc10a-107">Type</span></span></th>
<th><span data-ttu-id="bc10a-108">說明</span><span class="sxs-lookup"><span data-stu-id="bc10a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc10a-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="bc10a-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="bc10a-110">Nvarchar （50），not null</span><span class="sxs-lookup"><span data-stu-id="bc10a-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="bc10a-111">唯一標記（GUID）。</span><span class="sxs-lookup"><span data-stu-id="bc10a-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc10a-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="bc10a-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="bc10a-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="bc10a-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bc10a-114">要轉移檔案之主體的 ID。</span><span class="sxs-lookup"><span data-stu-id="bc10a-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc10a-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="bc10a-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="bc10a-116">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="bc10a-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bc10a-117">聊天室節點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="bc10a-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc10a-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="bc10a-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="bc10a-119">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="bc10a-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="bc10a-120">到期時間。</span><span class="sxs-lookup"><span data-stu-id="bc10a-120">Expiration time.</span></span> <span data-ttu-id="bc10a-121">（權杖會在30分鐘之後到期，除非已固定（請參閱此欄中的下列描述）。</span><span class="sxs-lookup"><span data-stu-id="bc10a-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc10a-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="bc10a-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="bc10a-123">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bc10a-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bc10a-124">已傳送檔案的 URL （適用于合規性服務使用）。</span><span class="sxs-lookup"><span data-stu-id="bc10a-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc10a-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="bc10a-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="bc10a-126">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bc10a-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bc10a-127">已傳送檔案的縮圖 URL （適用于合規性服務使用）。</span><span class="sxs-lookup"><span data-stu-id="bc10a-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc10a-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="bc10a-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="bc10a-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="bc10a-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="bc10a-130">實際檔案傳輸作業（適用于合規性服務使用）的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="bc10a-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc10a-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="bc10a-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="bc10a-132">稍微</span><span class="sxs-lookup"><span data-stu-id="bc10a-132">bit</span></span></p></td>
<td><p><span data-ttu-id="bc10a-133">如果上傳則為 True;如果下載（適用于相容性服務使用），則為 False。</span><span class="sxs-lookup"><span data-stu-id="bc10a-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc10a-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="bc10a-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="bc10a-135">bit、not null</span><span class="sxs-lookup"><span data-stu-id="bc10a-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bc10a-136">如果權杖已釘選，則為 True。</span><span class="sxs-lookup"><span data-stu-id="bc10a-136">True if token is pinned.</span></span> <span data-ttu-id="bc10a-137">它是用來在表格中保留權杖，直到合規性服務有機會從它取得相關欄位為止。</span><span class="sxs-lookup"><span data-stu-id="bc10a-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bc10a-138">鍵</span><span class="sxs-lookup"><span data-stu-id="bc10a-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc10a-139">左欄</span><span class="sxs-lookup"><span data-stu-id="bc10a-139">Column</span></span></th>
<th><span data-ttu-id="bc10a-140">說明</span><span class="sxs-lookup"><span data-stu-id="bc10a-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc10a-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="bc10a-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="bc10a-142">主鍵。</span><span class="sxs-lookup"><span data-stu-id="bc10a-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc10a-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="bc10a-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="bc10a-144">在 tblNode nodeGuid 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="bc10a-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

