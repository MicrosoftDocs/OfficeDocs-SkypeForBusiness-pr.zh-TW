---
title: 在商務用 Skype Server 中啟用呼叫許可控制
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 在商務用 Skype Server Enterprise Voice 中啟用 [通話許可控制]。
ms.openlocfilehash: a1a2259c754af0275e473e6c0d175039450cecf7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240681"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="02e0d-103">在商務用 Skype Server 中啟用呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="02e0d-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="02e0d-104">在商務用 Skype Server Enterprise Voice 中啟用 [通話許可控制]。</span><span class="sxs-lookup"><span data-stu-id="02e0d-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="02e0d-105">在您設定 [通話許可控制] 部署的網路設定之後, 您必須啟用 CAC, 才能使您的頻寬原則生效。</span><span class="sxs-lookup"><span data-stu-id="02e0d-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="02e0d-106">使用商務用 Skype Server Management 命令介面啟用呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="02e0d-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="02e0d-107">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="02e0d-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="02e0d-108">執行 CsNetworkConfiguration Cmdlet 以在您的網路中啟用 CAC。</span><span class="sxs-lookup"><span data-stu-id="02e0d-108">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network.</span></span> <span data-ttu-id="02e0d-109">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="02e0d-109">For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="02e0d-110">如果您想要在網路中停用 CAC, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="02e0d-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="02e0d-111">使用商務用 Skype Server [控制台] 啟用呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="02e0d-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="02e0d-112">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="02e0d-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="02e0d-113">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="02e0d-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="02e0d-114">按一下 [**全域**導覽] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="02e0d-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="02e0d-115">按一下清單中的 [**全域**], 然後選取 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="02e0d-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="02e0d-116">在 [**編輯全域設定**] 頁面上, 選取 [**啟用通話許可控制**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="02e0d-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="02e0d-117">如果您想要在整個部署中停用 [呼叫許可控制], 請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="02e0d-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="02e0d-118">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02e0d-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="02e0d-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="02e0d-119">See also</span></span>

[<span data-ttu-id="02e0d-120">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="02e0d-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="02e0d-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="02e0d-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="02e0d-122">移除-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="02e0d-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
