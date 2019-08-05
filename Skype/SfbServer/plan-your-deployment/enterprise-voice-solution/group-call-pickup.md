---
title: 在商務用 Skype 中規劃群組通話挑選
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: 規劃商務用 Skype Server Enterprise Voice 中的群組呼叫挑選, 可讓使用者接聽最初預期給其他人的通話。
ms.openlocfilehash: c729e2d672d104337820c44fa41c113dded3110f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187684"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a><span data-ttu-id="8393b-103">在商務用 Skype 中規劃群組通話挑選</span><span class="sxs-lookup"><span data-stu-id="8393b-103">Plan for Group Call Pickup in Skype for Business</span></span>
 
<span data-ttu-id="8393b-104">規劃商務用 Skype Server Enterprise Voice 中的群組呼叫挑選, 可讓使用者接聽最初預期給其他人的通話。</span><span class="sxs-lookup"><span data-stu-id="8393b-104">Planning for Group Call Pickup in Skype for Business Server Enterprise Voice, which enables users to answer calls originally intended for others.</span></span>
  
<span data-ttu-id="8393b-105">[群組通話挑選] 可讓使用者從自己的手機接聽來電給他們的同事。</span><span class="sxs-lookup"><span data-stu-id="8393b-105">Group Call Pickup enables users to answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="8393b-106">如此一來, 您就可以透過撥打電話挑選群組號碼, 讓其他使用者接聽來電, 以提高使用者線路的可用性。</span><span class="sxs-lookup"><span data-stu-id="8393b-106">This increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="8393b-107">當您部署群組通話時, 傳送到語音信箱的撥入通話數量可能會大幅減少, 這對於來自貴組織外部的客戶的呼叫尤為有用。</span><span class="sxs-lookup"><span data-stu-id="8393b-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>
  
<span data-ttu-id="8393b-108">[群組呼叫挑選] 功能專門針對開啟的 office 環境中的商務單位而設計。</span><span class="sxs-lookup"><span data-stu-id="8393b-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="8393b-109">來電不會中斷, 因為它們只會在預定的目的地響鈴。</span><span class="sxs-lookup"><span data-stu-id="8393b-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="8393b-110">但其他聽見鈴聲的使用者, 只要撥打群組號碼, 就能繼續接聽通話。</span><span class="sxs-lookup"><span data-stu-id="8393b-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span> 
  
<span data-ttu-id="8393b-111">在使用者不位於已開啟的 office 版面配置中, 或在地理位置分散共同職責的使用者, 小組通話會提供最適合的方案。</span><span class="sxs-lookup"><span data-stu-id="8393b-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="8393b-112">[群組呼叫挑選] 與 [團隊通話] 之間的主要差異在於, 群組呼叫挑選只會在預定的目的地進行來電, 但是任何人都可以撥打群組號碼來回答問題。</span><span class="sxs-lookup"><span data-stu-id="8393b-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="8393b-113">使用「小組通話」, 小組中的所有人都能接聽電話, 而團隊中的任何使用者都可以接聽電話來接聽通話。</span><span class="sxs-lookup"><span data-stu-id="8393b-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="8393b-114">[群組通話挑選] 與 [團隊通話] 之間的其他差異是, 群組呼叫挑選是由管理員 (透過商務用 Skype 伺服器) 管理。</span><span class="sxs-lookup"><span data-stu-id="8393b-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Skype for Business Server.</span></span> <span data-ttu-id="8393b-115">透過團隊通話, 使用者可以使用商務用 Skype 用戶端來管理功能。</span><span class="sxs-lookup"><span data-stu-id="8393b-115">With team call, end users manage the feature by using the Skype for Business client.</span></span> <span data-ttu-id="8393b-116">使用 [群組呼叫], 即可集中進行通話管理的這個方面。</span><span class="sxs-lookup"><span data-stu-id="8393b-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>
  
<span data-ttu-id="8393b-117">[群組呼叫挑選] 是以 [通話駐留] 應用程式建立。</span><span class="sxs-lookup"><span data-stu-id="8393b-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="8393b-118">當您部署群組呼叫挑選時, 您可以設定 [通話公園軌道] 表格, 並將指定為 [呼叫挑選] 群組編號的不同範圍延伸。</span><span class="sxs-lookup"><span data-stu-id="8393b-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="8393b-119">例如通話公園軌道編號, 呼叫挑選群組號碼必須是沒有指派給他們的使用者或電話的虛擬延伸。</span><span class="sxs-lookup"><span data-stu-id="8393b-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="8393b-120">您在其中部署 [群組呼叫挑選] 的每個前端池都可以有一或多個呼叫挑選群組編號範圍。</span><span class="sxs-lookup"><span data-stu-id="8393b-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="8393b-121">在商務用 Skype Server 部署中, 群組號碼範圍必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="8393b-121">The group number ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8393b-122">在 [通話駐留軌道] 表格中指定為群組呼叫的數位範圍無法使用商務用 Skype Server [控制台] 進行管理或查看。</span><span class="sxs-lookup"><span data-stu-id="8393b-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="8393b-123">若要查看 [通話公園軌道] 表格中所有的數位範圍, 唯一的方法是使用商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="8393b-123">The only way to see all the number ranges in the call park orbit table is to use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8393b-124">同樣地, 新增、修改或移除群組通話號碼的唯一方法, 就是使用商務用 Skype 伺服器管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="8393b-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="8393b-125">在您設定 [呼叫挑選] 群組號碼之後, 您可以將使用者指派給 [通話挑選] 群組。</span><span class="sxs-lookup"><span data-stu-id="8393b-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="8393b-126">任何指派給 [呼叫挑選] 群組的使用者, 都可以由其他使用者接聽來電。</span><span class="sxs-lookup"><span data-stu-id="8393b-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="8393b-127">當來電進入指派給來電挑選群組的使用者時, 任何其他通知呼叫的使用者, 都可以手動撥打呼叫挑選群組號碼來回答該問題。</span><span class="sxs-lookup"><span data-stu-id="8393b-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="8393b-128">挑選通話的使用者不需要是群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8393b-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="8393b-129">當其他使用者接聽來電時, 系統會將通知傳送到最初呼叫的號碼。</span><span class="sxs-lookup"><span data-stu-id="8393b-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8393b-130">使用者只能是一個 [呼叫挑選] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8393b-130">A user can be a member of only one call pickup group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8393b-131">雖然商務用 Skype 伺服器部署中的任何使用者都可以接聽通話分揀群組成員的通話, 但接聽通話的人員必須知道正確的呼叫挑選群組號碼才能進行撥號。</span><span class="sxs-lookup"><span data-stu-id="8393b-131">Although any user in the Skype for Business Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span> 
  
<span data-ttu-id="8393b-132">當群組中有多個電話響鈴時, 如果使用者撥打電話給您的電話挑選群組號碼接聽電話, 使用者就會接聽已響鈴最長的通話。</span><span class="sxs-lookup"><span data-stu-id="8393b-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>
  
<span data-ttu-id="8393b-133">[同時撥打] 設定可供進行群組通話的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="8393b-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="8393b-134">也就是說, 對有 [群組呼叫挑選] 的使用者撥打電話時, 會撥打所有已設定的目的地, 而另一個使用者可以接聽通話。</span><span class="sxs-lookup"><span data-stu-id="8393b-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="8393b-135">此規則的例外狀況是當使用者設定同時撥打給呼叫所有團隊成員的時間。</span><span class="sxs-lookup"><span data-stu-id="8393b-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>
  
<span data-ttu-id="8393b-136">[群組呼叫挑選] 無法用來回答下列類型的通話:</span><span class="sxs-lookup"><span data-stu-id="8393b-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>
  
- <span data-ttu-id="8393b-137">呼叫私人線路</span><span class="sxs-lookup"><span data-stu-id="8393b-137">Calls to a private line</span></span>
    
- <span data-ttu-id="8393b-138">從已被指派朋友和家人隱私權關聯的連絡人撥打電話</span><span class="sxs-lookup"><span data-stu-id="8393b-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8393b-139">在商務用 Skype 用戶端中, 將連絡人標示為個人連絡人, 就能以 [呼叫挑選] 群組成員的身份, 避免特定呼叫的檢索。</span><span class="sxs-lookup"><span data-stu-id="8393b-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Skype for Business client.</span></span> <span data-ttu-id="8393b-140">若要將連絡人標示為個人連絡人, 請將該連絡人的隱私權關係設定為 [朋友] 和 [家人]。</span><span class="sxs-lookup"><span data-stu-id="8393b-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="8393b-141">您無法使用 [群組通話挑選], 透過將 [隱私權關係] 設定為 [朋友] 和 [家人] 的連絡人進行任何來電。</span><span class="sxs-lookup"><span data-stu-id="8393b-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span> 
  
- <span data-ttu-id="8393b-142">音訊/視頻通話的影片部分</span><span class="sxs-lookup"><span data-stu-id="8393b-142">Video portion of audio/video calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8393b-143">如果使用者接聽音訊/視頻通話, 使用者只會收到音訊。</span><span class="sxs-lookup"><span data-stu-id="8393b-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="8393b-144">打電話給對方或接聽電話的人, 都可以將通話升級, 以新增影片。</span><span class="sxs-lookup"><span data-stu-id="8393b-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span> 
  
- <span data-ttu-id="8393b-145">傳送給小組通話成員的同時撥打的通話</span><span class="sxs-lookup"><span data-stu-id="8393b-145">Simultaneous ringing calls that are routed to team call members</span></span>
    
- <span data-ttu-id="8393b-146">傳送給代理人的通話</span><span class="sxs-lookup"><span data-stu-id="8393b-146">Calls routed to a delegate</span></span>
    
- <span data-ttu-id="8393b-147">傳送給回應群組的通話</span><span class="sxs-lookup"><span data-stu-id="8393b-147">Calls routed to a response group</span></span>
    
<span data-ttu-id="8393b-148">下列使用者類型無法參與群組通話分揀。</span><span class="sxs-lookup"><span data-stu-id="8393b-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="8393b-149">也就是說, 它們不應該包含在群組通話分揀群組中, 而且他們無法為已啟用群組通話分揀的使用者挑選來電。</span><span class="sxs-lookup"><span data-stu-id="8393b-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>
  
- <span data-ttu-id="8393b-150">在混合式部署中駐留在線上的使用者</span><span class="sxs-lookup"><span data-stu-id="8393b-150">Users who are homed online in a hybrid deployment</span></span>
    
- <span data-ttu-id="8393b-151">不是駐留在商務用 Skype Server 2015 文件庫或 Lync Server 2013 池中的使用者, 以及 Lync Server 2013 的累積更新: 內部部署部署中的二月2013</span><span class="sxs-lookup"><span data-stu-id="8393b-151">Users who are not homed on either a Skype for Business Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>
    
<span data-ttu-id="8393b-152">如果沒有人接聽 [呼叫挑選] 群組的成員來電, 該通話就會以用戶端設定中指定的方式進行路由。</span><span class="sxs-lookup"><span data-stu-id="8393b-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="8393b-153">也就是說, 通話會傳送至語音信箱, 或轉寄到不同的目的地, 就像在用戶端設定中所指定的一樣。</span><span class="sxs-lookup"><span data-stu-id="8393b-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="8393b-154">部署與需求</span><span class="sxs-lookup"><span data-stu-id="8393b-154">Deployment and requirements</span></span>

<span data-ttu-id="8393b-155">當您部署企業語音及通話駐留應用程式時, 系統會自動部署群組通話拾取。</span><span class="sxs-lookup"><span data-stu-id="8393b-155">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="8393b-156">您可以透過設定 [通話駐留軌道投影片] 表格, 並將指定為 [呼叫挑選] 群組數位的數位範圍分開, 然後將使用者指派給他們呼叫挑選群組, 並讓使用者進行群組通話挑選, 來啟用群組通話。</span><span class="sxs-lookup"><span data-stu-id="8393b-156">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span>
  
## <a name="clients-supported-for-group-call-pickup"></a><span data-ttu-id="8393b-157">群組呼叫挑選支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="8393b-157">Clients supported for Group Call Pickup</span></span>

<span data-ttu-id="8393b-158">下列任何用戶端都可以用來接聽呼叫群組通話成員的通話:</span><span class="sxs-lookup"><span data-stu-id="8393b-158">Any of the following clients can be used to answer calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="8393b-159">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="8393b-159">Skype for Business</span></span>
    
- <span data-ttu-id="8393b-160">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8393b-160">Lync 2013</span></span>
    
- <span data-ttu-id="8393b-161">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="8393b-161">Lync 2010</span></span>
    
- <span data-ttu-id="8393b-162">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="8393b-162">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="8393b-163">使用者可以使用這些用戶端的任何一種方式, 接聽呼叫給群組的呼叫成員, 但使用者必須駐留在商務用 Skype 伺服器池或 Lync Server 2013 池中 (含 Lync Server 2013 的累積更新: 年2月 2013)。</span><span class="sxs-lookup"><span data-stu-id="8393b-163">Users can use any of these clients to answer calls to Group Call Pickup members, but the users must be homed on a Skype for Business Server pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="8393b-164">下列用戶端和裝置不支援取得群組呼叫挑選成員的呼叫:</span><span class="sxs-lookup"><span data-stu-id="8393b-164">The following clients and devices are not supported for picking up calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="8393b-165">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="8393b-165">Lync Mobile</span></span>
    
- <span data-ttu-id="8393b-166">適用于 Windows 8 和 Windows RT 的 Lync 應用程式</span><span class="sxs-lookup"><span data-stu-id="8393b-166">Lync app for Windows 8 and Windows RT</span></span>
    
- <span data-ttu-id="8393b-167">IPad 版 Lync</span><span class="sxs-lookup"><span data-stu-id="8393b-167">Lync for iPad</span></span>
    
- <span data-ttu-id="8393b-168">類比電話</span><span class="sxs-lookup"><span data-stu-id="8393b-168">Analog phones</span></span>
    
- <span data-ttu-id="8393b-169">含公用交換電話網絡 (PSTN) 號碼的手機</span><span class="sxs-lookup"><span data-stu-id="8393b-169">Phones with public switched telephone network (PSTN) numbers</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="8393b-170">容量規劃</span><span class="sxs-lookup"><span data-stu-id="8393b-170">Capacity planning</span></span>

<span data-ttu-id="8393b-171">下表說明您可以用來做為容量規劃需求基礎的 [群組呼叫挑選使用者模型]。</span><span class="sxs-lookup"><span data-stu-id="8393b-171">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8393b-172">[群組呼叫挑選] 是以 [通話駐留] 應用程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="8393b-172">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="8393b-173">請記住, 對於災難復原容量規劃, 配對池的每個池都應該能夠處理通話駐留服務的工作負荷, 包括兩個池中的群組呼叫。</span><span class="sxs-lookup"><span data-stu-id="8393b-173">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span> 
  
<span data-ttu-id="8393b-174">**群組呼叫使用者模型**</span><span class="sxs-lookup"><span data-stu-id="8393b-174">**Group Call Pickup User Model**</span></span>

|<span data-ttu-id="8393b-175">**衡量**</span><span class="sxs-lookup"><span data-stu-id="8393b-175">**Metric**</span></span>|<span data-ttu-id="8393b-176">**每個前臺端<br/>池 (含8個前端伺服器)**</span><span class="sxs-lookup"><span data-stu-id="8393b-176">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="8393b-177">**每個標準版 server**</span><span class="sxs-lookup"><span data-stu-id="8393b-177">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8393b-178">建議的每個群組使用者數</span><span class="sxs-lookup"><span data-stu-id="8393b-178">Recommended number of users per group</span></span>  <br/> |<span data-ttu-id="8393b-179">50</span><span class="sxs-lookup"><span data-stu-id="8393b-179">50</span></span>  <br/> |<span data-ttu-id="8393b-180">50</span><span class="sxs-lookup"><span data-stu-id="8393b-180">50</span></span>  <br/> |
|<span data-ttu-id="8393b-181">建議的群組數</span><span class="sxs-lookup"><span data-stu-id="8393b-181">Recommended number of groups</span></span>  <br/> |<span data-ttu-id="8393b-182">500</span><span class="sxs-lookup"><span data-stu-id="8393b-182">500</span></span>  <br/> |<span data-ttu-id="8393b-183">60</span><span class="sxs-lookup"><span data-stu-id="8393b-183">60</span></span>  <br/> |
|<span data-ttu-id="8393b-184">針對群組呼叫挑選啟用的每個池的使用者數目上限</span><span class="sxs-lookup"><span data-stu-id="8393b-184">Maximum number of users per pool enabled for Group Call Pickup</span></span>  <br/> |<span data-ttu-id="8393b-185">25000</span><span class="sxs-lookup"><span data-stu-id="8393b-185">25,000</span></span>  <br/> |<span data-ttu-id="8393b-186">3000</span><span class="sxs-lookup"><span data-stu-id="8393b-186">3,000</span></span>  <br/> |
|<span data-ttu-id="8393b-187">每分鐘針對每個群組呼叫啟用群組通話的最大來電率</span><span class="sxs-lookup"><span data-stu-id="8393b-187">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="8393b-188">500</span><span class="sxs-lookup"><span data-stu-id="8393b-188">500</span></span>  <br/> |<span data-ttu-id="8393b-189">60</span><span class="sxs-lookup"><span data-stu-id="8393b-189">60</span></span>  <br/> |
|<span data-ttu-id="8393b-190">每分鐘由每個群組呼叫每個群組的使用者所檢索來電的最大比率</span><span class="sxs-lookup"><span data-stu-id="8393b-190">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="8393b-191">200</span><span class="sxs-lookup"><span data-stu-id="8393b-191">200</span></span>  <br/> |<span data-ttu-id="8393b-192">位</span><span class="sxs-lookup"><span data-stu-id="8393b-192">25</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="8393b-193">對於不超過八個前端伺服器的前端池, 請線性地計算度量單位。</span><span class="sxs-lookup"><span data-stu-id="8393b-193">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="8393b-194">例如, 如果您的前端池有一個前端伺服器, 請將最大負載計算為表格中顯示的值1/8。</span><span class="sxs-lookup"><span data-stu-id="8393b-194">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8393b-195">只要您不超過每個池中的使用者數目上限, 您就可以增加或減少每個群組的使用者數和群組數。</span><span class="sxs-lookup"><span data-stu-id="8393b-195">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="8393b-196">例如, 您的標準版伺服器可以有120個群組, 每個群組含25個使用者, 因為為群組通話挑選啟用的使用者數目仍在使用者模型最大值 (也就是, 120 群組乘以25個3000使用者為群組通話挑選的使用者)。</span><span class="sxs-lookup"><span data-stu-id="8393b-196">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span> 
  

