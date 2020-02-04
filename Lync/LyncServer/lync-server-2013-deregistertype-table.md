---
title: Lync Server 2013：DeRegisterType 表格
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
ms.openlocfilehash: 65c94513a3578f8608da555cdd0b3e2273b8a7da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="511e5-102">Lync Server 2013 中的 DeRegisterType 表格</span><span class="sxs-lookup"><span data-stu-id="511e5-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="511e5-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="511e5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="511e5-104">DeRegisterType 資料表是一個靜態資料表，它儲存可能的使用者取消註冊類型（例如「用戶端已啟動」、「註冊已過期」或「用戶端已停止回應」）清單。</span><span class="sxs-lookup"><span data-stu-id="511e5-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="511e5-105">左欄</span><span class="sxs-lookup"><span data-stu-id="511e5-105">Column</span></span></th>
<th><span data-ttu-id="511e5-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="511e5-106">Data Type</span></span></th>
<th><span data-ttu-id="511e5-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="511e5-107">Key/Index</span></span></th>
<th><span data-ttu-id="511e5-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="511e5-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="511e5-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="511e5-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="511e5-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="511e5-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="511e5-111">首選</span><span class="sxs-lookup"><span data-stu-id="511e5-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="511e5-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="511e5-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="511e5-113">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="511e5-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="511e5-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="511e5-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="511e5-115">0--未知</span><span class="sxs-lookup"><span data-stu-id="511e5-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="511e5-116">1--用戶端啟動取消註冊</span><span class="sxs-lookup"><span data-stu-id="511e5-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="511e5-117">2--註冊已過期</span><span class="sxs-lookup"><span data-stu-id="511e5-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="511e5-118">3-用戶端發生故障</span><span class="sxs-lookup"><span data-stu-id="511e5-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="511e5-119">4--使用者屬性已變更</span><span class="sxs-lookup"><span data-stu-id="511e5-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="511e5-120">5-首選註冊機構已變更</span><span class="sxs-lookup"><span data-stu-id="511e5-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="511e5-121">6--生存模式中的舊版用戶端</span><span class="sxs-lookup"><span data-stu-id="511e5-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

