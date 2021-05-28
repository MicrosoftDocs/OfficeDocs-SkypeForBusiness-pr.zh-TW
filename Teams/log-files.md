---
title: 使用記錄檔案疑難排解Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 瞭解由 Microsoft Teams 產生的 Debug、Media 和桌面記錄、可以在哪裡找到這些記錄，以及這些記錄如何協助監控和疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a18dbef0441055c1202c2b77ce4f8af87040e561
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689691"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="05336-103">使用記錄檔案來監控和疑難排解Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="05336-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="05336-104">用戶端自動產生的記錄檔案類型有三種，可運用這些記錄檔案以協助監控和疑難排解Teams：</span><span class="sxs-lookup"><span data-stu-id="05336-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="05336-105">調試記錄</span><span class="sxs-lookup"><span data-stu-id="05336-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="05336-106">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="05336-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="05336-107">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="05336-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="05336-108">本文將說明這些記錄及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="05336-108">This article describes these logs and how they are used.</span></span> <span data-ttu-id="05336-109">有關疑難排解特定問題的資訊，請參閱：Teams[疑難排解](/MicrosoftTeams/troubleshoot/teams)。</span><span class="sxs-lookup"><span data-stu-id="05336-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="05336-110">如需如何與支援人員聯繫的資訊，請參閱 [取得支援](/microsoft-365/business-video/get-help-support)。</span><span class="sxs-lookup"><span data-stu-id="05336-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span> <span data-ttu-id="05336-111">使用 Microsoft 支援服務建立支援要求時，支援工程師需要調試記錄。</span><span class="sxs-lookup"><span data-stu-id="05336-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="05336-112">建立支援要求之前，先將調試記錄放在手邊，Microsoft 就會快速開始疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="05336-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="05336-113">**媒體** 或 **桌面** 記錄只有在 Microsoft 要求時才能使用。</span><span class="sxs-lookup"><span data-stu-id="05336-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="05336-114">在本文中，" **調試記錄** "一詞是指用於疑難排解的記錄。</span><span class="sxs-lookup"><span data-stu-id="05336-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="05336-115">不過，這些記錄產生的檔案名稱中會包含診斷 **記錄** 一詞。</span><span class="sxs-lookup"><span data-stu-id="05336-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

## <a name="collect-and-enable-logging"></a><span data-ttu-id="05336-116">收集和啟用記錄</span><span class="sxs-lookup"><span data-stu-id="05336-116">Collect and enable logging</span></span>

<span data-ttu-id="05336-117">發生問題時，收集記錄非常重要。</span><span class="sxs-lookup"><span data-stu-id="05336-117">It’s important to collect logs as soon as an issue occurs.</span></span> <span data-ttu-id="05336-118">只要按幾下滑鼠，就能收集記錄。</span><span class="sxs-lookup"><span data-stu-id="05336-118">The logs can be collected together with just a couple of clicks.</span></span>

<span data-ttu-id="05336-119">Windows：以滑鼠右鍵按一下系統Teams中的 [檔案備份Teams，然後選擇 [**收集支援檔案**> 。</span><span class="sxs-lookup"><span data-stu-id="05336-119">Windows: Right-click on the Teams icon in the system tray and choose **Collect support files**.</span></span> 

<span data-ttu-id="05336-120">Mac：選取説明功能表，然後選擇收集 **支援檔案**。</span><span class="sxs-lookup"><span data-stu-id="05336-120">Mac: Select the Help menu and choose **Collect support files**.</span></span>

<span data-ttu-id="05336-121">Debug、Desktop 和 Media 記錄會收集到一個名稱為 MSTeams 診斷記錄的資料夾 <local data and time> 。</span><span class="sxs-lookup"><span data-stu-id="05336-121">Debug, Desktop, and Media logs will be collected in one folder with the name MSTeams Diagnostics Log <local data and time>.</span></span> <span data-ttu-id="05336-122">當您向 Microsoft 支援服務開啟支援要求時，可以壓縮並共用此資料夾。</span><span class="sxs-lookup"><span data-stu-id="05336-122">This folder can be compressed and shared when you open a support request with Microsoft Support.</span></span> <span data-ttu-id="05336-123">資料夾會包含桌面、會議 (媒體) 資料夾，以及 (網頁) 。</span><span class="sxs-lookup"><span data-stu-id="05336-123">The folder will contain folders for Desktop, Meeting (Media), and Debug (web).</span></span> <span data-ttu-id="05336-124">您可以使用下列鍵盤快速鍵收集檔案：</span><span class="sxs-lookup"><span data-stu-id="05336-124">You can collect the files using the following keyboard shortcuts:</span></span>

<span data-ttu-id="05336-125">Windows：Crtl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="05336-125">Windows: Crtl + Alt + Shift + 1</span></span>

<span data-ttu-id="05336-126">Mac：Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="05336-126">Mac: Option + Command + Shift + 1</span></span>

<span data-ttu-id="05336-127">媒體記錄預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="05336-127">Media logging is turned off by default.</span></span> <span data-ttu-id="05336-128">若要啟用媒體記錄，使用者必須在用戶端中開啟Teams選項。</span><span class="sxs-lookup"><span data-stu-id="05336-128">To enable Media logging, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="05336-129">請前往 **設定** 一般，然後選取啟用會議診斷記錄， ( >  \*\*\*\*\*\*重新開機Teams) 。\*\*</span><span class="sxs-lookup"><span data-stu-id="05336-129">Go to **Settings** > **General**, and select **Enable logging for meeting diagnostics (requires restarting Teams)**.</span></span> <span data-ttu-id="05336-130">您必須Teams用戶端，才能開始記錄。</span><span class="sxs-lookup"><span data-stu-id="05336-130">The Teams client must be restarted for logging to begin.</span></span>

> [!NOTE]
> <span data-ttu-id="05336-131">如果已啟用媒體記錄功能，會議資料夾中會包含其他檔案，這是調查音訊和視音訊問題的必要檔案。</span><span class="sxs-lookup"><span data-stu-id="05336-131">If Media logging is enabled, there will be additional files included in the Meeting folder which are necessary for investigating audio and video issues.</span></span> <span data-ttu-id="05336-132">如果未啟用媒體記錄，則可用的記錄數量會受到限制。</span><span class="sxs-lookup"><span data-stu-id="05336-132">If Media logging is not enabled, there will be a limited number of logs available.</span></span>

<span data-ttu-id="05336-133">下表概述各種用戶端及其相關聯的記錄。</span><span class="sxs-lookup"><span data-stu-id="05336-133">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="05336-134">記錄檔案會儲存在用戶端和作業系統的特定位置。</span><span class="sxs-lookup"><span data-stu-id="05336-134">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="05336-135">用戶端</span><span class="sxs-lookup"><span data-stu-id="05336-135">Client</span></span> |<span data-ttu-id="05336-136">調試</span><span class="sxs-lookup"><span data-stu-id="05336-136">Debug</span></span>|<span data-ttu-id="05336-137">桌面</span><span class="sxs-lookup"><span data-stu-id="05336-137">Desktop</span></span>|<span data-ttu-id="05336-138">媒體</span><span class="sxs-lookup"><span data-stu-id="05336-138">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="05336-139">Web</span><span class="sxs-lookup"><span data-stu-id="05336-139">Web</span></span>    |<span data-ttu-id="05336-140">X</span><span class="sxs-lookup"><span data-stu-id="05336-140">X</span></span>         |-         |-         |
|<span data-ttu-id="05336-141">Windows</span><span class="sxs-lookup"><span data-stu-id="05336-141">Windows</span></span>     |<span data-ttu-id="05336-142">X</span><span class="sxs-lookup"><span data-stu-id="05336-142">X</span></span>         |<span data-ttu-id="05336-143">X</span><span class="sxs-lookup"><span data-stu-id="05336-143">X</span></span>         |<span data-ttu-id="05336-144">X</span><span class="sxs-lookup"><span data-stu-id="05336-144">X</span></span>         |
|<span data-ttu-id="05336-145">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="05336-145">Mac OSX</span></span>     |<span data-ttu-id="05336-146">X</span><span class="sxs-lookup"><span data-stu-id="05336-146">X</span></span>         |<span data-ttu-id="05336-147">X</span><span class="sxs-lookup"><span data-stu-id="05336-147">X</span></span>         |<span data-ttu-id="05336-148">X</span><span class="sxs-lookup"><span data-stu-id="05336-148">X</span></span>         |
|<span data-ttu-id="05336-149">Linux</span><span class="sxs-lookup"><span data-stu-id="05336-149">Linux</span></span>     |<span data-ttu-id="05336-150">X</span><span class="sxs-lookup"><span data-stu-id="05336-150">X</span></span>         |<span data-ttu-id="05336-151">X</span><span class="sxs-lookup"><span data-stu-id="05336-151">X</span></span>         |<span data-ttu-id="05336-152">X</span><span class="sxs-lookup"><span data-stu-id="05336-152">X</span></span>         |
|<span data-ttu-id="05336-153">iOS</span><span class="sxs-lookup"><span data-stu-id="05336-153">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="05336-154">Android</span><span class="sxs-lookup"><span data-stu-id="05336-154">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="05336-155">有關支援的作業系統和瀏覽器的完整清單，請參閱取得[用戶端Microsoft Teams。](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="05336-155">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="05336-156">調試記錄</span><span class="sxs-lookup"><span data-stu-id="05336-156">Debug logs</span></span>

<span data-ttu-id="05336-157">請參閱收集和 _啟用記錄_ 一節，Windows Mac 指示。</span><span class="sxs-lookup"><span data-stu-id="05336-157">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="05336-158">調試記錄是由 Windows Mac 桌面用戶端，以及瀏覽器型用戶端所產生。</span><span class="sxs-lookup"><span data-stu-id="05336-158">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="05336-159">記錄是以文字為基礎，由下而上讀取。</span><span class="sxs-lookup"><span data-stu-id="05336-159">The logs are text-based and are read from the bottom-up.</span></span> <span data-ttu-id="05336-160">您可以使用任何文字型編輯器來讀取，登入用戶端時會建立新記錄。</span><span class="sxs-lookup"><span data-stu-id="05336-160">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="05336-161">調試記錄會顯示下列資料流程：</span><span class="sxs-lookup"><span data-stu-id="05336-161">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="05336-162">登錄</span><span class="sxs-lookup"><span data-stu-id="05336-162">Login</span></span>

-   <span data-ttu-id="05336-163">到中介層服務的連接要求</span><span class="sxs-lookup"><span data-stu-id="05336-163">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="05336-164">通話/交談</span><span class="sxs-lookup"><span data-stu-id="05336-164">Call/conversation</span></span>

<span data-ttu-id="05336-165">若要收集 Linux 的記錄：鍵盤快速鍵：Ctrl + Alt + Shift + 1 檔案可在 ~/Downloads 中使用</span><span class="sxs-lookup"><span data-stu-id="05336-165">To collect logs for Linux: Keyboard shortcut: Ctrl + Alt + Shift + 1 The files will be available in ~/Downloads</span></span>

<span data-ttu-id="05336-166">若要收集瀏覽器的記錄：鍵盤快速鍵：Crtl + Alt + Shift + 1 %userprofile%\Downloads 中會提供檔案</span><span class="sxs-lookup"><span data-stu-id="05336-166">To collect logs for Browser: Keyboard shortcut: Crtl + Alt + Shift + 1 The files will be available in %userprofile%\Downloads</span></span>

## <a name="media-logs"></a><span data-ttu-id="05336-167">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="05336-167">Media logs</span></span>

<span data-ttu-id="05336-168">請參閱收集和 _啟用記錄_ 一節，Windows Mac 指示。</span><span class="sxs-lookup"><span data-stu-id="05336-168">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="05336-169">媒體記錄包含會議中音訊、視像和螢幕Teams資料。</span><span class="sxs-lookup"><span data-stu-id="05336-169">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="05336-170">當支援案例與通話相關問題連結時，這些案例是必填專案。</span><span class="sxs-lookup"><span data-stu-id="05336-170">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="05336-171">媒體記錄預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="05336-171">Media logging is turned off by default.</span></span> <span data-ttu-id="05336-172">若要記錄會議Teams診斷資料，使用者必須在用戶端中開啟Teams選項。</span><span class="sxs-lookup"><span data-stu-id="05336-172">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="05336-173">請 **設定** 一般，選取啟用會議診斷記錄 (需要重新開機  >  \*\*\*\* **Teams)** 核取方塊、重新開機 Teams，然後重現問題。</span><span class="sxs-lookup"><span data-stu-id="05336-173">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="05336-174">當您將記錄檔案傳送給 Microsoft 支援人員時，請確認記錄檔案的時間戳記，以確保記錄在您重現問題時涵蓋時間範圍。</span><span class="sxs-lookup"><span data-stu-id="05336-174">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

<span data-ttu-id="05336-175">若要收集 Linux 的記錄：檔案可在 ~/.config/microsoft/Microsoft Teams/media-stack/*.blog 和 ~/.config/Microsoft/Microsoft Teams/skylib/*.blog 中提供。</span><span class="sxs-lookup"><span data-stu-id="05336-175">To collect logs for Linux: The files will be available in ~/.config/Microsoft/Microsoft Teams/media-stack/*.blog and ~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span></span>

<span data-ttu-id="05336-176">以下是產生的記錄檔案清單及其包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="05336-176">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="05336-177">記錄檔案名</span><span class="sxs-lookup"><span data-stu-id="05336-177">Log file name</span></span>  |<span data-ttu-id="05336-178">說明</span><span class="sxs-lookup"><span data-stu-id="05336-178">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="05336-179">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="05336-179">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="05336-180">包含媒體堆疊相關資訊。</span><span class="sxs-lookup"><span data-stu-id="05336-180">Contains information related to the media stack.</span></span> <span data-ttu-id="05336-181">這包括頻道狀態，例如解析度、使用的解碼器及編碼器，以及已送出和接收的畫面數目，以及攝影機和視 (視) 會話狀態。</span><span class="sxs-lookup"><span data-stu-id="05336-181">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="05336-182">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="05336-182">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="05336-183">記錄與遠端控制動作相關的資訊，例如提供控制項時時間戳記，以及滑鼠指標資訊。</span><span class="sxs-lookup"><span data-stu-id="05336-183">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="05336-184">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="05336-184">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="05336-185">記錄媒體堆疊追蹤事件。</span><span class="sxs-lookup"><span data-stu-id="05336-185">Records media stack trace events.</span></span>         |
|<span data-ttu-id="05336-186">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="05336-186">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="05336-187">包含媒體代理程式相關資訊，包括呈現品質。</span><span class="sxs-lookup"><span data-stu-id="05336-187">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="05336-188">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="05336-188">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="05336-189">在 ts-calling API 中記錄事件。</span><span class="sxs-lookup"><span data-stu-id="05336-189">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="05336-190">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="05336-190">Desktop logs</span></span>

<span data-ttu-id="05336-191">請參閱收集和 _啟用記錄_ 一節，Windows Mac 指示。</span><span class="sxs-lookup"><span data-stu-id="05336-191">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="05336-192">桌面記錄 ，也稱為 bootstrapper 記錄，包含桌面用戶端與瀏覽器之間發生的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="05336-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="05336-193">與媒體記錄一樣，這些記錄只有在 Microsoft 要求時才能使用。</span><span class="sxs-lookup"><span data-stu-id="05336-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="05336-194">記錄是以文字為基礎，而且可以使用由上而下格式的任何文字型編輯器來讀取。</span><span class="sxs-lookup"><span data-stu-id="05336-194">The logs are text-based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="05336-195">若要收集 Linux 的記錄：按一下系統Microsoft Teams中的 [取得記錄記錄>**圖示。**</span><span class="sxs-lookup"><span data-stu-id="05336-195">To collect logs for Linux: Click on the Microsoft Teams icon in your system tray, and select **Get Logs**.</span></span>
<span data-ttu-id="05336-196">檔案可在 ~/.config/microsoft/Microsoft Teams/logs.txt。</span><span class="sxs-lookup"><span data-stu-id="05336-196">The files will be available in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span></span>  


## <a name="browser-trace"></a><span data-ttu-id="05336-197">瀏覽器追蹤</span><span class="sxs-lookup"><span data-stu-id="05336-197">Browser trace</span></span>

<span data-ttu-id="05336-198">針對某些錯誤類別，Microsoft 支援服務可能會要求您收集瀏覽器追蹤。</span><span class="sxs-lookup"><span data-stu-id="05336-198">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="05336-199">這項資訊可提供發生錯誤時Teams用戶端狀態的重要詳細資料。</span><span class="sxs-lookup"><span data-stu-id="05336-199">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="05336-200">在啟動瀏覽器追蹤之前，請確認您已Teams。</span><span class="sxs-lookup"><span data-stu-id="05336-200">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="05336-201">在啟動追蹤之前，執行這項工作非常重要，這樣追蹤就不包含敏感性的登錄資訊。</span><span class="sxs-lookup"><span data-stu-id="05336-201">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="05336-202">在您登錄後，請選取下列其中一個連結 ，以適合您的瀏覽器使用，然後按照提供的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="05336-202">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="05336-203">Chrome & Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="05336-203">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="05336-204">邊緣</span><span class="sxs-lookup"><span data-stu-id="05336-204">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="05336-205">Safari</span><span class="sxs-lookup"><span data-stu-id="05336-205">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="05336-206">火狐</span><span class="sxs-lookup"><span data-stu-id="05336-206">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="05336-207">在步驟中，將 Azure 入口網站的所有參照取代為Teams用戶端。</span><span class="sxs-lookup"><span data-stu-id="05336-207">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="05336-208">相關主題</span><span class="sxs-lookup"><span data-stu-id="05336-208">Related topics</span></span>

[<span data-ttu-id="05336-209">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="05336-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
