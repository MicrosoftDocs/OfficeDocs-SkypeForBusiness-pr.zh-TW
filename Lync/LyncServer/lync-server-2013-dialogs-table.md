---
title: 'Lync Server 2013: Dialogs 表格'
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
ms.openlocfilehash: be0bb5a603f856aa0faa02074962618fcb82448e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="d3c24-102">Lync Server 2013 中的 dialogs 表格</span><span class="sxs-lookup"><span data-stu-id="d3c24-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3c24-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="d3c24-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d3c24-104">Dialogs 表格是一種支援資料表儲存的端對端工作階段的 Dialogid 資訊。</span><span class="sxs-lookup"><span data-stu-id="d3c24-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3c24-105">欄</span><span class="sxs-lookup"><span data-stu-id="d3c24-105">Column</span></span></th>
<th><span data-ttu-id="d3c24-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="d3c24-106">Data Type</span></span></th>
<th><span data-ttu-id="d3c24-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="d3c24-107">Key/Index</span></span></th>
<th><span data-ttu-id="d3c24-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="d3c24-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3c24-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d3c24-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d3c24-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d3c24-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d3c24-111">主要</span><span class="sxs-lookup"><span data-stu-id="d3c24-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="d3c24-112">工作階段要求;SessionIDSeq 搭配使用來唯一地識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="d3c24-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3c24-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d3c24-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d3c24-114">int</span><span class="sxs-lookup"><span data-stu-id="d3c24-114">int</span></span></p></td>
<td><p><span data-ttu-id="d3c24-115">主要</span><span class="sxs-lookup"><span data-stu-id="d3c24-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="d3c24-116">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="d3c24-116">ID number to identify the session.</span></span> <span data-ttu-id="d3c24-117">搭配 SessionIDTime 用來唯一地識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="d3c24-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3c24-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="d3c24-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="d3c24-119">int</span><span class="sxs-lookup"><span data-stu-id="d3c24-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d3c24-120">ExternalID 總和檢查碼。</span><span class="sxs-lookup"><span data-stu-id="d3c24-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="d3c24-121">若要增加資料庫搜尋的速度，會使用此欄位。</span><span class="sxs-lookup"><span data-stu-id="d3c24-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3c24-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="d3c24-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3c24-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="d3c24-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d3c24-124">SIP 對話方塊 ID，儲存為二進位。</span><span class="sxs-lookup"><span data-stu-id="d3c24-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="d3c24-125">二進位檔的格式為：</span><span class="sxs-lookup"><span data-stu-id="d3c24-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="d3c24-126">對話方塊; 從標籤; 來標記</span><span class="sxs-lookup"><span data-stu-id="d3c24-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="d3c24-127">可以使用下列語法，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="d3c24-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

