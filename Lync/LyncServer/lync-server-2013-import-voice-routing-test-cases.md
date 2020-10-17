---
title: Lync Server 2013：匯入語音路由測試案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8de7d29638a7d4a4ef8e480f85c0a310272f2863
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526690"
---
# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="652c3-102">在 Lync Server 2013 中匯入語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="652c3-102">Import voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="652c3-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="652c3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="652c3-104">測試案例為您提供測試組織中語音路由的方法：您可以定義要撥打的號碼，以及要採用的撥號對應表和語音原則等事項，而且 Lync Server 2013 可以確認是否已提供的號碼可成功路由傳送至 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="652c3-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="652c3-105">您可以使用 Lync Server 控制台建立的測試案例通常只會儲存在先前建立及執行案例的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="652c3-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="652c3-106">不過，這些測試案例可以用 XML 檔案 (副檔名為 .vtest) 的形式匯出，然後匯入到其他伺服器上。</span><span class="sxs-lookup"><span data-stu-id="652c3-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="652c3-107">這讓您可以在位於拓撲中不同點之不同電腦上執行相同的測試。</span><span class="sxs-lookup"><span data-stu-id="652c3-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="652c3-108">匯入語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="652c3-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="652c3-109">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="652c3-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="652c3-110">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="652c3-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="652c3-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="652c3-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="652c3-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="652c3-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="652c3-113">在左導覽列中，按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="652c3-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="652c3-114">在 **[執行]** 功能表上，按一下 **[匯入測試案例]**。</span><span class="sxs-lookup"><span data-stu-id="652c3-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="652c3-115">尋找想要匯入的測試案例檔案 (.vtest)，然後按一下 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="652c3-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="652c3-116">依序按一下 **[認可]** 和 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="652c3-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="652c3-117">只要匯入 .vtest 檔案，就必須執行 <STRONG>[全部認可]</STRONG> 命令，來發行測試案例。</span><span class="sxs-lookup"><span data-stu-id="652c3-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="652c3-118">如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。</span><span class="sxs-lookup"><span data-stu-id="652c3-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="652c3-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="652c3-119">See Also</span></span>


[<span data-ttu-id="652c3-120">在 Lync Server 2013 中匯出語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="652c3-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

