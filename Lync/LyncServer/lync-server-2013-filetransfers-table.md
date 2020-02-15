---
title: 'Lync Server 2013: FileTransfers 表格'
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
ms.openlocfilehash: 9aedca2ae840947aef4ccc6ec7bff4ba825090a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="1694b-102">Lync Server 2013 中的 FileTransfers 表格</span><span class="sxs-lookup"><span data-stu-id="1694b-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1694b-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="1694b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1694b-104">每筆記錄代表一個檔案傳輸工作階段。</span><span class="sxs-lookup"><span data-stu-id="1694b-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1694b-105">欄</span><span class="sxs-lookup"><span data-stu-id="1694b-105">Column</span></span></th>
<th><span data-ttu-id="1694b-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="1694b-106">Data Type</span></span></th>
<th><span data-ttu-id="1694b-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="1694b-107">Key/Index</span></span></th>
<th><span data-ttu-id="1694b-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="1694b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1694b-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1694b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1694b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1694b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1694b-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="1694b-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1694b-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="1694b-112">Time of session request.</span></span> <span data-ttu-id="1694b-113">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="1694b-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1694b-114"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="1694b-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1694b-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1694b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1694b-116">int</span><span class="sxs-lookup"><span data-stu-id="1694b-116">int</span></span></p></td>
<td><p><span data-ttu-id="1694b-117">主要，外部</span><span class="sxs-lookup"><span data-stu-id="1694b-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1694b-118">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="1694b-118">ID number to identify the session.</span></span> <span data-ttu-id="1694b-119">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="1694b-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1694b-120"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="1694b-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1694b-121"><strong>檔案名稱</strong></span><span class="sxs-lookup"><span data-stu-id="1694b-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="1694b-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1694b-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1694b-123">檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="1694b-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1694b-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="1694b-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="1694b-125">唯一</span><span class="sxs-lookup"><span data-stu-id="1694b-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1694b-126">唯一識別碼，用於分辨包含相同檔名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="1694b-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1694b-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="1694b-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="1694b-128">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="1694b-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="1694b-129">主要</span><span class="sxs-lookup"><span data-stu-id="1694b-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="1694b-130">可用來識別與此訊息相關聯的每則後續訊息。</span><span class="sxs-lookup"><span data-stu-id="1694b-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1694b-131"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="1694b-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="1694b-132">位元</span><span class="sxs-lookup"><span data-stu-id="1694b-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1694b-p103">可為 TRUE 或 NULL。若為 TRUE，則「拒絕」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="1694b-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1694b-135"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="1694b-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="1694b-136">位元</span><span class="sxs-lookup"><span data-stu-id="1694b-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1694b-p104">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="1694b-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1694b-139"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="1694b-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="1694b-140">位元</span><span class="sxs-lookup"><span data-stu-id="1694b-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1694b-p105">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「拒絕」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="1694b-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

