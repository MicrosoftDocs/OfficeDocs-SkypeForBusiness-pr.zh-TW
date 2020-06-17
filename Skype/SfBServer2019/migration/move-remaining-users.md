---
title: 移動剩餘的使用者
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
description: 您可以使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面，將使用者移至新的商務用 Skype Server 2019 部署。 您必須符合某些需求，以確保順利轉換為商務用 Skype Server 2019。 如需完成本主題中程式之必要條件的詳細資訊，請參閱設定用戶端進行遷移。 如需移動使用者的詳細步驟，請參閱第4階段：將測試使用者移至試驗集區。
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753711"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="015cf-106">將剩餘的使用者移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="015cf-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="015cf-107">您可以使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面，將使用者移至新的商務用 Skype Server 2019 部署。</span><span class="sxs-lookup"><span data-stu-id="015cf-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="015cf-108">您必須符合某些需求，以確保順利轉換為商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="015cf-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="015cf-109">如需完成本主題中程式之必要條件的詳細資訊，請參閱[設定用戶端進行遷移](configure-clients-for-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="015cf-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="015cf-110">如需移動使用者的詳細步驟，請參閱[第4階段：將測試使用者移至試驗集](phase-4-move-test-users-to-the-pilot-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="015cf-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="015cf-111">您無法使用 Active Directory 使用者及電腦嵌入式管理單元或舊版系統管理工具，將使用者從舊版環境移至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="015cf-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="015cf-112">當您將使用者移至商務用 Skype Server 2019 集區時，使用者的資料會移至與新集區相關聯的後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="015cf-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="015cf-113">這包括由舊使用者所建立之作用中的會議。</span><span class="sxs-lookup"><span data-stu-id="015cf-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="015cf-114">例如，如果舊版使用者已設定「我的**會議**會議」，該會議在使用者移動之後仍會在新的商務用 Skype Server 2019 集區中提供。</span><span class="sxs-lookup"><span data-stu-id="015cf-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="015cf-115">存取該會議的詳細資料仍為相同的 **[會議 URL 及會議 ID]**。</span><span class="sxs-lookup"><span data-stu-id="015cf-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="015cf-116">唯一不同之處在于，會議現在是在商務用 Skype Server 2019 集區，而不是在舊版集區中主控。</span><span class="sxs-lookup"><span data-stu-id="015cf-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="015cf-117">在商務用 Skype Server 2019 上的使用者，不需要同時部署已升級的用戶端。</span><span class="sxs-lookup"><span data-stu-id="015cf-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="015cf-118">只有當使用者已升級為新的用戶端軟體時，才可使用新功能。</span><span class="sxs-lookup"><span data-stu-id="015cf-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="015cf-119">遷移後工作</span><span class="sxs-lookup"><span data-stu-id="015cf-119">Post migration task</span></span>

1. <span data-ttu-id="015cf-120">一旦移除使用者之後，請驗證指派給他們的會議原則。</span><span class="sxs-lookup"><span data-stu-id="015cf-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="015cf-121">為了確保由位於商務用 Skype Server 2019 的使用者所組織的會議可與以舊版安裝的同盟使用者順利運作，指派給已遷移使用者的會議原則應該允許匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="015cf-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="015cf-122">允許匿名參與者的會議原則**可讓參與者邀請**商務用 skype Server 2019 控制台中所選取的匿名使用者，而且**AllowAnonymousParticipantsInMeetings**在商務用 skype server 管理命令介面中從**Get-CsConferencingPolicy**指令程式的輸出中，設定為**True** 。</span><span class="sxs-lookup"><span data-stu-id="015cf-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

