---
title: 'Lync Server 2013: tblComplianceParticipant'
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
ms.openlocfilehash: fbadec18ba7054c7b58522129fca01da7d015e7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="b06fb-102">Lync Server 2013 中的 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="b06fb-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b06fb-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="b06fb-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b06fb-104">tblComplianceParticipant 包含每個通道和每部伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="b06fb-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="b06fb-105">Columns</span><span class="sxs-lookup"><span data-stu-id="b06fb-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b06fb-106">欄</span><span class="sxs-lookup"><span data-stu-id="b06fb-106">Column</span></span></th>
<th><span data-ttu-id="b06fb-107">類型	</span><span class="sxs-lookup"><span data-stu-id="b06fb-107">Type</span></span></th>
<th><span data-ttu-id="b06fb-108">描述</span><span class="sxs-lookup"><span data-stu-id="b06fb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b06fb-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="b06fb-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="b06fb-110">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="b06fb-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="b06fb-111">通道統一資源識別項 (URI)。</span><span class="sxs-lookup"><span data-stu-id="b06fb-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b06fb-112">使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="b06fb-112">userId</span></span></p></td>
<td><p><span data-ttu-id="b06fb-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="b06fb-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b06fb-114">參與者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。</span><span class="sxs-lookup"><span data-stu-id="b06fb-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b06fb-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="b06fb-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="b06fb-116">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="b06fb-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="b06fb-117">加入活動的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="b06fb-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b06fb-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="b06fb-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="b06fb-119">bigint</span><span class="sxs-lookup"><span data-stu-id="b06fb-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="b06fb-p101">如果參與者仍加入，則為 Null。如果不是 Null，則是通道離開事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="b06fb-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="b06fb-122">當所有轉譯器處理事件時，這些項目最後都會移除。</span><span class="sxs-lookup"><span data-stu-id="b06fb-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b06fb-123">userUri</span><span class="sxs-lookup"><span data-stu-id="b06fb-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="b06fb-124">nvarchar(255)，非 null</span><span class="sxs-lookup"><span data-stu-id="b06fb-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="b06fb-125">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="b06fb-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b06fb-126">serverID</span><span class="sxs-lookup"><span data-stu-id="b06fb-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="b06fb-127">int</span><span class="sxs-lookup"><span data-stu-id="b06fb-127">int</span></span></p></td>
<td><p><span data-ttu-id="b06fb-128">伺服器識別碼 (如 tblServerIdentity.serverID 表格中所示)。</span><span class="sxs-lookup"><span data-stu-id="b06fb-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b06fb-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="b06fb-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="b06fb-130">bigint</span><span class="sxs-lookup"><span data-stu-id="b06fb-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="b06fb-p102">伺服器工作階段。這是聊天服務每次啟動時，所產生的隨機號碼。在識別孤立的參與者時，可使用此號碼來區別工作階段。</span><span class="sxs-lookup"><span data-stu-id="b06fb-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b06fb-134">索引鍵</span><span class="sxs-lookup"><span data-stu-id="b06fb-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b06fb-135">欄</span><span class="sxs-lookup"><span data-stu-id="b06fb-135">Column</span></span></th>
<th><span data-ttu-id="b06fb-136">描述</span><span class="sxs-lookup"><span data-stu-id="b06fb-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b06fb-137">&lt;channelUri，userId joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="b06fb-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="b06fb-138">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b06fb-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

