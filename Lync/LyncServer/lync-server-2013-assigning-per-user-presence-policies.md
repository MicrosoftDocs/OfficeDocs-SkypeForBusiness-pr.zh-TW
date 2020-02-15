---
title: Lync Server 2013： 指派每位使用者的顯示狀態原則
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
ms.openlocfilehash: 618ab1b18f92d19f65084d321b71219cc0fafb06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="4e58e-102">指派每位使用者在 Lync Server 2013 中的目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="4e58e-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e58e-103">_**主題上次修改日期：** 2012年-10-11_</span><span class="sxs-lookup"><span data-stu-id="4e58e-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="4e58e-104">目前狀態原則是一組的限制與限制會影響目前狀態。</span><span class="sxs-lookup"><span data-stu-id="4e58e-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="4e58e-105">下表說明適用於 Lync Server 2013 的目前狀態原則設定。</span><span class="sxs-lookup"><span data-stu-id="4e58e-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="4e58e-106">目前狀態原則設定</span><span class="sxs-lookup"><span data-stu-id="4e58e-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="4e58e-107">XML 名稱</span><span class="sxs-lookup"><span data-stu-id="4e58e-107">XML name</span></span></th>
<th><span data-ttu-id="4e58e-108">辨別名稱 (DN)</span><span class="sxs-lookup"><span data-stu-id="4e58e-108">Display name</span></span></th>
<th><span data-ttu-id="4e58e-109">描述</span><span class="sxs-lookup"><span data-stu-id="4e58e-109">Description</span></span></th>
<th><span data-ttu-id="4e58e-110">Type</span><span class="sxs-lookup"><span data-stu-id="4e58e-110">Type</span></span></th>
<th><span data-ttu-id="4e58e-111">值</span><span class="sxs-lookup"><span data-stu-id="4e58e-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e58e-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="4e58e-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="4e58e-113">訂閱者類別目錄訂閱數目上限</span><span class="sxs-lookup"><span data-stu-id="4e58e-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="4e58e-114">限制訂閱者類別目錄訂閱的數目。</span><span class="sxs-lookup"><span data-stu-id="4e58e-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="4e58e-115">例如，當 Communicator 訂閱使用者的目前狀態，它會取得類別訂用帳戶為每個連絡人卡片、 行事曆資料、 備忘稿、 服務和狀態類別。</span><span class="sxs-lookup"><span data-stu-id="4e58e-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="4e58e-116">如果設定為 0 表示使用者或連絡人物件無法由其他使用者訂閱。</span><span class="sxs-lookup"><span data-stu-id="4e58e-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="4e58e-117">此設定可以對效能造成重大影響，如果它設定為較高的數字，而且一般使用者會有大量使用者訂閱他/她的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="4e58e-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="4e58e-118">整數</span><span class="sxs-lookup"><span data-stu-id="4e58e-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="4e58e-119">0 – 3000</span><span class="sxs-lookup"><span data-stu-id="4e58e-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e58e-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="4e58e-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="4e58e-121">已排入佇列的目前狀態訂閱警示數目上限</span><span class="sxs-lookup"><span data-stu-id="4e58e-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="4e58e-122">限制提示 「 訂閱者 」 表格中的項目數。</span><span class="sxs-lookup"><span data-stu-id="4e58e-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="4e58e-123">此設定會決定可以排入佇列的指定使用者的提示的最大數目。</span><span class="sxs-lookup"><span data-stu-id="4e58e-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="4e58e-124">例如，當使用者的訂閱使用者 B 的目前狀態，使用者 B 會收到提示的現在訂閱給使用者 B，該使用者而認可提示字元中建立使用者 B 的提示 「 訂閱者 」 表格。</span><span class="sxs-lookup"><span data-stu-id="4e58e-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="4e58e-125">使用者 B 接受，或認可，訂閱之後, 的確認提示會移除使用者 B 的提示 「 訂閱者 」 表格。</span><span class="sxs-lookup"><span data-stu-id="4e58e-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="4e58e-126">當某人訂閱使用者的目前狀態時，系統提示您設定為 0 表示使用者不是。</span><span class="sxs-lookup"><span data-stu-id="4e58e-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="4e58e-127">整數或 Token</span><span class="sxs-lookup"><span data-stu-id="4e58e-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="4e58e-128">0-500</span><span class="sxs-lookup"><span data-stu-id="4e58e-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4e58e-129">根據預設，**預設原則**和**服務： 中型**當您部署 Lync Server 時，會安裝目前狀態原則。</span><span class="sxs-lookup"><span data-stu-id="4e58e-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="4e58e-130">下表說明兩個的目前狀態原則的特定設定。</span><span class="sxs-lookup"><span data-stu-id="4e58e-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="4e58e-131">目前狀態原則</span><span class="sxs-lookup"><span data-stu-id="4e58e-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e58e-132">原則名稱</span><span class="sxs-lookup"><span data-stu-id="4e58e-132">Policy name</span></span></th>
<th><span data-ttu-id="4e58e-133">描述</span><span class="sxs-lookup"><span data-stu-id="4e58e-133">Description</span></span></th>
<th><span data-ttu-id="4e58e-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="4e58e-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="4e58e-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="4e58e-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e58e-136">預設原則</span><span class="sxs-lookup"><span data-stu-id="4e58e-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="4e58e-137">一般使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="4e58e-137">Policy for typical users.</span></span> <span data-ttu-id="4e58e-138">這是預設的目前狀態原則。</span><span class="sxs-lookup"><span data-stu-id="4e58e-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="4e58e-139">1000</span><span class="sxs-lookup"><span data-stu-id="4e58e-139">1000</span></span></p></td>
<td><p><span data-ttu-id="4e58e-140">200</span><span class="sxs-lookup"><span data-stu-id="4e58e-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e58e-141">服務： 中等</span><span class="sxs-lookup"><span data-stu-id="4e58e-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="4e58e-142">需要更多使用者訂閱物件的目前狀態的應用程式的原則。</span><span class="sxs-lookup"><span data-stu-id="4e58e-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="4e58e-143">1000</span><span class="sxs-lookup"><span data-stu-id="4e58e-143">1000</span></span></p></td>
<td><p><span data-ttu-id="4e58e-144">0</span><span class="sxs-lookup"><span data-stu-id="4e58e-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

