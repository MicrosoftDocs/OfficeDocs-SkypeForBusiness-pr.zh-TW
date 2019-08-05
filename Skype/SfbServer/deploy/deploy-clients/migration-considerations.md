---
title: Skype 會議室系統的遷移考慮
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 請閱讀本主題, 瞭解如何在擁有多個版本商務用 Skype Server 和 Lync Server 的環境中部署 Skype 會議室系統。
ms.openlocfilehash: 35dd7cff34134791ebaf62bf4d0fcd1cf3b83a4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192494"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="aa328-103">Skype 會議室系統的遷移考慮</span><span class="sxs-lookup"><span data-stu-id="aa328-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="aa328-104">請閱讀本主題, 瞭解如何在擁有多個版本商務用 Skype Server 和 Lync Server 的環境中部署 Skype 會議室系統。</span><span class="sxs-lookup"><span data-stu-id="aa328-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="aa328-105">遷移考慮</span><span class="sxs-lookup"><span data-stu-id="aa328-105">Migration considerations</span></span>

<span data-ttu-id="aa328-106">如果您是在包含不同版本商務用 Skype Server 或 Lync Server 的多池環境中部署 Skype 會議室系統, 此區段會提供指導方針。</span><span class="sxs-lookup"><span data-stu-id="aa328-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="aa328-107">Lync Server 中的使用者複製程式 (UR) 元件會從 Active Directory 取得使用者物件, 並將它們放入 Lync Server 後端 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="aa328-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="aa328-108">只有 Lync Server 2013 中的 UR 可識別 Skype 室系統物件。</span><span class="sxs-lookup"><span data-stu-id="aa328-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="aa328-109">在舊版 Lync Server 和 Office 通訊伺服器的 UR 中, 不會偵測到指定 LRS 物件的 Active Directory 屬性, 因此無法辨識這些屬性。</span><span class="sxs-lookup"><span data-stu-id="aa328-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="aa328-110">如果 Skype 會議室系統帳戶嘗試登入 Lync, 並根據 SRV 記錄或 DNS A 記錄查詢來執行自動探索, 而如果這些帳戶指向舊版的 Lync Server 或 Office 通訊伺服器, LRS 將會收到404找不到的回應 舊版資源區。</span><span class="sxs-lookup"><span data-stu-id="aa328-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="aa328-111">舊版池將無法重新導向 Skype 會議室系統至其 Lync Server 2013 家用版池。</span><span class="sxs-lookup"><span data-stu-id="aa328-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="aa328-112">您可以使用下列選項來解決此問題:</span><span class="sxs-lookup"><span data-stu-id="aa328-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="aa328-113">將您的自動探索 SRV 記錄 (_sipinternaltls _tcp) 指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="aa328-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="aa328-114">如果第一個選項無法使用, 您必須手動設定 LRS, 並在 Skype 會議室系統主控台應用程式中直接設定, 以提供 Lync Server 2013 池位址。</span><span class="sxs-lookup"><span data-stu-id="aa328-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="aa328-115">如果您是在商業網路外部部署 Skype 室系統, 且已部署並設定 Lync Edge 伺服器以指向舊版池或控制器, 則需要副 Edge 伺服器網站, 該網站會指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="aa328-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="aa328-116">如需有關部署副 Edge 伺服器的詳細資訊, 請參閱 Edge 伺服器部署檔。</span><span class="sxs-lookup"><span data-stu-id="aa328-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="aa328-117">使用 Lync Server 2010 池的 Skype 會議室系統互通性</span><span class="sxs-lookup"><span data-stu-id="aa328-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="aa328-118">在遷移期間, 如果駐留在 Lync Server 2010 擁有者的使用者排程會議並邀請 Skype 室系統帳戶, Skype 聊天室系統用戶端在參加會議時將擁有有限的功能。</span><span class="sxs-lookup"><span data-stu-id="aa328-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="aa328-119">當 Skype 會議室系統用戶端加入由駐留在 Lync Server 2010 的使用者所組織的排程會議通話時, Skype 室系統具有下列會議限制:</span><span class="sxs-lookup"><span data-stu-id="aa328-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="aa328-120">Skype 室系統無法顯示多重查看影片庫。</span><span class="sxs-lookup"><span data-stu-id="aa328-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="aa328-121">如果您是簡報者的 Skype 會議室系統用戶端, 則無法在參與者上套用視頻鎖。</span><span class="sxs-lookup"><span data-stu-id="aa328-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="aa328-122">Skype 室系統無法顯示1080p 影片解析度 (入站或出站), 即使 Lync Server 2013 會議原則允許, 還是由於下列原因所示:</span><span class="sxs-lookup"><span data-stu-id="aa328-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="aa328-123">Lync Server 2010 不支援1080p 解析度。</span><span class="sxs-lookup"><span data-stu-id="aa328-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="aa328-124">Skype 室系統永遠受到召集人的影片解析度之會議原則的限制。</span><span class="sxs-lookup"><span data-stu-id="aa328-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="aa328-125">因此, 即使 Lync 2010 池支援720p 解析度, 只要召集人原則不支援 720p, Skype 室系統就無法利用720p 解析度。</span><span class="sxs-lookup"><span data-stu-id="aa328-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="aa328-126">Lync 2013 用戶端偵測會議室中的 LRS 目前狀態, 並自動將自己設為靜音, 以避免實體會議室中的回音。</span><span class="sxs-lookup"><span data-stu-id="aa328-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="aa328-127">此功能不適用於 Lync Server 2010 上託管的會議。</span><span class="sxs-lookup"><span data-stu-id="aa328-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="aa328-128">在 Lync Server 2010 上託管的會議的桌面共用效能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="aa328-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="aa328-129">使用者將無法加入在 Lync 2010 上託管的私人 (受限制) 會議與 Skype 會議室系統。</span><span class="sxs-lookup"><span data-stu-id="aa328-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

