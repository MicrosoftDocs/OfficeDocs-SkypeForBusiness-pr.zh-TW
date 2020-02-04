---
title: Lync Server 2013：啟用呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89c9b888dc610d60b2abbcefd4c9c67e9b0572e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="3f2a4-102">在 Lync Server 2013 中啟用呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="3f2a4-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f2a4-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3f2a4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3f2a4-104">通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="3f2a4-105">在您設定 CAC 網路之後，您必須啟用 CAC 來強制執行頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="3f2a4-106">您可以使用 Lync Server [控制台] 來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="3f2a4-107">從 Lync Server [控制台] 啟用 CAC</span><span class="sxs-lookup"><span data-stu-id="3f2a4-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3f2a4-108">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3f2a4-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3f2a4-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3f2a4-111">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**全域**]。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="3f2a4-112">在 [**全域**] 頁面上，按一下 [**全域**配置]。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f2a4-113">您只能針對任何 Microsoft Lync Server 2013 部署設定一個網路，因此清單中永遠不會有一個以上的網路設定。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="3f2a4-114">您無法重新命名全域配置。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="3f2a4-115">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3f2a4-116">在 [**編輯全域設定**] 頁面上，選取 [**啟用通話許可控制**] 核取方塊，然後按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="3f2a4-117">當您按一下 [**提交**] 時，就會執行設定測試。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-117">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="3f2a4-118">[**編輯全域設定**] 對話方塊隨即關閉，並返回 [**全域**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-118">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="3f2a4-119">如果您的網路設定中發現任何錯誤或不一致，都將會收到警告，避免它無法正常運作（例如，如果每個地區都未透過 interregion 路線連線到其他所有區域）。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-119">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="3f2a4-120">如果您對網路設定進行變更，您可以開啟 [全域設定] 並按一下 [ **Commit**]，再次執行驗證檢查。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-120">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="3f2a4-121">您不需要先停用 CAC，請選取核取方塊，然後按一下 [ **Commit**] （確認）。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-121">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="3f2a4-122">您可以隨時執行此動作，而不需變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="3f2a4-122">You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3f2a4-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="3f2a4-123">See Also</span></span>


[<span data-ttu-id="3f2a4-124">Lync Server 2013 中的通話許可控制概覽</span><span class="sxs-lookup"><span data-stu-id="3f2a4-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="3f2a4-125">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="3f2a4-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="3f2a4-126">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="3f2a4-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="3f2a4-127">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f2a4-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="3f2a4-128">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f2a4-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="3f2a4-129">移除-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="3f2a4-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

