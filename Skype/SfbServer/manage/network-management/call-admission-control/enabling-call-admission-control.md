---
title: 啟用通話許可控制
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
description: " 將通話許可控制設定 (CAC) 網路之後，您必須啟用 CAC 以強制執行頻寬限制。"
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816503"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="deea3-103">在商務用 Skype Server 中啟用通話許可控制</span><span class="sxs-lookup"><span data-stu-id="deea3-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="deea3-104">通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。</span><span class="sxs-lookup"><span data-stu-id="deea3-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="deea3-105">在您設定 CAC 網路之後，您必須啟用 CAC 以強制實施頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="deea3-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="deea3-106">您可以使用商務用 Skype Server 控制台執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="deea3-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="deea3-107">從商務用 Skype Server 控制台啟用 CAC</span><span class="sxs-lookup"><span data-stu-id="deea3-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="deea3-108">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="deea3-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="deea3-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="deea3-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="deea3-110">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **通用**]。</span><span class="sxs-lookup"><span data-stu-id="deea3-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="deea3-111">在 **[全域]** 頁面上，按一下 **[全域]** 設定。</span><span class="sxs-lookup"><span data-stu-id="deea3-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="deea3-112">只能為任何商務用 Skype Server 部署設定一個網路，所以清單中永遠不會有一個以上的網路設定。</span><span class="sxs-lookup"><span data-stu-id="deea3-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="deea3-113">您無法重新命名 [全域] 設定。</span><span class="sxs-lookup"><span data-stu-id="deea3-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="deea3-114">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="deea3-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="deea3-115">在 **[編輯通用設定]** 頁面上，選取 **[啟用通話許可控制]** 核取方塊，然後按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="deea3-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="deea3-p103">當您按一下 **[認可]** 時，便會執行設定的測試。**[編輯通用設定]** 對話方塊隨即關閉，您會回到 **[全域]** 頁面。如果在網路設定中發現任何會使網路無法正常運作 (例如，每個區域未透過區域間路由彼此連線) 的錯誤或不一致情形，您將會收到警告。</span><span class="sxs-lookup"><span data-stu-id="deea3-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="deea3-p104">如果您變更了網路設定，您可以開啟 [全域] 設定並按一下 **[認可]**，再次執行驗證檢查。您不需要先停用 CAC：使核取方塊保持已勾選狀態並按一下 **[認可]**。您可以隨時這麼做，而不需進行任何設定變更。</span><span class="sxs-lookup"><span data-stu-id="deea3-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="deea3-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="deea3-122">See Also</span></span>

[<span data-ttu-id="deea3-123">規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="deea3-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="deea3-124">設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="deea3-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="deea3-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="deea3-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="deea3-126">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="deea3-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="deea3-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="deea3-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
