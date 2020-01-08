---
title: Lync Server 2013：Dialogs 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a25ae1d298f1cf5908c4669a78485491fadd617d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="56052-102">Lync Server 2013 中的 Dialogs 表格</span><span class="sxs-lookup"><span data-stu-id="56052-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56052-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="56052-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="56052-104">對話方塊表格是一個支援資料表，可儲存點對點工作階段之 DialogIDs 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="56052-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56052-105">左欄</span><span class="sxs-lookup"><span data-stu-id="56052-105">Column</span></span></th>
<th><span data-ttu-id="56052-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="56052-106">Data Type</span></span></th>
<th><span data-ttu-id="56052-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="56052-107">Key/Index</span></span></th>
<th><span data-ttu-id="56052-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="56052-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56052-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="56052-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="56052-110">datetime</span><span class="sxs-lookup"><span data-stu-id="56052-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="56052-111">首選</span><span class="sxs-lookup"><span data-stu-id="56052-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="56052-112">會話要求的時間;與 SessionIDSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="56052-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56052-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="56052-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="56052-114">int</span><span class="sxs-lookup"><span data-stu-id="56052-114">int</span></span></p></td>
<td><p><span data-ttu-id="56052-115">首選</span><span class="sxs-lookup"><span data-stu-id="56052-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="56052-116">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="56052-116">ID number to identify the session.</span></span> <span data-ttu-id="56052-117">與 SessionIDTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="56052-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56052-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="56052-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="56052-119">int</span><span class="sxs-lookup"><span data-stu-id="56052-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="56052-120">ExternalID 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="56052-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="56052-121">此欄位可用來提高資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="56052-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56052-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="56052-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="56052-123">Varbinary （775）</span><span class="sxs-lookup"><span data-stu-id="56052-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="56052-124">SIP 對話方塊識別碼，儲存為二進位。</span><span class="sxs-lookup"><span data-stu-id="56052-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="56052-125">二進位檔案的格式為：</span><span class="sxs-lookup"><span data-stu-id="56052-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="56052-126">對話方塊; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="56052-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="56052-127">您可以使用下列語法，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="56052-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

