---
title: Lync Server 2013： [群組呼叫挑選] 簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="b36ce-102">Lync Server 2013 中的群組通話挑選概覽</span><span class="sxs-lookup"><span data-stu-id="b36ce-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b36ce-103">_**主題上次修改日期：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="b36ce-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="b36ce-104">[群組通話]： Lync Server 2013 的累積更新中的新功能：2013年2月，讓使用者從自己的手機向其同事接聽來電。</span><span class="sxs-lookup"><span data-stu-id="b36ce-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="b36ce-105">這項新功能可讓其他使用者透過撥打電話挑選群組號碼來接聽來電，以提高使用者線路的可用性。</span><span class="sxs-lookup"><span data-stu-id="b36ce-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="b36ce-106">當您部署群組通話時，傳送到語音信箱的撥入通話數量可能會大幅減少，這對於來自貴組織外部的客戶的呼叫尤為有用。</span><span class="sxs-lookup"><span data-stu-id="b36ce-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="b36ce-107">[群組呼叫挑選] 功能專門針對開啟的 office 環境中的商務單位而設計。</span><span class="sxs-lookup"><span data-stu-id="b36ce-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="b36ce-108">來電不會中斷，因為它們只會在預定的目的地響鈴。</span><span class="sxs-lookup"><span data-stu-id="b36ce-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="b36ce-109">但其他聽見鈴聲的使用者，只要撥打群組號碼，就能繼續接聽通話。</span><span class="sxs-lookup"><span data-stu-id="b36ce-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="b36ce-110">在使用者不位於已開啟的 office 版面配置中，或在地理位置分散共同職責的使用者，小組通話會提供最適合的方案。</span><span class="sxs-lookup"><span data-stu-id="b36ce-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="b36ce-111">[群組呼叫挑選] 與 [團隊通話] 之間的主要差異在於，群組呼叫挑選只會在預定的目的地進行來電，但是任何人都可以撥打群組號碼來回答問題。</span><span class="sxs-lookup"><span data-stu-id="b36ce-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="b36ce-112">使用「小組通話」，小組中的所有人都能接聽電話，而團隊中的任何使用者都可以接聽電話來接聽通話。</span><span class="sxs-lookup"><span data-stu-id="b36ce-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="b36ce-113">[群組通話挑選] 與 [團隊通話] 之間的其他差異是，群組呼叫挑選是由管理員（透過 Lync Server）管理。</span><span class="sxs-lookup"><span data-stu-id="b36ce-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="b36ce-114">透過團隊通話，使用者可以使用 Lync 用戶端來管理功能。</span><span class="sxs-lookup"><span data-stu-id="b36ce-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="b36ce-115">使用 [群組呼叫]，即可集中進行通話管理的這個方面。</span><span class="sxs-lookup"><span data-stu-id="b36ce-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="b36ce-116">[群組呼叫挑選] 是以 [通話駐留] 應用程式建立。</span><span class="sxs-lookup"><span data-stu-id="b36ce-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="b36ce-117">當您部署群組呼叫挑選時，您可以設定 [通話公園軌道] 表格，並將指定為 [呼叫挑選] 群組編號的不同範圍延伸。</span><span class="sxs-lookup"><span data-stu-id="b36ce-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="b36ce-118">例如通話公園軌道編號，呼叫挑選群組號碼必須是沒有指派給他們的使用者或電話的虛擬延伸。</span><span class="sxs-lookup"><span data-stu-id="b36ce-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="b36ce-119">您在其中部署 [群組呼叫挑選] 的每個前端池都可以有一或多個呼叫挑選群組編號範圍。</span><span class="sxs-lookup"><span data-stu-id="b36ce-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="b36ce-120">群組編號範圍在 Lync Server 部署中必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="b36ce-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b36ce-121">在 [通話駐留軌道] 表格中指定為群組通話編號的數位範圍，無法使用 Lync Server [控制台] 進行管理或查看。</span><span class="sxs-lookup"><span data-stu-id="b36ce-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="b36ce-122">若要查看 [通話公園軌道] 表格中所有的數位範圍，唯一的方法是使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b36ce-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="b36ce-123">同樣地，新增、修改或移除群組通話號碼的唯一方式就是使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b36ce-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="b36ce-124">在您設定 [呼叫挑選] 群組號碼之後，您可以將使用者指派給 [通話挑選] 群組。</span><span class="sxs-lookup"><span data-stu-id="b36ce-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="b36ce-125">任何指派給 [呼叫挑選] 群組的使用者，都可以由其他使用者接聽來電。</span><span class="sxs-lookup"><span data-stu-id="b36ce-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="b36ce-126">當來電進入指派給來電挑選群組的使用者時，任何其他通知呼叫的使用者，都可以手動撥打呼叫挑選群組號碼來回答該問題。</span><span class="sxs-lookup"><span data-stu-id="b36ce-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="b36ce-127">挑選通話的使用者不需要是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b36ce-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="b36ce-128">當其他使用者接聽來電時，系統會將通知傳送到最初呼叫的號碼。</span><span class="sxs-lookup"><span data-stu-id="b36ce-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b36ce-129">使用者只能是一個 [呼叫挑選] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b36ce-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b36ce-130">雖然 Lync Server 部署中的任何使用者都可以接聽通話分揀群組成員的通話，但接聽通話的人員必須知道正確的呼叫挑選群組號碼才能進行撥號。</span><span class="sxs-lookup"><span data-stu-id="b36ce-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="b36ce-131">當群組中有多個電話響鈴時，如果使用者撥打電話給您的電話挑選群組號碼接聽電話，使用者就會接聽已響鈴最長的通話。</span><span class="sxs-lookup"><span data-stu-id="b36ce-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="b36ce-132">[同時撥打] 設定可供進行群組通話的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="b36ce-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="b36ce-133">也就是說，對有 [群組呼叫挑選] 的使用者撥打電話時，會撥打所有已設定的目的地，而另一個使用者可以接聽通話。</span><span class="sxs-lookup"><span data-stu-id="b36ce-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="b36ce-134">此規則的例外狀況是當使用者設定同時撥打給呼叫所有團隊成員的時間。</span><span class="sxs-lookup"><span data-stu-id="b36ce-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="b36ce-135">[群組呼叫挑選] 無法用來回答下列類型的通話：</span><span class="sxs-lookup"><span data-stu-id="b36ce-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="b36ce-136">呼叫私人線路</span><span class="sxs-lookup"><span data-stu-id="b36ce-136">Calls to a private line</span></span>

  - <span data-ttu-id="b36ce-137">從已被指派朋友和家人隱私權關聯的連絡人撥打電話</span><span class="sxs-lookup"><span data-stu-id="b36ce-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="b36ce-138">作為呼叫挑選群組成員的使用者，您可以將連絡人標示為 Lync 用戶端中的個人連絡人，以避免透過群組呼叫進行檢索。</span><span class="sxs-lookup"><span data-stu-id="b36ce-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="b36ce-139">若要將連絡人標示為個人連絡人，請將該連絡人的隱私權關係設定為 [朋友] 和 [家人]。</span><span class="sxs-lookup"><span data-stu-id="b36ce-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="b36ce-140">您無法使用 [群組通話挑選]，透過將 [隱私權關係] 設定為 [朋友] 和 [家人] 的連絡人進行任何來電。</span><span class="sxs-lookup"><span data-stu-id="b36ce-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="b36ce-141">音訊/視頻通話的影片部分</span><span class="sxs-lookup"><span data-stu-id="b36ce-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b36ce-142">如果使用者接聽音訊/視頻通話，使用者只會收到音訊。</span><span class="sxs-lookup"><span data-stu-id="b36ce-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="b36ce-143">打電話給對方或接聽電話的人，都可以將通話升級，以新增影片。</span><span class="sxs-lookup"><span data-stu-id="b36ce-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="b36ce-144">傳送給小組通話成員的同時撥打的通話</span><span class="sxs-lookup"><span data-stu-id="b36ce-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="b36ce-145">傳送給代理人的通話</span><span class="sxs-lookup"><span data-stu-id="b36ce-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="b36ce-146">傳送給回應群組的通話</span><span class="sxs-lookup"><span data-stu-id="b36ce-146">Calls routed to a response group</span></span>

<span data-ttu-id="b36ce-147">下列使用者類型無法參與群組通話分揀。</span><span class="sxs-lookup"><span data-stu-id="b36ce-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="b36ce-148">也就是說，它們不應該包含在群組通話分揀群組中，而且他們無法為已啟用群組通話分揀的使用者挑選來電。</span><span class="sxs-lookup"><span data-stu-id="b36ce-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="b36ce-149">在混合式部署中駐留在線上的使用者</span><span class="sxs-lookup"><span data-stu-id="b36ce-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="b36ce-150">不是託管在 lync server 2013 pool 中的使用者，具有 Lync Server 2013 的累加更新：內部部署部署中的2月2013</span><span class="sxs-lookup"><span data-stu-id="b36ce-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="b36ce-151">如果沒有人接聽 [呼叫挑選] 群組的成員來電，該通話就會以用戶端設定中指定的方式進行路由。</span><span class="sxs-lookup"><span data-stu-id="b36ce-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="b36ce-152">也就是說，通話會傳送至語音信箱，或轉寄到不同的目的地，就像在用戶端設定中所指定的一樣。</span><span class="sxs-lookup"><span data-stu-id="b36ce-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

