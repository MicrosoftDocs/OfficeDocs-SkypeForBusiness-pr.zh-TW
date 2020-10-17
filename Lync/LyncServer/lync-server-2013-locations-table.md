---
title: Lync Server 2013：位置表格
description: Lync Server 2013：位置表格。
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
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570579"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="effe5-103">Lync Server 2013 中的位置表格</span><span class="sxs-lookup"><span data-stu-id="effe5-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="effe5-104">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="effe5-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="effe5-105">每筆記錄代表緊急通話中參照的一個位置，例如 E9-1-1 通話。</span><span class="sxs-lookup"><span data-stu-id="effe5-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="effe5-106">欄</span><span class="sxs-lookup"><span data-stu-id="effe5-106">Column</span></span></th>
<th><span data-ttu-id="effe5-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="effe5-107">Data Type</span></span></th>
<th><span data-ttu-id="effe5-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="effe5-108">Key/Index</span></span></th>
<th><span data-ttu-id="effe5-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="effe5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="effe5-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="effe5-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="effe5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="effe5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="effe5-112">主要，外部</span><span class="sxs-lookup"><span data-stu-id="effe5-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="effe5-113">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="effe5-113">Time of session request.</span></span> <span data-ttu-id="effe5-114">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="effe5-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="effe5-115">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="effe5-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="effe5-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="effe5-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="effe5-117">int</span><span class="sxs-lookup"><span data-stu-id="effe5-117">int</span></span></p></td>
<td><p><span data-ttu-id="effe5-118">主要，外部</span><span class="sxs-lookup"><span data-stu-id="effe5-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="effe5-119">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="effe5-119">ID number to identify the session.</span></span> <span data-ttu-id="effe5-120">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="effe5-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="effe5-121">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="effe5-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="effe5-122"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="effe5-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="effe5-123">Nvarchar (max) </span><span class="sxs-lookup"><span data-stu-id="effe5-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="effe5-124">緊急電話的位置。</span><span class="sxs-lookup"><span data-stu-id="effe5-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

