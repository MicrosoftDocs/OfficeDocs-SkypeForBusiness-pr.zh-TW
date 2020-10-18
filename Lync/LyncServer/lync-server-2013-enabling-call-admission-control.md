---
title: Lync Server 2013：啟用通話許可控制
description: Lync Server 2013：啟用通話許可控制。
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
ms.openlocfilehash: b2f5737f83a1965b920f2a23e1aabbbaec2af7b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572639"
---
# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="b65e3-103">在 Lync Server 2013 中啟用通話許可控制</span><span class="sxs-lookup"><span data-stu-id="b65e3-103">Enabling call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b65e3-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b65e3-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b65e3-105">通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。</span><span class="sxs-lookup"><span data-stu-id="b65e3-105">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="b65e3-106">在您設定 CAC 網路之後，您必須啟用 CAC 以強制實施頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="b65e3-106">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="b65e3-107">您可以使用 Lync Server 控制台執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="b65e3-107">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="b65e3-108">從 Lync Server 控制台啟用 CAC</span><span class="sxs-lookup"><span data-stu-id="b65e3-108">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b65e3-109">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b65e3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b65e3-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b65e3-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b65e3-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b65e3-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b65e3-112">在左導覽列中，按一下 **[網路設定]**，然後按一下 **[全域]**。</span><span class="sxs-lookup"><span data-stu-id="b65e3-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="b65e3-113">在 **[全域]** 頁面上，按一下 **[全域]** 設定。</span><span class="sxs-lookup"><span data-stu-id="b65e3-113">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b65e3-114">您只能為任何 Microsoft Lync Server 2013 部署設定一個網路，所以清單中永遠不會有一個以上的網路設定。</span><span class="sxs-lookup"><span data-stu-id="b65e3-114">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="b65e3-115">您無法重新命名 [全域] 設定。</span><span class="sxs-lookup"><span data-stu-id="b65e3-115">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="b65e3-116">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="b65e3-116">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="b65e3-117">在 **[編輯通用設定]** 頁面上，選取 **[啟用通話許可控制]** 核取方塊，然後按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b65e3-117">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="b65e3-p104">當您按一下 **[認可]** 時，便會執行設定的測試。**[編輯通用設定]** 對話方塊隨即關閉，您會回到 **[全域]** 頁面。如果在網路設定中發現任何會使網路無法正常運作 (例如，每個區域未透過區域間路由彼此連線) 的錯誤或不一致情形，您將會收到警告。</span><span class="sxs-lookup"><span data-stu-id="b65e3-p104">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="b65e3-p105">如果您變更了網路設定，您可以開啟 [全域] 設定並按一下 **[認可]**，再次執行驗證檢查。您不需要先停用 CAC：使核取方塊保持已勾選狀態並按一下 **[認可]**。您可以隨時這麼做，而不需進行任何設定變更。</span><span class="sxs-lookup"><span data-stu-id="b65e3-p105">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b65e3-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b65e3-124">See Also</span></span>


[<span data-ttu-id="b65e3-125">Lync Server 2013 中的通話許可控制概覽</span><span class="sxs-lookup"><span data-stu-id="b65e3-125">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="b65e3-126">在 Lync Server 2013 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="b65e3-126">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="b65e3-127">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="b65e3-127">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="b65e3-128">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b65e3-128">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="b65e3-129">CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b65e3-129">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="b65e3-130">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="b65e3-130">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

