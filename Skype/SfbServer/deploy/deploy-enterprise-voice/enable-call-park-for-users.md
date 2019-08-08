---
title: 在商務用 Skype 中啟用電話寄存給使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 在商務用 Skype Server Enterprise Voice 中, 允許通話駐留的使用者使用。
ms.openlocfilehash: 797b17cb3d9482d9059bedcbbc347c3dd592e478
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240636"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="35df2-103">在商務用 Skype 中啟用電話寄存給使用者</span><span class="sxs-lookup"><span data-stu-id="35df2-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="35df2-104">在商務用 Skype Server Enterprise Voice 中, 允許通話駐留的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="35df2-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="35df2-105">根據預設, 會停用所有使用者的 [通話駐留]。</span><span class="sxs-lookup"><span data-stu-id="35df2-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="35df2-106">使用者在語音原則中啟用通話駐留前, 不能寄存通話或取得停用通話。</span><span class="sxs-lookup"><span data-stu-id="35df2-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="35df2-107">您可以在全域範圍或在網站範圍或使用者範圍中啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="35df2-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="35df2-108">[使用者範圍] 的優先順序高於 [網站範圍], 而 [網站範圍] 的優先順序高於 [全域範圍]。</span><span class="sxs-lookup"><span data-stu-id="35df2-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="35df2-109">如果您有多個語音原則, 請查看所有原則來啟用通話駐留, 而不只是全域原則。</span><span class="sxs-lookup"><span data-stu-id="35df2-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="35df2-110">若要使用商務用 Skype Server 的 [控制台] 來為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="35df2-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="35df2-111">以**RTCUniversalServerAdmins**群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="35df2-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="35df2-112">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="35df2-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="35df2-113">在左側導覽列中, 按一下 [**語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="35df2-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="35df2-114">按一下 [**語音原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="35df2-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="35df2-115">按兩下現有的語音原則, 以開啟 [**編輯語音原則**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="35df2-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="35df2-116">在 [**呼叫功能**] 底下, 選取 [**啟用通話駐留**]。</span><span class="sxs-lookup"><span data-stu-id="35df2-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="35df2-117">按一下 **[確定]** 儲存語音原則</span><span class="sxs-lookup"><span data-stu-id="35df2-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="35df2-118">若要使用 Cmdlet 來為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="35df2-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="35df2-119">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 系統管理角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="35df2-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="35df2-120">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="35df2-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="35df2-121">用盡</span><span class="sxs-lookup"><span data-stu-id="35df2-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="35df2-122">例如, 若要針對預設的全域語音原則啟用通話駐留, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="35df2-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="35df2-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="35df2-123">See also</span></span>



[<span data-ttu-id="35df2-124">在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="35df2-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

