---
title: 'Lync Server 2013: tblPreference'
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
ms.openlocfilehash: 3976cb18336477c00a901116a125149b8c67ddeb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="9acf6-102">Lync Server 2013 中的 tblPreference</span><span class="sxs-lookup"><span data-stu-id="9acf6-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9acf6-103">_**主題上次修改日期：** 2012年-09-24_</span><span class="sxs-lookup"><span data-stu-id="9acf6-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="9acf6-104">tblPreference 包含使用者的用戶端喜好設定。</span><span class="sxs-lookup"><span data-stu-id="9acf6-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="9acf6-105">這通常是早 Lync 2013 的用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="9acf6-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="9acf6-106">Columns</span><span class="sxs-lookup"><span data-stu-id="9acf6-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9acf6-107">欄</span><span class="sxs-lookup"><span data-stu-id="9acf6-107">Column</span></span></th>
<th><span data-ttu-id="9acf6-108">類型	</span><span class="sxs-lookup"><span data-stu-id="9acf6-108">Type</span></span></th>
<th><span data-ttu-id="9acf6-109">描述</span><span class="sxs-lookup"><span data-stu-id="9acf6-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9acf6-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="9acf6-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="9acf6-111">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="9acf6-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="9acf6-112">標籤格式如下：&lt;使用者 sip uri&gt;| username。&lt;喜好設定&gt;。</span><span class="sxs-lookup"><span data-stu-id="9acf6-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9acf6-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="9acf6-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="9acf6-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="9acf6-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9acf6-115">序號 （每個標籤） 設定版本。</span><span class="sxs-lookup"><span data-stu-id="9acf6-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9acf6-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="9acf6-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="9acf6-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="9acf6-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="9acf6-118">編編的內容。</span><span class="sxs-lookup"><span data-stu-id="9acf6-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9acf6-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="9acf6-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="9acf6-120">int，非 null</span><span class="sxs-lookup"><span data-stu-id="9acf6-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9acf6-121">更新喜好設定之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="9acf6-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="9acf6-122">索引鍵</span><span class="sxs-lookup"><span data-stu-id="9acf6-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9acf6-123">欄</span><span class="sxs-lookup"><span data-stu-id="9acf6-123">Column</span></span></th>
<th><span data-ttu-id="9acf6-124">描述</span><span class="sxs-lookup"><span data-stu-id="9acf6-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9acf6-125">&lt;prefLabel prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="9acf6-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9acf6-126">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="9acf6-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

