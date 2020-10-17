---
title: Lync Server 2013： tblPrincipalMembers
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
ms.openlocfilehash: 4098b3ea8c9a5dda2cdee7d05f71b940ffcb0325
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523630"
---
# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="de2ca-102">Lync Server 2013 中的 tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="de2ca-102">tblPrincipalMembers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de2ca-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="de2ca-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="de2ca-104">tblPrincipalMembers 包含主體成員資格。</span><span class="sxs-lookup"><span data-stu-id="de2ca-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="de2ca-105">Columns</span><span class="sxs-lookup"><span data-stu-id="de2ca-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de2ca-106">欄</span><span class="sxs-lookup"><span data-stu-id="de2ca-106">Column</span></span></th>
<th><span data-ttu-id="de2ca-107">類型</span><span class="sxs-lookup"><span data-stu-id="de2ca-107">Type</span></span></th>
<th><span data-ttu-id="de2ca-108">描述</span><span class="sxs-lookup"><span data-stu-id="de2ca-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de2ca-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="de2ca-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="de2ca-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="de2ca-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="de2ca-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="de2ca-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de2ca-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="de2ca-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="de2ca-113">Nvarchar (384) ，非 null</span><span class="sxs-lookup"><span data-stu-id="de2ca-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="de2ca-114">成員的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="de2ca-114">Distinguished name of a member.</span></span> <span data-ttu-id="de2ca-115">成員不一定要是 tblPrincipal table) 中的主體 (。</span><span class="sxs-lookup"><span data-stu-id="de2ca-115">A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="de2ca-116">索引鍵</span><span class="sxs-lookup"><span data-stu-id="de2ca-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de2ca-117">欄</span><span class="sxs-lookup"><span data-stu-id="de2ca-117">Column</span></span></th>
<th><span data-ttu-id="de2ca-118">描述</span><span class="sxs-lookup"><span data-stu-id="de2ca-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de2ca-119">&lt;Tblprincipal.prinid、memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="de2ca-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="de2ca-120">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="de2ca-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de2ca-121">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="de2ca-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="de2ca-122">在 tblPrincipal.prinID 中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="de2ca-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

