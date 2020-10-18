---
title: Lync Server 2013： FileTransfers 表格
description: Lync Server 2013： FileTransfers 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573359"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="c7e96-103">Lync Server 2013 中的 FileTransfers 表格</span><span class="sxs-lookup"><span data-stu-id="c7e96-103">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7e96-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c7e96-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c7e96-105">每筆記錄代表一個檔案傳輸工作階段。</span><span class="sxs-lookup"><span data-stu-id="c7e96-105">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7e96-106">欄</span><span class="sxs-lookup"><span data-stu-id="c7e96-106">Column</span></span></th>
<th><span data-ttu-id="c7e96-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="c7e96-107">Data Type</span></span></th>
<th><span data-ttu-id="c7e96-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="c7e96-108">Key/Index</span></span></th>
<th><span data-ttu-id="c7e96-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="c7e96-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7e96-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c7e96-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e96-111">datetime</span><span class="sxs-lookup"><span data-stu-id="c7e96-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7e96-112">主要，外部</span><span class="sxs-lookup"><span data-stu-id="c7e96-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7e96-113">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="c7e96-113">Time of session request.</span></span> <span data-ttu-id="c7e96-114">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="c7e96-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c7e96-115">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c7e96-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7e96-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c7e96-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e96-117">int</span><span class="sxs-lookup"><span data-stu-id="c7e96-117">int</span></span></p></td>
<td><p><span data-ttu-id="c7e96-118">主要，外部</span><span class="sxs-lookup"><span data-stu-id="c7e96-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7e96-119">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="c7e96-119">ID number to identify the session.</span></span> <span data-ttu-id="c7e96-120">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="c7e96-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c7e96-121">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c7e96-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7e96-122"><strong>檔案名稱</strong></span><span class="sxs-lookup"><span data-stu-id="c7e96-122"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e96-123">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c7e96-123">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7e96-124">檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="c7e96-124">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7e96-125"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="c7e96-125"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e96-126">唯一</span><span class="sxs-lookup"><span data-stu-id="c7e96-126">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7e96-127">唯一識別碼，用於分辨包含相同檔名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="c7e96-127">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7e96-128"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="c7e96-128"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e96-129">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c7e96-129">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c7e96-130">主要</span><span class="sxs-lookup"><span data-stu-id="c7e96-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="c7e96-131">可用來識別與此訊息相關聯的每則後續訊息。</span><span class="sxs-lookup"><span data-stu-id="c7e96-131">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7e96-132"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="c7e96-132"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e96-133">位</span><span class="sxs-lookup"><span data-stu-id="c7e96-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7e96-p103">可為 TRUE 或 NULL。若為 TRUE，則「拒絕」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="c7e96-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7e96-136"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="c7e96-136"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e96-137">位</span><span class="sxs-lookup"><span data-stu-id="c7e96-137">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7e96-p104">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="c7e96-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7e96-140"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="c7e96-140"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="c7e96-141">位</span><span class="sxs-lookup"><span data-stu-id="c7e96-141">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7e96-p105">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「拒絕」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="c7e96-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

