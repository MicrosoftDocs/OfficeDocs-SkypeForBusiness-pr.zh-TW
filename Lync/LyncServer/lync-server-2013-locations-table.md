---
title: Lync Server 2013：Locations 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2d16ffd08184a650f993d175239f5aff72b8b3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="f99c9-102">Lync Server 2013 中的 Locations 表格</span><span class="sxs-lookup"><span data-stu-id="f99c9-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f99c9-103">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="f99c9-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="f99c9-104">每個記錄代表緊急呼叫中的一個位置參照，就像是 E9-1-1 通話。</span><span class="sxs-lookup"><span data-stu-id="f99c9-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f99c9-105">左欄</span><span class="sxs-lookup"><span data-stu-id="f99c9-105">Column</span></span></th>
<th><span data-ttu-id="f99c9-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="f99c9-106">Data Type</span></span></th>
<th><span data-ttu-id="f99c9-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="f99c9-107">Key/Index</span></span></th>
<th><span data-ttu-id="f99c9-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f99c9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f99c9-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f99c9-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f99c9-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f99c9-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f99c9-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="f99c9-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f99c9-112">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="f99c9-112">Time of session request.</span></span> <span data-ttu-id="f99c9-113">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="f99c9-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f99c9-114">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f99c9-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f99c9-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f99c9-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f99c9-116">int</span><span class="sxs-lookup"><span data-stu-id="f99c9-116">int</span></span></p></td>
<td><p><span data-ttu-id="f99c9-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="f99c9-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f99c9-118">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="f99c9-118">ID number to identify the session.</span></span> <span data-ttu-id="f99c9-119">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="f99c9-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f99c9-120">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f99c9-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f99c9-121"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="f99c9-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="f99c9-122">Nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="f99c9-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f99c9-123">緊急通話的位置。</span><span class="sxs-lookup"><span data-stu-id="f99c9-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

