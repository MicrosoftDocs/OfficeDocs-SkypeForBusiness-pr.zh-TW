---
title: 'Lync Server 2013: tblFileToken'
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
ms.openlocfilehash: 9e3d80b1a326140a94b840c212fc8577a73e468f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="d7e1e-102">Lync Server 2013 中的 tblFileToken</span><span class="sxs-lookup"><span data-stu-id="d7e1e-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7e1e-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="d7e1e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d7e1e-104">tblFileToken 包含用於檔案傳輸的臨時權杖。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="d7e1e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="d7e1e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7e1e-106">欄</span><span class="sxs-lookup"><span data-stu-id="d7e1e-106">Column</span></span></th>
<th><span data-ttu-id="d7e1e-107">類型	</span><span class="sxs-lookup"><span data-stu-id="d7e1e-107">Type</span></span></th>
<th><span data-ttu-id="d7e1e-108">描述</span><span class="sxs-lookup"><span data-stu-id="d7e1e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7e1e-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="d7e1e-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-110">nvarchar (50)，非 null</span><span class="sxs-lookup"><span data-stu-id="d7e1e-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-111">唯一 Token (GUID)。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7e1e-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="d7e1e-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="d7e1e-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-114">傳輸檔案之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7e1e-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="d7e1e-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-116">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="d7e1e-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-117">聊天室節點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7e1e-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="d7e1e-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-119">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="d7e1e-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-p101">到期時間 (權杖於 30 分鐘後到期，除非已固定 (請參閱此欄中下列說明)。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7e1e-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="d7e1e-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7e1e-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-124">已傳輸檔案的 URL (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7e1e-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="d7e1e-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7e1e-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-127">已傳輸檔案的縮圖 URL (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7e1e-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="d7e1e-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="d7e1e-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-130">實際檔案傳輸作業的時間戳記 (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7e1e-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="d7e1e-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-132">位元</span><span class="sxs-lookup"><span data-stu-id="d7e1e-132">bit</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-133">若上傳則為 True；若下載則為 False (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7e1e-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="d7e1e-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-135">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="d7e1e-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-p102">若權杖已固定則為 True，用於將權杖保存在表格中，直到 Compliance Service 有機會從中擷取相關欄位。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d7e1e-138">索引鍵</span><span class="sxs-lookup"><span data-stu-id="d7e1e-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7e1e-139">欄</span><span class="sxs-lookup"><span data-stu-id="d7e1e-139">Column</span></span></th>
<th><span data-ttu-id="d7e1e-140">描述</span><span class="sxs-lookup"><span data-stu-id="d7e1e-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7e1e-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="d7e1e-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-142">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7e1e-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="d7e1e-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="d7e1e-144">在 Node.nodeGuid 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="d7e1e-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

