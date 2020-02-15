---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
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
ms.openlocfilehash: 0ca8ccc9c60bdd608992dc3daf085568d34bee69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="47aac-102">Lync Server 2013 中的 tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="47aac-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47aac-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="47aac-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="47aac-104">tblPrincipalMemberDifference 包含稍後的 Active Directory 網域服務同步處理步驟尚未處理的群組成員資格變更 （新增和移除成員）。</span><span class="sxs-lookup"><span data-stu-id="47aac-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="47aac-105">Columns</span><span class="sxs-lookup"><span data-stu-id="47aac-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47aac-106">欄</span><span class="sxs-lookup"><span data-stu-id="47aac-106">Column</span></span></th>
<th><span data-ttu-id="47aac-107">類型	</span><span class="sxs-lookup"><span data-stu-id="47aac-107">Type</span></span></th>
<th><span data-ttu-id="47aac-108">描述</span><span class="sxs-lookup"><span data-stu-id="47aac-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47aac-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="47aac-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="47aac-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="47aac-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="47aac-111">已變更群組的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="47aac-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47aac-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="47aac-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="47aac-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="47aac-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="47aac-114">成員的辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="47aac-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47aac-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="47aac-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="47aac-116">bit，非 null</span><span class="sxs-lookup"><span data-stu-id="47aac-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="47aac-p101">False 表示已新增成員；True 表示已移除成員。</span><span class="sxs-lookup"><span data-stu-id="47aac-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="47aac-119">索引鍵</span><span class="sxs-lookup"><span data-stu-id="47aac-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47aac-120">欄</span><span class="sxs-lookup"><span data-stu-id="47aac-120">Column</span></span></th>
<th><span data-ttu-id="47aac-121">描述</span><span class="sxs-lookup"><span data-stu-id="47aac-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47aac-122">&lt;prinGuid memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="47aac-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="47aac-123">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="47aac-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

