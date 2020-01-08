---
title: Lync Server 2013： Lync PreCall 診斷工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e22b542a5840714455d4abdb0a7163e6a8ba748
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="bf9c7-102">Lync Server 2013 中的 lync PreCall 診斷工具</span><span class="sxs-lookup"><span data-stu-id="bf9c7-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf9c7-103">_**主題上次修改日期：** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="bf9c7-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="bf9c7-104">Lync PreCall 診斷工具（PCD）是一種用戶端的應用程式，可讓您查看網路目前狀態在未來的企業語音通話中可能會如何影響音訊品質。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="bf9c7-105">在網路的最後一個躍點可能是最弱（例如，在公用 WiFi 網路或家用使用者上使用膝上型電腦）時，PCD 非常有用。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="bf9c7-106">PCD 會建立一個可遍歷這個網路最後一個網段的小型資料包串流。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="bf9c7-107">然後，該工具會分析資料包資料流程，以估計此腿的抖動與遺失對通話品質有何影響，然後提供報告。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="bf9c7-108">您可以在用戶端連續執行 PCD，即使正在進行通話也一樣。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="bf9c7-109">資料包資料流程在頻寬上不會有顯著的影響。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="bf9c7-110">**PCD （版本1.1）最新版本包含下列增強功能：**</span><span class="sxs-lookup"><span data-stu-id="bf9c7-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="bf9c7-111">支援較長的密碼，現在最多可以使用127個字元</span><span class="sxs-lookup"><span data-stu-id="bf9c7-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="bf9c7-112">驗證登入問題的其他診斷資訊</span><span class="sxs-lookup"><span data-stu-id="bf9c7-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="bf9c7-113">更好地支援 Lync 混合式部署</span><span class="sxs-lookup"><span data-stu-id="bf9c7-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="bf9c7-114">認證選擇器的更新</span><span class="sxs-lookup"><span data-stu-id="bf9c7-114">Updates to credential picker</span></span>

  - <span data-ttu-id="bf9c7-115">穩定性改善</span><span class="sxs-lookup"><span data-stu-id="bf9c7-115">Stability improvements</span></span>

<span data-ttu-id="bf9c7-116">我們感謝任何意見反應。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-116">We appreciate any feedback.</span></span> <span data-ttu-id="bf9c7-117">請將所有支援問題或問題傳送給[PCD 的意見](mailto:pcdfb@microsoft.com)反應<pcdfb@microsoft.com>別名。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="bf9c7-118">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="bf9c7-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="bf9c7-119">Lync PCD 版本</span><span class="sxs-lookup"><span data-stu-id="bf9c7-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="bf9c7-120">Lync PCD 系統需求</span><span class="sxs-lookup"><span data-stu-id="bf9c7-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="bf9c7-121">Lync PCD 功能</span><span class="sxs-lookup"><span data-stu-id="bf9c7-121">Lync PCD Features</span></span>

  - <span data-ttu-id="bf9c7-122">執行 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="bf9c7-122">Running Lync PCD</span></span>

  - <span data-ttu-id="bf9c7-123">卸載 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="bf9c7-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="bf9c7-124">Lync PCD 版本</span><span class="sxs-lookup"><span data-stu-id="bf9c7-124">Lync PCD Versions</span></span>

<span data-ttu-id="bf9c7-125">本主題描述下列工具版本，提供免費下載：</span><span class="sxs-lookup"><span data-stu-id="bf9c7-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="bf9c7-126">Windows 傳統型應用程式[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)（）</span><span class="sxs-lookup"><span data-stu-id="bf9c7-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="bf9c7-127">Lync PCD 系統需求</span><span class="sxs-lookup"><span data-stu-id="bf9c7-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf9c7-128">PCD 要求在 Lync Server 部署中安裝並設定整合通訊網頁 API （UCWA）以支援行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="bf9c7-129">UCWA 是隨 Lync Server 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="bf9c7-130">Windows 桌面應用程式需求</span><span class="sxs-lookup"><span data-stu-id="bf9c7-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="bf9c7-131">任何版本的 Windows 7 或 Windows 8 作業系統</span><span class="sxs-lookup"><span data-stu-id="bf9c7-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="bf9c7-132">Microsoft .NET Framework 4.5 可在[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="bf9c7-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="bf9c7-133">Lync PCD 功能</span><span class="sxs-lookup"><span data-stu-id="bf9c7-133">Lync PCD Features</span></span>

<span data-ttu-id="bf9c7-134">Lync PCD 包括下列功能：</span><span class="sxs-lookup"><span data-stu-id="bf9c7-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="bf9c7-135">根據需求預設執行（2分鐘突發）</span><span class="sxs-lookup"><span data-stu-id="bf9c7-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="bf9c7-136">[持續開啟] （在貼齊模式中最多24小時）</span><span class="sxs-lookup"><span data-stu-id="bf9c7-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="bf9c7-137">測試執行的歷史視圖</span><span class="sxs-lookup"><span data-stu-id="bf9c7-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="bf9c7-138">診斷登入失敗（僅適用于 Windows 8 的 Lync PCD）</span><span class="sxs-lookup"><span data-stu-id="bf9c7-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="bf9c7-139">![LYNC PCD 功能 [登入進度] 畫面快照](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD 功能登入進度畫面快照")</span><span class="sxs-lookup"><span data-stu-id="bf9c7-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="bf9c7-140">網路度量的圖形化視圖： [MOS]、[資料包遺失] 和 [Interarrival 抖動]，以全螢幕顯示及貼齊模式。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="bf9c7-141">**全螢幕視圖**</span><span class="sxs-lookup"><span data-stu-id="bf9c7-141">**Full screen view**</span></span>

<span data-ttu-id="bf9c7-142">![PreCall 診斷工具測試結果圖形](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診斷工具測試結果圖形")</span><span class="sxs-lookup"><span data-stu-id="bf9c7-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="bf9c7-143">**貼齊視圖**</span><span class="sxs-lookup"><span data-stu-id="bf9c7-143">**Snapped view**</span></span>

<span data-ttu-id="bf9c7-144">![PreCall 診斷工具利用率測試結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診斷工具利用率測試結果")</span><span class="sxs-lookup"><span data-stu-id="bf9c7-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="bf9c7-145">執行 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="bf9c7-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="bf9c7-146">執行 Windows 桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="bf9c7-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="bf9c7-147">若要在 Windows 7 系統上啟動 PCD，請從 [**開始**] 功能表選取 [ **PreCall 診斷**]。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="bf9c7-148">若要在 Windows 8 系統上啟動 PCD，請選取 [開始] 畫面上的圖示，或搜尋「PreCall Diagnostics」。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="bf9c7-149">![PreCall 診斷工具圖示](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診斷工具圖示")</span><span class="sxs-lookup"><span data-stu-id="bf9c7-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="bf9c7-150">當工具啟動時，請選取您要提供認證的慣用方法，然後選取 [ **PreCall 診斷工具選項**] 對話方塊中的 [網路] 工作模式，然後選取 **[確定]**：</span><span class="sxs-lookup"><span data-stu-id="bf9c7-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="bf9c7-151">選取 [**開始測試**] 按鈕，即可開始執行診斷程式。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="bf9c7-152">如果您已選取 [**使用網路認證**] 選項，測試就會立即開始。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="bf9c7-153">如果您已選取 [**讓我輸入我的認證**] 選項，就會開啟 [ **Windows 安全性**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="bf9c7-154">輸入認證之後，就會開始測試。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="bf9c7-155">卸載 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="bf9c7-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="bf9c7-156">若要移除 Lync PCD，請依照適用于您作業系統的程式進行：</span><span class="sxs-lookup"><span data-stu-id="bf9c7-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="bf9c7-157">在 Windows 7 系統上，開啟 [**控制台**]，選取 [**程式和功能**]，然後按兩下 [ **Lync 2013 PreCall Diagnostics**]。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="bf9c7-158">在 Windows 8 系統上，以滑鼠右鍵按一下 [PCD] 磚，然後按一下 [開始] 畫面底部的應用程式行中的 [**卸載**]。</span><span class="sxs-lookup"><span data-stu-id="bf9c7-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

