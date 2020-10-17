---
title: Lync Server 2013：指派每個使用者的目前狀態原則
description: Lync Server 2013：指派每個使用者的目前狀態原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c3d4b4bda0c4bb85065d546fdbb4b2578db0e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563369"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="6dd50-103">在 Lync Server 2013 中指派每一使用者的目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="6dd50-103">Assigning per-user presence policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dd50-104">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="6dd50-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="6dd50-105">目前狀態原則是一組影響顯示狀態的限制和限制。</span><span class="sxs-lookup"><span data-stu-id="6dd50-105">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="6dd50-106">下表說明 Lync Server 2013 中可用的目前狀態原則設定。</span><span class="sxs-lookup"><span data-stu-id="6dd50-106">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="6dd50-107">顯示狀態原則設定</span><span class="sxs-lookup"><span data-stu-id="6dd50-107">Presence Policy Settings</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dd50-108">XML 名稱</span><span class="sxs-lookup"><span data-stu-id="6dd50-108">XML name</span></span></th>
<th><span data-ttu-id="6dd50-109">顯示名稱</span><span class="sxs-lookup"><span data-stu-id="6dd50-109">Display name</span></span></th>
<th><span data-ttu-id="6dd50-110">描述</span><span class="sxs-lookup"><span data-stu-id="6dd50-110">Description</span></span></th>
<th><span data-ttu-id="6dd50-111">Type</span><span class="sxs-lookup"><span data-stu-id="6dd50-111">Type</span></span></th>
<th><span data-ttu-id="6dd50-112">值</span><span class="sxs-lookup"><span data-stu-id="6dd50-112">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dd50-113">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="6dd50-113">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="6dd50-114">訂閱者類別訂閱數目上限</span><span class="sxs-lookup"><span data-stu-id="6dd50-114">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="6dd50-115">限制使用者類別訂閱數目。</span><span class="sxs-lookup"><span data-stu-id="6dd50-115">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="6dd50-116">例如，當 Communicator 訂閱使用者的目前狀態時，它會取得每個連絡人卡片、行事歷數據、記事、服務和狀態類別的類別訂閱。</span><span class="sxs-lookup"><span data-stu-id="6dd50-116">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="6dd50-117">設定為0表示使用者或連絡人物件無法由其他人訂閱。</span><span class="sxs-lookup"><span data-stu-id="6dd50-117">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6dd50-118">此設定在效能設定為高值時，對效能的影響很大，而且平均使用者有大量使用者訂閱其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="6dd50-118">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="6dd50-119">整數</span><span class="sxs-lookup"><span data-stu-id="6dd50-119">Integer</span></span></p></td>
<td><p><span data-ttu-id="6dd50-120">0-3000</span><span class="sxs-lookup"><span data-stu-id="6dd50-120">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dd50-121">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="6dd50-121">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="6dd50-122">佇列顯示訂閱警示的數目上限</span><span class="sxs-lookup"><span data-stu-id="6dd50-122">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="6dd50-123">限制提示的訂戶表格中的專案數。</span><span class="sxs-lookup"><span data-stu-id="6dd50-123">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="6dd50-124">此設定會決定指定使用者可以列隊的提示數目上限。</span><span class="sxs-lookup"><span data-stu-id="6dd50-124">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="6dd50-125">例如，當使用者 A 訂閱使用者 B 的狀態時，使用者 B 會收到提示，指出使用者 A 現在已訂閱使用者 B，而且會在使用者 B 的提示訂閱者表格中建立認可提示。</span><span class="sxs-lookup"><span data-stu-id="6dd50-125">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="6dd50-126">在使用者 B 接受（或承認）訂閱後，會從使用者 B 的提示訂閱者表格中移除確認提示。</span><span class="sxs-lookup"><span data-stu-id="6dd50-126">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="6dd50-127">設定為0時，表示當有人訂閱他或她的目前狀態時，不會提示使用者。</span><span class="sxs-lookup"><span data-stu-id="6dd50-127">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="6dd50-128">整數或標記</span><span class="sxs-lookup"><span data-stu-id="6dd50-128">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="6dd50-129">0-500</span><span class="sxs-lookup"><span data-stu-id="6dd50-129">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6dd50-130">根據預設，當您部署 Lync Server 時，會安裝 **預設原則** 及 **服務：「中** 狀態」原則。</span><span class="sxs-lookup"><span data-stu-id="6dd50-130">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="6dd50-131">下表說明兩種目前狀態原則的特定設定。</span><span class="sxs-lookup"><span data-stu-id="6dd50-131">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="6dd50-132">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="6dd50-132">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dd50-133">原則名稱</span><span class="sxs-lookup"><span data-stu-id="6dd50-133">Policy name</span></span></th>
<th><span data-ttu-id="6dd50-134">描述</span><span class="sxs-lookup"><span data-stu-id="6dd50-134">Description</span></span></th>
<th><span data-ttu-id="6dd50-135">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="6dd50-135">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="6dd50-136">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="6dd50-136">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dd50-137">預設原則</span><span class="sxs-lookup"><span data-stu-id="6dd50-137">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="6dd50-138">一般使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6dd50-138">Policy for typical users.</span></span> <span data-ttu-id="6dd50-139">這是預設的目前狀態原則。</span><span class="sxs-lookup"><span data-stu-id="6dd50-139">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="6dd50-140">1000</span><span class="sxs-lookup"><span data-stu-id="6dd50-140">1000</span></span></p></td>
<td><p><span data-ttu-id="6dd50-141">200</span><span class="sxs-lookup"><span data-stu-id="6dd50-141">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dd50-142">服務：中速</span><span class="sxs-lookup"><span data-stu-id="6dd50-142">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="6dd50-143">需要更多使用者訂閱物件目前狀態的應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="6dd50-143">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="6dd50-144">1000</span><span class="sxs-lookup"><span data-stu-id="6dd50-144">1000</span></span></p></td>
<td><p><span data-ttu-id="6dd50-145">0</span><span class="sxs-lookup"><span data-stu-id="6dd50-145">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

