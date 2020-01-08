---
title: Lync Server 2013：tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 652312c5ca48a140ee7f17486ef98debb4e08672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="3848b-102">Lync Server 2013 中的 tblPreference</span><span class="sxs-lookup"><span data-stu-id="3848b-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3848b-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="3848b-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="3848b-104">tblPreference 包含使用者的用戶端喜好設定。</span><span class="sxs-lookup"><span data-stu-id="3848b-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="3848b-105">這通常是由 Lync 2013 舊版用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="3848b-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="3848b-106">分欄</span><span class="sxs-lookup"><span data-stu-id="3848b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3848b-107">左欄</span><span class="sxs-lookup"><span data-stu-id="3848b-107">Column</span></span></th>
<th><span data-ttu-id="3848b-108">類型</span><span class="sxs-lookup"><span data-stu-id="3848b-108">Type</span></span></th>
<th><span data-ttu-id="3848b-109">描述</span><span class="sxs-lookup"><span data-stu-id="3848b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3848b-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="3848b-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="3848b-111">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="3848b-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="3848b-112">標籤的格式如下： &lt;使用者 sip uri&gt;| username。&lt;喜好設定&gt;。</span><span class="sxs-lookup"><span data-stu-id="3848b-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3848b-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="3848b-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="3848b-114">int，not null</span><span class="sxs-lookup"><span data-stu-id="3848b-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3848b-115">用於進行版本設定的順序編號（每個標籤）。</span><span class="sxs-lookup"><span data-stu-id="3848b-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3848b-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="3848b-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="3848b-117">Nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="3848b-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="3848b-118">已編碼的內容。</span><span class="sxs-lookup"><span data-stu-id="3848b-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3848b-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="3848b-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="3848b-120">int，not null</span><span class="sxs-lookup"><span data-stu-id="3848b-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3848b-121">更新喜好設定的主體 ID。</span><span class="sxs-lookup"><span data-stu-id="3848b-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="3848b-122">機碼</span><span class="sxs-lookup"><span data-stu-id="3848b-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3848b-123">左欄</span><span class="sxs-lookup"><span data-stu-id="3848b-123">Column</span></span></th>
<th><span data-ttu-id="3848b-124">描述</span><span class="sxs-lookup"><span data-stu-id="3848b-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3848b-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="3848b-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="3848b-126">主鍵。</span><span class="sxs-lookup"><span data-stu-id="3848b-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

