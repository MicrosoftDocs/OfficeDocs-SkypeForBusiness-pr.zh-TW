---
title: 'Lync Server 2013: ErrorDef 表格'
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
ms.openlocfilehash: c490bc9b5058af75704ec3d10c3535581c56df2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="0c6a9-102">Lync Server 2013 中的 ErrorDef 表格</span><span class="sxs-lookup"><span data-stu-id="0c6a9-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c6a9-103">_**主題上次修改日期：** 2012年-05-25_</span><span class="sxs-lookup"><span data-stu-id="0c6a9-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="0c6a9-104">ErrorDef 表格會儲存每一種可能會發生錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0c6a9-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="0c6a9-105">每一筆記錄是錯誤的一種類型。</span><span class="sxs-lookup"><span data-stu-id="0c6a9-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c6a9-106">欄</span><span class="sxs-lookup"><span data-stu-id="0c6a9-106">Column</span></span></th>
<th><span data-ttu-id="0c6a9-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="0c6a9-107">Data Type</span></span></th>
<th><span data-ttu-id="0c6a9-108">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="0c6a9-108">Key/Index</span></span></th>
<th><span data-ttu-id="0c6a9-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="0c6a9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c6a9-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="0c6a9-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c6a9-111">int</span><span class="sxs-lookup"><span data-stu-id="0c6a9-111">int</span></span></p></td>
<td><p><span data-ttu-id="0c6a9-112">主要</span><span class="sxs-lookup"><span data-stu-id="0c6a9-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="0c6a9-113">識別這類錯誤的唯一識別碼號碼。</span><span class="sxs-lookup"><span data-stu-id="0c6a9-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c6a9-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="0c6a9-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="0c6a9-115">int</span><span class="sxs-lookup"><span data-stu-id="0c6a9-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0c6a9-116">此錯誤相關聯標準 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="0c6a9-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c6a9-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="0c6a9-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c6a9-118">int</span><span class="sxs-lookup"><span data-stu-id="0c6a9-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0c6a9-119">Microsoft 診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="0c6a9-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c6a9-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="0c6a9-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c6a9-121">臨界值</span><span class="sxs-lookup"><span data-stu-id="0c6a9-121">Int</span></span></p></td>
<td><p><span data-ttu-id="0c6a9-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="0c6a9-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0c6a9-123">呼叫的類型。</span><span class="sxs-lookup"><span data-stu-id="0c6a9-123">Type of the call.</span></span> <span data-ttu-id="0c6a9-124">請參閱<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0c6a9-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c6a9-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="0c6a9-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="0c6a9-126">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="0c6a9-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0c6a9-127">失敗之要求的類型。</span><span class="sxs-lookup"><span data-stu-id="0c6a9-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="0c6a9-128">可以使用下列語法，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="0c6a9-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c6a9-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="0c6a9-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="0c6a9-130">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="0c6a9-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0c6a9-131">失敗之要求的內容類型。</span><span class="sxs-lookup"><span data-stu-id="0c6a9-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="0c6a9-132">可以使用以下語法將，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="0c6a9-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

