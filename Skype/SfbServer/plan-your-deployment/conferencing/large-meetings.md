---
title: 在商務用 Skype Server 中規劃大型會議
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
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: 摘要：閱讀此主題以瞭解在商務用 Skype Server 中實施及管理大型會議的最佳作法。
ms.openlocfilehash: 8e982f08b1ff65ac6a4ea6f47a15e57f1eded163
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813973"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a><span data-ttu-id="7eaeb-103">在商務用 Skype Server 中規劃大型會議</span><span class="sxs-lookup"><span data-stu-id="7eaeb-103">Plan for large meetings in Skype for Business Server</span></span>
 
<span data-ttu-id="7eaeb-104">**摘要：** 閱讀此主題以瞭解在商務用 Skype Server 中實施及管理大型會議的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-104">**Summary:** Read this topic to learn about best practices for implementing and managing large meetings in Skype for Business Server.</span></span>
  
<span data-ttu-id="7eaeb-105">商務用 Skype 伺服器可支援的會議大小，取決於會議是否主控于共用或專屬集區：任何地方從共用集區上的250參與者到專用集區上的1000參與者。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-105">The size of meetings that Skype for Business Server can support depends on whether conferencing is hosted on a shared or dedicated pool: anywhere from 250 participants on a shared pool to 1000 participants on a dedicated pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7eaeb-106">本主題著重于商務用 Skype Server 所支援之大型會議的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-106">This topic focuses on best practices for large meetings supported by Skype for Business Server.</span></span> <span data-ttu-id="7eaeb-107">如果您的組織需要較大的會議能力，您應該考慮實施使用 Skype 會議廣播的混合式環境，這是 Microsoft 365 和 Office 365 中的新線上服務。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-107">If your organization requires larger meeting capabilities, you should consider implementing a hybrid environment that takes advantage of Skype Meeting Broadcast, a new online service that is part of Microsoft 365 and Office 365.</span></span> 

> [!NOTE]
> <span data-ttu-id="7eaeb-108">Skype 會議廣播可讓使用者主控及廣播會議至最多10000參與者的大型線上受眾。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-108">Skype Meeting Broadcast enables users to host and broadcast meetings to large online audiences of up to 10,000 participants.</span></span> <span data-ttu-id="7eaeb-109">使用 Skype 會議廣播時，必須已在實際執行 Microsoft 365 或 Office 365 組織的混合式設定中設定商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-109">The use of Skype Meeting Broadcast requires that Skype for Business Server already be configured in a hybrid setup with a production Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="7eaeb-110">所有使用者都必須以必要條件建立線上承租人。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-110">All users must have an online tenant established as a prerequisite.</span></span> <span data-ttu-id="7eaeb-111">如果您想要部署可利用 Skype 會議廣播的混合式解決方案，請參閱 [什麼是 Skype 會議廣播？](https://go.microsoft.com/fwlink/?LinkId=617071) 和 [設定您的內部部署以進行 skype 會議廣播](../../deploy/configure-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-111">If you are interested in deploying a hybrid solution that can take advantage of Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="7eaeb-112">大型會議通常具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-112">Large meetings typically have the following characteristics:</span></span>
  
- <span data-ttu-id="7eaeb-113">會議格式是一對多簡報。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-113">The meeting format is a one-to-many presentation.</span></span>
    
- <span data-ttu-id="7eaeb-114">只有一位或少數使用者是簡報者，其他人都是以出席者的身分參加會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-114">One or a few users are presenters, and everyone else participates only as attendees.</span></span>
    
- <span data-ttu-id="7eaeb-115">PowerPoint 簡報共用是主要的資料共同作業活動。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-115">PowerPoint presentation sharing is the main data collaboration activity.</span></span>
    
- <span data-ttu-id="7eaeb-116">音訊是必要的，也可以使用視訊。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-116">Audio is required and video may also be used.</span></span>
    
- <span data-ttu-id="7eaeb-117">專業人員通常是會議召集人或召集人的助理，會事先設定會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-117">A dedicated person, generally either the meeting organizer or an assistant to the organizer, sets up the meeting well in advance.</span></span>
    
- <span data-ttu-id="7eaeb-118">代理 (非簡報者) 負責會議進行，包括與線上會議連線、確認音訊、視訊和投影片共用的運作、管理大廳與使用者角色、設定或取消設定參與者的靜音功能、記錄問題以及管理錄音。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-118">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>
    
<span data-ttu-id="7eaeb-119">當使用者排程會議時，商務用 Skype 伺服器會在會議資料庫中建立記錄，而該記錄會儲存會議資料，但不會事先為排程的會議保留任何硬體資源。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-119">When a user schedules a meeting, Skype for Business Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="7eaeb-120">相反地，商務用 Skype 伺服器具有內建負載平衡邏輯，可在前端伺服器上以平均方式在集區中的所有前端伺服器上平均分配會議資源。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-120">Instead, Skype for Business Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="7eaeb-121">這會有效地布建和使用硬體資源，但是請務必適當規劃以支援非常大的會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-121">This effectively provisions and uses hardware resources, but it is important that you plan appropriately to support very large meetings.</span></span> 
  
<span data-ttu-id="7eaeb-122">例如，當商務用 Skype 伺服器集區的最上層容量執行時，每一部前端伺服器可能會裝載大約125平均大小的會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-122">For example, when a Skype for Business Server pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="7eaeb-123">新增另一個小型會議不是問題，但為1000使用者新增會議時，可能會有問題，因為前端伺服器可能無法與其他125會議同時支援這類大型會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-123">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>
  
<span data-ttu-id="7eaeb-124">支援最多1000參與者的大型會議，需要解決與共享硬體模型和非保留模型相關的問題。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-124">Supporting large meetings of up to 1000 participants requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span> <span data-ttu-id="7eaeb-125">一般來講，您必須規劃專用集區，並遵循下列各節所述的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-125">In general, you need to plan for a dedicated pool and follow best practices as described in the following sections.</span></span> 
  
## <a name="plan-for-a-dedicated-pool"></a><span data-ttu-id="7eaeb-126">規劃專用集區</span><span class="sxs-lookup"><span data-stu-id="7eaeb-126">Plan for a dedicated pool</span></span>

<span data-ttu-id="7eaeb-127">如果您的組織需要超過250參與者的會議，您必須規劃專用集區以支援負載。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-127">If your organization requires meetings with greater than 250 participants, you need to plan for a dedicated pool to support the load.</span></span> 
  
<span data-ttu-id="7eaeb-128">為了讓最多1000使用者的會議具有足夠的 CPU 和記憶體資源，主控前端伺服器不應主控任何其他立即訊息 (IM) 和目前狀態或企業語音工作負載。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-128">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="7eaeb-129">不論其他的會議大小為何，伺服器也不會主控任何其他會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-129">The servers should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="7eaeb-130">若要主控最多1000使用者的會議，您需要設定個別的商務用 Skype 伺服器集區，專門用來主控大型會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-130">To host meetings of up to 1000 users, you need to set up a separate Skype for Business Server pool that is dedicated to hosting large meetings.</span></span>
  
<span data-ttu-id="7eaeb-131">專用於主控大型會議的商務用 Skype 伺服器集區，一次只能裝載一或1000多個會議，所以必須透過帶外排程過程預先保留會議時間，以確保前端伺服器的專屬支援。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-131">A Skype for Business Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="7eaeb-132">若要同時支援一個以上的大型會議，您應該設定多個專用的大型會議集區。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-132">To support more than one large meeting at the same time, you should set up multiple dedicated large-meeting pools.</span></span>
  
<span data-ttu-id="7eaeb-133">如需硬體和軟體需求的詳細資訊，以及規劃支援大型會議的拓撲，請參閱 [在商務用 Skype server 中的會議硬體和軟體需求](hardware-and-software-requirements.md) ，以及 [為商務用 skype server 規劃會議拓撲](conferencing-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-133">For more information about hardware and software requirements, and planning a topology that supports large meetings, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md) and [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).</span></span>
  
## <a name="implement-best-practices-for-large-meetings"></a><span data-ttu-id="7eaeb-134">實施大型會議的最佳作法</span><span class="sxs-lookup"><span data-stu-id="7eaeb-134">Implement best practices for large meetings</span></span>

<span data-ttu-id="7eaeb-135">為大型會議設定專用集區之後，您可以採取步驟來協助確保集區中的大型會議提供最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-135">After setting up a dedicated pool for large meetings, you can take steps to help ensure that large meetings hosted in the pool provide the best user experience.</span></span> <span data-ttu-id="7eaeb-136">下列各節提供管理大型會議的指導方針：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-136">The following sections provide guidelines for managing large meetings:</span></span>
  
- <span data-ttu-id="7eaeb-137">建立專屬會議召集人</span><span class="sxs-lookup"><span data-stu-id="7eaeb-137">Create dedicated meeting organizers</span></span>
    
- <span data-ttu-id="7eaeb-138">建立專屬仲裁者</span><span class="sxs-lookup"><span data-stu-id="7eaeb-138">Create dedicated moderators</span></span>
    
- <span data-ttu-id="7eaeb-139">維護不同的大型會議行事曆</span><span class="sxs-lookup"><span data-stu-id="7eaeb-139">Maintain a separate calendar of large meetings</span></span>
    
- <span data-ttu-id="7eaeb-140">實施大型會議排程處理常式</span><span class="sxs-lookup"><span data-stu-id="7eaeb-140">Implement a large-meeting scheduling process</span></span>
    
- <span data-ttu-id="7eaeb-141">指定適當的排程詳細資料</span><span class="sxs-lookup"><span data-stu-id="7eaeb-141">Specify appropriate scheduling details</span></span>
    
- <span data-ttu-id="7eaeb-142">為大型會議建立會議原則</span><span class="sxs-lookup"><span data-stu-id="7eaeb-142">Create a conferencing policy for large meetings</span></span>
    
### <a name="create-dedicated-meeting-organizers"></a><span data-ttu-id="7eaeb-143">建立專屬會議召集人</span><span class="sxs-lookup"><span data-stu-id="7eaeb-143">Create dedicated meeting organizers</span></span>

<span data-ttu-id="7eaeb-144">若要將大型會議集區中的即時通訊流量降到最低，Microsoft 不建議使用使用商務用 Skype 用戶端來定期登入的使用者，並參與立即訊息 (IM) 、顯示狀態、會議及語音會話。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-144">To minimize the real-time communications traffic in the large-meeting pool, Microsoft does not recommend hosting users who regularly sign in using Skype for Business clients and participate in instant messaging (IM), presence, conferencing, and voice sessions.</span></span> <span data-ttu-id="7eaeb-145">請改為執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-145">Instead, do one of the following:</span></span>
  
- <span data-ttu-id="7eaeb-146">建立一或多個專用的使用者帳戶，只用于排程大型會議</span><span class="sxs-lookup"><span data-stu-id="7eaeb-146">Create one or more dedicated user accounts just for scheduling large meetings</span></span>
    
- <span data-ttu-id="7eaeb-147">Home 負責在大型會議集區上排程大型會議之人員的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="7eaeb-147">Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool</span></span>
    
### <a name="create-dedicated-moderators"></a><span data-ttu-id="7eaeb-148">建立專屬仲裁者</span><span class="sxs-lookup"><span data-stu-id="7eaeb-148">Create dedicated moderators</span></span>

<span data-ttu-id="7eaeb-149">在會議中有數百個到一千位使用者的使用者，讓專屬人員進行大型會議的線上會話是一種很好的作法。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-149">With several hundred to a thousand users in a meeting, it is a good practice to have a dedicated person moderate the online session of a large meeting.</span></span> <span data-ttu-id="7eaeb-150">這個專屬人員可以是會議召集人的代理人，或是組織之大型會議支援人員的成員。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-150">This dedicated person can be a delegate of the meeting organizer or a member of the organization's large-meeting support staff.</span></span> <span data-ttu-id="7eaeb-151">排程會議時，將專門的會議版主新增為簡報者，不過在會議進行中時，可能會將線上會議出席者提升為簡報者角色，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-151">It is important to add the dedicated meeting moderator as a presenter at the time that the meeting is scheduled, although it is possible to promote an online meeting attendee to the presenter role while the meeting is in progress.</span></span>
  
<span data-ttu-id="7eaeb-152">會議版主可使用商務用 Skype 用戶端的所有簡報者功能來管理大型會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-152">The meeting moderator can use all presenter functionalities of Skype for Business clients to manage the large meeting.</span></span> <span data-ttu-id="7eaeb-153">這些功能包括：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-153">These functionalities include:</span></span>
  
- <span data-ttu-id="7eaeb-154">監視會議廳和准許或拒絕會議廳中的使用者</span><span class="sxs-lookup"><span data-stu-id="7eaeb-154">Monitoring the lobby and admitting or rejecting users in the lobby</span></span>
    
- <span data-ttu-id="7eaeb-155">移除會議中不應該存在於會議中的任何使用者</span><span class="sxs-lookup"><span data-stu-id="7eaeb-155">Removing any users from the meeting who should not be in the meeting</span></span>
    
- <span data-ttu-id="7eaeb-156">變更會議訪問類型</span><span class="sxs-lookup"><span data-stu-id="7eaeb-156">Changing meeting access types</span></span>
    
- <span data-ttu-id="7eaeb-157">變更參與者角色</span><span class="sxs-lookup"><span data-stu-id="7eaeb-157">Changing participant roles</span></span>
    
- <span data-ttu-id="7eaeb-158">在會議中使用拖放功能、電話撥出或電子郵件，邀請其他參與者</span><span class="sxs-lookup"><span data-stu-id="7eaeb-158">Inviting additional participants during the meeting using drag and drop functionality, phone dial out, or email</span></span>
    
- <span data-ttu-id="7eaeb-159">物件或個別使用者的靜音和 unmuting</span><span class="sxs-lookup"><span data-stu-id="7eaeb-159">Muting and unmuting the audience or individual users</span></span>
    
- <span data-ttu-id="7eaeb-160">管理會議內容，包括上傳內容、刪除內容及切換活動內容</span><span class="sxs-lookup"><span data-stu-id="7eaeb-160">Managing meeting content, including uploading content, deleting content, and switching active content</span></span>

    
### <a name="maintain-a-separate-calendar"></a><span data-ttu-id="7eaeb-161">維護個別的行事曆</span><span class="sxs-lookup"><span data-stu-id="7eaeb-161">Maintain a separate calendar</span></span>

<span data-ttu-id="7eaeb-162">針對每個大型會議集區，您應該維護在該集區上排定的大型會議的個別行事曆。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-162">For each large-meeting pool, you should maintain a separate calendar of large meetings scheduled on that pool.</span></span> <span data-ttu-id="7eaeb-163">例如，您可以在大型會議集區上家用單一使用者帳戶，並使用 Outlook 搭配商務用 Skype 的 Exchange 和線上會議增益集來維護個別的行事曆。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-163">For example, you can home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype for Business to maintain a separate calendar.</span></span> <span data-ttu-id="7eaeb-164">如果您為了讓支援人員建立大型會議而使用多個使用者帳戶，您可以設定個別行事曆，彙整所有由支援人員所建立的大型會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-164">If you use multiple user accounts to enable a support staff to create large meetings, you can set up a separate calendar that aggregates all large meetings created by the members of the support staff.</span></span> 
  
<span data-ttu-id="7eaeb-165">維護個別的大型會議行事曆有助於防止衝突，並確保任何時候只有一場大型會議正在舉辦中。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-165">Maintaining a separate large meeting calendar helps to prevent conflicts and ensure that only one large meeting is active at any time.</span></span>
  
### <a name="implement-a-scheduling-process"></a><span data-ttu-id="7eaeb-166">執行排程過程</span><span class="sxs-lookup"><span data-stu-id="7eaeb-166">Implement a scheduling process</span></span>

<span data-ttu-id="7eaeb-167">因為在專屬的大型會議集區上一次只支援一個大型會議，所以您應該執行大型會議排程處理常式，以協助設定大型會議及協助避免衝突。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-167">Because only one large meeting at a time is supported on the dedicated large meeting pool, you should implement a large meeting scheduling process to facilitate setting up large meetings and help prevent conflicts.</span></span> <span data-ttu-id="7eaeb-168">商務用 Skype Server 或商務用 Skype 用戶端不會直接提供這類功能。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-168">Such capability is not provided directly by Skype for Business Server or Skype for Business clients.</span></span> <span data-ttu-id="7eaeb-169">實施這類程式的其中一個方法是使用貴組織的支援小組的票證系統（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-169">One way to implement such a process is to use your organization's support team's ticketing system, if available.</span></span>
  
<span data-ttu-id="7eaeb-170">排程大型會議時，需要完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-170">Scheduling a large meeting involves completing the following steps:</span></span>
  
- <span data-ttu-id="7eaeb-171">會議召集人或代理人會決定即將召開之會議的時間、工期和大小，以及簡報者清單。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-171">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="7eaeb-172">如果預期的會議大小超過250的使用者，或是為了確保會議的使用者體驗低於250的使用者，召集人或代理人會送出大型會議的要求。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-172">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>
    
- <span data-ttu-id="7eaeb-173">排程員工會檢查是否有可用的要求日期和時間。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-173">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="7eaeb-174">因為我們一次只支援專屬集區的單一大型會議，所以排程人員需要檢查大型會議行事曆，以判斷是否有針對要求的日期和時間排定的其他會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-174">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="7eaeb-175">如果有可用的要求時間，則人員會核准會議邀請。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-175">If the requested time is available, the staff approves the meeting request.</span></span>
    
- <span data-ttu-id="7eaeb-176">如果要求得到核准，排程人員 (使用專用集區上的認證) 使用 Outlook 的商務用 Skype 增益集，在專屬的大型會議集區上設定會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-176">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Skype for Business with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="7eaeb-177">加入會議時所使用的 URL 會提供給申請者，做為核准通知的一部分。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-177">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>
    
- <span data-ttu-id="7eaeb-178">會議召集人或代理人會使用 Outlook 來排程即將召開的會議，新增將會議加入會議邀請的 URL。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-178">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="7eaeb-179">會議召集人或代理人會指定要邀請的使用者，併發出會議邀請。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-179">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
### <a name="specify-appropriate-scheduling-details"></a><span data-ttu-id="7eaeb-180">指定適當的排程詳細資料</span><span class="sxs-lookup"><span data-stu-id="7eaeb-180">Specify appropriate scheduling details</span></span>

<span data-ttu-id="7eaeb-181">在檢查確認於要求的時間沒有排程其他會議之後，處理該要求的大型會議支援人員會在大型會議集區中排程會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-181">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> 
  
<span data-ttu-id="7eaeb-182">為了確保最佳的使用者體驗，請務必使用適合會議召集人需求的適當訪問層級和會議設定來排程大型會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-182">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer's needs.</span></span> <span data-ttu-id="7eaeb-183">請考慮下列設定在商務用 Skype Meeting 選項中的排程設定：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-183">Consider the following scheduling settings configured in Skype for Business Meeting options:</span></span>
  
- <span data-ttu-id="7eaeb-184">針對每場大型會議使用新的會議空間，而非重複使用專用會議空間。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-184">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span> 
    
- <span data-ttu-id="7eaeb-185">以下列方式指定會議存取層級：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-185">Specify the meeting access level as follows:</span></span>
    
  - <span data-ttu-id="7eaeb-186">如果組織外部至少有一個被邀請者，請將會議存取類型設定為 [ **任何人]， (沒有任何限制)**。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-186">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions)**.</span></span> <span data-ttu-id="7eaeb-187">這可避免您在會議進行中還需要管理或許擁擠的大廳。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-187">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
  - <span data-ttu-id="7eaeb-188">如果會議是純內部會議，則設定會議存取類型為 **[來自我組織的任何人]**。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-188">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7eaeb-189">避免設定會議存取類型為 **[我公司中受邀請的人員]**，因為使用此設定時，召集人必須將所有使用者電子郵件地址新增到受邀者清單中，而且無法邀請通訊群組。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-189">Avoid setting the meeting access type to **People I invite from my company** because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span> <span data-ttu-id="7eaeb-190">避免設定會議存取類型為 **[只限會議召集人自己]**，因為此設定需要每位會議參與者 (包括簡報者) 在會議舉行時間聚集在大廳。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-190">Avoid setting the meeting access type to **Only me, the meeting organizer** because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="7eaeb-191">負責舉行該場大型會議的人員就必須時時監控大廳名冊，准許在大廳的新使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-191">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>
  
- <span data-ttu-id="7eaeb-192">核取 **[來電者可直接加入]** 設定，允許以電話撥入的使用者自動加入會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-192">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>
    
- <span data-ttu-id="7eaeb-193">明確邀請下列使用者：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-193">Explicitly invite the following users:</span></span>
    
  - <span data-ttu-id="7eaeb-194">會議召集人及代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="7eaeb-194">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="7eaeb-195">會議要求者提供的簡報者清單</span><span class="sxs-lookup"><span data-stu-id="7eaeb-195">The list of presenters provided by a meeting requester</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7eaeb-196">如果會議存取類型設定為 **[我選擇的人員]**，則必須將大型會議中每位參與者明確新增為會議的受邀者。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-196">If the meeting access type is set to **People I choose**, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span> 
  
- <span data-ttu-id="7eaeb-p121">明確管理簡報者，而非將簡報者選項設定為其中一項自動升級值。務必將下列使用者新增為簡報者：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-p121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
  - <span data-ttu-id="7eaeb-199">會議召集人及代理人 (要求者)</span><span class="sxs-lookup"><span data-stu-id="7eaeb-199">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="7eaeb-200">大型會議要求者提供的簡報者清單</span><span class="sxs-lookup"><span data-stu-id="7eaeb-200">The list of presenters provided by large meeting requesters</span></span>
    
    <span data-ttu-id="7eaeb-201">透過明確管理簡報者，您可以將簡報者限制為小一些的小數位，使其可以有有效的大型會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-201">By explicitly managing presenters, you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="7eaeb-202">如果大多數的會議參與者為出席者角色，這有助於降低以下事件的發生機會：人員意外主導簡報、刪除 PowerPoint 簡報、將簡報者靜音/取消靜音，以及其他會議干擾。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-202">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span> 
    
- <span data-ttu-id="7eaeb-203">核取 **[將所有出席者設為靜音]** 設定，確保只有簡報者能在會議中廣播音訊。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-203">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>
    
- <span data-ttu-id="7eaeb-204">請檢查 [ **封鎖出席者的影片** ] 設定，確定只有簡報者可以將影片廣播到會議中。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-204">Check the **Block attendees' video** setting to make sure only presenters can broadcast video into the meeting.</span></span>
    
### <a name="create-a-conferencing-policy"></a><span data-ttu-id="7eaeb-205">建立會議原則</span><span class="sxs-lookup"><span data-stu-id="7eaeb-205">Create a conferencing policy</span></span>

<span data-ttu-id="7eaeb-206">專門針對大型會議建立新的會議原則，然後將會議原則指派給位於專屬大型會議集區上的使用者。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-206">Create a new conferencing policy specifically for large meetings, and then assign the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="7eaeb-207">使用下列設定來設定會議原則：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-207">Configure the conferencing policy using the following settings:</span></span>
  
- <span data-ttu-id="7eaeb-208">將 **MaxMeetingSize** 選項設定為1000。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-208">Set the **MaxMeetingSize** option to 1000.</span></span> <span data-ttu-id="7eaeb-209"> (預設值為250。 ) </span><span class="sxs-lookup"><span data-stu-id="7eaeb-209">(The default is 250.)</span></span>
    
- <span data-ttu-id="7eaeb-210">將 **AllowLargeMeetings** 選項設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-210">Set the **AllowLargeMeetings** option to **True**.</span></span> 
    
- <span data-ttu-id="7eaeb-211">將 **EnableAppDesktopSharing** 選項設定為 [ **無**]。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-211">Set the **EnableAppDesktopSharing** option to **None**.</span></span>
    
- <span data-ttu-id="7eaeb-212">將 **AllowUserToScheduleMeetingsWithAppSharing** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-212">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>
    
- <span data-ttu-id="7eaeb-213">將 **AllowSharedNotes** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-213">Set the **AllowSharedNotes** option to **False**.</span></span>
    
- <span data-ttu-id="7eaeb-214">將 **AllowAnnotations** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-214">Set the **AllowAnnotations** option to **False**.</span></span>
    
- <span data-ttu-id="7eaeb-215">將 **DisablePowerPointAnnotations** 選項設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-215">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>
    
- <span data-ttu-id="7eaeb-216">將 **AllowMultiview** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-216">Set the **AllowMultiview** option to **False**.</span></span>
    
- <span data-ttu-id="7eaeb-217">將 **EnableMultiviewJoin** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-217">Set the **EnableMultiviewJoin** option to **False**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7eaeb-218">支援商務用 Skype Server 中的大型會議，必須將 [ **AllowLargeMeetings** ] 設定設為 true。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-218">Support for large meetings in Skype for Business Server requires that the **AllowLargeMeetings** setting be set to true.</span></span> <span data-ttu-id="7eaeb-219">當此設定設為 true 時，當使用者加入會議時，商務用 Skype 體驗會針對特大會議進行優化。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-219">When this setting is set to true, the Skype for Business experience will be optimized for extra-large meetings when users join the meeting.</span></span> <span data-ttu-id="7eaeb-220">特別是在大型會議中，商務用 Skype 不會顯示完整會議參與者清單的初始或更新，也就是用戶端和商務用 Skype Server 的效能瓶頸。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-220">Specifically, in a large meeting, Skype for Business will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Skype for Business Server.</span></span> <span data-ttu-id="7eaeb-221">相反地，商務用 Skype 只會顯示使用者和會議簡報者清單的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-221">Instead, Skype for Business will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="7eaeb-222">商務用 Skype 仍會顯示在大型會議中可用的參與者人數總數。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-222">Skype for Business will still show the total number of participants available in the large meetings.</span></span>

<span data-ttu-id="7eaeb-223">**AllowLargeMeetings $true** 設定會導致下列專案：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-223">The **AllowLargeMeetings $true** setting causes the following:</span></span>

- <span data-ttu-id="7eaeb-224">隱藏出席者名單。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-224">Hides the Attendee roster.</span></span> 

- <span data-ttu-id="7eaeb-225">停用 IM 視窗中的錯誤。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-225">Disables errors in the IM window.</span></span>

- <span data-ttu-id="7eaeb-226">停用多方影片。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-226">Disables multi-party video.</span></span>

- <span data-ttu-id="7eaeb-227">停用將出席者提升為簡報者的能力。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-227">Disables ability to promote an Attendee to Presenter.</span></span> <span data-ttu-id="7eaeb-228">您必須事先規劃並宣告所有的簡報者，才能進行會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-228">You must plan ahead and declare all Presenters before the meeting.</span></span>

- <span data-ttu-id="7eaeb-229">停用靜音個別出席者的功能。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-229">Disables ability to unmute individual Attendees.</span></span>

- <span data-ttu-id="7eaeb-230">停用將鎖定影片聚焦功能套用至出席者的功能。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-230">Disables ability to apply the Lock Video Spotlight feature to Attendees.</span></span>

- <span data-ttu-id="7eaeb-231">PSTN 撥號使用者將無法使用6來取消靜音，因為個人虛擬協助（負責作用中大型會議的 DTMF 命令）缺失。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-231">PSTN dial in users will be unable to unmute themselves using 6 because Personal Virtual Assistance which is responsible for DTMF commands in active large meetings is missing.</span></span>

- <span data-ttu-id="7eaeb-232">如果簡報者/召集人排程會議，其中的所有人都應該先設為靜音狀態 ( "全部靜音" ) ，PSTN 使用者將會在整個呼叫中靜音，而且將無法自行取消靜音。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-232">If the presenter/organizer schedules a meeting where everyone should be muted first ("Mute All"), PSTN users will be muted throughout the call and will not be able to unmute themselves.</span></span>

<span data-ttu-id="7eaeb-233">除了 [ **最大會議大小** ] 設定之外，您還需要在這裡指定的所有其他會議原則設定，才能停用大型會議中不需要的會議功能。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-233">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>
  
<span data-ttu-id="7eaeb-234">此外，您還需要設定專門的大型會議集區，讓駐留在集區中的每個商務用 Skype Server 使用者擁有適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-234">Additionally, you need to configure the dedicated large-meeting pool so that each Skype for Business Server user who is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="7eaeb-235">若要這麼做，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7eaeb-235">To do this, do the following:</span></span>
  
- <span data-ttu-id="7eaeb-236">將 [ **指定為簡報者** ] 選項設定為 [ **無**]。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-236">Set the **Designate as presenter** option to **None**.</span></span> <span data-ttu-id="7eaeb-237">通常，一或多個大型會議參與者的使用者都是簡報者，所以不應該以簡報者的身分，將參與者自動承認為大型會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-237">Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters.</span></span> <span data-ttu-id="7eaeb-238">相反地，簡報者應明確指派會議排程時間，或是在大型會議期間明確升級。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-238">Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>
    
- <span data-ttu-id="7eaeb-239">請確定未選取 [ **依預設指派指派會議類型** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-239">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="7eaeb-240">此設定可控制商務用 Skype 的線上會議增益集是否一定要使用召集人指派的會議排定會議，這表示已排程的會議具有相同的加入 URL 和音訊資訊。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-240">This setting controls whether the Online Meeting Add-in for Skype for Business always schedules conferences using the organizer's assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="7eaeb-241">在小型群組共同作業案例中，有這種指派的會議類型可順利運作，因為每個人都有自己的指派會議，而常數加入 URL 和音訊資訊可協助協助加入更快速的會議。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-241">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="7eaeb-242">不過，在大型會議案例中，大型會議支援人員會使用一組使用者認證來安排大型會議，然後為會議申請者提供加入 URLs 和音訊資訊。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-242">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="7eaeb-243">在此情況下，使用不同的 URL 來加入每個會議可更好地運作。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-243">In this case, using a different URL to join each meeting works better.</span></span>
    
- <span data-ttu-id="7eaeb-244">除非有必要，否則請確定未選取 [ **預設會承認匿名使用者** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-244">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="7eaeb-245">此設定會影響未使用指派會議時，由商務用 Skype For Business 之線上會議增益集排程的預設會議存取類型。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-245">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Skype for Business when not using an assigned conference.</span></span> <span data-ttu-id="7eaeb-246">此設定的適當選項取決於組織的需求。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-246">The appropriate option for this setting depends on your organization's needs.</span></span> <span data-ttu-id="7eaeb-247">如果貴組織大多數的大型會議為內部會議，請勿選取此選項。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-247">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="7eaeb-248">如果大多數大型會議都要求外部使用者可以加入，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-248">If most large meetings require that external users be able to join, select this option.</span></span>
    
<span data-ttu-id="7eaeb-249">如需建立會議原則的詳細資訊，請參閱 [在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7eaeb-249">For more information about creating a conferencing policy, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  

