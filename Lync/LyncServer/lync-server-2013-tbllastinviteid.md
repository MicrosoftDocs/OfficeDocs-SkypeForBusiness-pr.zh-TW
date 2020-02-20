---
title: 'Lync Server 2013: tbllastinviteid 表格'
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
ms.openlocfilehash: 40b77e2ccf7e689160e6072bdcfa7896bb3439d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="b0c9e-102">Lync Server 2013 中的 tbllastinviteid 表格</span><span class="sxs-lookup"><span data-stu-id="b0c9e-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0c9e-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="b0c9e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b0c9e-104">tblLastInviteId 表格含有每個使用者產生 (也用於 tblPrincipalInvites 表格) 的最後一個邀請 ID。</span><span class="sxs-lookup"><span data-stu-id="b0c9e-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="b0c9e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="b0c9e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0c9e-106">欄</span><span class="sxs-lookup"><span data-stu-id="b0c9e-106">Column</span></span></th>
<th><span data-ttu-id="b0c9e-107">類型	</span><span class="sxs-lookup"><span data-stu-id="b0c9e-107">Type</span></span></th>
<th><span data-ttu-id="b0c9e-108">描述</span><span class="sxs-lookup"><span data-stu-id="b0c9e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0c9e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b0c9e-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="b0c9e-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="b0c9e-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b0c9e-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="b0c9e-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c9e-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="b0c9e-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="b0c9e-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="b0c9e-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b0c9e-114">最後一個邀請 ID。</span><span class="sxs-lookup"><span data-stu-id="b0c9e-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b0c9e-115">索引鍵</span><span class="sxs-lookup"><span data-stu-id="b0c9e-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0c9e-116">欄</span><span class="sxs-lookup"><span data-stu-id="b0c9e-116">Column</span></span></th>
<th><span data-ttu-id="b0c9e-117">描述</span><span class="sxs-lookup"><span data-stu-id="b0c9e-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0c9e-118">prinID</span><span class="sxs-lookup"><span data-stu-id="b0c9e-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="b0c9e-119">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b0c9e-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c9e-120">prinID</span><span class="sxs-lookup"><span data-stu-id="b0c9e-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="b0c9e-121">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b0c9e-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b0c9e-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b0c9e-122">See Also</span></span>


[<span data-ttu-id="b0c9e-123">Lync Server 2013 中的 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="b0c9e-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

