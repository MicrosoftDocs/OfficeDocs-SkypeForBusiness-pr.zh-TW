---
title: Lync Server 2013： CallType 表格
description: Lync Server 2013： CallType 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af9c40396b993893f5157b89bedff0d80d87eb0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565169"
---
# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="a3fae-103">Lync Server 2013 中的 CallType 表格</span><span class="sxs-lookup"><span data-stu-id="a3fae-103">CallType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3fae-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a3fae-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a3fae-105">CallType 表格是儲存可能通話類型清單的靜態表格。</span><span class="sxs-lookup"><span data-stu-id="a3fae-105">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3fae-106">欄</span><span class="sxs-lookup"><span data-stu-id="a3fae-106">Column</span></span></th>
<th><span data-ttu-id="a3fae-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="a3fae-107">Data Type</span></span></th>
<th><span data-ttu-id="a3fae-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="a3fae-108">Key/Index</span></span></th>
<th><span data-ttu-id="a3fae-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a3fae-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3fae-110"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a3fae-110"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3fae-111">int</span><span class="sxs-lookup"><span data-stu-id="a3fae-111">int</span></span></p></td>
<td><p><span data-ttu-id="a3fae-112">主要</span><span class="sxs-lookup"><span data-stu-id="a3fae-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3fae-113"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="a3fae-113"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="a3fae-114">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="a3fae-114">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3fae-115">允許的值：</span><span class="sxs-lookup"><span data-stu-id="a3fae-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a3fae-116">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="a3fae-116">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="a3fae-117">1–立即訊息</span><span class="sxs-lookup"><span data-stu-id="a3fae-117">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="a3fae-118">2--應用程式共用</span><span class="sxs-lookup"><span data-stu-id="a3fae-118">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="a3fae-119">3--音訊</span><span class="sxs-lookup"><span data-stu-id="a3fae-119">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="a3fae-120">4–音訊和影片</span><span class="sxs-lookup"><span data-stu-id="a3fae-120">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="a3fae-121">5–檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="a3fae-121">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

