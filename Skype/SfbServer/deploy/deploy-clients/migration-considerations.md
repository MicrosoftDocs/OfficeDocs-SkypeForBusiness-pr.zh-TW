---
title: Skype 室系統移轉考慮
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 閱讀此主題以瞭解如何在具有多個版本的商務用 Skype Server 和 Lync Server 的環境中部署 Skype 會議室系統。
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805783"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="74f33-103">Skype 室系統移轉考慮</span><span class="sxs-lookup"><span data-stu-id="74f33-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="74f33-104">閱讀此主題以瞭解如何在具有多個版本的商務用 Skype Server 和 Lync Server 的環境中部署 Skype 會議室系統。</span><span class="sxs-lookup"><span data-stu-id="74f33-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="74f33-105">移轉考量</span><span class="sxs-lookup"><span data-stu-id="74f33-105">Migration considerations</span></span>

<span data-ttu-id="74f33-106">如果您要在包含不同版本的商務用 Skype Server 或 Lync Server 的多集區環境中部署 Skype 室系統，則本節提供指導方針。</span><span class="sxs-lookup"><span data-stu-id="74f33-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="74f33-107">Lync Server 中的使用者複寫器 (UR) 元件會從 Active Directory 取得使用者物件，並將它們放入 Lync Server 後端 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="74f33-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="74f33-108">只有 Lync Server 2013 中的 UR 知道 Skype 室系統物件。</span><span class="sxs-lookup"><span data-stu-id="74f33-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="74f33-109">舊版 Lync Server 和 Office 通訊伺服器的 UR 未偵測到指定 LRS 物件的 Active Directory 屬性，因此不會察覺到這些屬性。</span><span class="sxs-lookup"><span data-stu-id="74f33-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="74f33-110">如果 Skype 會議室系統帳戶嘗試登入 Lync，並根據 SRV 記錄或 DNS A 記錄的查詢來執行自動探索，而且如果這些帳戶指向舊版的 Lync Server 或 Office 通訊伺服器，則 LRS 將會從舊版集區接收未找到404的回應。</span><span class="sxs-lookup"><span data-stu-id="74f33-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="74f33-111">舊版集區將無法將 Skype 聊天室系統重新導向至其 Lync Server 2013 主集區。</span><span class="sxs-lookup"><span data-stu-id="74f33-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="74f33-112">您可以使用下列選項來解決此問題：</span><span class="sxs-lookup"><span data-stu-id="74f33-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="74f33-113">將您的自動探索 SRV 記錄指向 Lync Server 2013 集區 (_sipinternaltls ._tcp .com) 。</span><span class="sxs-lookup"><span data-stu-id="74f33-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="74f33-114">如果無法使用第一個選項，您必須手動設定 LRS，並在 Skype 會議室系統主控台應用程式中直接設定，以提供 Lync Server 2013 集區位址。</span><span class="sxs-lookup"><span data-stu-id="74f33-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="74f33-115">如果已在公司網路外部部署 Skype 會議室系統，且已部署並設定 Lync Edge Server 以指向舊版集區或 director，則需要次要 Edge Server 網站，它會指向 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="74f33-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="74f33-116">如需部署次要 Edge Server 的詳細資訊，請參閱 Edge Server 部署檔。</span><span class="sxs-lookup"><span data-stu-id="74f33-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="74f33-117">Lync Server 2010 集區的 Skype 聊天室系統互通性</span><span class="sxs-lookup"><span data-stu-id="74f33-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="74f33-118">在遷移期間，如果駐留在 Lync Server 2010 集區上的使用者排程會議並邀請 Skype 聊天室系統帳戶，則 Skype 會議室系統用戶端在出席會議時將具有有限的功能。</span><span class="sxs-lookup"><span data-stu-id="74f33-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="74f33-119">當 Skype 會議室系統用戶端加入已由位於 Lync Server 2010 之使用者所組織的排程會議呼叫時，Skype 會議室系統會有下列會議限制：</span><span class="sxs-lookup"><span data-stu-id="74f33-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="74f33-120">Skype 室系統無法顯示多視圖影片庫。</span><span class="sxs-lookup"><span data-stu-id="74f33-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="74f33-121">如果 Skype 室系統用戶端是簡報者，它無法在參與者上套用影片鎖定。</span><span class="sxs-lookup"><span data-stu-id="74f33-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="74f33-122">由於下列原因，Skype 會議室系統無法將1080p 影片解析度顯示 (輸入或輸出) ，即使 Lync Server 2013 會議原則允許它，也是如此：</span><span class="sxs-lookup"><span data-stu-id="74f33-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="74f33-123">Lync Server 2010 不支援1080p 解析度。</span><span class="sxs-lookup"><span data-stu-id="74f33-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="74f33-124">Skype 室系統一定會受限於影片解析度的召集人會議原則。</span><span class="sxs-lookup"><span data-stu-id="74f33-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="74f33-125">因此，即使 Lync 2010 集區支援720p 解析度，當召集人的原則不支援時，Skype 會議室系統將無法利用720p 解析度。</span><span class="sxs-lookup"><span data-stu-id="74f33-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="74f33-126">Lync 2013 用戶端偵測會議會議室中的 LRS 目前狀態，並自動將其靜音以避免實體會議會議室中的回聲。</span><span class="sxs-lookup"><span data-stu-id="74f33-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="74f33-127">這項功能無法在 Lync Server 2010 上主控的會議中運作。</span><span class="sxs-lookup"><span data-stu-id="74f33-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="74f33-128">在 Lync Server 2010 上主控會議的桌面共用效能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="74f33-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="74f33-129">使用者將無法使用具有 Skype 會議室系統的 Lync 2010 主控私人 (限制) 會議。</span><span class="sxs-lookup"><span data-stu-id="74f33-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

