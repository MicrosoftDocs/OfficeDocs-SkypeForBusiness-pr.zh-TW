---
title: 為商務用 Skype 中的使用者啟用通話駐留
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 在商務用 Skype Server Enterprise Voice 中為使用者啟用通話駐留功能。
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830953"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="9e918-103">為商務用 Skype 中的使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="9e918-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="9e918-104">在商務用 Skype Server Enterprise Voice 中為使用者啟用通話駐留功能。</span><span class="sxs-lookup"><span data-stu-id="9e918-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9e918-105">預設會停用所有使用者的通話駐留。</span><span class="sxs-lookup"><span data-stu-id="9e918-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="9e918-106">使用者在語音原則中為通話駐留啟用電話時，無法寄存通話或取得寄存的通話。</span><span class="sxs-lookup"><span data-stu-id="9e918-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="9e918-107">您可以在全域範圍或網站範圍或使用者範圍上啟用通話駐留。</span><span class="sxs-lookup"><span data-stu-id="9e918-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="9e918-108">使用者範圍優先于網站範圍，而網站範圍優先于全域範圍。</span><span class="sxs-lookup"><span data-stu-id="9e918-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="9e918-109">如果您有多個語音原則，請複習所有原則以啟用通話駐留，而不只是全域原則。</span><span class="sxs-lookup"><span data-stu-id="9e918-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="9e918-110">使用商務用 Skype Server 控制台為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="9e918-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="9e918-111">以 **RTCUniversalServerAdmins** 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="9e918-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="9e918-112">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="9e918-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9e918-113">在左導覽列中，按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="9e918-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="9e918-114">按一下 [ **語音原則** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9e918-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="9e918-115">按兩下現有的語音原則，以開啟 [ **編輯語音原則** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="9e918-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="9e918-116">在 [ **通話功能**] 底下，選取 [ **啟用通話駐留**]。</span><span class="sxs-lookup"><span data-stu-id="9e918-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="9e918-117">按一下 **[確定]** 以儲存語音原則</span><span class="sxs-lookup"><span data-stu-id="9e918-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="9e918-118">若要使用 Cmdlet 為使用者啟用通話駐留</span><span class="sxs-lookup"><span data-stu-id="9e918-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="9e918-119">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 系統管理角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="9e918-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="9e918-120">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="9e918-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9e918-121">運行：</span><span class="sxs-lookup"><span data-stu-id="9e918-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="9e918-122">例如，若要啟用預設全域語音原則的通話駐留：</span><span class="sxs-lookup"><span data-stu-id="9e918-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="9e918-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9e918-123">See also</span></span>



[<span data-ttu-id="9e918-124">在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="9e918-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

