---
title: 啟用呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " 在您設定 [呼叫許可控制 (CAC)] 網路之後, 您必須啟用 CAC 來強制執行頻寬限制。"
ms.openlocfilehash: cbe3ad690f7061611a91474ce6df1fe39d84b0fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188587"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="c948e-103">在商務用 Skype Server 中啟用呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="c948e-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="c948e-104">通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。</span><span class="sxs-lookup"><span data-stu-id="c948e-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="c948e-105">在您設定 CAC 網路之後, 您必須啟用 CAC 來強制執行頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="c948e-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="c948e-106">您可以使用商務用 Skype Server 的 [控制台] 來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="c948e-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="c948e-107">若要從商務用 Skype Server 的 [控制台] 啟用 CAC</span><span class="sxs-lookup"><span data-stu-id="c948e-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c948e-108">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c948e-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c948e-109">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c948e-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c948e-110">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**全域**]。</span><span class="sxs-lookup"><span data-stu-id="c948e-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="c948e-111">在 [**全域**] 頁面上, 按一下 [**全域**配置]。</span><span class="sxs-lookup"><span data-stu-id="c948e-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="c948e-112">您只能針對任何商務用 Skype Server 部署設定一個網路, 因此清單中永遠不會有一個以上的網路設定。</span><span class="sxs-lookup"><span data-stu-id="c948e-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="c948e-113">您無法重新命名全域配置。</span><span class="sxs-lookup"><span data-stu-id="c948e-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="c948e-114">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="c948e-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c948e-115">在 [**編輯全域設定**] 頁面上, 選取 [**啟用通話許可控制**] 核取方塊, 然後按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="c948e-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="c948e-116">當您按一下 [**提交**] 時, 就會執行設定測試。</span><span class="sxs-lookup"><span data-stu-id="c948e-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="c948e-117">[**編輯全域設定**] 對話方塊隨即關閉, 並返回 [**全域**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c948e-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="c948e-118">如果您的網路設定中發現任何錯誤或不一致, 都將會收到警告, 避免它無法正常運作 (例如, 如果每個地區都未透過 interregion 路線連線到其他所有區域)。</span><span class="sxs-lookup"><span data-stu-id="c948e-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="c948e-119">如果您對網路設定進行變更, 您可以開啟 [全域設定] 並按一下 [ **Commit**], 再次執行驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="c948e-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="c948e-120">您不需要先停用 CAC, 請選取核取方塊, 然後按一下 [ **Commit**] (確認)。</span><span class="sxs-lookup"><span data-stu-id="c948e-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="c948e-121">您可以隨時執行此動作, 而不需變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="c948e-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="c948e-122">請參閱</span><span class="sxs-lookup"><span data-stu-id="c948e-122">See Also</span></span>

[<span data-ttu-id="c948e-123">規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="c948e-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="c948e-124">設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="c948e-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="c948e-125">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="c948e-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="c948e-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="c948e-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="c948e-127">移除-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="c948e-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
