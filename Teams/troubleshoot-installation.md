---
title: 針對 Windows 上的 Microsoft Teams 安裝和更新問題進行疑難排解
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何針對 Windows 上的 Teams 桌面用戶端應用程式進行安裝和更新問題的疑難排解。
ms.openlocfilehash: 283b1818789624428aa772a4d71360a07eed6f00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097549"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a><span data-ttu-id="99a2e-103">針對 Windows 上的 Microsoft Teams 安裝和更新問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="99a2e-103">Troubleshoot Microsoft Teams installation and update issues on Windows</span></span>

<span data-ttu-id="99a2e-104">本文提供如何針對在 Windows 上執行的 Teams 桌面用戶端應用程式的安裝和更新問題進行診斷和疑難排解的指導方針。</span><span class="sxs-lookup"><span data-stu-id="99a2e-104">This article provides guidance for how to diagnose and troubleshoot installation and update issues for the Teams desktop client app running on Windows.</span></span>

## <a name="check-whether-teams-is-updated-successfully"></a><span data-ttu-id="99a2e-105">檢查 Teams 是否已順利更新</span><span class="sxs-lookup"><span data-stu-id="99a2e-105">Check whether Teams is updated successfully</span></span>

<span data-ttu-id="99a2e-106">按照這些步驟檢查是否已順利安裝 Teams 更新。</span><span class="sxs-lookup"><span data-stu-id="99a2e-106">Follow these steps to check whether a Teams update is successfully installed.</span></span>

1. <span data-ttu-id="99a2e-107">在 Teams 中，選取您的個人檔案圖片，然後按一下 [關於] > [版本]。</span><span class="sxs-lookup"><span data-stu-id="99a2e-107">In Teams, select your profile picture, and then click **About** > **Version**.</span></span>
2. <span data-ttu-id="99a2e-108">在同一個功能表上，按一下 [檢查更新]。</span><span class="sxs-lookup"><span data-stu-id="99a2e-108">On the same menu, click **Check for updates**.</span></span>
3. <span data-ttu-id="99a2e-109">等候應用程式最上方的橫幅，指出需要重新整理 Teams。</span><span class="sxs-lookup"><span data-stu-id="99a2e-109">Wait for the banner at the top of the app to indicate that a “refresh” of Teams is needed.</span></span> <span data-ttu-id="99a2e-110">此程序下載新版 Teams 後大約一分鐘應該會顯示連結。</span><span class="sxs-lookup"><span data-stu-id="99a2e-110">The link should be shown about a minute later as this process downloads the new version of Teams.</span></span> <span data-ttu-id="99a2e-111">橫幅也會讓您知道您是否執行最新的版本，如果是，就不需要更新。</span><span class="sxs-lookup"><span data-stu-id="99a2e-111">The banner also lets you know if you’re already running the latest version in which case, no update is necessary.</span></span>
4. <span data-ttu-id="99a2e-112">按一下橫幅中的重新整理連結。</span><span class="sxs-lookup"><span data-stu-id="99a2e-112">Click the refresh link in the banner.</span></span>
5. <span data-ttu-id="99a2e-113">請等候 Teams 重新啟動，然後重複步驟 1 以查看應用程式是否已更新。</span><span class="sxs-lookup"><span data-stu-id="99a2e-113">Wait until Teams restarts, and then repeat step 1 to see whether the app is updated.</span></span>

<span data-ttu-id="99a2e-114">如果您看到失敗訊息，或版本號碼與步驟 4 的相同，表示更新程序失敗。</span><span class="sxs-lookup"><span data-stu-id="99a2e-114">If you see a failure message or if the version number is the same as in step 4, the update process failed.</span></span>

## <a name="troubleshoot-installation-and-update-issues"></a><span data-ttu-id="99a2e-115">安裝和更新問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="99a2e-115">Troubleshoot installation and update issues</span></span>

### <a name="troubleshoot-installation-issues"></a><span data-ttu-id="99a2e-116">安裝問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="99a2e-116">Troubleshoot installation issues</span></span>

<span data-ttu-id="99a2e-117">Teams 安裝好後，Teams 安裝程式會將事件順序記錄到 %LocalAppData%\SquirrelTemp\SquirrelSetup.log。</span><span class="sxs-lookup"><span data-stu-id="99a2e-117">When Teams is installed, the Teams installer logs the sequence of events to %LocalAppData%\SquirrelTemp\SquirrelSetup.log.</span></span> <span data-ttu-id="99a2e-118">首先要尋找的是錯誤訊息或位於記錄結尾附近的呼叫堆疊。</span><span class="sxs-lookup"><span data-stu-id="99a2e-118">The first thing to look for is an error message or a call stack near the end of the log.</span></span> <span data-ttu-id="99a2e-119">請注意，記錄開頭的呼叫堆疊不一定表示安裝有問題。</span><span class="sxs-lookup"><span data-stu-id="99a2e-119">Note that call stacks at the beginning of the log may not mean that an installation issue exists.</span></span> <span data-ttu-id="99a2e-120">將您的記錄與成功安裝的記錄 (即使是在另一部電腦上) 做比較，會比較容易看出預期的結果。</span><span class="sxs-lookup"><span data-stu-id="99a2e-120">It can be easier to compare your log against the log from a successful installation (even on another machine) to see what's expected.</span></span>

<span data-ttu-id="99a2e-121">如果 SquirrelSetup.log 沒有指出原因，或您需要更多疑難排解問題的資訊，請參閱[收集和分析應用程式記錄與系統記錄](#collect-and-analyze-application-and-system-logs)。</span><span class="sxs-lookup"><span data-stu-id="99a2e-121">If SquirrelSetup.log doesn't indicate the cause or if you need more information to troubleshoot the issue, see [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

### <a name="troubleshoot-update-issues"></a><span data-ttu-id="99a2e-122">更新問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="99a2e-122">Troubleshoot update issues</span></span>

<span data-ttu-id="99a2e-123">Teams 成功安裝後，記錄位置會從 %LocalAppData%\SquirrelTemp 切換到 %LocalAppData%\Microsoft\Teams。</span><span class="sxs-lookup"><span data-stu-id="99a2e-123">When Teams is successfully installed, the log location switches from %LocalAppData%\SquirrelTemp to %LocalAppData%\Microsoft\Teams.</span></span> <span data-ttu-id="99a2e-124">這個位置有兩個需要注意的記錄檔：SquirrelSetup.log 和 logs.txt。</span><span class="sxs-lookup"><span data-stu-id="99a2e-124">At this location, there are two log files of interest, SquirrelSetup.log and logs.txt.</span></span>

- <span data-ttu-id="99a2e-125">這個位置的 SquirrelSetup.log 檔是由 Update.exe 寫入，這是一個服務 Teams 應用程式的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="99a2e-125">The SquirrelSetup.log file at this location is written by Update.exe, which is an executable that services the Teams app.</span></span>
- <span data-ttu-id="99a2e-126">Logs.txt 檔是 Teams 應用程式 (特別是 Teams.exe) 用來記錄重大的應用程式事件。</span><span class="sxs-lookup"><span data-stu-id="99a2e-126">The Logs.txt file is used by the Teams app (specifically Teams.exe) to record significant application events.</span></span> <span data-ttu-id="99a2e-127">它可能會包含失敗資訊。</span><span class="sxs-lookup"><span data-stu-id="99a2e-127">It will likely contain failure information.</span></span>

<span data-ttu-id="99a2e-128">這些記錄檔包含個人識別資訊 (PII)，因此不會傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="99a2e-128">These log files contain personally identifiable information (PII) and so they're not sent to Microsoft.</span></span>

<span data-ttu-id="99a2e-129">Teams 可以自動啟動更新程序 (視原則而定)，使用者也可以移至其設定檔圖片 > [檢查更新] 手動檢查更新。</span><span class="sxs-lookup"><span data-stu-id="99a2e-129">Teams can automatically start the update process (depending on the policy) or users can manually check for updates by going to their profile picture > **Check for updates**.</span></span> <span data-ttu-id="99a2e-130">這兩種方法都使用下列事件順序。</span><span class="sxs-lookup"><span data-stu-id="99a2e-130">Both methods use the following sequence of events.</span></span>

1. <span data-ttu-id="99a2e-131">**檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="99a2e-131">**Check for updates**.</span></span> <span data-ttu-id="99a2e-132">Teams 提出 Web 要求，並包括目前的應用程式版本和部署環資訊。</span><span class="sxs-lookup"><span data-stu-id="99a2e-132">Teams makes a web request and includes the current app version and deployment ring information.</span></span> <span data-ttu-id="99a2e-133">此步驟的目標是取得下載連結。</span><span class="sxs-lookup"><span data-stu-id="99a2e-133">The goal of this step is to get the download link.</span></span> <span data-ttu-id="99a2e-134">此步驟的失敗會記錄在 Logs.txt 中。</span><span class="sxs-lookup"><span data-stu-id="99a2e-134">A failure at this step is logged in Logs.txt.</span></span>
2. <span data-ttu-id="99a2e-135">**下載更新**。</span><span class="sxs-lookup"><span data-stu-id="99a2e-135">**Download update**.</span></span> <span data-ttu-id="99a2e-136">Teams 使用步驟 1 取得的下載連結下載更新。</span><span class="sxs-lookup"><span data-stu-id="99a2e-136">Teams downloads the update by using the download link obtained from step 1.</span></span> <span data-ttu-id="99a2e-137">下載完成後，Teams 會呼叫 Update.exe 來暫存下載。</span><span class="sxs-lookup"><span data-stu-id="99a2e-137">When the download is complete, Teams calls Update.exe to stage the download.</span></span> <span data-ttu-id="99a2e-138">下載失敗也會記錄在 Logs.txt 中。</span><span class="sxs-lookup"><span data-stu-id="99a2e-138">A download failure is also logged in Logs.txt.</span></span>
3. <span data-ttu-id="99a2e-139">**暫存更新**。</span><span class="sxs-lookup"><span data-stu-id="99a2e-139">**Stage the update**.</span></span> <span data-ttu-id="99a2e-140">下載的內容會由 Update.exe 驗證並解壓縮到中間資料夾 %LocalAppData%\Microsoft\Teams\stage。</span><span class="sxs-lookup"><span data-stu-id="99a2e-140">The downloaded content is verified and unpacked into an intermediate folder, %LocalAppData%\Microsoft\Teams\stage), which is done by Update.exe.</span></span> <span data-ttu-id="99a2e-141">此步驟的失敗會記錄在 SquirrelTemp.log 中。</span><span class="sxs-lookup"><span data-stu-id="99a2e-141">Failures at this step are logged in SquirrelTemp.log.</span></span>
4. <span data-ttu-id="99a2e-142">**安裝更新**。</span><span class="sxs-lookup"><span data-stu-id="99a2e-142">**Install the update**.</span></span> <span data-ttu-id="99a2e-143">有多種方式可以啟動 Teams。</span><span class="sxs-lookup"><span data-stu-id="99a2e-143">There are multiple ways to start Teams.</span></span> <span data-ttu-id="99a2e-144">使用者登入時，系統會自動啟動 Teams，或者您也可以透過快速鍵啟動 Teams。</span><span class="sxs-lookup"><span data-stu-id="99a2e-144">The system automatically starts Teams when a user logs in or you can start Teams through a shortcut.</span></span> <span data-ttu-id="99a2e-145">在此步驟中，Update.exe 會檢查是否有暫存資料夾、再次驗證內容，以及執行檔案作業取消暫存應用程式。</span><span class="sxs-lookup"><span data-stu-id="99a2e-145">In this step, Update.exe checks for the presence of the staging folder, verifies the content again, and performs file operations to un-stage the app.</span></span> <span data-ttu-id="99a2e-146">%LocalAppData%\Microsoft\Teams\current 中的舊應用程式資料夾會備份到 %LocalAppData%\Microsoft\Teams\previous，而 stage 資料夾會重新命名為 "current"。</span><span class="sxs-lookup"><span data-stu-id="99a2e-146">The old application folder in %LocalAppData%\Microsoft\Teams\current is backed up to %LocalAppData%\Microsoft\Teams\previous and the stage folder is renamed to "current".</span></span> <span data-ttu-id="99a2e-147">此步驟的失敗會記錄在 SquirrelTemp.log 中。</span><span class="sxs-lookup"><span data-stu-id="99a2e-147">Failures at this step are logged in SquirrelTemp.log.</span></span>

<span data-ttu-id="99a2e-148">如果 SquirrelTemp.log 或 Logs.txt 沒有足夠資訊可判斷問題的根本原因，而您需要更多疑難排解問題的資訊，請移至[收集和分析應用程式記錄與系統記錄](#collect-and-analyze-application-and-system-logs)。</span><span class="sxs-lookup"><span data-stu-id="99a2e-148">If SquirrelTemp.log or Logs.txt don't contain sufficient information to determine the underlying cause and you need more information to troubleshoot the issue, go to [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

## <a name="collect-and-analyze-application-and-system-logs"></a><span data-ttu-id="99a2e-149">收集和分析應用程式記錄與系統記錄</span><span class="sxs-lookup"><span data-stu-id="99a2e-149">Collect and analyze application and system logs</span></span>

<span data-ttu-id="99a2e-150">本節將說明如何收集和分析應用程式記錄與系統記錄，以便取得更全面的資訊來進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="99a2e-150">This section describes how to collect and analyze application and system logs to get more comprehensive information to troubleshoot the issue.</span></span> <span data-ttu-id="99a2e-151">您可以使用 Sysinternals 工具來完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="99a2e-151">You'll use Sysinternals tools to complete these steps.</span></span> <span data-ttu-id="99a2e-152">若要深入了解，請參閱 [Windows Sysinternals](/sysinternals/)。</span><span class="sxs-lookup"><span data-stu-id="99a2e-152">To learn more, see [Windows Sysinternals](/sysinternals/).</span></span>

### <a name="collect-logs"></a><span data-ttu-id="99a2e-153">收集記錄</span><span class="sxs-lookup"><span data-stu-id="99a2e-153">Collect logs</span></span>

1. <span data-ttu-id="99a2e-154">下載 [Sysinternals 工具](https://download.sysinternals.com/files/SysinternalsSuite.zip)。</span><span class="sxs-lookup"><span data-stu-id="99a2e-154">Download the [Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip).</span></span>
2. <span data-ttu-id="99a2e-155">將 zip 檔解壓縮到本機磁碟機的 %TEMP% 資料夾。</span><span class="sxs-lookup"><span data-stu-id="99a2e-155">Extract the zip file to the %TEMP% folder on your local drive.</span></span>
3. <span data-ttu-id="99a2e-156">開啟命令提示字元並提升權限，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="99a2e-156">Open an elevated command prompt, and then do the following:</span></span>

    1. <span data-ttu-id="99a2e-157">執行下列命令移至您的 TEMP 資料夾：</span><span class="sxs-lookup"><span data-stu-id="99a2e-157">Run the following to go to your TEMP folder:</span></span>

        ```console
        cd /d %TEMP%
        ```
    2. <span data-ttu-id="99a2e-158">複製安裝記錄和應用程式記錄。</span><span class="sxs-lookup"><span data-stu-id="99a2e-158">Copy the setup and application logs.</span></span> <span data-ttu-id="99a2e-159">請注意，視失敗點而定，不一定會有其中某些記錄。</span><span class="sxs-lookup"><span data-stu-id="99a2e-159">Note that depending on the point of failure, some of these logs may not be present.</span></span>

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. <span data-ttu-id="99a2e-160">執行下列命令可取得開啟的控制代碼。</span><span class="sxs-lookup"><span data-stu-id="99a2e-160">Run the following to capture the open handles.</span></span>

        ```console
        handle > handles.txt
        ```

    4. <span data-ttu-id="99a2e-161">執行下列命令可取得開啟的 DLL。</span><span class="sxs-lookup"><span data-stu-id="99a2e-161">Run the following to capture the opened DLLs.</span></span>

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. <span data-ttu-id="99a2e-162">執行下列命令可取得正在執行的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="99a2e-162">Run the following to capture the drivers that are running.</span></span>

        ```console
        driverquery /v > driverquery.txt
        ```

    6. <span data-ttu-id="99a2e-163">執行下列命令可取得 Teams 資料夾的存取控制清單 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="99a2e-163">Run the following to capture the access control lists (ACLs) of the Teams folder.</span></span>

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a><span data-ttu-id="99a2e-164">分析記錄 (適用於進階使用者)</span><span class="sxs-lookup"><span data-stu-id="99a2e-164">Analyze logs (for advanced users)</span></span>

<span data-ttu-id="99a2e-165">失敗的更新會導致無法預期的應用程式行為。</span><span class="sxs-lookup"><span data-stu-id="99a2e-165">A failed update can result in unpredictable app behavior.</span></span> <span data-ttu-id="99a2e-166">例如，使用者可能無法結束 Teams、擁有的 Teams 版本過舊，或無法啟動 Teams。</span><span class="sxs-lookup"><span data-stu-id="99a2e-166">For example, users may be unable to exit Teams, have a stale version of Teams, or can't start Teams.</span></span> <span data-ttu-id="99a2e-167">如果您在更新過程中遇到問題，首先要從 SquirrelTemp.log 尋找原因。</span><span class="sxs-lookup"><span data-stu-id="99a2e-167">If you experience an issue during an update, the first place to look to find the cause is SquirrelTemp.log.</span></span> <span data-ttu-id="99a2e-168">以下是幾種不同類型的更新失敗 (從最常見到最不常見)，以及如何使用記錄分析並進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="99a2e-168">Here are the different types of update failures, listed from most common to least common, and how to analyze and troubleshoot them using logs.</span></span>

#### <a name="unable-to-exit-teams"></a><span data-ttu-id="99a2e-169">無法結束 Teams</span><span class="sxs-lookup"><span data-stu-id="99a2e-169">Unable to exit Teams</span></span>

<span data-ttu-id="99a2e-170">當 Teams 認為必須將自己更新為較新版本時，就會下載並暫存新的應用程式，然後等待機會在下次電腦閒置時自行重新啟動。</span><span class="sxs-lookup"><span data-stu-id="99a2e-170">As Teams determines that it needs to update itself to a newer version, it downloads and stages the new app, and then waits for an opportunity to restart itself the next time the machine is idle.</span></span> <span data-ttu-id="99a2e-171">此程序的一個常見問題是，當另一個處理程序或某個檔案系統驅動程式鎖住 Teams.exe 處理程序時，會導致 Teams.exe 無法結束。</span><span class="sxs-lookup"><span data-stu-id="99a2e-171">A common issue during this process is when another process or a file system driver locks up the Teams.exe process, which prevents Teams.exe from exiting.</span></span> <span data-ttu-id="99a2e-172">此時，Teams 應用程式就無法被新下載並暫存的應用程式取代。</span><span class="sxs-lookup"><span data-stu-id="99a2e-172">As a result, the Teams app can't be replaced by the newly-downloaded and staged app.</span></span>

<span data-ttu-id="99a2e-173">疑難排解提示：</span><span class="sxs-lookup"><span data-stu-id="99a2e-173">Troubleshooting tips:</span></span>

- <span data-ttu-id="99a2e-174">若要確認這就是您遇到的問題，請結束 Teams (在工作列上以右鍵按一下 Teams，然後按一下 [結束])。</span><span class="sxs-lookup"><span data-stu-id="99a2e-174">To confirm that is the issue that you're experiencing, quit Teams (right-click Teams on the task bar, and then click **Quit**).</span></span> <span data-ttu-id="99a2e-175">然後在 Windows 中開啟工作管理員，查看 Teams 執行個體是否仍在執行。</span><span class="sxs-lookup"><span data-stu-id="99a2e-175">Then, open Task Manager in Windows to see whether an instance of Teams is still running.</span></span>  
- <span data-ttu-id="99a2e-176">如果您不在發生此問題的電腦上，請檢查發生此問題的電腦收集的 SquirrelTemp.log，並尋找 "Program: Unable to terminate the process in the log" (程式: 無法終止記錄中的處理程序) 項目。</span><span class="sxs-lookup"><span data-stu-id="99a2e-176">If you’re not on the computer that's having this issue, inspect the SquirrelTemp.log collected from the computer that's experiencing this issue and look for a "Program: Unable to terminate the process in the log" entry.</span></span>
- <span data-ttu-id="99a2e-177">若要判斷導致 Teams 無法結束的原因，請查看 Dll.txt 和 Handles.txt 記錄。</span><span class="sxs-lookup"><span data-stu-id="99a2e-177">To determine what's preventing Teams.exe from exiting, look at the Dlls.txt and Handles.txt logs.</span></span> <span data-ttu-id="99a2e-178">這些記錄會告訴您導致 Teams 無法結束的處理程序。</span><span class="sxs-lookup"><span data-stu-id="99a2e-178">These tell you the processes that prevented Teams from exiting.</span></span>
- <span data-ttu-id="99a2e-179">導致 Teams 無法結束的另一個可能原因是核心模式檔案系統篩選器驅動程式。</span><span class="sxs-lookup"><span data-stu-id="99a2e-179">Another culprit that can prevent Teams from exiting is the kernel-mode file system filter driver.</span></span> <span data-ttu-id="99a2e-180">您可以使用 SysInternals 工具 [ProcDump](/sysinternals/downloads/procdump)，執行 ```procdump -mk <pid>``` (其中 <pid> 是從工作管理員取得的處理程序識別碼) 收集核心模式處理程序傾印。</span><span class="sxs-lookup"><span data-stu-id="99a2e-180">Use the SysInternals tool, [ProcDump](/sysinternals/downloads/procdump), to collect the kernel-mode process dump by running ```procdump -mk <pid>```, where <pid> is the process ID obtained from Task Manager.</span></span> <span data-ttu-id="99a2e-181">您也可以檢查 Driverquery.txt 記錄檔，查看可能干擾 Teams 的作用中篩選器驅動程式。</span><span class="sxs-lookup"><span data-stu-id="99a2e-181">You can also inspect the Driverquery.txt log file to see the active filter drivers that may interfere with Teams.</span></span>
- <span data-ttu-id="99a2e-182">若要從此狀態復原，請重新啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="99a2e-182">To recover from this state, restart the computer.</span></span>

#### <a name="file-permissions"></a><span data-ttu-id="99a2e-183">檔案權限</span><span class="sxs-lookup"><span data-stu-id="99a2e-183">File permissions</span></span>

<span data-ttu-id="99a2e-184">在整個安裝和更新程序中，Teams 會在使用者設定檔中建立許多子資料夾和檔案。</span><span class="sxs-lookup"><span data-stu-id="99a2e-184">Teams creates a number of subfolders and files in the user's profile throughout the installation and update process.</span></span> <span data-ttu-id="99a2e-185">由於應用程式和更新程式是以非提升權限的使用者身份執行，因此必須對下列資料夾授與讀取和寫入權限：</span><span class="sxs-lookup"><span data-stu-id="99a2e-185">Because the app and the updater runs as a non-elevated user, read and write permissions must be granted on the following folders:</span></span>

|<span data-ttu-id="99a2e-186">資料夾</span><span class="sxs-lookup"><span data-stu-id="99a2e-186">Folder</span></span>  |<span data-ttu-id="99a2e-187">使用者</span><span class="sxs-lookup"><span data-stu-id="99a2e-187">Used by</span></span>  |
|---------|---------|
|<span data-ttu-id="99a2e-188">%LocalAppData%\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="99a2e-188">%LocalAppData%\SquirrelTemp</span></span>     | <span data-ttu-id="99a2e-189">Teams 安裝程式 (例如，Teams_Windows_x64.exe) 在安裝階段使用</span><span class="sxs-lookup"><span data-stu-id="99a2e-189">Teams installer (for example, Teams_Windows_x64.exe) during installation phase</span></span>        |
|<span data-ttu-id="99a2e-190">%LocalAppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="99a2e-190">%LocalAppData%\Microsoft\Teams</span></span>  | <span data-ttu-id="99a2e-191">Teams 更新程式 (Update.exe) 在更新程序中用來擷取並暫存應用程式套件</span><span class="sxs-lookup"><span data-stu-id="99a2e-191">Teams updater (Update.exe) to extract and stage the app package during update process</span></span>        |
|<span data-ttu-id="99a2e-192">%AppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="99a2e-192">%AppData%\Microsoft\Teams</span></span>   |  <span data-ttu-id="99a2e-193">Teams 應用程式 (Teams.exe) 用來儲存設定、應用程式狀態和 (預先暫存的) 已下載更新套件</span><span class="sxs-lookup"><span data-stu-id="99a2e-193">Teams app (Teams.exe) to save settings, app states, and the (pre-staged) downloaded update package</span></span>       |

<span data-ttu-id="99a2e-194">如果 Teams 因為無法寫入檔案而遭到拒絕存取，另一個軟體應用程式可能會產生干擾，或者安全性描述元項目可能會限制資料夾的寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="99a2e-194">If Teams is denied access because it can't write to a file, another software application may be interfering or a security descriptor entry may be limiting write access to a folder.</span></span>

<span data-ttu-id="99a2e-195">疑難排解提示：</span><span class="sxs-lookup"><span data-stu-id="99a2e-195">Troubleshooting tips:</span></span>

- <span data-ttu-id="99a2e-196">在 SquirrelTemp.log 或 Logs.txt 中尋找 "access denied" (拒絕存取) 的證據。</span><span class="sxs-lookup"><span data-stu-id="99a2e-196">Look for "access denied" evidence in SquirrelTemp.log or Logs.txt.</span></span> <span data-ttu-id="99a2e-197">檢查這些檔案，查看是否曾經嘗試寫入檔案但失敗。</span><span class="sxs-lookup"><span data-stu-id="99a2e-197">Check these files to see whether there was an attempt to write to a file that failed.</span></span>
- <span data-ttu-id="99a2e-198">開啟 Icacls,txt，尋找由非系統管理員的使用者封鎖寫入作業的有效存取控制項目 (ACE)。這通常會在其中一個 DACL 項目中。</span><span class="sxs-lookup"><span data-stu-id="99a2e-198">Open Icacls.txt and look for the effective access control entry (ACE) that blocks write operations by a user who is not an admin. Typically, this is in one of the DACL entries.</span></span> <span data-ttu-id="99a2e-199">如需詳細資訊，請參閱 [icacls 文件](/windows-server/administration/windows-commands/icacls)。</span><span class="sxs-lookup"><span data-stu-id="99a2e-199">For more information, see the [icacls documentation](/windows-server/administration/windows-commands/icacls).</span></span>

#### <a name="file-corrupted"></a><span data-ttu-id="99a2e-200">檔案損毀</span><span class="sxs-lookup"><span data-stu-id="99a2e-200">File corrupted</span></span>

<span data-ttu-id="99a2e-201">在某些情況下，加密軟體可以變更 %LocalAppData%\Microsoft\Teams 資料夾中的檔案，這可能會導致 Teams 無法啟動。</span><span class="sxs-lookup"><span data-stu-id="99a2e-201">In some cases, encryption software can change files in the %LocalAppData%\Microsoft\Teams folder, which can prevent Teams from starting.</span></span> <span data-ttu-id="99a2e-202">即使應用程式沒有更新，也可能會發生這個問題。</span><span class="sxs-lookup"><span data-stu-id="99a2e-202">This can happen at any time, even when the app isn't being updated.</span></span> <span data-ttu-id="99a2e-203">不幸的是，當檔案損毀時，從此狀態復原的唯一方法是解除安裝 Teams 後再重新安裝。</span><span class="sxs-lookup"><span data-stu-id="99a2e-203">Unfortunately, when a file is corrupted, the only way to recover from this state is to uninstall and re-install Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="99a2e-204">如果您無法使用上述任何步驟判斷問題的根源，您可以嘗試使用 [Process Monitor](/sysinternals/downloads/procmon) 工作階段。</span><span class="sxs-lookup"><span data-stu-id="99a2e-204">If you can't determine the underlying cause of the issue by using any of these steps, you may want to try a [Process Monitor](/sysinternals/downloads/procmon) session.</span></span> <span data-ttu-id="99a2e-205">Process Monitor 是一種 Sysinternals 工具，可記錄對登錄和檔案系統的存取。</span><span class="sxs-lookup"><span data-stu-id="99a2e-205">Process Monitor is a Sysinternals tool that records access to the registry and file system.</span></span>

## <a name="related-topics"></a><span data-ttu-id="99a2e-206">相關主題</span><span class="sxs-lookup"><span data-stu-id="99a2e-206">Related topics</span></span>

- [<span data-ttu-id="99a2e-207">取得 Teams 用戶端</span><span class="sxs-lookup"><span data-stu-id="99a2e-207">Get clients for Teams</span></span>](get-clients.md)
- [<span data-ttu-id="99a2e-208">Teams 用戶端更新</span><span class="sxs-lookup"><span data-stu-id="99a2e-208">Teams client updates</span></span>](teams-client-update.md)
- [<span data-ttu-id="99a2e-209">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="99a2e-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)