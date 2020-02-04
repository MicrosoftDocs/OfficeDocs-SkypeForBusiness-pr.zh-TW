---
title: Lync Server 2013：tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baaf336013ec09b17b8e688889fdf27aa29ef644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="1204b-102">Lync Server 2013 中的 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="1204b-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1204b-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1204b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1204b-104">tblPrincipalMemberDifference 包含尚未由後續 Active Directory 網域服務同步處理步驟處理的群組成員資格變更（新增和移除的成員）。</span><span class="sxs-lookup"><span data-stu-id="1204b-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="1204b-105">分欄</span><span class="sxs-lookup"><span data-stu-id="1204b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1204b-106">左欄</span><span class="sxs-lookup"><span data-stu-id="1204b-106">Column</span></span></th>
<th><span data-ttu-id="1204b-107">類型</span><span class="sxs-lookup"><span data-stu-id="1204b-107">Type</span></span></th>
<th><span data-ttu-id="1204b-108">說明</span><span class="sxs-lookup"><span data-stu-id="1204b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1204b-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="1204b-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="1204b-110">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="1204b-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="1204b-111">已變更之群組的主要 GUID。</span><span class="sxs-lookup"><span data-stu-id="1204b-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1204b-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="1204b-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="1204b-113">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1204b-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="1204b-114">成員的判別名。</span><span class="sxs-lookup"><span data-stu-id="1204b-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1204b-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="1204b-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="1204b-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="1204b-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1204b-117">如果成員已新增，則為 False。</span><span class="sxs-lookup"><span data-stu-id="1204b-117">False if the member was added.</span></span> <span data-ttu-id="1204b-118">如果成員已移除，則為 True。</span><span class="sxs-lookup"><span data-stu-id="1204b-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="1204b-119">機碼</span><span class="sxs-lookup"><span data-stu-id="1204b-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1204b-120">左欄</span><span class="sxs-lookup"><span data-stu-id="1204b-120">Column</span></span></th>
<th><span data-ttu-id="1204b-121">說明</span><span class="sxs-lookup"><span data-stu-id="1204b-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1204b-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="1204b-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="1204b-123">主鍵。</span><span class="sxs-lookup"><span data-stu-id="1204b-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

