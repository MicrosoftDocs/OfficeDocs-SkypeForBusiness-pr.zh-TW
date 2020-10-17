---
title: Lync Server 2013： tblFileToken
description: Lync Server 2013： tblFileToken。
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
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547629"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="2f92c-103">Lync Server 2013 中的 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="2f92c-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f92c-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2f92c-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2f92c-105">tblFileToken 包含用於檔案傳輸的臨時權杖。</span><span class="sxs-lookup"><span data-stu-id="2f92c-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="2f92c-106">Columns</span><span class="sxs-lookup"><span data-stu-id="2f92c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f92c-107">欄</span><span class="sxs-lookup"><span data-stu-id="2f92c-107">Column</span></span></th>
<th><span data-ttu-id="2f92c-108">類型</span><span class="sxs-lookup"><span data-stu-id="2f92c-108">Type</span></span></th>
<th><span data-ttu-id="2f92c-109">描述</span><span class="sxs-lookup"><span data-stu-id="2f92c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f92c-110">fileToken</span><span class="sxs-lookup"><span data-stu-id="2f92c-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="2f92c-111">nvarchar (50)，非 null</span><span class="sxs-lookup"><span data-stu-id="2f92c-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="2f92c-112">唯一 Token (GUID)。</span><span class="sxs-lookup"><span data-stu-id="2f92c-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f92c-113">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="2f92c-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="2f92c-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="2f92c-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2f92c-115">傳輸檔案之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="2f92c-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f92c-116">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="2f92c-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="2f92c-117">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="2f92c-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2f92c-118">聊天室節點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="2f92c-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f92c-119">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="2f92c-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="2f92c-120">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="2f92c-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="2f92c-p101">到期時間 (權杖於 30 分鐘後到期，除非已固定 (請參閱此欄中下列說明)。</span><span class="sxs-lookup"><span data-stu-id="2f92c-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f92c-123">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="2f92c-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="2f92c-124">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2f92c-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f92c-125">已傳輸檔案的 URL (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="2f92c-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f92c-126">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="2f92c-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="2f92c-127">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2f92c-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f92c-128">已傳輸檔案的縮圖 URL (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="2f92c-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f92c-129">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="2f92c-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="2f92c-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="2f92c-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="2f92c-131">實際檔案傳輸作業的時間戳記 (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="2f92c-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f92c-132">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="2f92c-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="2f92c-133">位</span><span class="sxs-lookup"><span data-stu-id="2f92c-133">bit</span></span></p></td>
<td><p><span data-ttu-id="2f92c-134">若上傳則為 True；若下載則為 False (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="2f92c-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f92c-135">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="2f92c-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="2f92c-136">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="2f92c-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="2f92c-p102">若權杖已固定則為 True，用於將權杖保存在表格中，直到 Compliance Service 有機會從中擷取相關欄位。</span><span class="sxs-lookup"><span data-stu-id="2f92c-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2f92c-139">索引鍵</span><span class="sxs-lookup"><span data-stu-id="2f92c-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f92c-140">欄</span><span class="sxs-lookup"><span data-stu-id="2f92c-140">Column</span></span></th>
<th><span data-ttu-id="2f92c-141">描述</span><span class="sxs-lookup"><span data-stu-id="2f92c-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f92c-142">fileToken</span><span class="sxs-lookup"><span data-stu-id="2f92c-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="2f92c-143">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2f92c-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f92c-144">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="2f92c-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="2f92c-145">在 Node.nodeGuid 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2f92c-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

