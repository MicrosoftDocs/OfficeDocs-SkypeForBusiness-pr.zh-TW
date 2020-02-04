---
title: Lync Server 2013：tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c92a51ed9b775990d048bf45bfa54a893ba15856
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="527f9-102">Lync Server 2013 中的 tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="527f9-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="527f9-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="527f9-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="527f9-104">tblLastInviteId 包含每位使用者所產生（並在 tblPrincipalInvites 資料表中使用）的最後一個邀請識別碼。</span><span class="sxs-lookup"><span data-stu-id="527f9-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="527f9-105">分欄</span><span class="sxs-lookup"><span data-stu-id="527f9-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="527f9-106">左欄</span><span class="sxs-lookup"><span data-stu-id="527f9-106">Column</span></span></th>
<th><span data-ttu-id="527f9-107">類型</span><span class="sxs-lookup"><span data-stu-id="527f9-107">Type</span></span></th>
<th><span data-ttu-id="527f9-108">說明</span><span class="sxs-lookup"><span data-stu-id="527f9-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="527f9-109">prinID</span><span class="sxs-lookup"><span data-stu-id="527f9-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="527f9-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="527f9-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="527f9-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="527f9-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="527f9-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="527f9-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="527f9-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="527f9-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="527f9-114">上次使用邀請 ID。</span><span class="sxs-lookup"><span data-stu-id="527f9-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="527f9-115">鍵</span><span class="sxs-lookup"><span data-stu-id="527f9-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="527f9-116">左欄</span><span class="sxs-lookup"><span data-stu-id="527f9-116">Column</span></span></th>
<th><span data-ttu-id="527f9-117">說明</span><span class="sxs-lookup"><span data-stu-id="527f9-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="527f9-118">prinID</span><span class="sxs-lookup"><span data-stu-id="527f9-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="527f9-119">主鍵。</span><span class="sxs-lookup"><span data-stu-id="527f9-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="527f9-120">prinID</span><span class="sxs-lookup"><span data-stu-id="527f9-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="527f9-121">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="527f9-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="527f9-122">請參閱</span><span class="sxs-lookup"><span data-stu-id="527f9-122">See Also</span></span>


[<span data-ttu-id="527f9-123">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="527f9-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

