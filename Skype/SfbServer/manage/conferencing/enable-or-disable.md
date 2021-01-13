---
title: 啟用或停用商務用 Skype Server 中的電話撥入式會議
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 摘要：瞭解如何使用控制台或管理命令介面來啟用或停用商務用 Skype Server 中的電話撥入式會議。
ms.openlocfilehash: 99691540306ba0cccf9c63af2e2188e839367bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828123"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="75403-103">啟用或停用商務用 Skype Server 中的電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="75403-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="75403-104">**摘要：** 瞭解如何使用控制台或管理命令介面，在商務用 Skype Server 中啟用或停用電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="75403-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="75403-105">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來啟用電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="75403-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="75403-106">使用商務用 Skype Server 控制台來啟用或停用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="75403-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="75403-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="75403-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="75403-108">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="75403-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="75403-109">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="75403-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="75403-110">在會議原則清單中，選取要啟用電話撥入式會議的原則，然後按一下 **[編輯]**，再按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="75403-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="75403-p101">若要允許使用者藉由撥入電話來加入會議，請勾選 **[啟用 PSTN 電話撥入式會議]** 核取方塊。根據預設，使用者可以使用公用交換電話網路 (PSTN) 來撥入會議。</span><span class="sxs-lookup"><span data-stu-id="75403-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="75403-113">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="75403-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="75403-114">使用商務用 Skype Server 管理命令介面來啟用或停用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="75403-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="75403-115">若要啟用或停用電話撥入式會議，請使用具有 EnableDialInConferencing 參數的 **Set-CsConferencingPolicy** Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="75403-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="75403-116">如需詳細資訊，請參閱 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="75403-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

