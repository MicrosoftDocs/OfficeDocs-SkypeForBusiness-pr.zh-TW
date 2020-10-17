---
title: Lync Server 2013： tblPreference
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
ms.openlocfilehash: ef0ee11cd780037410ea1d7e0d94c83e139d8418
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523770"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="2ba7f-102">Lync Server 2013 中的 tblPreference</span><span class="sxs-lookup"><span data-stu-id="2ba7f-102">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ba7f-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="2ba7f-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="2ba7f-104">tblPreference 包含使用者的用戶端喜好設定。</span><span class="sxs-lookup"><span data-stu-id="2ba7f-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="2ba7f-105">這通常是 Lync 2013 之前的用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="2ba7f-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="2ba7f-106">Columns</span><span class="sxs-lookup"><span data-stu-id="2ba7f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ba7f-107">欄</span><span class="sxs-lookup"><span data-stu-id="2ba7f-107">Column</span></span></th>
<th><span data-ttu-id="2ba7f-108">類型</span><span class="sxs-lookup"><span data-stu-id="2ba7f-108">Type</span></span></th>
<th><span data-ttu-id="2ba7f-109">描述</span><span class="sxs-lookup"><span data-stu-id="2ba7f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ba7f-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="2ba7f-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="2ba7f-111">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="2ba7f-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="2ba7f-112">標籤，格式如下： &lt; user sip uri &gt; | username。 &lt;喜好設定 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="2ba7f-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ba7f-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="2ba7f-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="2ba7f-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="2ba7f-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2ba7f-115">每個標籤的序數位 (，供版本設定之用) 。</span><span class="sxs-lookup"><span data-stu-id="2ba7f-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ba7f-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="2ba7f-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="2ba7f-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="2ba7f-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="2ba7f-118">編碼內容。</span><span class="sxs-lookup"><span data-stu-id="2ba7f-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ba7f-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="2ba7f-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="2ba7f-120">int，非 null</span><span class="sxs-lookup"><span data-stu-id="2ba7f-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2ba7f-121">更新首選項的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="2ba7f-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="2ba7f-122">索引鍵</span><span class="sxs-lookup"><span data-stu-id="2ba7f-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ba7f-123">欄</span><span class="sxs-lookup"><span data-stu-id="2ba7f-123">Column</span></span></th>
<th><span data-ttu-id="2ba7f-124">描述</span><span class="sxs-lookup"><span data-stu-id="2ba7f-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ba7f-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="2ba7f-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="2ba7f-126">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="2ba7f-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

