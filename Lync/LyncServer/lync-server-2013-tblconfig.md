---
title: Lync Server 2013： tblConfig
description: Lync Server 2013： tblConfig。
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
ms.openlocfilehash: 8990e0b2c8724a5e90c36e706b92f9985f288772
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550429"
---
# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="5a429-103">Lync Server 2013 中的 tblConfig</span><span class="sxs-lookup"><span data-stu-id="5a429-103">tblConfig in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a429-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5a429-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5a429-105">tblConfig 包含一些持久聊天伺服器不支援的設定，一列。</span><span class="sxs-lookup"><span data-stu-id="5a429-105">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="5a429-106">Columns</span><span class="sxs-lookup"><span data-stu-id="5a429-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a429-107">欄</span><span class="sxs-lookup"><span data-stu-id="5a429-107">Column</span></span></th>
<th><span data-ttu-id="5a429-108">類型</span><span class="sxs-lookup"><span data-stu-id="5a429-108">Type</span></span></th>
<th><span data-ttu-id="5a429-109">描述</span><span class="sxs-lookup"><span data-stu-id="5a429-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a429-110">configLabel</span><span class="sxs-lookup"><span data-stu-id="5a429-110">configLabel</span></span></p></td>
<td><p><span data-ttu-id="5a429-111">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="5a429-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5a429-112">包含 &quot; 集區。&quot;</span><span class="sxs-lookup"><span data-stu-id="5a429-112">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a429-113">configContent</span><span class="sxs-lookup"><span data-stu-id="5a429-113">configContent</span></span></p></td>
<td><p><span data-ttu-id="5a429-114">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5a429-114">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="5a429-115">設定內容。</span><span class="sxs-lookup"><span data-stu-id="5a429-115">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a429-116">configPoolID</span><span class="sxs-lookup"><span data-stu-id="5a429-116">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="5a429-117">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="5a429-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5a429-118">資料庫執行個體的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="5a429-118">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5a429-119">索引鍵</span><span class="sxs-lookup"><span data-stu-id="5a429-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a429-120">欄</span><span class="sxs-lookup"><span data-stu-id="5a429-120">Column</span></span></th>
<th><span data-ttu-id="5a429-121">描述</span><span class="sxs-lookup"><span data-stu-id="5a429-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a429-122">configLabel</span><span class="sxs-lookup"><span data-stu-id="5a429-122">configLabel</span></span></p></td>
<td><p><span data-ttu-id="5a429-123">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="5a429-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

