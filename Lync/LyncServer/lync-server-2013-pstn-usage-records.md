---
title: Lync Server 2013： PSTN 使用方式記錄
description: Lync Server 2013： PSTN 使用方式記錄。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8ff428dc2fa5cf8cf0f10e37f0f79c38d70d70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565579"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="ce8cb-103">Lync Server 2013 中的 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="ce8cb-103">PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce8cb-104">_**主題上次修改日期：** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="ce8cb-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="ce8cb-105">規劃 PSTN 使用方式記錄，主要是列出組織中目前強制執行的所有呼叫許可權，從 CEO 到暫存工作者、顧問和員工。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-105">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff.</span></span> <span data-ttu-id="ce8cb-106">此程式也可讓您重新檢查現有的呼叫許可權並加以修正。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-106">This process also provides an opportunity to reexamine existing call permissions and revise them.</span></span> <span data-ttu-id="ce8cb-107">您只能為適用于您預期的 Enterprise Voice 使用者的呼叫許可權建立 PSTN 使用方式記錄，但較好的長方案可能是針對所有呼叫許可權建立 PSTN 使用方式記錄，而不論某些可能目前未套用到啟用 Enterprise Voice 的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-107">You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice.</span></span> <span data-ttu-id="ce8cb-108">如果新增了具有不同呼叫許可權的撥號許可權變更或新使用者，您就已建立必要的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-108">If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="ce8cb-109">下表顯示一般的 PSTN 使用方式表格。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-109">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="ce8cb-110">PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="ce8cb-110">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce8cb-111">Phone 屬性</span><span class="sxs-lookup"><span data-stu-id="ce8cb-111">Phone attribute</span></span></th>
<th><span data-ttu-id="ce8cb-112">描述</span><span class="sxs-lookup"><span data-stu-id="ce8cb-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce8cb-113">本機</span><span class="sxs-lookup"><span data-stu-id="ce8cb-113">Local</span></span></p></td>
<td><p><span data-ttu-id="ce8cb-114">本機通話</span><span class="sxs-lookup"><span data-stu-id="ce8cb-114">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce8cb-115">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="ce8cb-115">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="ce8cb-116">長途通話</span><span class="sxs-lookup"><span data-stu-id="ce8cb-116">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce8cb-117">International</span><span class="sxs-lookup"><span data-stu-id="ce8cb-117">International</span></span></p></td>
<td><p><span data-ttu-id="ce8cb-118">國際通話</span><span class="sxs-lookup"><span data-stu-id="ce8cb-118">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce8cb-119">德里</span><span class="sxs-lookup"><span data-stu-id="ce8cb-119">Delhi</span></span></p></td>
<td><p><span data-ttu-id="ce8cb-120">新德里全職員工</span><span class="sxs-lookup"><span data-stu-id="ce8cb-120">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce8cb-121">雷德蒙</span><span class="sxs-lookup"><span data-stu-id="ce8cb-121">Redmond</span></span></p></td>
<td><p><span data-ttu-id="ce8cb-122">雷德蒙的全職員工</span><span class="sxs-lookup"><span data-stu-id="ce8cb-122">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce8cb-123">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="ce8cb-123">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="ce8cb-124">Redmond 臨時員工</span><span class="sxs-lookup"><span data-stu-id="ce8cb-124">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce8cb-125">蘇黎世</span><span class="sxs-lookup"><span data-stu-id="ce8cb-125">Zurich</span></span></p></td>
<td><p><span data-ttu-id="ce8cb-126">蘇黎世全職員工</span><span class="sxs-lookup"><span data-stu-id="ce8cb-126">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ce8cb-127">PSTN 使用方式記錄本身不會執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-127">By themselves, PSTN usage records do not do anything.</span></span> <span data-ttu-id="ce8cb-128">為了讓他們能夠運作，您必須將它們與下列專案產生關聯：</span><span class="sxs-lookup"><span data-stu-id="ce8cb-128">For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="ce8cb-129">指派給使用者的語音原則。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-129">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="ce8cb-130">指派給電話號碼的路由。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-130">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="ce8cb-131">如需語音原則和路由的詳細資訊，請參閱 lync server [2013 中的語音原則](lync-server-2013-voice-policies.md) 和 [lync server 2013 中的語音路由](lync-server-2013-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-131">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="ce8cb-132">如需如何建立及設定的詳細資訊，請參閱 [在 Lync Server 2013 中設定撥出電話的語音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。</span><span class="sxs-lookup"><span data-stu-id="ce8cb-132">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

