---
title: 啟用商務用 Skype Server 中的通話許可控制
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 在商務用 Skype Server Enterprise Voice 中啟用通話許可控制。
ms.openlocfilehash: 9ea8b03b48827abbb73e3d6e93ffb88ab93ad1ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831013"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="a8def-103">啟用商務用 Skype Server 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="a8def-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="a8def-104">在商務用 Skype Server Enterprise Voice 中啟用通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="a8def-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="a8def-105">在設定通話許可控制部署的網路設定後，必須啟用 CAC，您的頻寬原則才能生效。</span><span class="sxs-lookup"><span data-stu-id="a8def-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a8def-106">使用商務用 Skype Server 管理命令介面來啟用通話許可控制</span><span class="sxs-lookup"><span data-stu-id="a8def-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a8def-107">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="a8def-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a8def-p101">執行 Set-CsNetworkConfiguration Cmdlet 以在您的網路中啟用 CAC。例如，執行：</span><span class="sxs-lookup"><span data-stu-id="a8def-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="a8def-110">如果您要在網路中停用 CAC，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a8def-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a8def-111">使用商務用 Skype Server 控制台啟用通話許可控制</span><span class="sxs-lookup"><span data-stu-id="a8def-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a8def-112">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a8def-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="a8def-113">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="a8def-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="a8def-114">按一下 **[通用]** 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="a8def-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="a8def-115">按一下清單中的 **[通用]**，然後選取 **[編輯]** 功能表上的 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="a8def-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="a8def-116">在 **[編輯通用設定]** 頁面上，選取 **[啟用通話許可控制台]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a8def-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a8def-117">如果您要在整個部署中停用通話許可控制，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a8def-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="a8def-118">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="a8def-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="a8def-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a8def-119">See also</span></span>

[<span data-ttu-id="a8def-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8def-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="a8def-121">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8def-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="a8def-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8def-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
