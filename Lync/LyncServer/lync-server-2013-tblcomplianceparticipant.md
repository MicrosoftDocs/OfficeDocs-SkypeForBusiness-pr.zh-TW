---
title: Lync Server 2013：tblComplianceParticipant
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
ms.openlocfilehash: 484948a01c82dc8ca256e3e50e484c94a9b81de4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="81d15-102">Lync Server 2013 中的 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="81d15-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81d15-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="81d15-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="81d15-104">tblComplianceParticipant 包含每個通道及每個伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="81d15-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="81d15-105">分欄</span><span class="sxs-lookup"><span data-stu-id="81d15-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81d15-106">左欄</span><span class="sxs-lookup"><span data-stu-id="81d15-106">Column</span></span></th>
<th><span data-ttu-id="81d15-107">類型</span><span class="sxs-lookup"><span data-stu-id="81d15-107">Type</span></span></th>
<th><span data-ttu-id="81d15-108">說明</span><span class="sxs-lookup"><span data-stu-id="81d15-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81d15-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="81d15-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="81d15-110">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="81d15-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="81d15-111">通道統一資源識別項（URI）。</span><span class="sxs-lookup"><span data-stu-id="81d15-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d15-112">userId</span><span class="sxs-lookup"><span data-stu-id="81d15-112">userId</span></span></p></td>
<td><p><span data-ttu-id="81d15-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="81d15-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="81d15-114">參與者的主體識別碼（對應至 tblPrincipal prinID 資料表）。</span><span class="sxs-lookup"><span data-stu-id="81d15-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81d15-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="81d15-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="81d15-116">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="81d15-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="81d15-117">加入事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="81d15-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d15-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="81d15-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="81d15-119">Bigint</span><span class="sxs-lookup"><span data-stu-id="81d15-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="81d15-120">如果參與者仍在加入，則為 Null。</span><span class="sxs-lookup"><span data-stu-id="81d15-120">Null if participant is still joined.</span></span> <span data-ttu-id="81d15-121">如果 not null，則通道的時間戳記會保留事件。</span><span class="sxs-lookup"><span data-stu-id="81d15-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="81d15-122">這些專案會在所有翻譯員處理事件時最終移除。</span><span class="sxs-lookup"><span data-stu-id="81d15-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81d15-123">userUri</span><span class="sxs-lookup"><span data-stu-id="81d15-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="81d15-124">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="81d15-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="81d15-125">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="81d15-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81d15-126">serverID</span><span class="sxs-lookup"><span data-stu-id="81d15-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="81d15-127">int</span><span class="sxs-lookup"><span data-stu-id="81d15-127">int</span></span></p></td>
<td><p><span data-ttu-id="81d15-128">伺服器身分識別（例如在 serverID 資料表中則為 tblServerIdentity）。</span><span class="sxs-lookup"><span data-stu-id="81d15-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81d15-129">識別碼</span><span class="sxs-lookup"><span data-stu-id="81d15-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="81d15-130">Bigint</span><span class="sxs-lookup"><span data-stu-id="81d15-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="81d15-131">伺服器會話。</span><span class="sxs-lookup"><span data-stu-id="81d15-131">Server session.</span></span> <span data-ttu-id="81d15-132">這是在每次聊天服務啟動時產生的亂數字。</span><span class="sxs-lookup"><span data-stu-id="81d15-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="81d15-133">它是用來區分會話，目的是識別孤立參與者。</span><span class="sxs-lookup"><span data-stu-id="81d15-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="81d15-134">機碼</span><span class="sxs-lookup"><span data-stu-id="81d15-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81d15-135">左欄</span><span class="sxs-lookup"><span data-stu-id="81d15-135">Column</span></span></th>
<th><span data-ttu-id="81d15-136">說明</span><span class="sxs-lookup"><span data-stu-id="81d15-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81d15-137">&lt;channelUri、userId、joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="81d15-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="81d15-138">主鍵。</span><span class="sxs-lookup"><span data-stu-id="81d15-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

