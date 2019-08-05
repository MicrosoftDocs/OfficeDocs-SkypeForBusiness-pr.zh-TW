---
title: 在商務用 Skype Server 中啟用或停用電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '摘要: 瞭解如何使用 [控制台] 或 [管理命令介面] 來啟用或停用商務用 Skype Server 中的電話撥入式會議。'
ms.openlocfilehash: 6723c3501b226d11977ad176a804210540f1a2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192578"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="095a9-103">在商務用 Skype Server 中啟用或停用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="095a9-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="095a9-104">**摘要:** 瞭解如何使用 [控制台] 或 [管理命令介面] 來啟用或停用商務用 Skype Server 中的電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="095a9-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="095a9-105">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面來啟用電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="095a9-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="095a9-106">使用商務用 Skype Server 的 [控制台] 來啟用或停用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="095a9-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="095a9-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="095a9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="095a9-108">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="095a9-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="095a9-109">在左側導覽列中, 按一下 [**會議**], 然後按一下 [**會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="095a9-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="095a9-110">在會議原則清單中, 選取您要啟用電話撥入式會議的原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="095a9-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="095a9-111">若要允許使用者透過撥入方式加入會議, 請核取 [**啟用 PSTN 電話撥入式會議**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="095a9-111">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="095a9-112">根據預設, 使用者可以使用公開交換電話網絡 (PSTN) 撥入會議。</span><span class="sxs-lookup"><span data-stu-id="095a9-112">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="095a9-113">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="095a9-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="095a9-114">使用商務用 Skype Server Management Shell 來啟用或停用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="095a9-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="095a9-115">若要啟用或停用電話撥入式會議, 請使用**CsConferencingPolicy** Cmdlet 及 EnableDialInConferencing 參數, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="095a9-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="095a9-116">如需詳細資訊, 請參閱[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="095a9-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

