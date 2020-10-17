---
title: Lync Server 2013：群組呼叫收取的概覽
description: Lync Server 2013：群組呼叫收取的簡介。
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
ms.openlocfilehash: c968ac466c7242253cb5a9594e1942d86031494d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562879"
---
# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="c0f4f-103">Lync Server 2013 中的群組呼叫收取概覽</span><span class="sxs-lookup"><span data-stu-id="c0f4f-103">Overview of Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0f4f-104">_**主題上次修改日期：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="c0f4f-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="c0f4f-105">群組呼叫收取（Lync Server 2013 的累計更新中的新功能：2月2013）可讓使用者從自己的電話接聽來電給其同事。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-105">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="c0f4f-106">這項新功能可讓其他使用者撥打呼叫收取群組號碼來接聽來電，以提高使用者線路的可用性。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-106">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="c0f4f-107">當部署群組呼叫收取時，路由傳送至語音信箱的來電數目會大幅減少，這對於來自組織外部客戶的呼叫特別有用。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="c0f4f-108">群組呼叫收取功能專用於開啟的 office 環境中的商務單位。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="c0f4f-109">傳入的呼叫不會造成中斷，因為它們只會在預定目的地振鈴。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="c0f4f-110">不過，其他聽到該鈴聲的使用者，只要撥號組號碼，仍然可以選擇通話。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="c0f4f-111">在使用者不在開放 office 版面配置中的環境中，或在地理位置分散共同責任的使用者時，小組通話會提供最適合的解決方案。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="c0f4f-112">「群組呼叫挑選」和「小組通話」兩者之間的主要差異在於，使用「群組通話」時，來電只會接聽預定目的地，但任何人仍可選擇撥打群組號碼加以回復。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="c0f4f-113">使用「小組通話」時，所有小組成員的電話都會撥打來電，而且小組中的任何使用者都可以接聽電話接聽來電。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="c0f4f-114">群組呼叫收取和小組通話之間的另一個差異是，群組呼叫收取是由系統管理員管理，透過 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="c0f4f-115">使用「小組通話」，使用者可以使用 Lync 用戶端管理功能。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-115">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="c0f4f-116">因此，使用「群組呼叫收取」時，可以集中進行通話管理的此方面。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="c0f4f-117">群組呼叫收取是以通話駐留應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="c0f4f-118">當您部署群組呼叫收取時，您可以設定通話駐留軌道表，其中包含指定為呼叫收取群組號碼的不同分機號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="c0f4f-119">與通話駐留軌道號碼類似，來電收取群組號碼必須是未獲指派使用者或電話的虛擬分機。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="c0f4f-120">您部署群組呼叫收取的每個前端集區，都可以有一或多個呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="c0f4f-121">群組號碼範圍必須在 Lync Server 部署間具有全域唯一性。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-121">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0f4f-122">指定為「通話駐留軌道」表格中的群組呼叫收取號碼的號碼範圍，無法使用 Lync Server 控制台進行管理或查看。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="c0f4f-123">在通話駐留軌道表格中查看所有號碼範圍的唯一方法，就是使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-123">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="c0f4f-124">同樣地，新增、修改或移除群組呼叫收取號碼的唯一方法，就是使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="c0f4f-125">設定呼叫收取群組號碼後，您可以將使用者指派給呼叫收取群組。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="c0f4f-126">指派給呼叫收取群組的任何使用者，都可以讓其他使用者接聽來電。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="c0f4f-127">當來電進入指派給來電收取群組的使用者時，任何其他通告來電的使用者都可以手動撥打通話收取群組號碼來接聽。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="c0f4f-128">挑選通話的使用者不需要是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="c0f4f-129">當其他使用者接聽來電時，會將通知傳送至最初呼叫的號碼。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0f4f-130">使用者只能是一個呼叫收取群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-130">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c0f4f-131">[！注意事項] 雖然 Lync Server 部署中的任何使用者都可以接聽呼叫收取群組成員，接聽電話的人員必須知道正確的呼叫收取群組號碼才能進行撥號。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-131">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="c0f4f-132">如果使用者撥打呼叫收取群組號碼來接聽來電時，當群組中的多個電話振鈴時，使用者會接聽來電最長的來電。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="c0f4f-133">同時震鈴設定可用於具有群組呼叫收取的使用者。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="c0f4f-134">也就是說，對具有「群組呼叫收取」之使用者所進行的呼叫將會撥打所有已設定的目的地，另一個使用者可以接聽通話。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="c0f4f-135">此規則的例外情況是使用者設定同時震鈴呼叫所有小組成員時。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="c0f4f-136">群組呼叫收取無法用來接聽下列通話類型：</span><span class="sxs-lookup"><span data-stu-id="c0f4f-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="c0f4f-137">撥打私人線路</span><span class="sxs-lookup"><span data-stu-id="c0f4f-137">Calls to a private line</span></span>

  - <span data-ttu-id="c0f4f-138">來自已獲指派朋友和家人隱私權關聯之連絡人的呼叫</span><span class="sxs-lookup"><span data-stu-id="c0f4f-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c0f4f-139">屬於呼叫收取群組成員的使用者，可將連絡人標示為 Lync 用戶端中的個人連絡人，以防止透過群組通話取回特定通話。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="c0f4f-140">若要將連絡人標示為個人連絡人，請將連絡人的隱私權關聯設定為「朋友和家人」。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="c0f4f-141">所有來自具有隱私權關聯設定為「朋友和家人」的來電，都無法透過「群組呼叫收取」來檢索。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="c0f4f-142">音訊/視頻通話的影片部分</span><span class="sxs-lookup"><span data-stu-id="c0f4f-142">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0f4f-143">如果使用者接聽音訊/視頻通話，使用者只會收到音訊。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="c0f4f-144">呼叫者或接聽電話的人員可以提升通話，以加入影片。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="c0f4f-145">路由傳送給小組通話成員的同時震鈴通話</span><span class="sxs-lookup"><span data-stu-id="c0f4f-145">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="c0f4f-146">路由傳送至代理人的來電</span><span class="sxs-lookup"><span data-stu-id="c0f4f-146">Calls routed to a delegate</span></span>

  - <span data-ttu-id="c0f4f-147">路由傳送至回應群組的來電</span><span class="sxs-lookup"><span data-stu-id="c0f4f-147">Calls routed to a response group</span></span>

<span data-ttu-id="c0f4f-148">下列類型的使用者無法參與「群組呼叫收取」。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="c0f4f-149">也就是說，不應將它們包含在群組呼叫收取群組中，也不能為已啟用群組呼叫收取的使用者挑選來電。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="c0f4f-150">在混合式部署中進行線上的使用者</span><span class="sxs-lookup"><span data-stu-id="c0f4f-150">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="c0f4f-151">不是在 Lync Server 2013 集區上的使用者，其具有 Lync Server 2013 的累計更新：內部部署部署中的2月2013</span><span class="sxs-lookup"><span data-stu-id="c0f4f-151">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="c0f4f-152">如果沒有人接聽呼叫收取群組的成員來電，該呼叫會依照用戶端設定中所指定的方式路由傳送。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="c0f4f-153">也就是說，來電會移至語音信箱或轉接至其他目的地，如用戶端設定中所指定。</span><span class="sxs-lookup"><span data-stu-id="c0f4f-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

