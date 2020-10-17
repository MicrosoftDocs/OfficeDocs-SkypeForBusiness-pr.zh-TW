---
title: Lync Server 2013：集區表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pool table
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48184803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5843908cf97a66e40ed2e9f945941c84615212
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528000"
---
# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="26eaf-102">Lync Server 2013 中的 Pool 表格</span><span class="sxs-lookup"><span data-stu-id="26eaf-102">Pool table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26eaf-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="26eaf-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="26eaf-104">Pool 表格是一種支援資料表，可儲存各種前端集區的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="26eaf-104">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="26eaf-105">資料表中的每一筆記錄都代表一個集區。</span><span class="sxs-lookup"><span data-stu-id="26eaf-105">Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26eaf-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="26eaf-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="26eaf-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="26eaf-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="26eaf-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="26eaf-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="26eaf-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="26eaf-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26eaf-110"><strong>PoolKey</strong></span><span class="sxs-lookup"><span data-stu-id="26eaf-110"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="26eaf-111">int</span><span class="sxs-lookup"><span data-stu-id="26eaf-111">int</span></span></p></td>
<td><p><span data-ttu-id="26eaf-112">主要</span><span class="sxs-lookup"><span data-stu-id="26eaf-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="26eaf-113">用於識別此集區的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="26eaf-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26eaf-114"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="26eaf-114"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="26eaf-115">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="26eaf-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26eaf-116">獨特 </span><span class="sxs-lookup"><span data-stu-id="26eaf-116">Unique </span></span></p></td>
<td><p><span data-ttu-id="26eaf-117">集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="26eaf-117">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

