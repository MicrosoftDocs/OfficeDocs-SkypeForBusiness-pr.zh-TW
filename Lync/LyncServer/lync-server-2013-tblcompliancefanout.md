---
title: Lync Server 2013：tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6edae4c6e37f5abb6714e7c6863c80b7a6e7756b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="f670f-102">Lync Server 2013 中的 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="f670f-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f670f-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f670f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f670f-104">tblComplianceFanout 包含已處理合規性事件的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="f670f-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="f670f-105">分欄</span><span class="sxs-lookup"><span data-stu-id="f670f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f670f-106">左欄</span><span class="sxs-lookup"><span data-stu-id="f670f-106">Column</span></span></th>
<th><span data-ttu-id="f670f-107">類型</span><span class="sxs-lookup"><span data-stu-id="f670f-107">Type</span></span></th>
<th><span data-ttu-id="f670f-108">描述</span><span class="sxs-lookup"><span data-stu-id="f670f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f670f-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="f670f-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="f670f-110">int</span><span class="sxs-lookup"><span data-stu-id="f670f-110">int</span></span></p></td>
<td><p><span data-ttu-id="f670f-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="f670f-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f670f-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="f670f-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="f670f-113">int</span><span class="sxs-lookup"><span data-stu-id="f670f-113">int</span></span></p></td>
<td><p><span data-ttu-id="f670f-114">伺服器身分識別（對應至 tblServerIdentity serverID 表）。</span><span class="sxs-lookup"><span data-stu-id="f670f-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f670f-115">機碼</span><span class="sxs-lookup"><span data-stu-id="f670f-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f670f-116">左欄</span><span class="sxs-lookup"><span data-stu-id="f670f-116">Column</span></span></th>
<th><span data-ttu-id="f670f-117">描述</span><span class="sxs-lookup"><span data-stu-id="f670f-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f670f-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="f670f-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="f670f-119">在 tblComplianceData cmplEventID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="f670f-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

