---
title: Lync Server 2013：發佈語音路由設定的擱置變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22cabe1725d899ace42e5b525105c1753c3d9925
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="ecf34-102">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="ecf34-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecf34-103">_**主題上次修改日期：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="ecf34-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="ecf34-104">在您針對 [**語音路由**] 群組中的頁面變更任何設定設定之後，請執行此程式來審閱、發佈或解除擱置中的變更。</span><span class="sxs-lookup"><span data-stu-id="ecf34-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ecf34-105">確定一次只有一個使用者會修改 [語音路由設定] 設定。</span><span class="sxs-lookup"><span data-stu-id="ecf34-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="ecf34-106">只要執行 [<STRONG>全部提交</STRONG>] 命令，就必須同時發佈所有擱置中的變更。</span><span class="sxs-lookup"><span data-stu-id="ecf34-106">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command.</span></span> <span data-ttu-id="ecf34-107">您無法選擇性地發佈擱置中的變更。</span><span class="sxs-lookup"><span data-stu-id="ecf34-107">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="ecf34-108">發佈待定變更之前，請先執行 [<STRONG>查看未提交的變更</STRONG>] 命令，然後取消任何您不想發佈的設定變更。</span><span class="sxs-lookup"><span data-stu-id="ecf34-108">Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="ecf34-109">如果您在提交掛起的變更前，移出 [<STRONG>語音路由</STRONG>] 群組中的頁面，所有擱置的變更都會遺失。</span><span class="sxs-lookup"><span data-stu-id="ecf34-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="ecf34-110">不過，您可以將目前的設定（包括任何擱置中的變更）匯出到語音設定檔案，然後匯入併發布更新的設定。</span><span class="sxs-lookup"><span data-stu-id="ecf34-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="ecf34-111">如需詳細資訊，請參閱<A href="lync-server-2013-export-a-voice-route-configuration-file.md">在 Lync Server 2013 中匯出語音路由設定檔</A>。</span><span class="sxs-lookup"><span data-stu-id="ecf34-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="ecf34-112">若要查看、發佈或取消語音路由設定變更</span><span class="sxs-lookup"><span data-stu-id="ecf34-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="ecf34-113">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ecf34-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ecf34-114">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf34-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ecf34-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ecf34-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ecf34-116">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf34-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ecf34-117">在左側導覽列中，按一下 [**語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="ecf34-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="ecf34-118">針對 [**語音路由**] 群組的每個頁面上的設定變更您想要的設定。</span><span class="sxs-lookup"><span data-stu-id="ecf34-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="ecf34-119">若要查看待定的變更而不發佈，請選取 [**確認**] 功能表中的 [**查看未提交的變更**]。</span><span class="sxs-lookup"><span data-stu-id="ecf34-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="ecf34-120">如果您想要取消任何待定的變更，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ecf34-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="ecf34-121">從 [**認可**] 功能表中選取 [**取消所有未提交的變更**]。</span><span class="sxs-lookup"><span data-stu-id="ecf34-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="ecf34-122">流覽至含有您要取消之待定變更之 [**語音路由**] 頁面的索引標籤，選取含有待定變更的專案，按一下 [**認可**]，然後按一下 [**取消選取的變更**]。</span><span class="sxs-lookup"><span data-stu-id="ecf34-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="ecf34-123">審閱完所有擱置的變更並取消任何不想發佈的變更之後，請按一下 [**認可**]，然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="ecf34-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="ecf34-124">在 [**未提交的語音設定**] 對話方塊中，顯示所有待定變更的清單，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ecf34-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="ecf34-125">當 Lync Server 控制台提交變更之後，就會出現 [**成功發佈的語音路由**設定] 訊息。</span><span class="sxs-lookup"><span data-stu-id="ecf34-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

