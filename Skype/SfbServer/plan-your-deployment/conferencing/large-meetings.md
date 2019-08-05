---
title: 在商務用 Skype Server 中規劃大型會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: '摘要: 請閱讀本主題, 瞭解如何在商務用 Skype Server 中實施及管理大型會議的最佳做法。'
ms.openlocfilehash: 136896a45be36508af419d84bc5bd684c9d8a429
ms.sourcegitcommit: 3678dbbc8c36010fbf12c57b52281ef4fca9f065
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2019
ms.locfileid: "36193930"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a><span data-ttu-id="5000f-103">在商務用 Skype Server 中規劃大型會議</span><span class="sxs-lookup"><span data-stu-id="5000f-103">Plan for large meetings in Skype for Business Server</span></span>
 
<span data-ttu-id="5000f-104">**摘要:** 請閱讀本主題, 瞭解在商務用 Skype 伺服器中實施及管理大型會議的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="5000f-104">**Summary:** Read this topic to learn about best practices for implementing and managing large meetings in Skype for Business Server.</span></span>
  
<span data-ttu-id="5000f-105">商務用 Skype 伺服器所能支援的會議大小, 取決於會議是託管在共用或專用的池中: 從共用文件庫的250參與者到專用池上的1000參與者。</span><span class="sxs-lookup"><span data-stu-id="5000f-105">The size of meetings that Skype for Business Server can support depends on whether conferencing is hosted on a shared or dedicated pool: anywhere from 250 participants on a shared pool to 1000 participants on a dedicated pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5000f-106">本主題重點針對商務用 Skype Server 所支援的大型會議的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="5000f-106">This topic focuses on best practices for large meetings supported by Skype for Business Server.</span></span> <span data-ttu-id="5000f-107">如果您的組織需要較大的會議功能, 您應該考慮實施利用 Skype 會議廣播的混合式環境, 這是 Office 365 中的新線上服務。</span><span class="sxs-lookup"><span data-stu-id="5000f-107">If your organization requires larger meeting capabilities, you should consider implementing a hybrid environment that takes advantage of Skype Meeting Broadcast, a new online service that is part of Office 365.</span></span> 

> [!NOTE]
> <span data-ttu-id="5000f-108">Skype 會議廣播可讓使用者主持並將會議廣播至最多10000個參與者的大型線上物件。</span><span class="sxs-lookup"><span data-stu-id="5000f-108">Skype Meeting Broadcast enables users to host and broadcast meetings to large online audiences of up to 10,000 participants.</span></span> <span data-ttu-id="5000f-109">使用 Skype 會議廣播需要在混合式設定中針對生產 Office 365 租使用者設定商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="5000f-109">The use of Skype Meeting Broadcast requires that Skype for Business Server already be configured in a hybrid setup with a production Office 365 tenant.</span></span> <span data-ttu-id="5000f-110">所有使用者都必須已建立作為先決條件的線上租使用者。</span><span class="sxs-lookup"><span data-stu-id="5000f-110">All users must have an online tenant established as a prerequisite.</span></span> <span data-ttu-id="5000f-111">如果您想要部署可利用 Skype 會議廣播的混合式解決方案, 請參閱[什麼是 Skype 會議廣播？](https://go.microsoft.com/fwlink/?LinkId=617071)以及[設定 skype 會議廣播的內部部署部署](../../deploy/configure-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="5000f-111">If you are interested in deploying a hybrid solution that can take advantage of Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="5000f-112">大型會議通常具有下列特性:</span><span class="sxs-lookup"><span data-stu-id="5000f-112">Large meetings typically have the following characteristics:</span></span>
  
- <span data-ttu-id="5000f-113">會議格式是一對多份簡報。</span><span class="sxs-lookup"><span data-stu-id="5000f-113">The meeting format is a one-to-many presentation.</span></span>
    
- <span data-ttu-id="5000f-114">一或幾個使用者是簡報者, 而其他人則只參與為出席者。</span><span class="sxs-lookup"><span data-stu-id="5000f-114">One or a few users are presenters, and everyone else participates only as attendees.</span></span>
    
- <span data-ttu-id="5000f-115">PowerPoint 簡報共用是主要的資料共同作業活動。</span><span class="sxs-lookup"><span data-stu-id="5000f-115">PowerPoint presentation sharing is the main data collaboration activity.</span></span>
    
- <span data-ttu-id="5000f-116">音訊是必要的, 也可能會使用影片。</span><span class="sxs-lookup"><span data-stu-id="5000f-116">Audio is required and video may also be used.</span></span>
    
- <span data-ttu-id="5000f-117">專屬人員 (通常是會議召集人或召集人的助理) 會提前設定會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-117">A dedicated person, generally either the meeting organizer or an assistant to the organizer, sets up the meeting well in advance.</span></span>
    
- <span data-ttu-id="5000f-118">專用員工 (而不是簡報者) 會執行會議, 包括連線至線上會議、驗證音訊、影片及投影片共用工作、管理大廳及使用者角色、靜音及 unmuting 參與者、提出問題, 以及管理錄製 (例如適宜.</span><span class="sxs-lookup"><span data-stu-id="5000f-118">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>
    
<span data-ttu-id="5000f-119">當使用者排程會議時, 商務用 Skype 伺服器會在會議資料庫中建立一筆記錄, 該記錄會儲存會議資料, 但不會提前為排程的會議保留任何硬體資源。</span><span class="sxs-lookup"><span data-stu-id="5000f-119">When a user schedules a meeting, Skype for Business Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="5000f-120">相反地, 商務用 Skype 伺服器具有內建負載平衡邏輯, 可在前端伺服器上以平均分佈負載的方式, 在池中的所有前端伺服器上分配會議資源。</span><span class="sxs-lookup"><span data-stu-id="5000f-120">Instead, Skype for Business Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="5000f-121">這會有效地提供和使用硬體資源, 但您必須適當規劃以支援超大型會議, 這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="5000f-121">This effectively provisions and uses hardware resources, but it is important that you plan appropriately to support very large meetings.</span></span> 
  
<span data-ttu-id="5000f-122">例如, 當商務用 Skype 伺服器池正在接近其最上層容量時, 每個前端伺服器都可能主持大約125平均大小的會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-122">For example, when a Skype for Business Server pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="5000f-123">新增另一個小型會議並不是問題, 但為1000使用者新增會議時可能會有問題, 因為前端伺服器可能無法與其他125會議同時支援這類大型會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-123">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>
  
<span data-ttu-id="5000f-124">支援最多1000個參與者的大型會議, 需要解決與共享硬體模型和無保留模型相關的問題。</span><span class="sxs-lookup"><span data-stu-id="5000f-124">Supporting large meetings of up to 1000 participants requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span> <span data-ttu-id="5000f-125">一般來說, 您需要規劃專用的池子, 並遵循下列各節所述的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="5000f-125">In general, you need to plan for a dedicated pool and follow best practices as described in the following sections.</span></span> 
  
## <a name="plan-for-a-dedicated-pool"></a><span data-ttu-id="5000f-126">規劃專用池</span><span class="sxs-lookup"><span data-stu-id="5000f-126">Plan for a dedicated pool</span></span>

<span data-ttu-id="5000f-127">如果您的組織需要超過250個參與者的會議, 您必須規劃專用的池來支援載入。</span><span class="sxs-lookup"><span data-stu-id="5000f-127">If your organization requires meetings with greater than 250 participants, you need to plan for a dedicated pool to support the load.</span></span> 
  
<span data-ttu-id="5000f-128">若要在最多1000使用者的會議中擁有充足的 CPU 和記憶體資源, 託管前端伺服器不應該託管任何其他的立即訊息 (IM) 與目前狀態或企業語音工作負載。</span><span class="sxs-lookup"><span data-stu-id="5000f-128">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="5000f-129">無論其他會議的規模為何, 伺服器也不應該主持任何其他會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-129">The servers should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="5000f-130">若要寄存最多1000個使用者的會議, 您需要設定專用來主持大型會議的個別商務用 Skype 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="5000f-130">To host meetings of up to 1000 users, you need to set up a separate Skype for Business Server pool that is dedicated to hosting large meetings.</span></span>
  
<span data-ttu-id="5000f-131">專用來主持大型會議的商務用 Skype 伺服器池應該同時主持一或多達1000使用者的會議時間, 因此必須透過不限頻帶的排程程式來預先預留會議時間, 以確保從前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5000f-131">A Skype for Business Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="5000f-132">若要同時支援多個大型會議, 您應該設定多個專用大型會議池。</span><span class="sxs-lookup"><span data-stu-id="5000f-132">To support more than one large meeting at the same time, you should set up multiple dedicated large-meeting pools.</span></span>
  
<span data-ttu-id="5000f-133">如需硬體和軟體需求的詳細資訊, 以及規劃支援大型會議的拓撲, 請參閱[商務用 Skype Server 中的會議硬體和軟體需求](hardware-and-software-requirements.md), 以及[規劃會議拓撲商務用 Skype 伺服器](conferencing-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="5000f-133">For more information about hardware and software requirements, and planning a topology that supports large meetings, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md) and [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).</span></span>
  
## <a name="implement-best-practices-for-large-meetings"></a><span data-ttu-id="5000f-134">針對大型會議實施最佳做法</span><span class="sxs-lookup"><span data-stu-id="5000f-134">Implement best practices for large meetings</span></span>

<span data-ttu-id="5000f-135">針對大型會議設定專用池之後, 您可以採取一些步驟, 協助確保該文件庫中託管的大型會議都能提供最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="5000f-135">After setting up a dedicated pool for large meetings, you can take steps to help ensure that large meetings hosted in the pool provide the best user experience.</span></span> <span data-ttu-id="5000f-136">下列各節提供管理大型會議的指導方針:</span><span class="sxs-lookup"><span data-stu-id="5000f-136">The following sections provide guidelines for managing large meetings:</span></span>
  
- <span data-ttu-id="5000f-137">建立專用的會議召集人</span><span class="sxs-lookup"><span data-stu-id="5000f-137">Create dedicated meeting organizers</span></span>
    
- <span data-ttu-id="5000f-138">建立專屬的仲裁者</span><span class="sxs-lookup"><span data-stu-id="5000f-138">Create dedicated moderators</span></span>
    
- <span data-ttu-id="5000f-139">維護大型會議的個別行事曆</span><span class="sxs-lookup"><span data-stu-id="5000f-139">Maintain a separate calendar of large meetings</span></span>
    
- <span data-ttu-id="5000f-140">實施大型會議排程流程</span><span class="sxs-lookup"><span data-stu-id="5000f-140">Implement a large-meeting scheduling process</span></span>
    
- <span data-ttu-id="5000f-141">指定適當的排程詳細資料</span><span class="sxs-lookup"><span data-stu-id="5000f-141">Specify appropriate scheduling details</span></span>
    
- <span data-ttu-id="5000f-142">建立大型會議的會議原則</span><span class="sxs-lookup"><span data-stu-id="5000f-142">Create a conferencing policy for large meetings</span></span>
    
### <a name="create-dedicated-meeting-organizers"></a><span data-ttu-id="5000f-143">建立專用的會議召集人</span><span class="sxs-lookup"><span data-stu-id="5000f-143">Create dedicated meeting organizers</span></span>

<span data-ttu-id="5000f-144">若要將大型會議池中的即時通訊流量最小化, Microsoft 不建議將定期使用商務用 Skype 用戶端登入的使用者主持, 並參與立即訊息 (IM)、目前狀態、會議和語音會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-144">To minimize the real-time communications traffic in the large-meeting pool, Microsoft does not recommend hosting users who regularly sign in using Skype for Business clients and participate in instant messaging (IM), presence, conferencing, and voice sessions.</span></span> <span data-ttu-id="5000f-145">請改為執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="5000f-145">Instead, do one of the following:</span></span>
  
- <span data-ttu-id="5000f-146">針對排程大型會議建立一或多個專用的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="5000f-146">Create one or more dedicated user accounts just for scheduling large meetings</span></span>
    
- <span data-ttu-id="5000f-147">家用負責在大型會議池中排程大型會議的人員使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="5000f-147">Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool</span></span>
    
### <a name="create-dedicated-moderators"></a><span data-ttu-id="5000f-148">建立專屬的仲裁者</span><span class="sxs-lookup"><span data-stu-id="5000f-148">Create dedicated moderators</span></span>

<span data-ttu-id="5000f-149">在會議中有幾百位以上的使用者, 是一種很好的做法, 那就是讓專屬人員成為大型會議的線上會話是個不錯的做法。</span><span class="sxs-lookup"><span data-stu-id="5000f-149">With several hundred to a thousand users in a meeting, it is a good practice to have a dedicated person moderate the online session of a large meeting.</span></span> <span data-ttu-id="5000f-150">這個專用人員可以是會議召集人的代理人, 或是組織的大型會議支援人員的成員。</span><span class="sxs-lookup"><span data-stu-id="5000f-150">This dedicated person can be a delegate of the meeting organizer or a member of the organization's large-meeting support staff.</span></span> <span data-ttu-id="5000f-151">在排程會議時, 將專門的會議版主新增為簡報者, 不過在會議進行中時, 可以將線上會議出席者宣傳給簡報者角色是很重要的。</span><span class="sxs-lookup"><span data-stu-id="5000f-151">It is important to add the dedicated meeting moderator as a presenter at the time that the meeting is scheduled, although it is possible to promote an online meeting attendee to the presenter role while the meeting is in progress.</span></span>
  
<span data-ttu-id="5000f-152">會議仲裁者可以使用商務用 Skype 用戶端的所有簡報者功能來管理大型會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-152">The meeting moderator can use all presenter functionalities of Skype for Business clients to manage the large meeting.</span></span> <span data-ttu-id="5000f-153">這些功能包括:</span><span class="sxs-lookup"><span data-stu-id="5000f-153">These functionalities include:</span></span>
  
- <span data-ttu-id="5000f-154">監控大廳及 admitting 或拒絕大廳中的使用者</span><span class="sxs-lookup"><span data-stu-id="5000f-154">Monitoring the lobby and admitting or rejecting users in the lobby</span></span>
    
- <span data-ttu-id="5000f-155">移除會議中不應在會議中的任何使用者</span><span class="sxs-lookup"><span data-stu-id="5000f-155">Removing any users from the meeting who should not be in the meeting</span></span>
    
- <span data-ttu-id="5000f-156">變更會議存取類型</span><span class="sxs-lookup"><span data-stu-id="5000f-156">Changing meeting access types</span></span>
    
- <span data-ttu-id="5000f-157">變更參與者角色</span><span class="sxs-lookup"><span data-stu-id="5000f-157">Changing participant roles</span></span>
    
- <span data-ttu-id="5000f-158">使用拖放功能、電話撥出或電子郵件在會議期間邀請其他參與者</span><span class="sxs-lookup"><span data-stu-id="5000f-158">Inviting additional participants during the meeting using drag and drop functionality, phone dial out, or email</span></span>
    
- <span data-ttu-id="5000f-159">靜音及 unmuting 觀眾或個別使用者</span><span class="sxs-lookup"><span data-stu-id="5000f-159">Muting and unmuting the audience or individual users</span></span>
    
- <span data-ttu-id="5000f-160">管理會議內容, 包括上傳內容、刪除內容, 以及切換活動內容</span><span class="sxs-lookup"><span data-stu-id="5000f-160">Managing meeting content, including uploading content, deleting content, and switching active content</span></span>

    
### <a name="maintain-a-separate-calendar"></a><span data-ttu-id="5000f-161">維護個別行事曆</span><span class="sxs-lookup"><span data-stu-id="5000f-161">Maintain a separate calendar</span></span>

<span data-ttu-id="5000f-162">針對每個大型會議文件庫, 您應該為在該泳池上排程的大型會議維護一個單獨的行事曆。</span><span class="sxs-lookup"><span data-stu-id="5000f-162">For each large-meeting pool, you should maintain a separate calendar of large meetings scheduled on that pool.</span></span> <span data-ttu-id="5000f-163">例如, 您可以在大型會議文件庫中家用單一使用者帳戶, 並使用 Outlook 搭配商務用 Skype 的 Exchange 和線上會議增益集來維護個別的行事曆。</span><span class="sxs-lookup"><span data-stu-id="5000f-163">For example, you can home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype for Business to maintain a separate calendar.</span></span> <span data-ttu-id="5000f-164">如果您使用多個使用者帳戶來啟用支援人員來建立大型會議, 您可以設定一個單獨的行事曆, 將所有大型會議匯總給支援人員的成員所建立。</span><span class="sxs-lookup"><span data-stu-id="5000f-164">If you use multiple user accounts to enable a support staff to create large meetings, you can set up a separate calendar that aggregates all large meetings created by the members of the support staff.</span></span> 
  
<span data-ttu-id="5000f-165">維護個別大型會議行事曆有助於避免衝突, 並確保任何時候只有一個大型會議處於作用中。</span><span class="sxs-lookup"><span data-stu-id="5000f-165">Maintaining a separate large meeting calendar helps to prevent conflicts and ensure that only one large meeting is active at any time.</span></span>
  
### <a name="implement-a-scheduling-process"></a><span data-ttu-id="5000f-166">實施排程流程</span><span class="sxs-lookup"><span data-stu-id="5000f-166">Implement a scheduling process</span></span>

<span data-ttu-id="5000f-167">因為在專門大型的會議池中只支援一支大型會議, 所以您應該執行大型會議排程程式, 以協助您設定大型會議, 並協助避免衝突。</span><span class="sxs-lookup"><span data-stu-id="5000f-167">Because only one large meeting at a time is supported on the dedicated large meeting pool, you should implement a large meeting scheduling process to facilitate setting up large meetings and help prevent conflicts.</span></span> <span data-ttu-id="5000f-168">商務用 Skype Server 或商務用 Skype 用戶端不會直接提供此類功能。</span><span class="sxs-lookup"><span data-stu-id="5000f-168">Such capability is not provided directly by Skype for Business Server or Skype for Business clients.</span></span> <span data-ttu-id="5000f-169">實施這類程式的其中一個方法是使用貴組織的支援小組的票證系統 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="5000f-169">One way to implement such a process is to use your organization's support team's ticketing system, if available.</span></span>
  
<span data-ttu-id="5000f-170">排程大型會議時, 需要完成下列步驟:</span><span class="sxs-lookup"><span data-stu-id="5000f-170">Scheduling a large meeting involves completing the following steps:</span></span>
  
- <span data-ttu-id="5000f-171">除了簡報者清單之外, 會議召集人或代理人決定近期會議的時間、持續時間及大小。</span><span class="sxs-lookup"><span data-stu-id="5000f-171">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="5000f-172">如果預期的會議大小超過250的使用者, 或可確保會議的使用者經驗少於250個使用者, 召集人或代理人會提交大型會議的要求。</span><span class="sxs-lookup"><span data-stu-id="5000f-172">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>
    
- <span data-ttu-id="5000f-173">排程員工會檢查是否有可用的要求日期和時間。</span><span class="sxs-lookup"><span data-stu-id="5000f-173">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="5000f-174">因為我們一次只支援專用池的單一大型會議, 所以排程員工必須檢查大型會議行事曆, 以判斷是否有針對要求的日期和時間排程其他會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-174">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="5000f-175">如果有所要求的時間, 員工會核准會議邀請。</span><span class="sxs-lookup"><span data-stu-id="5000f-175">If the requested time is available, the staff approves the meeting request.</span></span>
    
- <span data-ttu-id="5000f-176">如果要求受到核准, 排程員工 (在專用的池中使用認證) 使用 Outlook 的商務用 Skype 增益集, 在專門的大型會議泳池上設定會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-176">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Skype for Business with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="5000f-177">要用來加入會議的 URL 會提供給申請者, 作為核准通知的一部分。</span><span class="sxs-lookup"><span data-stu-id="5000f-177">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>
    
- <span data-ttu-id="5000f-178">會議召集人或代理人會使用 Outlook 來排程即將到來的會議, 新增加入會議的 URL 至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="5000f-178">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="5000f-179">[會議召集人] 或 [代理人] 會指定受邀的使用者, 併發出會議邀請。</span><span class="sxs-lookup"><span data-stu-id="5000f-179">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
### <a name="specify-appropriate-scheduling-details"></a><span data-ttu-id="5000f-180">指定適當的排程詳細資料</span><span class="sxs-lookup"><span data-stu-id="5000f-180">Specify appropriate scheduling details</span></span>

<span data-ttu-id="5000f-181">在您檢查並確定未在要求的時間前排程任何其他會議之後, 處理要求的大型會議支援人員會在大型會議泳池上排程會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-181">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> 
  
<span data-ttu-id="5000f-182">若要確保最佳的使用者體驗, 請務必按照適合會議召集人需求的正確存取層級和會議設定來排程大型會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-182">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer's needs.</span></span> <span data-ttu-id="5000f-183">考慮在商務用 Skype 會議選項中設定的下列排程設定:</span><span class="sxs-lookup"><span data-stu-id="5000f-183">Consider the following scheduling settings configured in Skype for Business Meeting options:</span></span>
  
- <span data-ttu-id="5000f-184">針對每個大型會議使用新的會議空間, 而不是重複使用專用會議空間。</span><span class="sxs-lookup"><span data-stu-id="5000f-184">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span> 
    
- <span data-ttu-id="5000f-185">指定會議存取層級, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="5000f-185">Specify the meeting access level as follows:</span></span>
    
  - <span data-ttu-id="5000f-186">如果組織中至少有一個受邀者, 請將會議存取類型設定為 **[任何人] (無限制)**。</span><span class="sxs-lookup"><span data-stu-id="5000f-186">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions)**.</span></span> <span data-ttu-id="5000f-187">這可讓您避免在會議進行中時, 不需要管理可能較大的大廳。</span><span class="sxs-lookup"><span data-stu-id="5000f-187">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
  - <span data-ttu-id="5000f-188">如果會議是僅限內部會議, 請將會議存取類型設定為 [**我的組織中的任何人**]。</span><span class="sxs-lookup"><span data-stu-id="5000f-188">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5000f-189">避免將 [會議存取類型] 設定為 [**我從公司邀請的人員**], 因為當您使用此設定時, 召集人必須將所有使用者電子郵件地址新增至被邀請者清單, 而且您無法邀請通訊群組。</span><span class="sxs-lookup"><span data-stu-id="5000f-189">Avoid setting the meeting access type to **People I invite from my company** because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span> <span data-ttu-id="5000f-190">避免將會議存取類型設定為 **[僅自己] (會議召集人),** 因為這項設定需要每個會議參與者 (包括簡報者) 都必須放在會議執行時間的大廳中。</span><span class="sxs-lookup"><span data-stu-id="5000f-190">Avoid setting the meeting access type to **Only me, the meeting organizer** because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="5000f-191">負責執行大型會議的人員必須持續監視大廳名單並承認大廳中的新使用者。</span><span class="sxs-lookup"><span data-stu-id="5000f-191">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>
  
- <span data-ttu-id="5000f-192">[允許從手機撥入的使用者] 透過核取 [來電者**直接取得**] 設定來自動進入會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-192">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>
    
- <span data-ttu-id="5000f-193">明確邀請下列使用者:</span><span class="sxs-lookup"><span data-stu-id="5000f-193">Explicitly invite the following users:</span></span>
    
  - <span data-ttu-id="5000f-194">會議召集人和委派 (申請者)</span><span class="sxs-lookup"><span data-stu-id="5000f-194">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="5000f-195">會議申請者提供的簡報者清單</span><span class="sxs-lookup"><span data-stu-id="5000f-195">The list of presenters provided by a meeting requester</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5000f-196">如果 [會議存取類型] 設定為 **[我選擇的人員**], 您必須明確將大型會議的參與者新增為會議的被邀請者。</span><span class="sxs-lookup"><span data-stu-id="5000f-196">If the meeting access type is set to **People I choose**, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span> 
  
- <span data-ttu-id="5000f-197">明確管理簡報者, 而不是將簡報者選項設定為其中一個自動升級值。</span><span class="sxs-lookup"><span data-stu-id="5000f-197">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values.</span></span> <span data-ttu-id="5000f-198">請務必將下列使用者新增為簡報者:</span><span class="sxs-lookup"><span data-stu-id="5000f-198">Be sure to add the following users as presenters:</span></span>
    
  - <span data-ttu-id="5000f-199">會議召集人和委派 (申請者)</span><span class="sxs-lookup"><span data-stu-id="5000f-199">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="5000f-200">大型會議申請者提供的簡報者清單</span><span class="sxs-lookup"><span data-stu-id="5000f-200">The list of presenters provided by large meeting requesters</span></span>
    
    <span data-ttu-id="5000f-201">透過顯式管理簡報者, 您可以將簡報者限制為小數位, 以使其擁有有效的大型會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-201">By explicitly managing presenters, you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="5000f-202">如果大多數會議參與者都有出席者角色, 這有助於減少人員不小心控制簡報的機率、刪除 PowerPoint 簡報、靜音/unmuting 簡報者, 以及其他中斷會議的機會。</span><span class="sxs-lookup"><span data-stu-id="5000f-202">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span> 
    
- <span data-ttu-id="5000f-203">核取 [**所有出席者靜音**] 設定, 以確保只有簡報者可以將音訊廣播到會議中。</span><span class="sxs-lookup"><span data-stu-id="5000f-203">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>
    
- <span data-ttu-id="5000f-204">核取 [**封鎖出席者的影片**] 設定, 以確保只有簡報者可以將影片廣播到會議中。</span><span class="sxs-lookup"><span data-stu-id="5000f-204">Check the **Block attendees' video** setting to make sure only presenters can broadcast video into the meeting.</span></span>
    
### <a name="create-a-conferencing-policy"></a><span data-ttu-id="5000f-205">建立會議原則</span><span class="sxs-lookup"><span data-stu-id="5000f-205">Create a conferencing policy</span></span>

<span data-ttu-id="5000f-206">特別針對大型會議建立新的會議策略, 然後將會議原則指派給駐留在專門大型會議池的使用者。</span><span class="sxs-lookup"><span data-stu-id="5000f-206">Create a new conferencing policy specifically for large meetings, and then assign the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="5000f-207">使用下列設定來設定會議原則:</span><span class="sxs-lookup"><span data-stu-id="5000f-207">Configure the conferencing policy using the following settings:</span></span>
  
- <span data-ttu-id="5000f-208">將**MaxMeetingSize**選項設定為1000。</span><span class="sxs-lookup"><span data-stu-id="5000f-208">Set the **MaxMeetingSize** option to 1000.</span></span> <span data-ttu-id="5000f-209">(預設值為 250)。</span><span class="sxs-lookup"><span data-stu-id="5000f-209">(The default is 250.)</span></span>
    
- <span data-ttu-id="5000f-210">將**AllowLargeMeetings**選項設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="5000f-210">Set the **AllowLargeMeetings** option to **True**.</span></span> 
    
- <span data-ttu-id="5000f-211">將 [ **EnableAppDesktopSharing** ] 選項設定為 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="5000f-211">Set the **EnableAppDesktopSharing** option to **None**.</span></span>
    
- <span data-ttu-id="5000f-212">將 [ **AllowUserToScheduleMeetingsWithAppSharing** ] 選項設定為 [ **False**]。</span><span class="sxs-lookup"><span data-stu-id="5000f-212">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>
    
- <span data-ttu-id="5000f-213">將 [ **AllowSharedNotes** ] 選項設定為 [ **False**]。</span><span class="sxs-lookup"><span data-stu-id="5000f-213">Set the **AllowSharedNotes** option to **False**.</span></span>
    
- <span data-ttu-id="5000f-214">將 [ **AllowAnnotations** ] 選項設定為 [ **False**]。</span><span class="sxs-lookup"><span data-stu-id="5000f-214">Set the **AllowAnnotations** option to **False**.</span></span>
    
- <span data-ttu-id="5000f-215">將**DisablePowerPointAnnotations**選項設定為**True**。</span><span class="sxs-lookup"><span data-stu-id="5000f-215">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>
    
- <span data-ttu-id="5000f-216">將 [ **AllowMultiview** ] 選項設定為 [ **False**]。</span><span class="sxs-lookup"><span data-stu-id="5000f-216">Set the **AllowMultiview** option to **False**.</span></span>
    
- <span data-ttu-id="5000f-217">將 [ **EnableMultiviewJoin** ] 選項設定為 [ **False**]。</span><span class="sxs-lookup"><span data-stu-id="5000f-217">Set the **EnableMultiviewJoin** option to **False**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5000f-218">在商務用 Skype Server 中的大型會議支援, 必須將 [ **AllowLargeMeetings** ] 設定設為 true。</span><span class="sxs-lookup"><span data-stu-id="5000f-218">Support for large meetings in Skype for Business Server requires that the **AllowLargeMeetings** setting be set to true.</span></span> <span data-ttu-id="5000f-219">當此設定設為 true 時, 當使用者加入會議時, 商務用 Skype 體驗將會針對超大型會議進行優化。</span><span class="sxs-lookup"><span data-stu-id="5000f-219">When this setting is set to true, the Skype for Business experience will be optimized for extra-large meetings when users join the meeting.</span></span> <span data-ttu-id="5000f-220">特別是在大型會議中, 商務用 Skype 不會顯示完整會議參與者清單的初始或更新, 這是用戶端與商務用 Skype 伺服器的效能瓶頸。</span><span class="sxs-lookup"><span data-stu-id="5000f-220">Specifically, in a large meeting, Skype for Business will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Skype for Business Server.</span></span> <span data-ttu-id="5000f-221">相反地, 商務用 Skype 只會顯示使用者的相關資訊和會議的簡報者清單。</span><span class="sxs-lookup"><span data-stu-id="5000f-221">Instead, Skype for Business will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="5000f-222">商務用 Skype 仍會顯示大型會議中可用的參與者總數。</span><span class="sxs-lookup"><span data-stu-id="5000f-222">Skype for Business will still show the total number of participants available in the large meetings.</span></span>

<span data-ttu-id="5000f-223">[ **AllowLargeMeetings $true** ] 設定會造成下列問題:</span><span class="sxs-lookup"><span data-stu-id="5000f-223">The **AllowLargeMeetings $true** setting causes the following:</span></span>

- <span data-ttu-id="5000f-224">隱藏出席者名單。</span><span class="sxs-lookup"><span data-stu-id="5000f-224">Hides the Attendee roster.</span></span> 

- <span data-ttu-id="5000f-225">停用 IM 視窗中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="5000f-225">Disables errors in the IM window.</span></span>

- <span data-ttu-id="5000f-226">停用多方影片。</span><span class="sxs-lookup"><span data-stu-id="5000f-226">Disables multi-party video.</span></span>

- <span data-ttu-id="5000f-227">停用將出席者促銷給簡報者的能力。</span><span class="sxs-lookup"><span data-stu-id="5000f-227">Disables ability to promote an Attendee to Presenter.</span></span> <span data-ttu-id="5000f-228">您必須預先規劃並宣告所有簡報者之後, 才能進行會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-228">You must plan ahead and declare all Presenters before the meeting.</span></span>

- <span data-ttu-id="5000f-229">停用取消靜音個別出席者的功能。</span><span class="sxs-lookup"><span data-stu-id="5000f-229">Disables ability to unmute individual Attendees.</span></span>

- <span data-ttu-id="5000f-230">停用將 [鎖定影片焦點] 功能套用到 [出席者] 的功能。</span><span class="sxs-lookup"><span data-stu-id="5000f-230">Disables ability to apply the Lock Video Spotlight feature to Attendees.</span></span>

- <span data-ttu-id="5000f-231">使用者將無法使用6取消靜音, 因為在活躍大型會議中負責 DTMF 命令的個人虛擬協助將遺失。</span><span class="sxs-lookup"><span data-stu-id="5000f-231">PSTN dial in users will be unable to unmute themselves using 6 because Personal Virtual Assistance which is responsible for DTMF commands in active large meetings is missing.</span></span>

- <span data-ttu-id="5000f-232">如果簡報者/召集人將會議安排在其中每個人都應該設為靜音的位置 (「全部靜音」), PSTN 使用者將在整個通話中靜音, 而且無法自行取消靜音。</span><span class="sxs-lookup"><span data-stu-id="5000f-232">If the presenter/organizer schedules a meeting where everyone should be muted first ("Mute All"), PSTN users will be muted throughout the call and will not be able to unmute themselves.</span></span>

<span data-ttu-id="5000f-233">除了 [**最大會議大小**] 設定之外, 您還需要在此處指定的所有其他會議原則設定, 才能停用大型會議中不需要的會議功能。</span><span class="sxs-lookup"><span data-stu-id="5000f-233">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>
  
<span data-ttu-id="5000f-234">此外, 您還需要設定專用大型會議池, 以便駐留在該擁有者且負責管理會議排程的每個商務用 Skype 伺服器使用者都具備適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="5000f-234">Additionally, you need to configure the dedicated large-meeting pool so that each Skype for Business Server user who is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="5000f-235">若要這樣做, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="5000f-235">To do this, do the following:</span></span>
  
- <span data-ttu-id="5000f-236">將 [**指定為簡報者**] 選項設定為 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="5000f-236">Set the **Designate as presenter** option to **None**.</span></span> <span data-ttu-id="5000f-237">通常, 大型會議所有參與者的一或多個使用者都是簡報者, 所以不應以簡報者的身分自動准許參與者參加大型會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-237">Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters.</span></span> <span data-ttu-id="5000f-238">相反地, 簡報者應該在會議排程時間明確指定, 或在大型會議中明確地進行升級。</span><span class="sxs-lookup"><span data-stu-id="5000f-238">Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>
    
- <span data-ttu-id="5000f-239">請確認未選取 [**預設為指派的會議類型**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5000f-239">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="5000f-240">此設定控制商務用 Skype 的線上會議增益集是否總是使用召集人指派的會議來排程會議, 這表示排程的會議具有相同的聯接 URL 和音訊資訊。</span><span class="sxs-lookup"><span data-stu-id="5000f-240">This setting controls whether the Online Meeting Add-in for Skype for Business always schedules conferences using the organizer's assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="5000f-241">在小型群組共同作業案例中, 由於每個人都有自己指派的會議, 且常數加入 URL 和音訊資訊都能協助您更快速地加入會議, 因此在小組共同作業案例中擁有此類會議。</span><span class="sxs-lookup"><span data-stu-id="5000f-241">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="5000f-242">不過, 在大型會議案例中, 大型會議支援人員會使用一組使用者認證來安排大型會議, 然後提供加入 Url 和音訊資訊給會議申請者。</span><span class="sxs-lookup"><span data-stu-id="5000f-242">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="5000f-243">在這種情況下, 使用不同的 URL 加入每個會議都能更好。</span><span class="sxs-lookup"><span data-stu-id="5000f-243">In this case, using a different URL to join each meeting works better.</span></span>
    
- <span data-ttu-id="5000f-244">除非必要, 否則請確認未選取 [**以預設方式承認匿名使用者**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5000f-244">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="5000f-245">此設定會影響不使用指派的會議時, 由商務用 Skype 的線上會議增益集排程的預設會議存取類型。</span><span class="sxs-lookup"><span data-stu-id="5000f-245">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Skype for Business when not using an assigned conference.</span></span> <span data-ttu-id="5000f-246">此設定的適當選項視貴組織的需求而定。</span><span class="sxs-lookup"><span data-stu-id="5000f-246">The appropriate option for this setting depends on your organization's needs.</span></span> <span data-ttu-id="5000f-247">如果貴組織的大多數大型會議都是內部會議, 請勿選取此選項。</span><span class="sxs-lookup"><span data-stu-id="5000f-247">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="5000f-248">如果大多數大型會議都需要外部使用者能夠加入, 請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="5000f-248">If most large meetings require that external users be able to join, select this option.</span></span>
    
<span data-ttu-id="5000f-249">如需建立會議原則的詳細資訊, 請參閱[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5000f-249">For more information about creating a conferencing policy, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  

