---
title: 移動剩餘的使用者
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype Server 管理] 命令介面, 將使用者移至新的商務用 Skype Server 2019 部署。 您必須符合一些需求, 才能確保順利轉換至商務用 Skype Server 2019。 如需有關完成本主題中程式的先決條件的詳細資訊, 請參閱設定要遷移的用戶端。 如需有關移動使用者的詳細步驟, 請參閱階段 4: 將測試使用者移至試驗池。'
ms.openlocfilehash: 8c12ca52e162c4317dabc59d5de9b74082730882
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244783"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="62be3-106">將剩餘的使用者移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="62be3-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="62be3-107">您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype Server 管理] 命令介面, 將使用者移至新的商務用 Skype Server 2019 部署。</span><span class="sxs-lookup"><span data-stu-id="62be3-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="62be3-108">您必須符合一些需求, 才能確保順利轉換至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="62be3-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="62be3-109">如需有關完成本主題中程式的先決條件的詳細資訊, 請參閱[設定要遷移的用戶端](configure-clients-for-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="62be3-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="62be3-110">如需有關移動使用者的詳細步驟, 請參閱[階段 4: 將測試使用者移至試驗池](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="62be3-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="62be3-111">您無法使用 Active Directory 使用者和電腦管理單元或舊版管理工具, 將使用者從舊版環境移至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="62be3-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="62be3-112">當您將使用者移至商務用 Skype Server 2019 文件庫時, 該使用者的資料會移至與新的資料庫池相關聯的後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="62be3-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="62be3-113">這包括舊版使用者建立的作用中會議。</span><span class="sxs-lookup"><span data-stu-id="62be3-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="62be3-114">例如, 如果舊版使用者已設定「我的**會議**會議, 則在使用者移動之後, 新的商務用 Skype Server 2019 池中仍會提供該會議。</span><span class="sxs-lookup"><span data-stu-id="62be3-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="62be3-115">存取該會議的詳細資料仍會是相同的**會議 URL 與會議 ID**。</span><span class="sxs-lookup"><span data-stu-id="62be3-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="62be3-116">唯一的差異是, 會議現在是託管在商務用 Skype Server 2019 池中, 而不是在舊版池中。</span><span class="sxs-lookup"><span data-stu-id="62be3-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="62be3-117">在商務用 Skype Server 2019 上託管使用者, 不需要您同時部署已升級的用戶端。</span><span class="sxs-lookup"><span data-stu-id="62be3-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="62be3-118">只有在使用者升級至新的用戶端軟體時, 才能使用新的功能。</span><span class="sxs-lookup"><span data-stu-id="62be3-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="62be3-119">遷移後任務</span><span class="sxs-lookup"><span data-stu-id="62be3-119">Post migration task</span></span>

1. <span data-ttu-id="62be3-120">在您移動使用者之後, 請確認指派給他們的會議原則。</span><span class="sxs-lookup"><span data-stu-id="62be3-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="62be3-121">若要確保由2019駐留在舊版安裝中的使用者所組織的會議能與駐留在舊版安裝的聯盟使用者順暢運作, 指派給已遷移使用者的會議原則應該允許匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="62be3-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="62be3-122">允許匿名參與者的會議原則**允許參與者邀請**在商務用 Skype Server 2019 [控制台] 中選取匿名使用者, 並將**AllowAnonymousParticipantsInMeetings**設定為**True** (在從商務用 Skype Server Management Shell 中的**CsConferencingPolicy** Cmdlet 輸出。</span><span class="sxs-lookup"><span data-stu-id="62be3-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

