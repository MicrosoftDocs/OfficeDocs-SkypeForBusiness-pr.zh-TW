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
ms.openlocfilehash: 516eb1b9c9487e9213ad28601de656a5959fc0e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="48456-102">Lync Server 2013 中的 tblprincipalmembers 表格</span><span class="sxs-lookup"><span data-stu-id="48456-102">tblPrincipalMembers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48456-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="48456-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="48456-104">tblprincipalmembers 表格包含主體成員資格。</span><span class="sxs-lookup"><span data-stu-id="48456-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="48456-105">Columns</span><span class="sxs-lookup"><span data-stu-id="48456-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48456-106">欄</span><span class="sxs-lookup"><span data-stu-id="48456-106">Column</span></span></th>
<th><span data-ttu-id="48456-107">類型	</span><span class="sxs-lookup"><span data-stu-id="48456-107">Type</span></span></th>
<th><span data-ttu-id="48456-108">描述</span><span class="sxs-lookup"><span data-stu-id="48456-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48456-109">prinID</span><span class="sxs-lookup"><span data-stu-id="48456-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="48456-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="48456-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="48456-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="48456-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48456-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="48456-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="48456-113">nvarchar (384)，非 null</span><span class="sxs-lookup"><span data-stu-id="48456-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="48456-114">成員的辨別的名稱。</span><span class="sxs-lookup"><span data-stu-id="48456-114">Distinguished name of a member.</span></span> <span data-ttu-id="48456-115">成員可能沒有 （以 tblPrincipal 表格） 的主體。</span><span class="sxs-lookup"><span data-stu-id="48456-115">A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="48456-116">索引鍵</span><span class="sxs-lookup"><span data-stu-id="48456-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48456-117">欄</span><span class="sxs-lookup"><span data-stu-id="48456-117">Column</span></span></th>
<th><span data-ttu-id="48456-118">描述</span><span class="sxs-lookup"><span data-stu-id="48456-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48456-119">&lt;prinID memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="48456-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="48456-120">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="48456-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48456-121">prinID</span><span class="sxs-lookup"><span data-stu-id="48456-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="48456-122">在 tblPrincipal.prinID 中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="48456-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

