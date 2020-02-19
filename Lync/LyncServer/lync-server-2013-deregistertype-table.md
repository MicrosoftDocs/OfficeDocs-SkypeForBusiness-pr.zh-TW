---
title: 'Lync Server 2013: DeRegisterType 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f1bee5dfa5a0f24b46ba51abafee8d0a89b0a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="2ebe9-102">Lync Server 2013 中的 DeRegisterType 表格</span><span class="sxs-lookup"><span data-stu-id="2ebe9-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ebe9-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="2ebe9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2ebe9-104">DeRegisterType 表格是靜態表格，可儲存使用者取消註冊可能類型的清單 (如「由用戶端起始」、「註冊到期」或「用戶端停止回應」)。</span><span class="sxs-lookup"><span data-stu-id="2ebe9-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ebe9-105">欄</span><span class="sxs-lookup"><span data-stu-id="2ebe9-105">Column</span></span></th>
<th><span data-ttu-id="2ebe9-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="2ebe9-106">Data Type</span></span></th>
<th><span data-ttu-id="2ebe9-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="2ebe9-107">Key/Index</span></span></th>
<th><span data-ttu-id="2ebe9-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2ebe9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ebe9-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="2ebe9-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ebe9-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="2ebe9-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2ebe9-111">主要</span><span class="sxs-lookup"><span data-stu-id="2ebe9-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ebe9-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="2ebe9-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="2ebe9-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ebe9-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ebe9-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="2ebe9-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ebe9-115">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="2ebe9-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="2ebe9-116">1 -- 由用戶端起始取消註冊</span><span class="sxs-lookup"><span data-stu-id="2ebe9-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="2ebe9-117">2 -- 註冊到期</span><span class="sxs-lookup"><span data-stu-id="2ebe9-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="2ebe9-118">3 – 用戶端損毀</span><span class="sxs-lookup"><span data-stu-id="2ebe9-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="2ebe9-119">4 -- 使用者屬性變更</span><span class="sxs-lookup"><span data-stu-id="2ebe9-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="2ebe9-120">5 – 慣用的登錄器變更</span><span class="sxs-lookup"><span data-stu-id="2ebe9-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="2ebe9-121">6 -- 舊版用戶端處於生存模式</span><span class="sxs-lookup"><span data-stu-id="2ebe9-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

