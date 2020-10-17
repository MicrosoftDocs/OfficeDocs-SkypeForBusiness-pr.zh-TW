---
title: Lync Server 2013： Lync PreCall 診斷工具
description: Lync Server 2013： Lync PreCall 診斷工具。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c2c51551fe0991eb354a628b1d4660baa1532b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571989"
---
# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="ef74f-103">Lync Server 2013 中的 lync PreCall 診斷工具</span><span class="sxs-lookup"><span data-stu-id="ef74f-103">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef74f-104">_**主題上次修改日期：** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="ef74f-104">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="ef74f-105">Lync PreCall Diagnostics Tool (.PCD) 是一種用戶端應用程式，可讓您查看網路目前的狀態如何影響即將到來的 Enterprise Voice 通話中的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="ef74f-105">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="ef74f-106">在網路的最後一個躍點可能是最弱的 (，例如，在公用 WiFi 網路或家用使用者) 上的膝上型電腦上，.PCD 非常有用。</span><span class="sxs-lookup"><span data-stu-id="ef74f-106">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="ef74f-107">.PCD 建立一個小型的封包資料流程，以流經這段網路的最後一個腿。</span><span class="sxs-lookup"><span data-stu-id="ef74f-107">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="ef74f-108">然後，該工具會分析封包資料流程，以估計沿著此腳的抖動和遺失可能會影響通話品質的方式，然後提供報告。</span><span class="sxs-lookup"><span data-stu-id="ef74f-108">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="ef74f-109">您可以在用戶端持續地執行 .PCD，甚至在撥打通話時也一樣。</span><span class="sxs-lookup"><span data-stu-id="ef74f-109">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="ef74f-110">封包資料流程對頻寬的影響不大。</span><span class="sxs-lookup"><span data-stu-id="ef74f-110">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="ef74f-111">**.PCD 版本1.1 的最新版本包含下列增強功能：**</span><span class="sxs-lookup"><span data-stu-id="ef74f-111">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="ef74f-112">支援較長的密碼，現在可達127個字元</span><span class="sxs-lookup"><span data-stu-id="ef74f-112">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="ef74f-113">驗證登入問題的其他診斷</span><span class="sxs-lookup"><span data-stu-id="ef74f-113">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="ef74f-114">更好支援 Lync 混合式部署</span><span class="sxs-lookup"><span data-stu-id="ef74f-114">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="ef74f-115">更新憑證選擇器</span><span class="sxs-lookup"><span data-stu-id="ef74f-115">Updates to credential picker</span></span>

  - <span data-ttu-id="ef74f-116">穩定性改進</span><span class="sxs-lookup"><span data-stu-id="ef74f-116">Stability improvements</span></span>

<span data-ttu-id="ef74f-117">感謝您的意見反應。</span><span class="sxs-lookup"><span data-stu-id="ef74f-117">We appreciate any feedback.</span></span> <span data-ttu-id="ef74f-118">請將所有支援問題或問題傳送至中的 [.Pcd 意見](mailto:pcdfb@microsoft.com) 反應別名 <pcdfb@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="ef74f-118">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="ef74f-119">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="ef74f-119">This topic includes the following sections:</span></span>

  - <span data-ttu-id="ef74f-120">Lync .PCD 版本</span><span class="sxs-lookup"><span data-stu-id="ef74f-120">Lync PCD Versions</span></span>

  - <span data-ttu-id="ef74f-121">Lync .PCD 系統需求</span><span class="sxs-lookup"><span data-stu-id="ef74f-121">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="ef74f-122">Lync .PCD 功能</span><span class="sxs-lookup"><span data-stu-id="ef74f-122">Lync PCD Features</span></span>

  - <span data-ttu-id="ef74f-123">執行 Lync .PCD</span><span class="sxs-lookup"><span data-stu-id="ef74f-123">Running Lync PCD</span></span>

  - <span data-ttu-id="ef74f-124">卸載 Lync .PCD</span><span class="sxs-lookup"><span data-stu-id="ef74f-124">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="ef74f-125">Lync .PCD 版本</span><span class="sxs-lookup"><span data-stu-id="ef74f-125">Lync PCD Versions</span></span>

<span data-ttu-id="ef74f-126">本主題說明下列工具版本，可供免費下載：</span><span class="sxs-lookup"><span data-stu-id="ef74f-126">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="ef74f-127">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914)) </span><span class="sxs-lookup"><span data-stu-id="ef74f-127">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="ef74f-128">Lync .PCD 系統需求</span><span class="sxs-lookup"><span data-stu-id="ef74f-128">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef74f-129">.PCD 需要安裝並設定整合通訊網頁 API () UCWA，以支援 Lync Server 部署中的行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="ef74f-129">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="ef74f-130">UCWA 與 Lync Server 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="ef74f-130">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="ef74f-131">Windows 桌面應用程式需求</span><span class="sxs-lookup"><span data-stu-id="ef74f-131">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="ef74f-132">任何版本的 Windows 7 或 Windows 8 作業系統</span><span class="sxs-lookup"><span data-stu-id="ef74f-132">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="ef74f-133">Microsoft .NET Framework 4.5 可于 [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="ef74f-133">Microsoft .NET Framework 4.5 available at [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="ef74f-134">Lync .PCD 功能</span><span class="sxs-lookup"><span data-stu-id="ef74f-134">Lync PCD Features</span></span>

<span data-ttu-id="ef74f-135">Lync .PCD 包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="ef74f-135">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="ef74f-136">在預設按需要執行 (2 分鐘的猝量) </span><span class="sxs-lookup"><span data-stu-id="ef74f-136">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="ef74f-137">在對齊模式) 模式中，以 Always On (于24小時內執行</span><span class="sxs-lookup"><span data-stu-id="ef74f-137">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="ef74f-138">測試執行的歷史視圖</span><span class="sxs-lookup"><span data-stu-id="ef74f-138">Historical view of your test runs</span></span>

  - <span data-ttu-id="ef74f-139">在僅限 Windows 8 的 Lync .PCD 中診斷登入失敗 () </span><span class="sxs-lookup"><span data-stu-id="ef74f-139">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="ef74f-140">![Lync .PCD 功能登入進度螢幕擷取畫面](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync .PCD 功能登入進度螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="ef74f-140">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="ef74f-141">網路計量的圖形化視圖，以全屏和貼齊模式顯示網路 MOS、封包遺失和 Interarrival 抖動。</span><span class="sxs-lookup"><span data-stu-id="ef74f-141">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="ef74f-142">**全螢幕視圖**</span><span class="sxs-lookup"><span data-stu-id="ef74f-142">**Full screen view**</span></span>

<span data-ttu-id="ef74f-143">![PreCall 診斷工具測試結果圖形](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診斷工具測試結果圖形")</span><span class="sxs-lookup"><span data-stu-id="ef74f-143">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="ef74f-144">**貼齊視圖**</span><span class="sxs-lookup"><span data-stu-id="ef74f-144">**Snapped view**</span></span>

<span data-ttu-id="ef74f-145">![PreCall 診斷工具利用率測試結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診斷工具利用率測試結果")</span><span class="sxs-lookup"><span data-stu-id="ef74f-145">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="ef74f-146">執行 Lync .PCD</span><span class="sxs-lookup"><span data-stu-id="ef74f-146">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="ef74f-147">執行 Windows 桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="ef74f-147">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="ef74f-148">若要在 Windows 7 系統上啟動 .PCD，請從 [**開始**] 功能表中選取 [ **PreCall 診斷**]。</span><span class="sxs-lookup"><span data-stu-id="ef74f-148">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="ef74f-149">若要在 Windows 8 系統上啟動 .PCD，請在 [開始] 畫面上選取圖示，或搜尋「PreCall 診斷」。</span><span class="sxs-lookup"><span data-stu-id="ef74f-149">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="ef74f-150">![PreCall 診斷工具圖示](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診斷工具圖示")</span><span class="sxs-lookup"><span data-stu-id="ef74f-150">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="ef74f-151">當工具開始時，請選取您要提供認證的慣用方法，並在 [ **PreCall 診斷工具選項** ] 對話方塊中選取 [網路] 工作模式，然後選取 [ **確定]**：</span><span class="sxs-lookup"><span data-stu-id="ef74f-151">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="ef74f-152">選取 [ **開始測試** ] 按鈕開始執行診斷。</span><span class="sxs-lookup"><span data-stu-id="ef74f-152">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="ef74f-153">如果您選取 [ **使用網路認證** ] 選項，測試會立即開始。</span><span class="sxs-lookup"><span data-stu-id="ef74f-153">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="ef74f-154">如果您選取 [ **讓我輸入我的認證** ] 選項，則會開啟 [ **Windows 安全性** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="ef74f-154">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="ef74f-155">在您輸入認證之後，就會開始測試。</span><span class="sxs-lookup"><span data-stu-id="ef74f-155">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="ef74f-156">卸載 Lync .PCD</span><span class="sxs-lookup"><span data-stu-id="ef74f-156">Uninstalling Lync PCD</span></span>

<span data-ttu-id="ef74f-157">若要移除 Lync .PCD，請遵循作業系統的程式：</span><span class="sxs-lookup"><span data-stu-id="ef74f-157">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="ef74f-158">在 Windows 7 系統上，開啟 [ **控制台**]，選取 [ **程式和功能**]，然後按兩下 [ **Lync 2013 PreCall 診斷**]。</span><span class="sxs-lookup"><span data-stu-id="ef74f-158">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="ef74f-159">在 Windows 8 系統上，以滑鼠右鍵按一下 [.PCD] 磚，然後按一下 [開始] 畫面底部的 [應用程式] 欄中的 [ **卸載** ]。</span><span class="sxs-lookup"><span data-stu-id="ef74f-159">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

