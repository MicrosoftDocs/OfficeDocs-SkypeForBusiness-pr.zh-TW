---
title: Lync Server 2013： tblPreference
description: Lync Server 2013： tblPreference。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e8b81a6af93e9bf1d7673e54492579a1bed08e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547509"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="e898a-103">Lync Server 2013 中的 tblPreference</span><span class="sxs-lookup"><span data-stu-id="e898a-103">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e898a-104">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="e898a-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="e898a-105">tblPreference 包含使用者的用戶端喜好設定。</span><span class="sxs-lookup"><span data-stu-id="e898a-105">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="e898a-106">這通常是 Lync 2013 之前的用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="e898a-106">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="e898a-107">Columns</span><span class="sxs-lookup"><span data-stu-id="e898a-107">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e898a-108">欄</span><span class="sxs-lookup"><span data-stu-id="e898a-108">Column</span></span></th>
<th><span data-ttu-id="e898a-109">類型</span><span class="sxs-lookup"><span data-stu-id="e898a-109">Type</span></span></th>
<th><span data-ttu-id="e898a-110">描述</span><span class="sxs-lookup"><span data-stu-id="e898a-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e898a-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="e898a-111">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="e898a-112">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="e898a-112">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="e898a-113">標籤，格式如下： &lt; user sip uri &gt; | username。 &lt;喜好設定 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="e898a-113">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e898a-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="e898a-114">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="e898a-115">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e898a-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e898a-116">每個標籤的序數位 (，供版本設定之用) 。</span><span class="sxs-lookup"><span data-stu-id="e898a-116">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e898a-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="e898a-117">prefContent</span></span></p></td>
<td><p><span data-ttu-id="e898a-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="e898a-118">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="e898a-119">編碼內容。</span><span class="sxs-lookup"><span data-stu-id="e898a-119">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e898a-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="e898a-120">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="e898a-121">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e898a-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e898a-122">更新首選項的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="e898a-122">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e898a-123">索引鍵</span><span class="sxs-lookup"><span data-stu-id="e898a-123">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e898a-124">欄</span><span class="sxs-lookup"><span data-stu-id="e898a-124">Column</span></span></th>
<th><span data-ttu-id="e898a-125">描述</span><span class="sxs-lookup"><span data-stu-id="e898a-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e898a-126">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="e898a-126">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e898a-127">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e898a-127">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

