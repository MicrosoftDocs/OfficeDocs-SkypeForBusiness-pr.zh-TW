---
title: Lync Server 2013： tblComplianceFanout
description: Lync Server 2013： tblComplianceFanout。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cb94fff579c504598f027c8c68c7dde00a5a516
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568569"
---
# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="d9b89-103">Lync Server 2013 中的 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="d9b89-103">tblComplianceFanout in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9b89-104">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d9b89-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d9b89-105">tblComplianceFanout 包含處理符合性事件的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="d9b89-105">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="d9b89-106">Columns</span><span class="sxs-lookup"><span data-stu-id="d9b89-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9b89-107">欄</span><span class="sxs-lookup"><span data-stu-id="d9b89-107">Column</span></span></th>
<th><span data-ttu-id="d9b89-108">類型</span><span class="sxs-lookup"><span data-stu-id="d9b89-108">Type</span></span></th>
<th><span data-ttu-id="d9b89-109">描述</span><span class="sxs-lookup"><span data-stu-id="d9b89-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9b89-110">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d9b89-110">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="d9b89-111">int</span><span class="sxs-lookup"><span data-stu-id="d9b89-111">int</span></span></p></td>
<td><p><span data-ttu-id="d9b89-112">事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="d9b89-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9b89-113">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="d9b89-113">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="d9b89-114">int</span><span class="sxs-lookup"><span data-stu-id="d9b89-114">int</span></span></p></td>
<td><p><span data-ttu-id="d9b89-115">與 tblServerIdentity.serverID table) 相對應的伺服器身分識別 (。</span><span class="sxs-lookup"><span data-stu-id="d9b89-115">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="d9b89-116">索引鍵</span><span class="sxs-lookup"><span data-stu-id="d9b89-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9b89-117">欄</span><span class="sxs-lookup"><span data-stu-id="d9b89-117">Column</span></span></th>
<th><span data-ttu-id="d9b89-118">描述</span><span class="sxs-lookup"><span data-stu-id="d9b89-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9b89-119">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d9b89-119">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="d9b89-120">在 tblComplianceData.cmplEventID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="d9b89-120">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

