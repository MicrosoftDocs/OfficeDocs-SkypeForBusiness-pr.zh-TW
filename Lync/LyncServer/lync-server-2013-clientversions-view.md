---
title: Lync Server 2013： ClientVersions view
description: Lync Server 2013： ClientVersions view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42ede7107a59db3162ac7f5344e47e81a80d57df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542799"
---
# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="7967f-103">Lync Server 2013 中的 ClientVersions 視圖</span><span class="sxs-lookup"><span data-stu-id="7967f-103">ClientVersions view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7967f-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7967f-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7967f-105">ClientVersions view 儲存已參與資料庫中記錄之會話的各種用戶端類型和版本資訊。</span><span class="sxs-lookup"><span data-stu-id="7967f-105">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="7967f-106">視圖中的每一筆記錄都代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="7967f-106">Each record in the view represents one client version.</span></span> <span data-ttu-id="7967f-107">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="7967f-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7967f-108">某些欄可能會有多筆記錄。</span><span class="sxs-lookup"><span data-stu-id="7967f-108">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7967f-109">欄</span><span class="sxs-lookup"><span data-stu-id="7967f-109">Column</span></span></th>
<th><span data-ttu-id="7967f-110">資料類型</span><span class="sxs-lookup"><span data-stu-id="7967f-110">Data Type</span></span></th>
<th><span data-ttu-id="7967f-111">詳細資料</span><span class="sxs-lookup"><span data-stu-id="7967f-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7967f-112"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="7967f-112"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="7967f-113">int</span><span class="sxs-lookup"><span data-stu-id="7967f-113">int</span></span></p></td>
<td><p><span data-ttu-id="7967f-114">用於識別此用戶端類型及版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="7967f-114">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7967f-115"><strong>版本</strong></span><span class="sxs-lookup"><span data-stu-id="7967f-115"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="7967f-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7967f-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7967f-117">代表使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="7967f-117">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7967f-118"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="7967f-118"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7967f-119">int</span><span class="sxs-lookup"><span data-stu-id="7967f-119">int</span></span></p></td>
<td><p><span data-ttu-id="7967f-120">用戶端的類型。</span><span class="sxs-lookup"><span data-stu-id="7967f-120">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7967f-121"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="7967f-121"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7967f-122">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="7967f-122">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7967f-123">用戶端所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="7967f-123">Category that the client belongs to.</span></span> <span data-ttu-id="7967f-124">例如，用戶端 Conferencing_Attendant_1 .0 屬於 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="7967f-124">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

