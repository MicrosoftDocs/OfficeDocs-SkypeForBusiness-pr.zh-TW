---
title: 'Lync Server 2013: Locations 表格'
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
ms.openlocfilehash: d93300acda297a026af03070680825899a608d86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="bb165-102">Lync Server 2013 中的位置表格</span><span class="sxs-lookup"><span data-stu-id="bb165-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb165-103">_**主題上次修改日期：** 2012年-05-25_</span><span class="sxs-lookup"><span data-stu-id="bb165-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="bb165-104">每筆記錄代表緊急通話中參照的一個位置，例如 E9-1-1 通話。</span><span class="sxs-lookup"><span data-stu-id="bb165-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb165-105">欄</span><span class="sxs-lookup"><span data-stu-id="bb165-105">Column</span></span></th>
<th><span data-ttu-id="bb165-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="bb165-106">Data Type</span></span></th>
<th><span data-ttu-id="bb165-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="bb165-107">Key/Index</span></span></th>
<th><span data-ttu-id="bb165-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="bb165-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb165-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb165-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb165-110">datetime</span><span class="sxs-lookup"><span data-stu-id="bb165-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb165-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="bb165-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb165-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="bb165-112">Time of session request.</span></span> <span data-ttu-id="bb165-113">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="bb165-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bb165-114"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bb165-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb165-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bb165-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bb165-116">int</span><span class="sxs-lookup"><span data-stu-id="bb165-116">int</span></span></p></td>
<td><p><span data-ttu-id="bb165-117">主要，外部</span><span class="sxs-lookup"><span data-stu-id="bb165-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bb165-118">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="bb165-118">ID number to identify the session.</span></span> <span data-ttu-id="bb165-119">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="bb165-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bb165-120"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bb165-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb165-121"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="bb165-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="bb165-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="bb165-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb165-123">緊急電話的位置。</span><span class="sxs-lookup"><span data-stu-id="bb165-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

