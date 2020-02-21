---
title: 'Lync Server 2013: tblSiopWhiteList'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625400f6b6cd602de247cc0bdf612e81713e1663
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="4dc4e-102">Lync Server 2013 中的 tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="4dc4e-102">tblSiopWhiteList in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dc4e-103">_**主題上次修改日期：** 2012年-06-28_</span><span class="sxs-lookup"><span data-stu-id="4dc4e-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="4dc4e-104">tblSiopWhiteList 是可與節點相關聯的註冊增益集清單。</span><span class="sxs-lookup"><span data-stu-id="4dc4e-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="4dc4e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="4dc4e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4dc4e-106">欄</span><span class="sxs-lookup"><span data-stu-id="4dc4e-106">Column</span></span></th>
<th><span data-ttu-id="4dc4e-107">類型	</span><span class="sxs-lookup"><span data-stu-id="4dc4e-107">Type</span></span></th>
<th><span data-ttu-id="4dc4e-108">描述</span><span class="sxs-lookup"><span data-stu-id="4dc4e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4dc4e-109">siopID</span><span class="sxs-lookup"><span data-stu-id="4dc4e-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="4dc4e-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="4dc4e-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="4dc4e-111">增益集的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4dc4e-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dc4e-112">siopName</span><span class="sxs-lookup"><span data-stu-id="4dc4e-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="4dc4e-113">nvarchar (50)，非 null</span><span class="sxs-lookup"><span data-stu-id="4dc4e-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="4dc4e-114">增益集的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="4dc4e-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dc4e-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="4dc4e-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="4dc4e-116">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="4dc4e-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="4dc4e-117">增益集的 URL。</span><span class="sxs-lookup"><span data-stu-id="4dc4e-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4dc4e-118">索引鍵</span><span class="sxs-lookup"><span data-stu-id="4dc4e-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4dc4e-119">欄</span><span class="sxs-lookup"><span data-stu-id="4dc4e-119">Column</span></span></th>
<th><span data-ttu-id="4dc4e-120">描述</span><span class="sxs-lookup"><span data-stu-id="4dc4e-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4dc4e-121">siopID</span><span class="sxs-lookup"><span data-stu-id="4dc4e-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="4dc4e-122">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="4dc4e-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

