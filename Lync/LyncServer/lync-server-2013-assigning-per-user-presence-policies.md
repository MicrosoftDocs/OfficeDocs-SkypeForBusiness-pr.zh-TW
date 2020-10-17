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
ms.openlocfilehash: 7c4f561189b72cf19fad28879711e3a1da0da8fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527120"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="02591-102">在 Lync Server 2013 中指派每一使用者的目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="02591-102">Assigning per-user presence policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02591-103">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="02591-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="02591-104">目前狀態原則是一組影響顯示狀態的限制和限制。</span><span class="sxs-lookup"><span data-stu-id="02591-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="02591-105">下表說明 Lync Server 2013 中可用的目前狀態原則設定。</span><span class="sxs-lookup"><span data-stu-id="02591-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="02591-106">顯示狀態原則設定</span><span class="sxs-lookup"><span data-stu-id="02591-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="02591-107">XML 名稱</span><span class="sxs-lookup"><span data-stu-id="02591-107">XML name</span></span></th>
<th><span data-ttu-id="02591-108">顯示名稱</span><span class="sxs-lookup"><span data-stu-id="02591-108">Display name</span></span></th>
<th><span data-ttu-id="02591-109">描述</span><span class="sxs-lookup"><span data-stu-id="02591-109">Description</span></span></th>
<th><span data-ttu-id="02591-110">Type</span><span class="sxs-lookup"><span data-stu-id="02591-110">Type</span></span></th>
<th><span data-ttu-id="02591-111">值</span><span class="sxs-lookup"><span data-stu-id="02591-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02591-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="02591-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="02591-113">訂閱者類別訂閱數目上限</span><span class="sxs-lookup"><span data-stu-id="02591-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="02591-114">限制使用者類別訂閱數目。</span><span class="sxs-lookup"><span data-stu-id="02591-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="02591-115">例如，當 Communicator 訂閱使用者的目前狀態時，它會取得每個連絡人卡片、行事歷數據、記事、服務和狀態類別的類別訂閱。</span><span class="sxs-lookup"><span data-stu-id="02591-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="02591-116">設定為0表示使用者或連絡人物件無法由其他人訂閱。</span><span class="sxs-lookup"><span data-stu-id="02591-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="02591-117">此設定在效能設定為高值時，對效能的影響很大，而且平均使用者有大量使用者訂閱其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="02591-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="02591-118">整數</span><span class="sxs-lookup"><span data-stu-id="02591-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="02591-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="02591-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02591-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="02591-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="02591-121">佇列顯示訂閱警示的數目上限</span><span class="sxs-lookup"><span data-stu-id="02591-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="02591-122">限制提示的訂戶表格中的專案數。</span><span class="sxs-lookup"><span data-stu-id="02591-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="02591-123">此設定會決定指定使用者可以列隊的提示數目上限。</span><span class="sxs-lookup"><span data-stu-id="02591-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="02591-124">例如，當使用者 A 訂閱使用者 B 的狀態時，使用者 B 會收到提示，指出使用者 A 現在已訂閱使用者 B，而且會在使用者 B 的提示訂閱者表格中建立認可提示。</span><span class="sxs-lookup"><span data-stu-id="02591-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="02591-125">在使用者 B 接受（或承認）訂閱後，會從使用者 B 的提示訂閱者表格中移除確認提示。</span><span class="sxs-lookup"><span data-stu-id="02591-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="02591-126">設定為0時，表示當有人訂閱他或她的目前狀態時，不會提示使用者。</span><span class="sxs-lookup"><span data-stu-id="02591-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="02591-127">整數或標記</span><span class="sxs-lookup"><span data-stu-id="02591-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="02591-128">0-500</span><span class="sxs-lookup"><span data-stu-id="02591-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02591-129">根據預設，當您部署 Lync Server 時，會安裝 **預設原則** 及 **服務：「中** 狀態」原則。</span><span class="sxs-lookup"><span data-stu-id="02591-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="02591-130">下表說明兩種目前狀態原則的特定設定。</span><span class="sxs-lookup"><span data-stu-id="02591-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="02591-131">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="02591-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02591-132">原則名稱</span><span class="sxs-lookup"><span data-stu-id="02591-132">Policy name</span></span></th>
<th><span data-ttu-id="02591-133">描述</span><span class="sxs-lookup"><span data-stu-id="02591-133">Description</span></span></th>
<th><span data-ttu-id="02591-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="02591-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="02591-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="02591-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02591-136">預設原則</span><span class="sxs-lookup"><span data-stu-id="02591-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="02591-137">一般使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="02591-137">Policy for typical users.</span></span> <span data-ttu-id="02591-138">這是預設的目前狀態原則。</span><span class="sxs-lookup"><span data-stu-id="02591-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="02591-139">1000</span><span class="sxs-lookup"><span data-stu-id="02591-139">1000</span></span></p></td>
<td><p><span data-ttu-id="02591-140">200</span><span class="sxs-lookup"><span data-stu-id="02591-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02591-141">服務：中速</span><span class="sxs-lookup"><span data-stu-id="02591-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="02591-142">需要更多使用者訂閱物件目前狀態的應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="02591-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="02591-143">1000</span><span class="sxs-lookup"><span data-stu-id="02591-143">1000</span></span></p></td>
<td><p><span data-ttu-id="02591-144">0</span><span class="sxs-lookup"><span data-stu-id="02591-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

