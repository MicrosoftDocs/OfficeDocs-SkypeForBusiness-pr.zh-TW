---
title: Lync Server 2013：tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5db403431c182e3f5bb8e7a3fabaa04cd2a94d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="23258-102">Lync Server 2013 中的 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="23258-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23258-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="23258-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="23258-104">tblPrincipalMemberDifference 包含尚未由後續 Active Directory 網域服務同步處理步驟處理的群組成員資格變更（新增和移除的成員）。</span><span class="sxs-lookup"><span data-stu-id="23258-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="23258-105">分欄</span><span class="sxs-lookup"><span data-stu-id="23258-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23258-106">左欄</span><span class="sxs-lookup"><span data-stu-id="23258-106">Column</span></span></th>
<th><span data-ttu-id="23258-107">類型</span><span class="sxs-lookup"><span data-stu-id="23258-107">Type</span></span></th>
<th><span data-ttu-id="23258-108">描述</span><span class="sxs-lookup"><span data-stu-id="23258-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23258-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="23258-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="23258-110">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="23258-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="23258-111">已變更之群組的主要 GUID。</span><span class="sxs-lookup"><span data-stu-id="23258-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23258-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="23258-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="23258-113">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="23258-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="23258-114">成員的判別名。</span><span class="sxs-lookup"><span data-stu-id="23258-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23258-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="23258-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="23258-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="23258-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="23258-117">如果成員已新增，則為 False。</span><span class="sxs-lookup"><span data-stu-id="23258-117">False if the member was added.</span></span> <span data-ttu-id="23258-118">如果成員已移除，則為 True。</span><span class="sxs-lookup"><span data-stu-id="23258-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="23258-119">機碼</span><span class="sxs-lookup"><span data-stu-id="23258-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23258-120">左欄</span><span class="sxs-lookup"><span data-stu-id="23258-120">Column</span></span></th>
<th><span data-ttu-id="23258-121">描述</span><span class="sxs-lookup"><span data-stu-id="23258-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23258-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="23258-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="23258-123">主鍵。</span><span class="sxs-lookup"><span data-stu-id="23258-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

