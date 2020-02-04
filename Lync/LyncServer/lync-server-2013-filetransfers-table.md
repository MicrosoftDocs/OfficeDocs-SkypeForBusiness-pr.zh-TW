---
title: Lync Server 2013：FileTransfers 表格
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
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="502ff-102">Lync Server 2013 中的 FileTransfers 表格</span><span class="sxs-lookup"><span data-stu-id="502ff-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="502ff-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="502ff-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="502ff-104">每個記錄代表一個檔案傳輸會話。</span><span class="sxs-lookup"><span data-stu-id="502ff-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="502ff-105">左欄</span><span class="sxs-lookup"><span data-stu-id="502ff-105">Column</span></span></th>
<th><span data-ttu-id="502ff-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="502ff-106">Data Type</span></span></th>
<th><span data-ttu-id="502ff-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="502ff-107">Key/Index</span></span></th>
<th><span data-ttu-id="502ff-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="502ff-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="502ff-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="502ff-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="502ff-110">datetime</span><span class="sxs-lookup"><span data-stu-id="502ff-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="502ff-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="502ff-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="502ff-112">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="502ff-112">Time of session request.</span></span> <span data-ttu-id="502ff-113">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="502ff-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="502ff-114">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="502ff-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="502ff-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="502ff-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="502ff-116">int</span><span class="sxs-lookup"><span data-stu-id="502ff-116">int</span></span></p></td>
<td><p><span data-ttu-id="502ff-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="502ff-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="502ff-118">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="502ff-118">ID number to identify the session.</span></span> <span data-ttu-id="502ff-119">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="502ff-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="502ff-120">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="502ff-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="502ff-121"><strong>檔案名</strong></span><span class="sxs-lookup"><span data-stu-id="502ff-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="502ff-122">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="502ff-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="502ff-123">檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="502ff-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="502ff-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="502ff-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="502ff-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="502ff-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="502ff-126">唯一識別碼，區分涉及相同檔案名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="502ff-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="502ff-127"><strong>C</strong></span><span class="sxs-lookup"><span data-stu-id="502ff-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="502ff-128">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="502ff-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="502ff-129">首選</span><span class="sxs-lookup"><span data-stu-id="502ff-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="502ff-130">用來識別與此郵件相關聯的每一封後續訊息。</span><span class="sxs-lookup"><span data-stu-id="502ff-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="502ff-131"><strong>接受</strong></span><span class="sxs-lookup"><span data-stu-id="502ff-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="502ff-132">稍微</span><span class="sxs-lookup"><span data-stu-id="502ff-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="502ff-133">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="502ff-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="502ff-134">如果為 TRUE，則 [拒絕] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="502ff-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="502ff-135"><strong>否決</strong></span><span class="sxs-lookup"><span data-stu-id="502ff-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="502ff-136">稍微</span><span class="sxs-lookup"><span data-stu-id="502ff-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="502ff-137">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="502ff-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="502ff-138">如果為 TRUE，則 [接受] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="502ff-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="502ff-139"><strong>取消</strong></span><span class="sxs-lookup"><span data-stu-id="502ff-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="502ff-140">稍微</span><span class="sxs-lookup"><span data-stu-id="502ff-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="502ff-141">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="502ff-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="502ff-142">如果為 TRUE，則 [接受] 和 [拒絕] 會是 Null。</span><span class="sxs-lookup"><span data-stu-id="502ff-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

