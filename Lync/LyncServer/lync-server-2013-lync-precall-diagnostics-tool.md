---
title: 'Lync Server 2013: Lync PreCall 診斷工具'
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
ms.openlocfilehash: 79009ce890e37e7238e3fef18f719fb3da411889
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="c9c66-102">Lync Server 2013 中的 Lync PreCall 診斷工具</span><span class="sxs-lookup"><span data-stu-id="c9c66-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9c66-103">_**主題上次修改日期：** 2016年-11-04_</span><span class="sxs-lookup"><span data-stu-id="c9c66-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="c9c66-104">Lync PreCall 診斷工具 (PCD) 是網路的用戶端為基礎的應用程式，可讓您查看您的目前狀態可能會如何影響中即將來臨的企業語音通話的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="c9c66-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="c9c66-105">PCD 是最適合用在網路的最後一個躍點可能是最弱 （例如，具有公用 WiFi 網路或隸屬使用者上的膝上型電腦） 的情況。</span><span class="sxs-lookup"><span data-stu-id="c9c66-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="c9c66-106">PCD 建立周遊網路此最終 leg 小型的封包資料流。</span><span class="sxs-lookup"><span data-stu-id="c9c66-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="c9c66-107">此工具然後分析來評估抖動和沿著此 leg 遺失可能會影響通話品質的封包資料流，然後將報表。</span><span class="sxs-lookup"><span data-stu-id="c9c66-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="c9c66-108">您可以 PCD 持續在用戶端，同時也可以執行所在的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c9c66-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="c9c66-109">封包資料流沒有頻寬重大影響。</span><span class="sxs-lookup"><span data-stu-id="c9c66-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="c9c66-110">**最新版的 PCD，版本 1.1 中，包含下列增強功能：**</span><span class="sxs-lookup"><span data-stu-id="c9c66-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="c9c66-111">支援較長的密碼，現在可達 127 個字元</span><span class="sxs-lookup"><span data-stu-id="c9c66-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="c9c66-112">驗證登入問題的其他診斷</span><span class="sxs-lookup"><span data-stu-id="c9c66-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="c9c66-113">進一步支援 Lync 混合式部署</span><span class="sxs-lookup"><span data-stu-id="c9c66-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="c9c66-114">更新認證選擇器</span><span class="sxs-lookup"><span data-stu-id="c9c66-114">Updates to credential picker</span></span>

  - <span data-ttu-id="c9c66-115">穩定性增強功能</span><span class="sxs-lookup"><span data-stu-id="c9c66-115">Stability improvements</span></span>

<span data-ttu-id="c9c66-116">我們歡迎任何意見反應。</span><span class="sxs-lookup"><span data-stu-id="c9c66-116">We appreciate any feedback.</span></span> <span data-ttu-id="c9c66-117">請將所有支援問題都傳送給在[PCD 意見反應](mailto:pcdfb@microsoft.com)別名<pcdfb@microsoft.com>。</span><span class="sxs-lookup"><span data-stu-id="c9c66-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="c9c66-118">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="c9c66-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="c9c66-119">Lync PCD 版本</span><span class="sxs-lookup"><span data-stu-id="c9c66-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="c9c66-120">Lync PCD 系統需求</span><span class="sxs-lookup"><span data-stu-id="c9c66-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="c9c66-121">Lync PCD 功能</span><span class="sxs-lookup"><span data-stu-id="c9c66-121">Lync PCD Features</span></span>

  - <span data-ttu-id="c9c66-122">執行 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="c9c66-122">Running Lync PCD</span></span>

  - <span data-ttu-id="c9c66-123">解除安裝 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="c9c66-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="c9c66-124">Lync PCD 版本</span><span class="sxs-lookup"><span data-stu-id="c9c66-124">Lync PCD Versions</span></span>

<span data-ttu-id="c9c66-125">本主題說明工具，可供免費下載的下列的版本：</span><span class="sxs-lookup"><span data-stu-id="c9c66-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="c9c66-126">Windows 桌面應用程式 ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span><span class="sxs-lookup"><span data-stu-id="c9c66-126">Windows Desktop App ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="c9c66-127">Lync PCD 系統需求</span><span class="sxs-lookup"><span data-stu-id="c9c66-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9c66-128">PCD 需要 Unified Communications Web API (UCWA) 是安裝和設定 Lync Server 部署中支援行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="c9c66-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="c9c66-129">使用 Lync Server 安裝 ucwa 的參考。</span><span class="sxs-lookup"><span data-stu-id="c9c66-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="c9c66-130">Windows 桌面應用程式需求</span><span class="sxs-lookup"><span data-stu-id="c9c66-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="c9c66-131">任何版本的 Windows 7 或 Windows 8 作業系統</span><span class="sxs-lookup"><span data-stu-id="c9c66-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="c9c66-132">Microsoft.NET Framework 4.5 可在[https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="c9c66-132">Microsoft .NET Framework 4.5 available at [https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="c9c66-133">Lync PCD 功能</span><span class="sxs-lookup"><span data-stu-id="c9c66-133">Lync PCD Features</span></span>

<span data-ttu-id="c9c66-134">Lync PCD 包含下列功能：</span><span class="sxs-lookup"><span data-stu-id="c9c66-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="c9c66-135">執行預設的隨選 （2 分鐘激增）</span><span class="sxs-lookup"><span data-stu-id="c9c66-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="c9c66-136">Always On 中執行 （最多 24 小時貼齊] 檢視中） 模式</span><span class="sxs-lookup"><span data-stu-id="c9c66-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="c9c66-137">您在測試回合的歷史檢視</span><span class="sxs-lookup"><span data-stu-id="c9c66-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="c9c66-138">診斷登入失敗 (僅限 Windows 8 的 Lync PCD)</span><span class="sxs-lookup"><span data-stu-id="c9c66-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="c9c66-139">![Lync PCD 功能登入進度螢幕擷取畫面](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD 功能登入進度螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="c9c66-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="c9c66-140">圖形網路計量 – 網路 MOS、 封包遺失和 Interarrival 抖動在全螢幕] 和 [貼齊的檢視的檢視。</span><span class="sxs-lookup"><span data-stu-id="c9c66-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="c9c66-141">**全螢幕檢視**</span><span class="sxs-lookup"><span data-stu-id="c9c66-141">**Full screen view**</span></span>

<span data-ttu-id="c9c66-142">![PreCall 診斷工具測試結果圖形](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 診斷工具測試結果圖形")</span><span class="sxs-lookup"><span data-stu-id="c9c66-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="c9c66-143">**貼齊的檢視**</span><span class="sxs-lookup"><span data-stu-id="c9c66-143">**Snapped view**</span></span>

<span data-ttu-id="c9c66-144">![PreCall 診斷工具使用率測試結果](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 診斷工具使用率測試結果")</span><span class="sxs-lookup"><span data-stu-id="c9c66-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="c9c66-145">執行 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="c9c66-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="c9c66-146">執行 Windows 桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="c9c66-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="c9c66-147">若要 PCD 系統上啟動 Windows 7，請從 [**開始**] 功能表中選取**PreCall 診斷**。</span><span class="sxs-lookup"><span data-stu-id="c9c66-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="c9c66-148">若要在 Windows 8 的系統上啟動 PCD，選取 [開始] 畫面中或搜尋 「 PreCall 診斷。 」 上的圖示</span><span class="sxs-lookup"><span data-stu-id="c9c66-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="c9c66-149">![PreCall 診斷工具圖示](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 診斷工具圖示")</span><span class="sxs-lookup"><span data-stu-id="c9c66-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="c9c66-150">工具開始時，選取您偏好的方法，提供認證和選取網路作業系統模式**PreCall 診斷工具選項**] 對話方塊中，然後選取 **[確定]**:</span><span class="sxs-lookup"><span data-stu-id="c9c66-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="c9c66-151">選取 [**開始測試**] 按鈕，開始執行診斷。</span><span class="sxs-lookup"><span data-stu-id="c9c66-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="c9c66-152">如果您選取 [**使用的網路認證**] 選項，會立即開始測試。</span><span class="sxs-lookup"><span data-stu-id="c9c66-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="c9c66-153">如果您選取 [**讓我輸入我的認證**] 選項，會開啟 [ **Windows 安全性**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c9c66-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="c9c66-154">輸入您的認證之後，測試便會啟動。</span><span class="sxs-lookup"><span data-stu-id="c9c66-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="c9c66-155">解除安裝 Lync PCD</span><span class="sxs-lookup"><span data-stu-id="c9c66-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="c9c66-156">若要移除 Lync PCD，請依照下列程序適用於您作業系統：</span><span class="sxs-lookup"><span data-stu-id="c9c66-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="c9c66-157">在 Windows 7 系統上，開啟 [**控制台**]，選取 [**程式和功能**]，按兩下 [ **Lync 2013 PreCall 診斷**。</span><span class="sxs-lookup"><span data-stu-id="c9c66-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="c9c66-158">在 Windows 8 系統上，PCD 磚上按一下滑鼠右鍵，並在 [開始] 畫面底部的 [應用程式] 列中按一下 [**解除安裝**。</span><span class="sxs-lookup"><span data-stu-id="c9c66-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

