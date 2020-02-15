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
ms.openlocfilehash: c535dc860c5d1a8725d27217e8269c3d6c4902d2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="68ff5-102">Lync Server 2013 中的 tblcompliancefanout 表格</span><span class="sxs-lookup"><span data-stu-id="68ff5-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68ff5-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="68ff5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="68ff5-104">tblcompliancefanout 表格包含處理規範事件的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="68ff5-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="68ff5-105">Columns</span><span class="sxs-lookup"><span data-stu-id="68ff5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68ff5-106">欄</span><span class="sxs-lookup"><span data-stu-id="68ff5-106">Column</span></span></th>
<th><span data-ttu-id="68ff5-107">類型	</span><span class="sxs-lookup"><span data-stu-id="68ff5-107">Type</span></span></th>
<th><span data-ttu-id="68ff5-108">描述</span><span class="sxs-lookup"><span data-stu-id="68ff5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68ff5-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="68ff5-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="68ff5-110">int</span><span class="sxs-lookup"><span data-stu-id="68ff5-110">int</span></span></p></td>
<td><p><span data-ttu-id="68ff5-111">事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="68ff5-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68ff5-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="68ff5-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="68ff5-113">int</span><span class="sxs-lookup"><span data-stu-id="68ff5-113">int</span></span></p></td>
<td><p><span data-ttu-id="68ff5-114">伺服器識別 （對應 tblServerIdentity.serverID 表）。</span><span class="sxs-lookup"><span data-stu-id="68ff5-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="68ff5-115">索引鍵</span><span class="sxs-lookup"><span data-stu-id="68ff5-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68ff5-116">欄</span><span class="sxs-lookup"><span data-stu-id="68ff5-116">Column</span></span></th>
<th><span data-ttu-id="68ff5-117">描述</span><span class="sxs-lookup"><span data-stu-id="68ff5-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68ff5-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="68ff5-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="68ff5-119">在 tblComplianceData.cmplEventID 表中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="68ff5-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

