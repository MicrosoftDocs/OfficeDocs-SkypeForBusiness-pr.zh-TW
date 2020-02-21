---
title: 'Lync Server 2013: tblcompliancefanout 表格'
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
ms.openlocfilehash: 6bb9ab36bbbec83ea706231d2a3fa6dd890fb1e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="5a2b9-102">Lync Server 2013 中的 tblcompliancefanout 表格</span><span class="sxs-lookup"><span data-stu-id="5a2b9-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a2b9-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="5a2b9-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5a2b9-104">tblcompliancefanout 表格包含處理規範事件的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="5a2b9-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="5a2b9-105">Columns</span><span class="sxs-lookup"><span data-stu-id="5a2b9-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a2b9-106">欄</span><span class="sxs-lookup"><span data-stu-id="5a2b9-106">Column</span></span></th>
<th><span data-ttu-id="5a2b9-107">類型	</span><span class="sxs-lookup"><span data-stu-id="5a2b9-107">Type</span></span></th>
<th><span data-ttu-id="5a2b9-108">描述</span><span class="sxs-lookup"><span data-stu-id="5a2b9-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a2b9-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="5a2b9-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="5a2b9-110">int</span><span class="sxs-lookup"><span data-stu-id="5a2b9-110">int</span></span></p></td>
<td><p><span data-ttu-id="5a2b9-111">事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="5a2b9-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a2b9-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="5a2b9-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="5a2b9-113">int</span><span class="sxs-lookup"><span data-stu-id="5a2b9-113">int</span></span></p></td>
<td><p><span data-ttu-id="5a2b9-114">伺服器識別 （對應 tblServerIdentity.serverID 表）。</span><span class="sxs-lookup"><span data-stu-id="5a2b9-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5a2b9-115">索引鍵</span><span class="sxs-lookup"><span data-stu-id="5a2b9-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a2b9-116">欄</span><span class="sxs-lookup"><span data-stu-id="5a2b9-116">Column</span></span></th>
<th><span data-ttu-id="5a2b9-117">描述</span><span class="sxs-lookup"><span data-stu-id="5a2b9-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a2b9-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="5a2b9-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="5a2b9-119">在 tblComplianceData.cmplEventID 表中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="5a2b9-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

