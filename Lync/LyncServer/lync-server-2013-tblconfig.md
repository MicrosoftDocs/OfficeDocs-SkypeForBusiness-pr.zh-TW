---
title: 'Lync Server 2013: tblConfig'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 399d4e794b45f549aed86838463091db437b286f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="02b23-102">Lync Server 2013 中的 tblConfig</span><span class="sxs-lookup"><span data-stu-id="02b23-102">tblConfig in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02b23-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="02b23-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="02b23-104">tblConfig 包含部分 Persistent Chat Server 不支援的組態，其中一個資料列。</span><span class="sxs-lookup"><span data-stu-id="02b23-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="02b23-105">Columns</span><span class="sxs-lookup"><span data-stu-id="02b23-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b23-106">欄</span><span class="sxs-lookup"><span data-stu-id="02b23-106">Column</span></span></th>
<th><span data-ttu-id="02b23-107">類型	</span><span class="sxs-lookup"><span data-stu-id="02b23-107">Type</span></span></th>
<th><span data-ttu-id="02b23-108">描述</span><span class="sxs-lookup"><span data-stu-id="02b23-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b23-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="02b23-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="02b23-110">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="02b23-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="02b23-111">包含&quot;集區。&quot;</span><span class="sxs-lookup"><span data-stu-id="02b23-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b23-112">configContent</span><span class="sxs-lookup"><span data-stu-id="02b23-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="02b23-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="02b23-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="02b23-114">設定內容。</span><span class="sxs-lookup"><span data-stu-id="02b23-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b23-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="02b23-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="02b23-116">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="02b23-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="02b23-117">資料庫執行個體的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="02b23-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="02b23-118">索引鍵</span><span class="sxs-lookup"><span data-stu-id="02b23-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b23-119">欄</span><span class="sxs-lookup"><span data-stu-id="02b23-119">Column</span></span></th>
<th><span data-ttu-id="02b23-120">描述</span><span class="sxs-lookup"><span data-stu-id="02b23-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b23-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="02b23-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="02b23-122">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="02b23-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

