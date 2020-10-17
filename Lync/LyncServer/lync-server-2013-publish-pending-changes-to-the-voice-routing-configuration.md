---
title: Lync Server 2013：將暫止的變更發佈至語音路由設定
description: Lync Server 2013：將暫止的變更發佈至語音路由設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7a56b9a07606932a34dea7149a799dbb60b376
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565449"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="3bd01-103">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="3bd01-103">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bd01-104">_**主題上次修改日期：** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="3bd01-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="3bd01-105">變更 [ **語音路由** ] 群組中的任何設定設定後，請執行此程式以複查、發佈或取消暫止的變更。</span><span class="sxs-lookup"><span data-stu-id="3bd01-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3bd01-106">請確定一次只能有一個使用者修改語音路由設定的設定。</span><span class="sxs-lookup"><span data-stu-id="3bd01-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="3bd01-107">所有擱置的變更都必須同時發佈，只要執行 [ <STRONG>全部認可</STRONG> ] 命令即可。</span><span class="sxs-lookup"><span data-stu-id="3bd01-107">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command.</span></span> <span data-ttu-id="3bd01-108">您無法選擇性發行暫止的變更。</span><span class="sxs-lookup"><span data-stu-id="3bd01-108">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="3bd01-109">在您發佈暫止的變更之前，請執行 [ <STRONG>檢查未</STRONG> 認可的變更] 命令，並取消您不想發佈的任何設定變更。</span><span class="sxs-lookup"><span data-stu-id="3bd01-109">Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="3bd01-110">如果您在提交暫止的變更之前，移離 <STRONG>語音路由</STRONG> 群組中的頁面，所有擱置的變更將會遺失。</span><span class="sxs-lookup"><span data-stu-id="3bd01-110">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="3bd01-111">不過，您可以將目前的設定 (包括任何擱置的變更) 至語音設定檔，然後匯入併發行更新的設定。</span><span class="sxs-lookup"><span data-stu-id="3bd01-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="3bd01-112">如需詳細資訊，請參閱 <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="3bd01-112">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="3bd01-113">若要檢查、發佈或取消語音路由設定變更</span><span class="sxs-lookup"><span data-stu-id="3bd01-113">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="3bd01-114">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="3bd01-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3bd01-115">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3bd01-115">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3bd01-116">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="3bd01-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3bd01-117">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3bd01-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3bd01-118">在左導覽列中，按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="3bd01-118">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="3bd01-119">在 [ **語音路由** ] 群組的每一頁上進行設定的設定變更。</span><span class="sxs-lookup"><span data-stu-id="3bd01-119">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="3bd01-120">若要在未發佈的情況下複查擱置中的變更，請選取 [從**認可**] 功能表**查看未**認可的變更</span><span class="sxs-lookup"><span data-stu-id="3bd01-120">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="3bd01-121">如果您想要取消任何擱置的變更，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="3bd01-121">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="3bd01-122">從 [**認可**] 功能表中，選取 [**取消所有未**認可的變更]。</span><span class="sxs-lookup"><span data-stu-id="3bd01-122">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="3bd01-123">流覽至 [ **語音路由** ] 頁面上的 [語音路由] 頁面，其中含有您想要取消的待處理變更，選取具有暫止變更的專案，按一下 [ **認可**]，然後按一下 [ **取消選取的變更**]。</span><span class="sxs-lookup"><span data-stu-id="3bd01-123">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="3bd01-124">在您檢查所有擱置的變更並取消任何不想發佈的變更之後，請按一下 [ **認可**]，然後按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="3bd01-124">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="3bd01-125">在 [ **未認可的語音設定** ] 對話方塊中，顯示所有擱置變更的清單，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3bd01-125">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="3bd01-126">當 Lync Server 控制台認可變更時，就會出現 [ **成功發行的語音路由** 設定] 訊息。</span><span class="sxs-lookup"><span data-stu-id="3bd01-126">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

