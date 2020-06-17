---
title: 確認已完成使用者複製
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 執行 Move-CsUser Cmdlet 時，可能會發生失敗，因為 Active Directory 網域服務（AD DS）和商務用 Skype Server 2019 資料庫之間的使用者資訊因初始複寫不完整而不同步。 成功完成商務用 Skype Server 2019 User 複寫器服務的初始同步處理所需的時間，取決於主控商務用 Skype Server 2019 集區之 Active Directory 樹系中主控的網域控制站數目。 當商務用 skype Server 2019 前端伺服器第一次啟動時，就會發生商務用 Skype Server 2019 使用者複寫器服務初始同步處理常式。 完成後，則是根據使用者複寫器間隔來進行同步化。 在執行 Move-CsUser Cmdlet 之前，請完成下列步驟來確認已完成使用者複寫。
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751645"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="ed2f4-107">確認已完成使用者複製</span><span class="sxs-lookup"><span data-stu-id="ed2f4-107">Verify user replication has completed</span></span>

<span data-ttu-id="ed2f4-108">執行**Move-CsUser**指令程式時，如果 Active Directory 網域服務（AD DS）和商務用 Skype Server 2019 資料庫之間的使用者資訊因初始複寫不完整而不同步，您可能會遇到失敗。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="ed2f4-109">成功完成商務用 Skype Server 2019 User 複寫器服務的初始同步處理所需的時間，取決於主控商務用 Skype Server 2019 集區之 Active Directory 樹系中主控的網域控制站數目。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ed2f4-110">當商務用 skype Server 2019 前端伺服器第一次啟動時，就會發生商務用 Skype Server 2019 使用者複寫器服務初始同步處理常式。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="ed2f4-111">之後，同步處理是以使用者複製器間隔為基礎。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="ed2f4-112">完成下列步驟，以確認使用者複寫已完成，再執行**Move-CsUser** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="ed2f4-113">確認使用者複寫已完成</span><span class="sxs-lookup"><span data-stu-id="ed2f4-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="ed2f4-114">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="ed2f4-115">按一下 [開始]\*\*\*\* 功能表，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="ed2f4-116">輸入 **eventvwr.exe**，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="ed2f4-117">在事件檢視器中，按一下 [**應用程式及服務記錄**檔] 加以展開，然後選取 [商務用 Skype 伺服器]。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="ed2f4-118">在 [動作]\*\*\*\* 窗格中，按一下 [篩選目前的記錄]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="ed2f4-119">在 [事件來源]\*\*\*\* 清單中，按一下 [LS 使用者複寫器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="ed2f4-120">在中 **\<All Event IDs\>** ，輸入**30024**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="ed2f4-121">在 [篩選的事件] 清單中的 [**一般**] 索引標籤上，尋找表明使用者複寫順利完成的專案。</span><span class="sxs-lookup"><span data-stu-id="ed2f4-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

