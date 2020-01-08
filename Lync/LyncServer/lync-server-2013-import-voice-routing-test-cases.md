---
title: Lync Server 2013：改善語音路由測試案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8b1aba05447904d4515df7ab6137743edb52ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="353ba-102">在 Lync Server 2013 中改善語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="353ba-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="353ba-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="353ba-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="353ba-104">測試案例提供您在組織中測試語音路線的方式：您可以定義要撥打的號碼，以及要使用的撥號計畫和語音原則，而 Lync Server 2013 可以在已知這些條件下驗證，提供的號碼可以 successfully 會路由到 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="353ba-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="353ba-105">您可以使用 Lync Server [控制台] 建立的測試案例通常只會儲存在當初建立並執行該案例的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="353ba-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="353ba-106">不過，這些測試案例可以匯出為 XML 檔案（副檔名為 vtest），然後匯入到其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="353ba-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="353ba-107">這可讓您在拓撲中不同的電腦上執行相同的測試。</span><span class="sxs-lookup"><span data-stu-id="353ba-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="353ba-108">若要匯入語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="353ba-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="353ba-109">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="353ba-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="353ba-110">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="353ba-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="353ba-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="353ba-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="353ba-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="353ba-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="353ba-113">在左側導覽列中，按一下 [**語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="353ba-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="353ba-114">在 [**動作**] 功能表上，按一下 [匯**入測試案例**]。</span><span class="sxs-lookup"><span data-stu-id="353ba-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="353ba-115">找出您想要匯入的測試案例檔案（vtest），然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="353ba-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="353ba-116">按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="353ba-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="353ba-117">每當您匯入 vtest 檔案時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈測試案例。</span><span class="sxs-lookup"><span data-stu-id="353ba-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="353ba-118">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="353ba-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="353ba-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="353ba-119">See Also</span></span>


[<span data-ttu-id="353ba-120">在 Lync Server 2013 中匯出語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="353ba-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

