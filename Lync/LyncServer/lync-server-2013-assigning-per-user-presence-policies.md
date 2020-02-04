---
title: Lync Server 2013：指派每個使用者的目前狀態原則
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
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="f466b-102">在 Lync Server 2013 中指派每個使用者的目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="f466b-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f466b-103">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="f466b-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="f466b-104">目前狀態原則是一組會影響目前狀態的限制與限制。</span><span class="sxs-lookup"><span data-stu-id="f466b-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="f466b-105">下表說明 Lync Server 2013 中的目前狀態原則設定。</span><span class="sxs-lookup"><span data-stu-id="f466b-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="f466b-106">目前狀態原則設定</span><span class="sxs-lookup"><span data-stu-id="f466b-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="f466b-107">XML 名稱</span><span class="sxs-lookup"><span data-stu-id="f466b-107">XML name</span></span></th>
<th><span data-ttu-id="f466b-108">顯示名稱</span><span class="sxs-lookup"><span data-stu-id="f466b-108">Display name</span></span></th>
<th><span data-ttu-id="f466b-109">說明</span><span class="sxs-lookup"><span data-stu-id="f466b-109">Description</span></span></th>
<th><span data-ttu-id="f466b-110">類型</span><span class="sxs-lookup"><span data-stu-id="f466b-110">Type</span></span></th>
<th><span data-ttu-id="f466b-111">值</span><span class="sxs-lookup"><span data-stu-id="f466b-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f466b-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="f466b-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="f466b-113">最大訂閱者類別訂閱數</span><span class="sxs-lookup"><span data-stu-id="f466b-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="f466b-114">限制訂閱者類別訂閱的數目。</span><span class="sxs-lookup"><span data-stu-id="f466b-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="f466b-115">例如，當 Communicator 訂閱使用者的目前狀態時，它會針對每一個連絡人卡片、行事歷數據、記事、服務和狀態類別，取得類別訂閱。</span><span class="sxs-lookup"><span data-stu-id="f466b-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="f466b-116">設定為0表示使用者或連絡人物件不能由其他人訂閱。</span><span class="sxs-lookup"><span data-stu-id="f466b-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f466b-117">此設定會對效能產生很大的影響（如果它設定為高數位），而一般使用者有大量的使用者訂閱自己的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="f466b-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="f466b-118">整</span><span class="sxs-lookup"><span data-stu-id="f466b-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="f466b-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="f466b-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f466b-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="f466b-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="f466b-121">已排隊的目前狀態訂閱通知數量上限</span><span class="sxs-lookup"><span data-stu-id="f466b-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="f466b-122">限制提示訂閱者資料表中的專案數。</span><span class="sxs-lookup"><span data-stu-id="f466b-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="f466b-123">這個設定決定了指定使用者可以列隊的最大提示數。</span><span class="sxs-lookup"><span data-stu-id="f466b-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="f466b-124">例如，當使用者 A 訂閱使用者 B 的目前狀態時，使用者 B 會收到提示：使用者 A 現在已訂閱使用者 B，而使用者 B 的提示訂閱者資料表中則會建立確認提示。</span><span class="sxs-lookup"><span data-stu-id="f466b-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="f466b-125">當使用者 B 接受或確認訂閱之後，就會從使用者 B 的提示訂閱者資料表中移除確認提示。</span><span class="sxs-lookup"><span data-stu-id="f466b-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="f466b-126">設定為0表示某人訂閱自己的目前狀態時，系統不會提示使用者。</span><span class="sxs-lookup"><span data-stu-id="f466b-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="f466b-127">整型或標記</span><span class="sxs-lookup"><span data-stu-id="f466b-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="f466b-128">0-500</span><span class="sxs-lookup"><span data-stu-id="f466b-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f466b-129">根據預設**原則**和服務，當您部署 Lync Server 時，就會安裝 [**中**目前狀態] 原則。</span><span class="sxs-lookup"><span data-stu-id="f466b-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="f466b-130">下表說明這兩種目前狀態原則的特定設定。</span><span class="sxs-lookup"><span data-stu-id="f466b-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="f466b-131">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="f466b-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f466b-132">原則名稱</span><span class="sxs-lookup"><span data-stu-id="f466b-132">Policy name</span></span></th>
<th><span data-ttu-id="f466b-133">說明</span><span class="sxs-lookup"><span data-stu-id="f466b-133">Description</span></span></th>
<th><span data-ttu-id="f466b-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="f466b-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="f466b-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="f466b-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f466b-136">預設原則</span><span class="sxs-lookup"><span data-stu-id="f466b-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="f466b-137">一般使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="f466b-137">Policy for typical users.</span></span> <span data-ttu-id="f466b-138">這是預設的目前狀態原則。</span><span class="sxs-lookup"><span data-stu-id="f466b-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="f466b-139">1000</span><span class="sxs-lookup"><span data-stu-id="f466b-139">1000</span></span></p></td>
<td><p><span data-ttu-id="f466b-140">200</span><span class="sxs-lookup"><span data-stu-id="f466b-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f466b-141">服務：中型</span><span class="sxs-lookup"><span data-stu-id="f466b-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="f466b-142">需要更多使用者才能訂閱物件目前狀態的應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="f466b-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="f466b-143">1000</span><span class="sxs-lookup"><span data-stu-id="f466b-143">1000</span></span></p></td>
<td><p><span data-ttu-id="f466b-144">0</span><span class="sxs-lookup"><span data-stu-id="f466b-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

