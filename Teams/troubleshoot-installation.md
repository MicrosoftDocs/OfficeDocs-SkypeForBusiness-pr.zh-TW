---
title: 針對 Windows 上的 Microsoft 團隊安裝和更新問題進行疑難排解
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何針對 Windows 上的小組桌面用戶端應用程式的安裝與更新問題進行疑難排解。
ms.openlocfilehash: f47edf351d6a55f57977fee823d670b749896049
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837623"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a><span data-ttu-id="4018f-103">針對 Windows 上的 Microsoft 團隊安裝和更新問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="4018f-103">Troubleshoot Microsoft Teams installation and update issues on Windows</span></span>

<span data-ttu-id="4018f-104">本文提供如何診斷和疑難排解 Windows 上執行之小組桌面用戶端應用程式的安裝與更新問題的指導方針。</span><span class="sxs-lookup"><span data-stu-id="4018f-104">This article provides guidance for how to diagnose and troubleshoot installation and update issues for the Teams desktop client app running on Windows.</span></span>

## <a name="check-whether-teams-is-updated-successfully"></a><span data-ttu-id="4018f-105">檢查團隊是否已順利更新</span><span class="sxs-lookup"><span data-stu-id="4018f-105">Check whether Teams is updated successfully</span></span>

<span data-ttu-id="4018f-106">請依照下列步驟檢查是否已成功安裝團隊更新。</span><span class="sxs-lookup"><span data-stu-id="4018f-106">Follow these steps to check whether a Teams update is successfully installed.</span></span>

1. <span data-ttu-id="4018f-107">在 [團隊] 中，選取您的個人檔案圖片，然後按一下 [**關於** > **版本**]。</span><span class="sxs-lookup"><span data-stu-id="4018f-107">In Teams, select your profile picture, and then click **About** > **Version**.</span></span>
2. <span data-ttu-id="4018f-108">在相同的功能表上，按一下 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="4018f-108">On the same menu, click **Check for updates**.</span></span>
3. <span data-ttu-id="4018f-109">請等候應用程式頂端的橫幅，指出需要小組的 [重新整理]。</span><span class="sxs-lookup"><span data-stu-id="4018f-109">Wait for the banner at the top of the app to indicate that a “refresh” of Teams is needed.</span></span> <span data-ttu-id="4018f-110">此程式會在此程式下載新的團隊版本之後，大約一分鐘就會顯示該連結。</span><span class="sxs-lookup"><span data-stu-id="4018f-110">The link should be shown about a minute later as this process downloads the new version of Teams.</span></span> <span data-ttu-id="4018f-111">[橫幅] 也會讓您知道是否已執行最新版本（在這種情況下），不需要進行任何更新。</span><span class="sxs-lookup"><span data-stu-id="4018f-111">The banner also lets you know if you’re already running the latest version in which case, no update is necessary.</span></span>
4. <span data-ttu-id="4018f-112">按一下橫幅中的 [重新整理] 連結。</span><span class="sxs-lookup"><span data-stu-id="4018f-112">Click the refresh link in the banner.</span></span>
5. <span data-ttu-id="4018f-113">等到小組重新開機之後，再重複步驟1，查看應用程式是否已更新。</span><span class="sxs-lookup"><span data-stu-id="4018f-113">Wait until Teams restarts, and then repeat step 1 to see whether the app is updated.</span></span>

<span data-ttu-id="4018f-114">如果您看到失敗訊息，或版本號碼與步驟4中的相同，則更新程式失敗。</span><span class="sxs-lookup"><span data-stu-id="4018f-114">If you see a failure message or if the version number is the same as in step 4, the update process failed.</span></span>

## <a name="troubleshoot-installation-and-update-issues"></a><span data-ttu-id="4018f-115">安裝和更新問題疑難排解</span><span class="sxs-lookup"><span data-stu-id="4018f-115">Troubleshoot installation and update issues</span></span>

### <a name="troubleshoot-installation-issues"></a><span data-ttu-id="4018f-116">疑難排解安裝問題</span><span class="sxs-lookup"><span data-stu-id="4018f-116">Troubleshoot installation issues</span></span>

<span data-ttu-id="4018f-117">安裝團隊後，小組安裝程式會將事件順序記錄到%LocalAppData%\SquirrelTemp\SquirrelSetup.log。</span><span class="sxs-lookup"><span data-stu-id="4018f-117">When Teams is installed, the Teams installer logs the sequence of events to %LocalAppData%\SquirrelTemp\SquirrelSetup.log.</span></span> <span data-ttu-id="4018f-118">您要尋找的第一件事是在記錄結尾附近出現錯誤訊息或呼叫堆疊。</span><span class="sxs-lookup"><span data-stu-id="4018f-118">The first thing to look for is an error message or a call stack near the end of the log.</span></span> <span data-ttu-id="4018f-119">請注意，記錄開頭的呼叫堆疊可能並不表示存在安裝問題。</span><span class="sxs-lookup"><span data-stu-id="4018f-119">Note that call stacks at the beginning of the log may not mean that an installation issue exists.</span></span> <span data-ttu-id="4018f-120">您可以更輕鬆地將記錄與記錄（即使在另一部電腦上）進行比較，以查看預期情況。</span><span class="sxs-lookup"><span data-stu-id="4018f-120">It can be easier to compare your log against the log from a successful installation (even on another machine) to see what's expected.</span></span>

<span data-ttu-id="4018f-121">如果 SquirrelSetup 沒有指出原因，或者您需要進一步的資訊來排查問題，請參閱[收集及分析應用程式和系統記錄](#collect-and-analyze-application-and-system-logs)。</span><span class="sxs-lookup"><span data-stu-id="4018f-121">If SquirrelSetup.log doesn't indicate the cause or if you need more information to troubleshoot the issue, see [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

### <a name="troubleshoot-update-issues"></a><span data-ttu-id="4018f-122">疑難排解更新問題</span><span class="sxs-lookup"><span data-stu-id="4018f-122">Troubleshoot update issues</span></span>

<span data-ttu-id="4018f-123">成功安裝團隊後，日誌位置會從%LocalAppData%\SquirrelTemp 切換為%AppData%\Microsoft\Teams。</span><span class="sxs-lookup"><span data-stu-id="4018f-123">When Teams is successfully installed, the log location switches from %LocalAppData%\SquirrelTemp to %AppData%\Microsoft\Teams.</span></span> <span data-ttu-id="4018f-124">在這個位置，有兩個 SquirrelSetup 記錄檔案： [感興趣]、[記錄] 和 [記錄 .txt]。</span><span class="sxs-lookup"><span data-stu-id="4018f-124">At this location, there are two log files of interest, SquirrelSetup.log and logs.txt.</span></span>

- <span data-ttu-id="4018f-125">此位置的 SquirrelSetup 檔案是由 update.exe 所撰寫，後者是一個可供使用團隊 app 的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="4018f-125">The SquirrelSetup.log file at this location is written by Update.exe, which is an executable that services the Teams app.</span></span>
- <span data-ttu-id="4018f-126">[小組] 應用程式（特別是 "團隊 .exe]）會使用 [Logs] （記錄 .txt）來記錄重要的應用程式事件。</span><span class="sxs-lookup"><span data-stu-id="4018f-126">The Logs.txt file is used by the Teams app (specifically Teams.exe) to record significant application events.</span></span> <span data-ttu-id="4018f-127">它可能會包含失敗資訊。</span><span class="sxs-lookup"><span data-stu-id="4018f-127">It will likely contain failure information.</span></span>

<span data-ttu-id="4018f-128">這些記錄檔包含個人可識別資訊（PII），因此不會傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="4018f-128">These log files contain personally identifiable information (PII) and so they're not sent to Microsoft.</span></span>

<span data-ttu-id="4018f-129">小組可以自動啟動更新程式（視原則而定），或者，使用者可以移至他們的個人檔案圖片 >**檢查更新**，以手動檢查更新。</span><span class="sxs-lookup"><span data-stu-id="4018f-129">Teams can automatically start the update process (depending on the policy) or users can manually check for updates by going to their profile picture > **Check for updates**.</span></span> <span data-ttu-id="4018f-130">這兩種方法都使用下列事件順序。</span><span class="sxs-lookup"><span data-stu-id="4018f-130">Both methods use the following sequence of events.</span></span>

1. <span data-ttu-id="4018f-131">**檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="4018f-131">**Check for updates**.</span></span> <span data-ttu-id="4018f-132">小組提出 web 要求，並包含目前的 app 版本和部署鈴聲資訊。</span><span class="sxs-lookup"><span data-stu-id="4018f-132">Teams makes a web request and includes the current app version and deployment ring information.</span></span> <span data-ttu-id="4018f-133">此步驟的目標是取得下載連結。</span><span class="sxs-lookup"><span data-stu-id="4018f-133">The goal of this step is to get the download link.</span></span> <span data-ttu-id="4018f-134">此步驟的失敗會記錄在 Logs 中。</span><span class="sxs-lookup"><span data-stu-id="4018f-134">A failure at this step is logged in Logs.txt.</span></span>
2. <span data-ttu-id="4018f-135">**下載更新**。</span><span class="sxs-lookup"><span data-stu-id="4018f-135">**Download update**.</span></span> <span data-ttu-id="4018f-136">團隊會使用從步驟1取得的下載連結來下載更新。</span><span class="sxs-lookup"><span data-stu-id="4018f-136">Teams downloads the update by using the download link obtained from step 1.</span></span> <span data-ttu-id="4018f-137">下載完成後，小組會呼叫 update.exe 來暫存下載。</span><span class="sxs-lookup"><span data-stu-id="4018f-137">When the download is complete, Teams calls Update.exe to stage the download.</span></span> <span data-ttu-id="4018f-138">您也會在 [readme.txt] 中記錄下載失敗。</span><span class="sxs-lookup"><span data-stu-id="4018f-138">A download failure is also logged in Logs.txt.</span></span>
3. <span data-ttu-id="4018f-139">**暫存更新**。</span><span class="sxs-lookup"><span data-stu-id="4018f-139">**Stage the update**.</span></span> <span data-ttu-id="4018f-140">已下載的內容會驗證並解壓縮至中間資料夾（%LocalAppData%\Microsoft\Teams\stage），這是由 update.exe 完成。</span><span class="sxs-lookup"><span data-stu-id="4018f-140">The downloaded content is verified and unpacked into an intermediate folder, %LocalAppData%\Microsoft\Teams\stage), which is done by Update.exe.</span></span> <span data-ttu-id="4018f-141">此步驟的失敗會記錄在 SquirrelTemp 中。</span><span class="sxs-lookup"><span data-stu-id="4018f-141">Failures at this step are logged in SquirrelTemp.log.</span></span>
4. <span data-ttu-id="4018f-142">**安裝更新**。</span><span class="sxs-lookup"><span data-stu-id="4018f-142">**Install the update**.</span></span> <span data-ttu-id="4018f-143">有多種方式可開始團隊。</span><span class="sxs-lookup"><span data-stu-id="4018f-143">There are multiple ways to start Teams.</span></span> <span data-ttu-id="4018f-144">當使用者登入時，系統會自動啟動小組，或者您可以透過快速鍵啟動團隊。</span><span class="sxs-lookup"><span data-stu-id="4018f-144">The system automatically starts Teams when a user logs in or you can start Teams through a shortcut.</span></span> <span data-ttu-id="4018f-145">在這個步驟中，update.exe 會檢查暫存資料夾是否存在、再次驗證內容，並執行檔案作業來取消階段 app。</span><span class="sxs-lookup"><span data-stu-id="4018f-145">In this step, Update.exe checks for the presence of the staging folder, verifies the content again, and performs file operations to un-stage the app.</span></span> <span data-ttu-id="4018f-146">%LocalAppData%\Microsoft\Teams\current 中的舊應用程式資料夾會備份到%LocalAppData%\Microsoft\Teams\previous，而階段資料夾會重新命名為「目前」。</span><span class="sxs-lookup"><span data-stu-id="4018f-146">The old application folder in %LocalAppData%\Microsoft\Teams\current is backed up to %LocalAppData%\Microsoft\Teams\previous and the stage folder is renamed to "current".</span></span> <span data-ttu-id="4018f-147">此步驟的失敗會記錄在 SquirrelTemp 中。</span><span class="sxs-lookup"><span data-stu-id="4018f-147">Failures at this step are logged in SquirrelTemp.log.</span></span>

<span data-ttu-id="4018f-148">如果 SquirrelTemp 或 Logs 沒有足夠的資訊來判斷基本原因，而您需要更多的資訊來排查問題，請移至[收集及分析應用程式和系統記錄](#collect-and-analyze-application-and-system-logs)。</span><span class="sxs-lookup"><span data-stu-id="4018f-148">If SquirrelTemp.log or Logs.txt don't contain sufficient information to determine the underlying cause and you need more information to troubleshoot the issue, go to [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

## <a name="collect-and-analyze-application-and-system-logs"></a><span data-ttu-id="4018f-149">收集及分析應用程式與系統記錄</span><span class="sxs-lookup"><span data-stu-id="4018f-149">Collect and analyze application and system logs</span></span>

<span data-ttu-id="4018f-150">本節說明如何收集及分析應用程式和系統記錄，以取得更完整的資訊來排查問題。</span><span class="sxs-lookup"><span data-stu-id="4018f-150">This section describes how to collect and analyze application and system logs to get more comprehensive information to troubleshoot the issue.</span></span> <span data-ttu-id="4018f-151">您將會使用 Sysinternals 工具來完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="4018f-151">You'll use Sysinternals tools to complete these steps.</span></span> <span data-ttu-id="4018f-152">若要深入瞭解，請參閱[Windows Sysinternals](https://docs.microsoft.com/sysinternals/)。</span><span class="sxs-lookup"><span data-stu-id="4018f-152">To learn more, see [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).</span></span>

### <a name="collect-logs"></a><span data-ttu-id="4018f-153">收集記錄</span><span class="sxs-lookup"><span data-stu-id="4018f-153">Collect logs</span></span>

1. <span data-ttu-id="4018f-154">下載[Sysinternals 工具](https://download.sysinternals.com/files/SysinternalsSuite.zip)。</span><span class="sxs-lookup"><span data-stu-id="4018f-154">Download the [Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip).</span></span>
2. <span data-ttu-id="4018f-155">將 zip 檔案解壓縮至本機磁片磁碟機上的% TEMP% 資料夾。</span><span class="sxs-lookup"><span data-stu-id="4018f-155">Extract the zip file to the %TEMP% folder on your local drive.</span></span>
3. <span data-ttu-id="4018f-156">開啟提升許可權的命令提示字元，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4018f-156">Open an elevated command prompt, and then do the following:</span></span>

    1. <span data-ttu-id="4018f-157">執行下列動作，移至您的 TEMP 資料夾：</span><span class="sxs-lookup"><span data-stu-id="4018f-157">Run the following to go to your TEMP folder:</span></span>

        ```
        cd /d %TEMP%
        ```
    2. <span data-ttu-id="4018f-158">複製設定和應用程式記錄。</span><span class="sxs-lookup"><span data-stu-id="4018f-158">Copy the setup and application logs.</span></span> <span data-ttu-id="4018f-159">請注意，根據失敗的點，可能不會顯示部分記錄。</span><span class="sxs-lookup"><span data-stu-id="4018f-159">Note that depending on the point of failure, some of these logs may not be present.</span></span>

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. <span data-ttu-id="4018f-160">執行下列動作來捕獲開啟的控點。</span><span class="sxs-lookup"><span data-stu-id="4018f-160">Run the following to capture the open handles.</span></span>

        ```
        handle > handles.txt
        ```

    4. <span data-ttu-id="4018f-161">執行下列動作來捕獲開啟的 Dll。</span><span class="sxs-lookup"><span data-stu-id="4018f-161">Run the following to capture the opened DLLs.</span></span>

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. <span data-ttu-id="4018f-162">執行下列動作來捕獲正在執行的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="4018f-162">Run the following to capture the drivers that are running.</span></span>

        ```
        driverquery /v > driverquery.txt
        ```

    6. <span data-ttu-id="4018f-163">執行下列動作來捕獲 [小組] 資料夾的存取控制清單（Acl）。</span><span class="sxs-lookup"><span data-stu-id="4018f-163">Run the following to capture the access control lists (ACLs) of the Teams folder.</span></span>

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a><span data-ttu-id="4018f-164">分析記錄（適用于高級使用者）</span><span class="sxs-lookup"><span data-stu-id="4018f-164">Analyze logs (for advanced users)</span></span>

<span data-ttu-id="4018f-165">失敗的更新可能會導致無法預測的 app 行為。</span><span class="sxs-lookup"><span data-stu-id="4018f-165">A failed update can result in unpredictable app behavior.</span></span> <span data-ttu-id="4018f-166">例如，使用者可能無法結束團隊、擁有陳舊的團隊版本，或是無法啟動團隊。</span><span class="sxs-lookup"><span data-stu-id="4018f-166">For example, users may be unable to exit Teams, have a stale version of Teams, or can't start Teams.</span></span> <span data-ttu-id="4018f-167">如果您在更新期間遇到問題，我們首先要尋找的位置是 SquirrelTemp 記錄。</span><span class="sxs-lookup"><span data-stu-id="4018f-167">If you experience an issue during an update, the first place to look to find the cause is SquirrelTemp.log.</span></span> <span data-ttu-id="4018f-168">以下是不同類型的更新失敗（從最常見到最常見），以及如何使用記錄進行分析和疑難排解。</span><span class="sxs-lookup"><span data-stu-id="4018f-168">Here are the different types of update failures, listed from most common to least common, and how to analyze and troubleshoot them using logs.</span></span>

#### <a name="unable-to-exit-teams"></a><span data-ttu-id="4018f-169">無法結束團隊</span><span class="sxs-lookup"><span data-stu-id="4018f-169">Unable to exit Teams</span></span>

<span data-ttu-id="4018f-170">當團隊認為需要將本身更新為較新的版本時，它會下載並階段新的應用程式，然後在下次電腦空閒時等待商機自行重新開機。</span><span class="sxs-lookup"><span data-stu-id="4018f-170">As Teams determines that it needs to update itself to a newer version, it downloads and stages the new app, and then waits for an opportunity to restart itself the next time the machine is idle.</span></span> <span data-ttu-id="4018f-171">這個程式的常見問題是，另一個進程或檔案系統驅動程式鎖定了團隊 .exe 進程，這會使球隊無法退出。</span><span class="sxs-lookup"><span data-stu-id="4018f-171">A common issue during this process is when another process or a file system driver locks up the Teams.exe process, which prevents Teams.exe from exiting.</span></span> <span data-ttu-id="4018f-172">因此，新下載和暫存的應用程式無法取代團隊 app。</span><span class="sxs-lookup"><span data-stu-id="4018f-172">As a result, the Teams app can't be replaced by the newly-downloaded and staged app.</span></span>

<span data-ttu-id="4018f-173">疑難排解秘訣：</span><span class="sxs-lookup"><span data-stu-id="4018f-173">Troubleshooting tips:</span></span>

- <span data-ttu-id="4018f-174">若要確認是否為您遇到的問題，請結束小組（在工作列上按一下 [小組]，然後按一下 [結束 **]）。**</span><span class="sxs-lookup"><span data-stu-id="4018f-174">To confirm that is the issue that you're experiencing, quit Teams (right-click Teams on the task bar, and then click **Quit**).</span></span> <span data-ttu-id="4018f-175">然後，在 Windows 中開啟 [工作管理員]，查看團隊的實例是否仍在執行。</span><span class="sxs-lookup"><span data-stu-id="4018f-175">Then, open Task Manager in Windows to see whether an instance of Teams is still running.</span></span>  
- <span data-ttu-id="4018f-176">如果您不在遇到此問題的電腦上，請檢查從遇到此問題的電腦收集的 SquirrelTemp，並尋找「程式：無法終止記錄中的進程」專案。</span><span class="sxs-lookup"><span data-stu-id="4018f-176">If you’re not on the computer that's having this issue, inspect the SquirrelTemp.log collected from the computer that's experiencing this issue and look for a "Program: Unable to terminate the process in the log" entry.</span></span>
- <span data-ttu-id="4018f-177">若要判斷禁止團隊成員退出，請查看 Dll 並處理 .txt 記錄。</span><span class="sxs-lookup"><span data-stu-id="4018f-177">To determine what's preventing Teams.exe from exiting, look at the Dlls.txt and Handles.txt logs.</span></span> <span data-ttu-id="4018f-178">這些程式會告訴您禁止小組退出的進程。</span><span class="sxs-lookup"><span data-stu-id="4018f-178">These tell you the processes that prevented Teams from exiting.</span></span>
- <span data-ttu-id="4018f-179">可防止團隊退出的另一個原因是核心模式檔案系統篩選驅動程式。</span><span class="sxs-lookup"><span data-stu-id="4018f-179">Another culprit that can prevent Teams from exiting is the kernel-mode file system filter driver.</span></span> <span data-ttu-id="4018f-180">您可以使用 SysInternals 工具（ [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump)）來透過執行來收集核心模式進程轉儲```procdump -mk <pid>```，其中<pid> ，其中是從工作管理員取得的進程 ID。</span><span class="sxs-lookup"><span data-stu-id="4018f-180">Use the SysInternals tool, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), to collect the kernel-mode process dump by running ```procdump -mk <pid>```, where <pid> is the process ID obtained from Task Manager.</span></span> <span data-ttu-id="4018f-181">您也可以檢查 Driverquery 記錄檔，以查看可能會干擾小組的活動篩選驅動程式。</span><span class="sxs-lookup"><span data-stu-id="4018f-181">You can also inspect the Driverquery.txt log file to see the active filter drivers that may interfere with Teams.</span></span>
- <span data-ttu-id="4018f-182">若要從這種狀態復原，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="4018f-182">To recover from this state, restart the computer.</span></span>

#### <a name="file-permissions"></a><span data-ttu-id="4018f-183">檔案許可權</span><span class="sxs-lookup"><span data-stu-id="4018f-183">File permissions</span></span>

<span data-ttu-id="4018f-184">小組會在整個安裝和更新程式中，在使用者的設定檔中建立許多子資料夾和檔案。</span><span class="sxs-lookup"><span data-stu-id="4018f-184">Teams creates a number of subfolders and files in the user's profile throughout the installation and update process.</span></span> <span data-ttu-id="4018f-185">因為應用程式和更新程式是以非提升的使用者身分執行，所以必須在下列資料夾上授予讀取和寫入權限：</span><span class="sxs-lookup"><span data-stu-id="4018f-185">Because the app and the updater runs as a non-elevated user, read and write permissions must be granted on the following folders:</span></span>

|<span data-ttu-id="4018f-186">資料夾</span><span class="sxs-lookup"><span data-stu-id="4018f-186">Folder</span></span>  |<span data-ttu-id="4018f-187">消費者</span><span class="sxs-lookup"><span data-stu-id="4018f-187">Used by</span></span>  |
|---------|---------|
|<span data-ttu-id="4018f-188">%LocalAppData%\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="4018f-188">%LocalAppData%\SquirrelTemp</span></span>     | <span data-ttu-id="4018f-189">在安裝階段中的團隊安裝程式（例如 Teams_Windows_x64 .exe）</span><span class="sxs-lookup"><span data-stu-id="4018f-189">Teams installer (for example, Teams_Windows_x64.exe) during installation phase</span></span>        |
|<span data-ttu-id="4018f-190">%LocalAppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="4018f-190">%LocalAppData%\Microsoft\Teams</span></span>  | <span data-ttu-id="4018f-191">小組更新程式（更新 .exe），以在更新程式期間提取並暫存應用程式套件</span><span class="sxs-lookup"><span data-stu-id="4018f-191">Teams updater (Update.exe) to extract and stage the app package during update process</span></span>        |
|<span data-ttu-id="4018f-192">%AppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="4018f-192">%AppData%\Microsoft\Teams</span></span>   |  <span data-ttu-id="4018f-193">[小組] app （團隊 .exe）來儲存設定、應用程式狀態及（預先暫存的）已下載的更新套件</span><span class="sxs-lookup"><span data-stu-id="4018f-193">Teams app (Teams.exe) to save settings, app states, and the (pre-staged) downloaded update package</span></span>       |

<span data-ttu-id="4018f-194">如果團隊由於無法寫入檔案而遭到拒絕存取，可能會有另一個軟體應用程式受到干擾，或安全性描述項專案可能會限制對資料夾的寫入權。</span><span class="sxs-lookup"><span data-stu-id="4018f-194">If Teams is denied access because it can't write to a file, another software application may be interfering or a security descriptor entry may be limiting write access to a folder.</span></span>

<span data-ttu-id="4018f-195">疑難排解秘訣：</span><span class="sxs-lookup"><span data-stu-id="4018f-195">Troubleshooting tips:</span></span>

- <span data-ttu-id="4018f-196">在 SquirrelTemp 或 Logs 中尋找「拒絕存取」證據。</span><span class="sxs-lookup"><span data-stu-id="4018f-196">Look for "access denied" evidence in SquirrelTemp.log or Logs.txt.</span></span> <span data-ttu-id="4018f-197">檢查這些檔案，查看是否有人嘗試寫入失敗的檔案。</span><span class="sxs-lookup"><span data-stu-id="4018f-197">Check these files to see whether there was an attempt to write to a file that failed.</span></span>
- <span data-ttu-id="4018f-198">開啟 Icacls，並尋找有效的存取控制專案（ACE）來封鎖由非管理員的使用者寫入作業。這通常是在其中一個 DACL 專案中。</span><span class="sxs-lookup"><span data-stu-id="4018f-198">Open Icacls.txt and look for the effective access control entry (ACE) that blocks write operations by a user who is not an admin. Typically, this is in one of the DACL entries.</span></span> <span data-ttu-id="4018f-199">如需詳細資訊，請參閱[icacls 檔](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)。</span><span class="sxs-lookup"><span data-stu-id="4018f-199">For more information, see the [icacls documentation](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).</span></span>

#### <a name="file-corrupted"></a><span data-ttu-id="4018f-200">檔損毀</span><span class="sxs-lookup"><span data-stu-id="4018f-200">File corrupted</span></span>

<span data-ttu-id="4018f-201">在某些情況下，加密軟體可以變更%LocalAppData%\Microsoft\Teams 資料夾中的檔案，這可以避免小組的啟動。</span><span class="sxs-lookup"><span data-stu-id="4018f-201">In some cases, encryption software can change files in the %LocalAppData%\Microsoft\Teams folder, which can prevent Teams from starting.</span></span> <span data-ttu-id="4018f-202">即使沒有更新應用程式，也可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="4018f-202">This can happen at any time, even when the app isn't being updated.</span></span> <span data-ttu-id="4018f-203">遺憾的是，當檔案損毀時，從這種狀態復原的唯一方式就是卸載並重新安裝小組。</span><span class="sxs-lookup"><span data-stu-id="4018f-203">Unfortunately, when a file is corrupted, the only way to recover from this state is to uninstall and re-install Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="4018f-204">如果您無法使用上述任何步驟來判斷問題的根本原因，您可能會想要嘗試[進程監視器](https://docs.microsoft.com/sysinternals/downloads/procmon)會話。</span><span class="sxs-lookup"><span data-stu-id="4018f-204">If you can't determine the underlying cause of the issue by using any of these steps, you may want to try a [Process Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) session.</span></span> <span data-ttu-id="4018f-205">[進程監視器] 是一種 Sysinternals 工具，可記錄對註冊表和檔案系統的存取權。</span><span class="sxs-lookup"><span data-stu-id="4018f-205">Process Monitor is a Sysinternals tool that records access to the registry and file system.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4018f-206">相關主題</span><span class="sxs-lookup"><span data-stu-id="4018f-206">Related topics</span></span>

- [<span data-ttu-id="4018f-207">取得 Teams 用戶端</span><span class="sxs-lookup"><span data-stu-id="4018f-207">Get clients for Teams</span></span>](get-clients.md)
- [<span data-ttu-id="4018f-208">Teams 用戶端更新</span><span class="sxs-lookup"><span data-stu-id="4018f-208">Teams client updates</span></span>](teams-client-update.md)