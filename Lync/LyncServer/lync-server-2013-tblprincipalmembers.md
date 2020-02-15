---
title: 'Lync Server 2013: tblprincipalmembers 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c81e9ae5b2a712e3d6bb43fc35bd8083334efc1a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="ba16e-102">Lync Server 2013 中的 tblprincipalmembers 表格</span><span class="sxs-lookup"><span data-stu-id="ba16e-102">tblPrincipalMembers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba16e-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="ba16e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ba16e-104">tblprincipalmembers 表格包含主體成員資格。</span><span class="sxs-lookup"><span data-stu-id="ba16e-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="ba16e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="ba16e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba16e-106">欄</span><span class="sxs-lookup"><span data-stu-id="ba16e-106">Column</span></span></th>
<th><span data-ttu-id="ba16e-107">類型	</span><span class="sxs-lookup"><span data-stu-id="ba16e-107">Type</span></span></th>
<th><span data-ttu-id="ba16e-108">描述</span><span class="sxs-lookup"><span data-stu-id="ba16e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba16e-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ba16e-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="ba16e-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="ba16e-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ba16e-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="ba16e-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba16e-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="ba16e-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="ba16e-113">nvarchar (384)，非 null</span><span class="sxs-lookup"><span data-stu-id="ba16e-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="ba16e-114">成員的辨別的名稱。</span><span class="sxs-lookup"><span data-stu-id="ba16e-114">Distinguished name of a member.</span></span> <span data-ttu-id="ba16e-115">成員可能沒有 （以 tblPrincipal 表格） 的主體。</span><span class="sxs-lookup"><span data-stu-id="ba16e-115">A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ba16e-116">索引鍵</span><span class="sxs-lookup"><span data-stu-id="ba16e-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba16e-117">欄</span><span class="sxs-lookup"><span data-stu-id="ba16e-117">Column</span></span></th>
<th><span data-ttu-id="ba16e-118">描述</span><span class="sxs-lookup"><span data-stu-id="ba16e-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba16e-119">&lt;prinID memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="ba16e-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="ba16e-120">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="ba16e-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba16e-121">prinID</span><span class="sxs-lookup"><span data-stu-id="ba16e-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="ba16e-122">在 tblPrincipal.prinID 中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="ba16e-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

