---
title: Lync Server 2013： tblComplianceParticipant
description: Lync Server 2013： tblComplianceParticipant。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569069"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="18427-103">Lync Server 2013 中的 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="18427-103">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18427-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="18427-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="18427-105">tblComplianceParticipant 包含每個通道和每部伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="18427-105">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="18427-106">Columns</span><span class="sxs-lookup"><span data-stu-id="18427-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18427-107">欄</span><span class="sxs-lookup"><span data-stu-id="18427-107">Column</span></span></th>
<th><span data-ttu-id="18427-108">類型</span><span class="sxs-lookup"><span data-stu-id="18427-108">Type</span></span></th>
<th><span data-ttu-id="18427-109">描述</span><span class="sxs-lookup"><span data-stu-id="18427-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18427-110">channelUri</span><span class="sxs-lookup"><span data-stu-id="18427-110">channelUri</span></span></p></td>
<td><p><span data-ttu-id="18427-111">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="18427-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="18427-112">通道統一資源識別項 (URI)。</span><span class="sxs-lookup"><span data-stu-id="18427-112">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18427-113">userId</span><span class="sxs-lookup"><span data-stu-id="18427-113">userId</span></span></p></td>
<td><p><span data-ttu-id="18427-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="18427-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="18427-115">參與者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。</span><span class="sxs-lookup"><span data-stu-id="18427-115">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18427-116">joinedAt</span><span class="sxs-lookup"><span data-stu-id="18427-116">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="18427-117">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="18427-117">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="18427-118">加入活動的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="18427-118">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18427-119">partedAt</span><span class="sxs-lookup"><span data-stu-id="18427-119">partedAt</span></span></p></td>
<td><p><span data-ttu-id="18427-120">Bigint</span><span class="sxs-lookup"><span data-stu-id="18427-120">bigint</span></span></p></td>
<td><p><span data-ttu-id="18427-p101">如果參與者仍加入，則為 Null。如果不是 Null，則是通道離開事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="18427-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="18427-123">當所有轉譯器處理事件時，這些項目最後都會移除。</span><span class="sxs-lookup"><span data-stu-id="18427-123">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18427-124">userUri</span><span class="sxs-lookup"><span data-stu-id="18427-124">userUri</span></span></p></td>
<td><p><span data-ttu-id="18427-125">nvarchar(255)，非 null</span><span class="sxs-lookup"><span data-stu-id="18427-125">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="18427-126">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="18427-126">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18427-127">serverID</span><span class="sxs-lookup"><span data-stu-id="18427-127">serverID</span></span></p></td>
<td><p><span data-ttu-id="18427-128">int</span><span class="sxs-lookup"><span data-stu-id="18427-128">int</span></span></p></td>
<td><p><span data-ttu-id="18427-129">伺服器識別碼 (如 tblServerIdentity.serverID 表格中所示)。</span><span class="sxs-lookup"><span data-stu-id="18427-129">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18427-130">sessionId</span><span class="sxs-lookup"><span data-stu-id="18427-130">sessionId</span></span></p></td>
<td><p><span data-ttu-id="18427-131">Bigint</span><span class="sxs-lookup"><span data-stu-id="18427-131">bigint</span></span></p></td>
<td><p><span data-ttu-id="18427-p102">伺服器工作階段。這是聊天服務每次啟動時，所產生的隨機號碼。在識別孤立的參與者時，可使用此號碼來區別工作階段。</span><span class="sxs-lookup"><span data-stu-id="18427-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="18427-135">索引鍵</span><span class="sxs-lookup"><span data-stu-id="18427-135">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18427-136">欄</span><span class="sxs-lookup"><span data-stu-id="18427-136">Column</span></span></th>
<th><span data-ttu-id="18427-137">描述</span><span class="sxs-lookup"><span data-stu-id="18427-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18427-138">&lt;channelUri、userId、joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="18427-138">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="18427-139">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="18427-139">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

