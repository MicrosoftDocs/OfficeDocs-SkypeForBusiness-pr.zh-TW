---
title: 在商務用 Skype 中規劃群組呼叫收取
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: 在商務用 Skype Server Enterprise Voice 中規劃群組呼叫收取，讓使用者可以接聽原本供其他人接聽的來電。
ms.openlocfilehash: 874b9385352a8c51d9c9a356dd0ccc2ca3070601
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825613"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a><span data-ttu-id="34a95-103">在商務用 Skype 中規劃群組呼叫收取</span><span class="sxs-lookup"><span data-stu-id="34a95-103">Plan for Group Call Pickup in Skype for Business</span></span>
 
<span data-ttu-id="34a95-104">在商務用 Skype Server Enterprise Voice 中規劃群組呼叫收取，讓使用者可以接聽原本供其他人接聽的來電。</span><span class="sxs-lookup"><span data-stu-id="34a95-104">Planning for Group Call Pickup in Skype for Business Server Enterprise Voice, which enables users to answer calls originally intended for others.</span></span>
  
<span data-ttu-id="34a95-105">群組叫用收取可讓使用者從自己的電話接聽來電給其同事。</span><span class="sxs-lookup"><span data-stu-id="34a95-105">Group Call Pickup enables users to answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="34a95-106">這樣可讓其他使用者撥打呼叫收取群組號碼來接聽來電，以提高使用者線路的可用性。</span><span class="sxs-lookup"><span data-stu-id="34a95-106">This increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="34a95-107">當部署群組呼叫收取時，路由傳送至語音信箱的來電數目會大幅減少，這對於來自組織外部客戶的呼叫特別有用。</span><span class="sxs-lookup"><span data-stu-id="34a95-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>
  
<span data-ttu-id="34a95-108">群組呼叫收取功能專用於開啟的 office 環境中的商務單位。</span><span class="sxs-lookup"><span data-stu-id="34a95-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="34a95-109">傳入的呼叫不會造成中斷，因為它們只會在預定目的地振鈴。</span><span class="sxs-lookup"><span data-stu-id="34a95-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="34a95-110">不過，其他聽到該鈴聲的使用者，只要撥號組號碼，仍然可以選擇通話。</span><span class="sxs-lookup"><span data-stu-id="34a95-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span> 
  
<span data-ttu-id="34a95-111">在使用者不在開放 office 版面配置中的環境中，或在地理位置分散共同責任的使用者時，小組通話會提供最適合的解決方案。</span><span class="sxs-lookup"><span data-stu-id="34a95-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="34a95-112">「群組呼叫挑選」和「小組通話」兩者之間的主要差異在於，使用「群組通話」時，來電只會接聽預定目的地，但任何人仍可選擇撥打群組號碼加以回復。</span><span class="sxs-lookup"><span data-stu-id="34a95-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="34a95-113">使用「小組通話」時，所有小組成員的電話都會撥打來電，而且小組中的任何使用者都可以接聽電話接聽來電。</span><span class="sxs-lookup"><span data-stu-id="34a95-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="34a95-114">「群組呼叫收取」和「小組通話」間的另一個差異是，群組呼叫收取是由系統管理員管理，透過商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="34a95-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Skype for Business Server.</span></span> <span data-ttu-id="34a95-115">使用「小組通話」，使用者可以使用商務用 Skype 用戶端管理該功能。</span><span class="sxs-lookup"><span data-stu-id="34a95-115">With team call, end users manage the feature by using the Skype for Business client.</span></span> <span data-ttu-id="34a95-116">因此，使用「群組呼叫收取」時，可以集中進行通話管理的此方面。</span><span class="sxs-lookup"><span data-stu-id="34a95-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>
  
<span data-ttu-id="34a95-117">群組呼叫收取是以通話駐留應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="34a95-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="34a95-118">當您部署群組呼叫收取時，您可以設定通話駐留軌道表，其中包含指定為呼叫收取群組號碼的不同分機號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="34a95-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="34a95-119">與通話駐留軌道號碼類似，來電收取群組號碼必須是未獲指派使用者或電話的虛擬分機。</span><span class="sxs-lookup"><span data-stu-id="34a95-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="34a95-120">您部署群組呼叫收取的每個前端集區，都可以有一或多個呼叫收取群組號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="34a95-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="34a95-121">群組號碼範圍必須在整個商務用 Skype 伺服器部署中具有全域唯一性。</span><span class="sxs-lookup"><span data-stu-id="34a95-121">The group number ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="34a95-122">指定為「通話駐留軌道」表格中的群組呼叫收取號碼的號碼範圍，無法使用商務用 Skype Server 控制台進行管理或查看。</span><span class="sxs-lookup"><span data-stu-id="34a95-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="34a95-123">查看通話駐留軌道表格中所有號碼範圍的唯一方法，就是使用商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="34a95-123">The only way to see all the number ranges in the call park orbit table is to use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="34a95-124">同樣地，新增、修改或移除群組呼叫收取號碼的唯一方法，就是使用商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="34a95-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="34a95-125">設定呼叫收取群組號碼後，您可以將使用者指派給呼叫收取群組。</span><span class="sxs-lookup"><span data-stu-id="34a95-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="34a95-126">指派給呼叫收取群組的任何使用者，都可以讓其他使用者接聽來電。</span><span class="sxs-lookup"><span data-stu-id="34a95-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="34a95-127">當來電進入指派給來電收取群組的使用者時，任何其他通告來電的使用者都可以手動撥打通話收取群組號碼來接聽。</span><span class="sxs-lookup"><span data-stu-id="34a95-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="34a95-128">挑選通話的使用者不需要是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="34a95-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="34a95-129">當其他使用者接聽來電時，會將通知傳送至最初呼叫的號碼。</span><span class="sxs-lookup"><span data-stu-id="34a95-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34a95-130">使用者只能是一個呼叫收取群組的成員。</span><span class="sxs-lookup"><span data-stu-id="34a95-130">A user can be a member of only one call pickup group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="34a95-131">雖然商務用 Skype 伺服器部署中的任何使用者都可以接聽呼叫收取群組成員，接聽電話的人員必須知道正確的呼叫收取群組號碼才能撥打。</span><span class="sxs-lookup"><span data-stu-id="34a95-131">Although any user in the Skype for Business Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span> 
  
<span data-ttu-id="34a95-132">如果使用者撥打呼叫收取群組號碼來接聽來電時，當群組中的多個電話振鈴時，使用者會接聽來電最長的來電。</span><span class="sxs-lookup"><span data-stu-id="34a95-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>
  
<span data-ttu-id="34a95-133">同時震鈴設定可用於具有群組呼叫收取的使用者。</span><span class="sxs-lookup"><span data-stu-id="34a95-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="34a95-134">也就是說，對具有「群組呼叫收取」之使用者所進行的呼叫將會撥打所有已設定的目的地，另一個使用者可以接聽通話。</span><span class="sxs-lookup"><span data-stu-id="34a95-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="34a95-135">此規則的例外情況是使用者設定同時震鈴呼叫所有小組成員時。</span><span class="sxs-lookup"><span data-stu-id="34a95-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>
  
<span data-ttu-id="34a95-136">群組呼叫收取無法用來接聽下列通話類型：</span><span class="sxs-lookup"><span data-stu-id="34a95-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>
  
- <span data-ttu-id="34a95-137">撥打私人線路</span><span class="sxs-lookup"><span data-stu-id="34a95-137">Calls to a private line</span></span>
    
- <span data-ttu-id="34a95-138">來自已獲指派朋友和家人隱私權關聯之連絡人的呼叫</span><span class="sxs-lookup"><span data-stu-id="34a95-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    > [!TIP]
    > <span data-ttu-id="34a95-139">屬於呼叫收取群組成員的使用者，可將連絡人標示為商務用 Skype 用戶端中的個人連絡人，以防止透過群組通話取回特定通話。</span><span class="sxs-lookup"><span data-stu-id="34a95-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Skype for Business client.</span></span> <span data-ttu-id="34a95-140">若要將連絡人標示為個人連絡人，請將連絡人的隱私權關聯設定為「朋友和家人」。</span><span class="sxs-lookup"><span data-stu-id="34a95-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="34a95-141">所有來自具有隱私權關聯設定為「朋友和家人」的來電，都無法透過「群組呼叫收取」來檢索。</span><span class="sxs-lookup"><span data-stu-id="34a95-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span> 
  
- <span data-ttu-id="34a95-142">音訊/視頻通話的影片部分</span><span class="sxs-lookup"><span data-stu-id="34a95-142">Video portion of audio/video calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="34a95-143">如果使用者接聽音訊/視頻通話，使用者只會收到音訊。</span><span class="sxs-lookup"><span data-stu-id="34a95-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="34a95-144">呼叫者或接聽電話的人員可以提升通話，以加入影片。</span><span class="sxs-lookup"><span data-stu-id="34a95-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span> 
  
- <span data-ttu-id="34a95-145">路由傳送給小組通話成員的同時震鈴通話</span><span class="sxs-lookup"><span data-stu-id="34a95-145">Simultaneous ringing calls that are routed to team call members</span></span>
    
- <span data-ttu-id="34a95-146">路由傳送至代理人的來電</span><span class="sxs-lookup"><span data-stu-id="34a95-146">Calls routed to a delegate</span></span>
    
- <span data-ttu-id="34a95-147">路由傳送至回應群組的來電</span><span class="sxs-lookup"><span data-stu-id="34a95-147">Calls routed to a response group</span></span>
    
<span data-ttu-id="34a95-148">下列類型的使用者無法參與「群組呼叫收取」。</span><span class="sxs-lookup"><span data-stu-id="34a95-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="34a95-149">也就是說，不應將它們包含在群組呼叫收取群組中，也不能為已啟用群組呼叫收取的使用者挑選來電。</span><span class="sxs-lookup"><span data-stu-id="34a95-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>
  
- <span data-ttu-id="34a95-150">在混合式部署中進行線上的使用者</span><span class="sxs-lookup"><span data-stu-id="34a95-150">Users who are homed online in a hybrid deployment</span></span>
    
- <span data-ttu-id="34a95-151">不是位於商務用 Skype Server 2015 集區或具有 Lync Server 2013 累計更新的 Lync Server 2013 集區的使用者，在內部部署中部署中的2月2013：</span><span class="sxs-lookup"><span data-stu-id="34a95-151">Users who are not homed on either a Skype for Business Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>
    
<span data-ttu-id="34a95-152">如果沒有人接聽呼叫收取群組的成員來電，該呼叫會依照用戶端設定中所指定的方式路由傳送。</span><span class="sxs-lookup"><span data-stu-id="34a95-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="34a95-153">也就是說，來電會移至語音信箱或轉接至其他目的地，如用戶端設定中所指定。</span><span class="sxs-lookup"><span data-stu-id="34a95-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="34a95-154">部署和需求</span><span class="sxs-lookup"><span data-stu-id="34a95-154">Deployment and requirements</span></span>

<span data-ttu-id="34a95-155">當您部署企業語音和通話駐留應用程式時，會自動部署群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="34a95-155">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="34a95-156">您可以將通話駐留軌道表設定為呼叫收取群組的號碼，然後指派使用者呼叫收取群組，並為使用者啟用群組通話收取，以啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="34a95-156">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span>
  
## <a name="clients-supported-for-group-call-pickup"></a><span data-ttu-id="34a95-157">群組呼叫收取支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="34a95-157">Clients supported for Group Call Pickup</span></span>

<span data-ttu-id="34a95-158">您可以使用下列任一用戶端接聽呼叫群組的來電成員：</span><span class="sxs-lookup"><span data-stu-id="34a95-158">Any of the following clients can be used to answer calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="34a95-159">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="34a95-159">Skype for Business</span></span>
    
- <span data-ttu-id="34a95-160">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="34a95-160">Lync 2013</span></span>
    
- <span data-ttu-id="34a95-161">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="34a95-161">Lync 2010</span></span>
    
- <span data-ttu-id="34a95-162">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="34a95-162">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="34a95-163">使用者可以使用這些用戶端的任何用戶端接聽呼叫群組的來電成員，但是使用者必須位於商務用 Skype 伺服器集區或 Lync Server 2013 集區，其具有「Lync Server 2013」的累計更新：2月2013。</span><span class="sxs-lookup"><span data-stu-id="34a95-163">Users can use any of these clients to answer calls to Group Call Pickup members, but the users must be homed on a Skype for Business Server pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="34a95-164">下列用戶端和裝置不支援拾取群組呼叫收取成員的通話：</span><span class="sxs-lookup"><span data-stu-id="34a95-164">The following clients and devices are not supported for picking up calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="34a95-165">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="34a95-165">Lync Mobile</span></span>
    
- <span data-ttu-id="34a95-166">適用于 Windows 8 和 Windows RT 的 Lync 應用程式</span><span class="sxs-lookup"><span data-stu-id="34a95-166">Lync app for Windows 8 and Windows RT</span></span>
    
- <span data-ttu-id="34a95-167">Lync for iPad</span><span class="sxs-lookup"><span data-stu-id="34a95-167">Lync for iPad</span></span>
    
- <span data-ttu-id="34a95-168">類比電話</span><span class="sxs-lookup"><span data-stu-id="34a95-168">Analog phones</span></span>
    
- <span data-ttu-id="34a95-169">具有公用交換電話網路 (PSTN) 號碼的電話</span><span class="sxs-lookup"><span data-stu-id="34a95-169">Phones with public switched telephone network (PSTN) numbers</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="34a95-170">容量規劃</span><span class="sxs-lookup"><span data-stu-id="34a95-170">Capacity planning</span></span>

<span data-ttu-id="34a95-171">下表說明您可以用來作為容量規劃需求基礎的群組呼叫收取使用者模型。</span><span class="sxs-lookup"><span data-stu-id="34a95-171">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="34a95-172">群組呼叫收取是以通話駐留應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="34a95-172">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="34a95-173">請記住，針對嚴重損壞修復容量規劃，成對集區的每個集區都應該可以處理通話駐留服務的工作負載，包括兩個集區中的群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="34a95-173">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span> 
  
<span data-ttu-id="34a95-174">**群組呼叫收取使用者模型**</span><span class="sxs-lookup"><span data-stu-id="34a95-174">**Group Call Pickup User Model**</span></span>

|<span data-ttu-id="34a95-175">**計量**</span><span class="sxs-lookup"><span data-stu-id="34a95-175">**Metric**</span></span>|<span data-ttu-id="34a95-176">**每個前端伺服器集區  <br/>  (8 部前端伺服器)**</span><span class="sxs-lookup"><span data-stu-id="34a95-176">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="34a95-177">**每個 Standard Edition server**</span><span class="sxs-lookup"><span data-stu-id="34a95-177">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="34a95-178">每個群組的使用者建議數量</span><span class="sxs-lookup"><span data-stu-id="34a95-178">Recommended number of users per group</span></span>  <br/> |<span data-ttu-id="34a95-179">50</span><span class="sxs-lookup"><span data-stu-id="34a95-179">50</span></span>  <br/> |<span data-ttu-id="34a95-180">50</span><span class="sxs-lookup"><span data-stu-id="34a95-180">50</span></span>  <br/> |
|<span data-ttu-id="34a95-181">建議的群組數目</span><span class="sxs-lookup"><span data-stu-id="34a95-181">Recommended number of groups</span></span>  <br/> |<span data-ttu-id="34a95-182">500</span><span class="sxs-lookup"><span data-stu-id="34a95-182">500</span></span>  <br/> |<span data-ttu-id="34a95-183">60</span><span class="sxs-lookup"><span data-stu-id="34a95-183">60</span></span>  <br/> |
|<span data-ttu-id="34a95-184">群組呼叫收取啟用每個集區的使用者數目上限</span><span class="sxs-lookup"><span data-stu-id="34a95-184">Maximum number of users per pool enabled for Group Call Pickup</span></span>  <br/> |<span data-ttu-id="34a95-185">25,000</span><span class="sxs-lookup"><span data-stu-id="34a95-185">25,000</span></span>  <br/> |<span data-ttu-id="34a95-186">3000</span><span class="sxs-lookup"><span data-stu-id="34a95-186">3,000</span></span>  <br/> |
|<span data-ttu-id="34a95-187">每分鐘針對每個集區啟用群組來電收取的總來電數上限</span><span class="sxs-lookup"><span data-stu-id="34a95-187">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="34a95-188">500</span><span class="sxs-lookup"><span data-stu-id="34a95-188">500</span></span>  <br/> |<span data-ttu-id="34a95-189">60</span><span class="sxs-lookup"><span data-stu-id="34a95-189">60</span></span>  <br/> |
|<span data-ttu-id="34a95-190">每分鐘由使用者每個集區呼叫一次，每個集區的呼叫率上限</span><span class="sxs-lookup"><span data-stu-id="34a95-190">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="34a95-191">200</span><span class="sxs-lookup"><span data-stu-id="34a95-191">200</span></span>  <br/> |<span data-ttu-id="34a95-192">0.25</span><span class="sxs-lookup"><span data-stu-id="34a95-192">25</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="34a95-193">前端伺服器的前端集區少於8部，以線性方式計算度量。</span><span class="sxs-lookup"><span data-stu-id="34a95-193">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="34a95-194">例如，如果您的前端集區有一部前端伺服器，請將表格中所顯示的值的最大負載計算為1/8。</span><span class="sxs-lookup"><span data-stu-id="34a95-194">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="34a95-195">您可以增加或減少每個群組的使用者人數和群組數目，只要您不要超過每個集區的最大使用者數目。</span><span class="sxs-lookup"><span data-stu-id="34a95-195">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="34a95-196">例如，您的 Standard Edition server 可以每個群組有25位使用者的120群組，因為為群組呼叫收取的使用者人數仍然在使用者模型中的最大 (，也就是120群組乘以25位3000使用者為使用者啟用群組呼叫收取) 的使用者。</span><span class="sxs-lookup"><span data-stu-id="34a95-196">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span> 
  

