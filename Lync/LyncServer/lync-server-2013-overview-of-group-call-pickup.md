---
title: 'Lync Server 2013: Overview of 群組來電接聽'
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
ms.openlocfilehash: 222d587f7c4972a8aee313d3d66da578cde08960
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="043e7-102">群組來電接聽 Lync Server 2013 中的概觀</span><span class="sxs-lookup"><span data-stu-id="043e7-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="043e7-103">_**上次修改主題：** 2013年-02-12_</span><span class="sxs-lookup"><span data-stu-id="043e7-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="043e7-104">群組呼叫收取，Cumulative Updates for Lync Server 2013 中的新功能： 2 月 2013年可讓使用者接聽來電從他們自己的電話其同事。</span><span class="sxs-lookup"><span data-stu-id="043e7-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="043e7-105">這項新功能會增加使用者的一行的可用性讓其他使用者可以撥出通話收取群組號碼接聽來電。</span><span class="sxs-lookup"><span data-stu-id="043e7-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="043e7-106">部署群組來電接聽時，會路由傳送至語音信箱的來電數目可以大幅降低，也就是特別適合用來從組織外部的客戶的通話。</span><span class="sxs-lookup"><span data-stu-id="043e7-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="043e7-107">群組來電接聽功能特別設計來開啟 office 環境中的業務單位。</span><span class="sxs-lookup"><span data-stu-id="043e7-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="043e7-108">傳入呼叫並不中斷，因為他們撥打只會在預定目的地。</span><span class="sxs-lookup"><span data-stu-id="043e7-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="043e7-109">聽到鈴聲，其他使用者不過，可以仍收取通話只要撥號群組編號。</span><span class="sxs-lookup"><span data-stu-id="043e7-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="043e7-110">在環境中，使用者不是所位於中開啟 office 版面配置或地理位置分散共用共同責任的使用者，小組通話會呈現最適合的解決方案。</span><span class="sxs-lookup"><span data-stu-id="043e7-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="043e7-111">群組來電接聽與小組通話的主要差異是，與群組來電接聽來電鈴響只會在預定的目的地，但任何人仍然可以選擇接聽撥出群組號碼。</span><span class="sxs-lookup"><span data-stu-id="043e7-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="043e7-112">與小組通話通話響起所有小組成員的電話，但小組中的任何使用者可以接聽電話時接電話。</span><span class="sxs-lookup"><span data-stu-id="043e7-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="043e7-113">群組來電接聽與小組通話其他差異是群組來電接聽由系統管理員，透過 Lync Server 管理。</span><span class="sxs-lookup"><span data-stu-id="043e7-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="043e7-114">與小組通話，使用者會使用 Lync 用戶端管理該功能。</span><span class="sxs-lookup"><span data-stu-id="043e7-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="043e7-115">使用群組來電接聽，因此，這方面的通話管理可以是集中式。</span><span class="sxs-lookup"><span data-stu-id="043e7-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="043e7-116">群組來電接聽做為基礎的通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="043e7-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="043e7-117">當您部署群組來電接聽時，您可以設定通話駐留軌道表各種不同的範圍內的指定為呼叫收取群組號碼的分機號碼。</span><span class="sxs-lookup"><span data-stu-id="043e7-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="043e7-118">例如通話駐留軌道數字、 呼叫收取群組號碼必須不有任何使用者或電話指派給他們的虛擬分機。</span><span class="sxs-lookup"><span data-stu-id="043e7-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="043e7-119">您將部署群組來電接聽每個前端集區可以有一或多個範圍的通話收取群組數字。</span><span class="sxs-lookup"><span data-stu-id="043e7-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="043e7-120">在 Lync Server 部署，群組號碼範圍必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="043e7-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="043e7-121">會指定為 [群組來電接聽通話駐留軌道表中的數字無法管理或檢視使用 Lync Server Control Panel 的號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="043e7-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="043e7-122">若要查看在通話駐留軌道表中的所有號碼範圍的唯一方法是使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="043e7-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="043e7-123">同樣地，若要新增，唯有修改或移除群組來電接聽數字是使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="043e7-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="043e7-124">設定通話收取群組號碼之後，您會將使用者指派給通話收取群組中。</span><span class="sxs-lookup"><span data-stu-id="043e7-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="043e7-125">指派給呼叫收取群組的任何使用者可以有其其他使用者所接聽的通話。</span><span class="sxs-lookup"><span data-stu-id="043e7-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="043e7-126">當接獲指派給呼叫收取群組的使用者時，通知來電者的其他使用者可以接聽它來手動撥打的通話收取群組編號。</span><span class="sxs-lookup"><span data-stu-id="043e7-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="043e7-127">挑選通話之使用者不必是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="043e7-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="043e7-128">當呼叫收取的另一位使用者時，就會傳送通知，原本呼叫的數字。</span><span class="sxs-lookup"><span data-stu-id="043e7-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="043e7-129">使用者可以是只有一個呼叫收取群組的成員。</span><span class="sxs-lookup"><span data-stu-id="043e7-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="043e7-130">雖然 Lync Server 部署中的任何使用者可以接聽通話收取群組成員的呼叫，接聽電話的人必須知道正確的呼叫收取群組號碼。</span><span class="sxs-lookup"><span data-stu-id="043e7-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="043e7-131">如果使用者撥打通話收取群組數字，以接聽來電，當群組中的多個電話響鈴時，使用者會接聽來電，具有最長響鈴。</span><span class="sxs-lookup"><span data-stu-id="043e7-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="043e7-132">同時響鈴設定適用於擁有群組呼叫收取] 目錄的使用者。</span><span class="sxs-lookup"><span data-stu-id="043e7-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="043e7-133">也就是撥至具有群組來電接聽的使用者將會撥打的所有設定的目的地，與另一位使用者可以接聽來電。</span><span class="sxs-lookup"><span data-stu-id="043e7-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="043e7-134">此規則的例外是當使用者設定同時響鈴呼叫所有小組成員。</span><span class="sxs-lookup"><span data-stu-id="043e7-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="043e7-135">群組來電接聽無法用來接聽來電下列幾種：</span><span class="sxs-lookup"><span data-stu-id="043e7-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="043e7-136">私人線路的電話</span><span class="sxs-lookup"><span data-stu-id="043e7-136">Calls to a private line</span></span>

  - <span data-ttu-id="043e7-137">呼叫從連絡人朋友和家人獲指派私人關係</span><span class="sxs-lookup"><span data-stu-id="043e7-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="043e7-138">呼叫收取群組成員的使用者可能會使某些藉由將連絡人標示為已在 Lync 用戶端的個人連絡人正在擷取透過群組來電接聽的來電。</span><span class="sxs-lookup"><span data-stu-id="043e7-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="043e7-139">若要將標示為個人連絡人的連絡人，將連絡人的私人關係設朋友和家人。</span><span class="sxs-lookup"><span data-stu-id="043e7-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="043e7-140">從 [連絡人] 私人關係與任何傳入呼叫設朋友並無法使用群組來電接聽擷取系列。</span><span class="sxs-lookup"><span data-stu-id="043e7-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="043e7-141">視訊部分的音訊/視訊通話</span><span class="sxs-lookup"><span data-stu-id="043e7-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="043e7-142">如果使用者接聽，音訊/視訊通話，使用者會收到僅音訊。</span><span class="sxs-lookup"><span data-stu-id="043e7-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="043e7-143">呼叫的人員或接聽電話的人員可以擴大以加入視訊通話。</span><span class="sxs-lookup"><span data-stu-id="043e7-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="043e7-144">同時響鈴的通話，路由傳送到小組呼叫成員</span><span class="sxs-lookup"><span data-stu-id="043e7-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="043e7-145">通話路由傳送至代理人</span><span class="sxs-lookup"><span data-stu-id="043e7-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="043e7-146">通話路由傳送至回應群組</span><span class="sxs-lookup"><span data-stu-id="043e7-146">Calls routed to a response group</span></span>

<span data-ttu-id="043e7-147">下列類型的使用者無法參與群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="043e7-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="043e7-148">也就是說，不應該包含群組來電接聽群組中，和他們無法揀選使用者已啟用的群組來電接聽通話。</span><span class="sxs-lookup"><span data-stu-id="043e7-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="043e7-149">位於 online 混合式部署中的使用者</span><span class="sxs-lookup"><span data-stu-id="043e7-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="043e7-150">不位於 Cumulative Updates for Lync Server 2013 與 Lync Server 2013 集區的使用者： 在內部部署中的年 2 月 2013年</span><span class="sxs-lookup"><span data-stu-id="043e7-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="043e7-151">如果沒有人的用戶端設定中指定為路由傳送通話收取群組成員，呼叫藉由呼叫的答案。</span><span class="sxs-lookup"><span data-stu-id="043e7-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="043e7-152">也就是在呼叫移至語音信箱或郵件會轉送到不同的目的，用戶端設定中所指定。</span><span class="sxs-lookup"><span data-stu-id="043e7-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

