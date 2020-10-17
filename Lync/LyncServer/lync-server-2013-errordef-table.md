---
title: Lync Server 2013： ErrorDef 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f94f926193fe6a0ac389f5aed6e5cc2f9eb536a8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533130"
---
# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="22a2a-102">Lync Server 2013 中的 ErrorDef 表格</span><span class="sxs-lookup"><span data-stu-id="22a2a-102">ErrorDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22a2a-103">_**主題上次修改日期：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="22a2a-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="22a2a-104">ErrorDef 表會儲存可能發生的每一種錯誤類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="22a2a-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="22a2a-105">每個記錄是一種錯誤類型。</span><span class="sxs-lookup"><span data-stu-id="22a2a-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22a2a-106">欄</span><span class="sxs-lookup"><span data-stu-id="22a2a-106">Column</span></span></th>
<th><span data-ttu-id="22a2a-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="22a2a-107">Data Type</span></span></th>
<th><span data-ttu-id="22a2a-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="22a2a-108">Key/Index</span></span></th>
<th><span data-ttu-id="22a2a-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="22a2a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22a2a-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="22a2a-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="22a2a-111">int</span><span class="sxs-lookup"><span data-stu-id="22a2a-111">int</span></span></p></td>
<td><p><span data-ttu-id="22a2a-112">主要</span><span class="sxs-lookup"><span data-stu-id="22a2a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="22a2a-113">用來識別這種錯誤類型的唯一識別碼號碼。</span><span class="sxs-lookup"><span data-stu-id="22a2a-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22a2a-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="22a2a-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="22a2a-115">int</span><span class="sxs-lookup"><span data-stu-id="22a2a-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22a2a-116">與此錯誤相關聯的標準 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="22a2a-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22a2a-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="22a2a-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="22a2a-118">int</span><span class="sxs-lookup"><span data-stu-id="22a2a-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22a2a-119">Microsoft 診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="22a2a-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22a2a-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="22a2a-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="22a2a-121">臨界值</span><span class="sxs-lookup"><span data-stu-id="22a2a-121">Int</span></span></p></td>
<td><p><span data-ttu-id="22a2a-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="22a2a-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="22a2a-123">通話的類型。</span><span class="sxs-lookup"><span data-stu-id="22a2a-123">Type of the call.</span></span> <span data-ttu-id="22a2a-124">如需詳細資訊，請參閱 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="22a2a-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22a2a-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="22a2a-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="22a2a-126">Varbinary (33) </span><span class="sxs-lookup"><span data-stu-id="22a2a-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22a2a-127">失敗的要求類型。</span><span class="sxs-lookup"><span data-stu-id="22a2a-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="22a2a-128">您可以使用下列語法將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="22a2a-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22a2a-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="22a2a-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="22a2a-130">Varbinary (257) </span><span class="sxs-lookup"><span data-stu-id="22a2a-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="22a2a-131">失敗之要求的內容類型。</span><span class="sxs-lookup"><span data-stu-id="22a2a-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="22a2a-132">您可以使用此 syntaxt 將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="22a2a-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

