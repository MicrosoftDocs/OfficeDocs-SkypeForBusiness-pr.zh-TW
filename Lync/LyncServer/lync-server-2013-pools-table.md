---
title: Lync Server 2013： Pool 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pools table
ms:assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398991(v=OCS.15)
ms:contentKeyID: 48185680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f9895307599210a7d30fde58d7e09b8353388db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527990"
---
# <a name="pools-table-in-lync-server-2013"></a><span data-ttu-id="87b5b-102">Lync Server 2013 中的 pool 表格</span><span class="sxs-lookup"><span data-stu-id="87b5b-102">Pools table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87b5b-103">_**主題上次修改日期：** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="87b5b-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="87b5b-104">Pool 表格是一種支援資料表，可儲存各種集區的資訊。</span><span class="sxs-lookup"><span data-stu-id="87b5b-104">The Pools table is a supporting table that stores information about the various pool.</span></span> <span data-ttu-id="87b5b-105">資料表中的每一筆記錄都代表一個集區。</span><span class="sxs-lookup"><span data-stu-id="87b5b-105">Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87b5b-106">欄</span><span class="sxs-lookup"><span data-stu-id="87b5b-106">Column</span></span></th>
<th><span data-ttu-id="87b5b-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="87b5b-107">Data Type</span></span></th>
<th><span data-ttu-id="87b5b-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="87b5b-108">Key/Index</span></span></th>
<th><span data-ttu-id="87b5b-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="87b5b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87b5b-110"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="87b5b-110"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="87b5b-111">int</span><span class="sxs-lookup"><span data-stu-id="87b5b-111">int</span></span></p></td>
<td><p><span data-ttu-id="87b5b-112">主要</span><span class="sxs-lookup"><span data-stu-id="87b5b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="87b5b-113">用於識別此集區的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="87b5b-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87b5b-114"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="87b5b-114"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="87b5b-115">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="87b5b-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="87b5b-116">集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="87b5b-116">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

