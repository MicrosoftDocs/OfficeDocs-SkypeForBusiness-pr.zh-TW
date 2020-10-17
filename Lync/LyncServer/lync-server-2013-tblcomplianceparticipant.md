---
title: Lync Server 2013： tblComplianceParticipant
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
ms.openlocfilehash: 0d6ce992f7a36bd5ce731f26dcb5dbfac0e2acae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509430"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="0286e-102">Lync Server 2013 中的 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="0286e-102">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0286e-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0286e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0286e-104">tblComplianceParticipant 包含每個通道和每部伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="0286e-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="0286e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="0286e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0286e-106">欄</span><span class="sxs-lookup"><span data-stu-id="0286e-106">Column</span></span></th>
<th><span data-ttu-id="0286e-107">類型</span><span class="sxs-lookup"><span data-stu-id="0286e-107">Type</span></span></th>
<th><span data-ttu-id="0286e-108">描述</span><span class="sxs-lookup"><span data-stu-id="0286e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0286e-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="0286e-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="0286e-110">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="0286e-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="0286e-111">通道統一資源識別項 (URI)。</span><span class="sxs-lookup"><span data-stu-id="0286e-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0286e-112">userId</span><span class="sxs-lookup"><span data-stu-id="0286e-112">userId</span></span></p></td>
<td><p><span data-ttu-id="0286e-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="0286e-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0286e-114">參與者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。</span><span class="sxs-lookup"><span data-stu-id="0286e-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0286e-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="0286e-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="0286e-116">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="0286e-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="0286e-117">加入活動的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="0286e-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0286e-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="0286e-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="0286e-119">Bigint</span><span class="sxs-lookup"><span data-stu-id="0286e-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="0286e-p101">如果參與者仍加入，則為 Null。如果不是 Null，則是通道離開事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="0286e-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="0286e-122">當所有轉譯器處理事件時，這些項目最後都會移除。</span><span class="sxs-lookup"><span data-stu-id="0286e-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0286e-123">userUri</span><span class="sxs-lookup"><span data-stu-id="0286e-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="0286e-124">nvarchar(255)，非 null</span><span class="sxs-lookup"><span data-stu-id="0286e-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="0286e-125">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="0286e-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0286e-126">serverID</span><span class="sxs-lookup"><span data-stu-id="0286e-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="0286e-127">int</span><span class="sxs-lookup"><span data-stu-id="0286e-127">int</span></span></p></td>
<td><p><span data-ttu-id="0286e-128">伺服器識別碼 (如 tblServerIdentity.serverID 表格中所示)。</span><span class="sxs-lookup"><span data-stu-id="0286e-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0286e-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="0286e-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="0286e-130">Bigint</span><span class="sxs-lookup"><span data-stu-id="0286e-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="0286e-p102">伺服器工作階段。這是聊天服務每次啟動時，所產生的隨機號碼。在識別孤立的參與者時，可使用此號碼來區別工作階段。</span><span class="sxs-lookup"><span data-stu-id="0286e-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0286e-134">索引鍵</span><span class="sxs-lookup"><span data-stu-id="0286e-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0286e-135">欄</span><span class="sxs-lookup"><span data-stu-id="0286e-135">Column</span></span></th>
<th><span data-ttu-id="0286e-136">描述</span><span class="sxs-lookup"><span data-stu-id="0286e-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0286e-137">&lt;channelUri、userId、joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="0286e-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="0286e-138">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="0286e-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

