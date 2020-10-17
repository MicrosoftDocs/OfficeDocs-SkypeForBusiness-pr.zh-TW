---
title: Lync Server 2013：對話方塊表格
description: Lync Server 2013：對話方塊表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2c9cf9ec59fc48f7f5ffc6232980e3f8aa68c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559699"
---
# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="a80c8-103">Lync Server 2013 中的對話方塊表格</span><span class="sxs-lookup"><span data-stu-id="a80c8-103">Dialogs table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a80c8-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a80c8-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a80c8-105">對話方塊表格是一種支援資料表，可儲存點對點工作階段之 Dialogid 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a80c8-105">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a80c8-106">欄</span><span class="sxs-lookup"><span data-stu-id="a80c8-106">Column</span></span></th>
<th><span data-ttu-id="a80c8-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="a80c8-107">Data Type</span></span></th>
<th><span data-ttu-id="a80c8-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="a80c8-108">Key/Index</span></span></th>
<th><span data-ttu-id="a80c8-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a80c8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a80c8-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a80c8-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a80c8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a80c8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a80c8-112">主要</span><span class="sxs-lookup"><span data-stu-id="a80c8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a80c8-113">會話要求的時間;與 SessionIDSeq 搭配使用，以唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="a80c8-113">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a80c8-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a80c8-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a80c8-115">int</span><span class="sxs-lookup"><span data-stu-id="a80c8-115">int</span></span></p></td>
<td><p><span data-ttu-id="a80c8-116">主要</span><span class="sxs-lookup"><span data-stu-id="a80c8-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a80c8-117">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="a80c8-117">ID number to identify the session.</span></span> <span data-ttu-id="a80c8-118">與 SessionIDTime 搭配使用，以唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="a80c8-118">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a80c8-119"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="a80c8-119"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="a80c8-120">int</span><span class="sxs-lookup"><span data-stu-id="a80c8-120">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a80c8-121">ExternalID 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="a80c8-121">Checksum of the ExternalID.</span></span> <span data-ttu-id="a80c8-122">此欄位是用來增加資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="a80c8-122">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a80c8-123"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="a80c8-123"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="a80c8-124">Varbinary (775) </span><span class="sxs-lookup"><span data-stu-id="a80c8-124">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a80c8-125">以二進位儲存的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="a80c8-125">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="a80c8-126">二進位檔案的格式為：</span><span class="sxs-lookup"><span data-stu-id="a80c8-126">The format of the binary is:</span></span></p>
<p><span data-ttu-id="a80c8-127">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="a80c8-127">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="a80c8-128">您可以使用下列語法將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="a80c8-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

