---
title: 在 Microsoft 團隊的疑難排解中使用記錄檔
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 瞭解 Microsoft 團隊所產生的調試、媒體和桌面記錄，以及可在哪裡找到這些記錄，以及如何協助疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761091"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="744a1-103">在 Microsoft 團隊的疑難排解中使用記錄檔</span><span class="sxs-lookup"><span data-stu-id="744a1-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="744a1-104">用戶端自動產生三種類型的記錄檔案，可利用這些檔案協助 Microsoft 團隊進行疑難排解：</span><span class="sxs-lookup"><span data-stu-id="744a1-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="744a1-105">調試記錄</span><span class="sxs-lookup"><span data-stu-id="744a1-105">Debug logs</span></span>

-   <span data-ttu-id="744a1-106">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="744a1-106">Media logs</span></span>

-   <span data-ttu-id="744a1-107">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="744a1-107">Desktop logs</span></span>

<span data-ttu-id="744a1-108">建立含 Microsoft 支援的支援要求時，支援工程師將需要調試記錄。</span><span class="sxs-lookup"><span data-stu-id="744a1-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="744a1-109">在建立支援要求之前，先準備好調試記錄，就能讓 Microsoft 快速開始疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="744a1-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="744a1-110">**媒體** 或 **桌面** 記錄只有 Microsoft 要求時才是必要的。</span><span class="sxs-lookup"><span data-stu-id="744a1-110">**Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="744a1-111">在本文中，「 **調試記錄** 」一詞是指用來進行疑難排解的記錄。</span><span class="sxs-lookup"><span data-stu-id="744a1-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="744a1-112">不過，為這些記錄產生的檔案，會在其名稱中包含字詞 **診斷記錄** 。</span><span class="sxs-lookup"><span data-stu-id="744a1-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="744a1-113">下表列出各種用戶端及其相關記錄。</span><span class="sxs-lookup"><span data-stu-id="744a1-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="744a1-114">記錄檔案會儲存在用戶端與作業系統專用的位置。</span><span class="sxs-lookup"><span data-stu-id="744a1-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="744a1-115">用戶端</span><span class="sxs-lookup"><span data-stu-id="744a1-115">Client</span></span> |<span data-ttu-id="744a1-116">Debug</span><span class="sxs-lookup"><span data-stu-id="744a1-116">Debug</span></span>|<span data-ttu-id="744a1-117">桌面</span><span class="sxs-lookup"><span data-stu-id="744a1-117">Desktop</span></span>|<span data-ttu-id="744a1-118">媒體</span><span class="sxs-lookup"><span data-stu-id="744a1-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="744a1-119">網站</span><span class="sxs-lookup"><span data-stu-id="744a1-119">Web</span></span>    |<span data-ttu-id="744a1-120">X</span><span class="sxs-lookup"><span data-stu-id="744a1-120">X</span></span>         |-         |-         |
|<span data-ttu-id="744a1-121">Windows</span><span class="sxs-lookup"><span data-stu-id="744a1-121">Windows</span></span>     |<span data-ttu-id="744a1-122">X</span><span class="sxs-lookup"><span data-stu-id="744a1-122">X</span></span>         |<span data-ttu-id="744a1-123">X</span><span class="sxs-lookup"><span data-stu-id="744a1-123">X</span></span>         |<span data-ttu-id="744a1-124">X</span><span class="sxs-lookup"><span data-stu-id="744a1-124">X</span></span>         |
|<span data-ttu-id="744a1-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="744a1-125">Mac OSX</span></span>     |<span data-ttu-id="744a1-126">X</span><span class="sxs-lookup"><span data-stu-id="744a1-126">X</span></span>         |<span data-ttu-id="744a1-127">X</span><span class="sxs-lookup"><span data-stu-id="744a1-127">X</span></span>         |<span data-ttu-id="744a1-128">X</span><span class="sxs-lookup"><span data-stu-id="744a1-128">X</span></span>         |
|<span data-ttu-id="744a1-129">Linux</span><span class="sxs-lookup"><span data-stu-id="744a1-129">Linux</span></span>     |<span data-ttu-id="744a1-130">X</span><span class="sxs-lookup"><span data-stu-id="744a1-130">X</span></span>         |<span data-ttu-id="744a1-131">X</span><span class="sxs-lookup"><span data-stu-id="744a1-131">X</span></span>         |<span data-ttu-id="744a1-132">X</span><span class="sxs-lookup"><span data-stu-id="744a1-132">X</span></span>         |
|<span data-ttu-id="744a1-133">iOS</span><span class="sxs-lookup"><span data-stu-id="744a1-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="744a1-134">Android</span><span class="sxs-lookup"><span data-stu-id="744a1-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="744a1-135">如需支援的作業系統和瀏覽器的完整清單，請參閱 [取得 Microsoft 團隊的用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="744a1-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="744a1-136">調試記錄</span><span class="sxs-lookup"><span data-stu-id="744a1-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="744a1-137">這些是最常見的記錄，而且對於所有 Microsoft 支援案例都是必要的。</span><span class="sxs-lookup"><span data-stu-id="744a1-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="744a1-138">調試記錄是由 Windows 和 Mac 桌面用戶端以及瀏覽器的用戶端產生。</span><span class="sxs-lookup"><span data-stu-id="744a1-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="744a1-139">這些記錄都是以文字為基礎，並從下到上閱讀。</span><span class="sxs-lookup"><span data-stu-id="744a1-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="744a1-140">它們可以使用任何文字型編輯器讀取，而且會在登入用戶端時建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="744a1-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="744a1-141">[調試記錄] 會顯示下列資料流程程：</span><span class="sxs-lookup"><span data-stu-id="744a1-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="744a1-142">Id</span><span class="sxs-lookup"><span data-stu-id="744a1-142">Login</span></span>

-   <span data-ttu-id="744a1-143">連接要求至中介層服務</span><span class="sxs-lookup"><span data-stu-id="744a1-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="744a1-144">通話/交談</span><span class="sxs-lookup"><span data-stu-id="744a1-144">Call/conversation</span></span>

<span data-ttu-id="744a1-145">調試記錄是使用下列 OS 專用方法產生：</span><span class="sxs-lookup"><span data-stu-id="744a1-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="744a1-146">時間</span><span class="sxs-lookup"><span data-stu-id="744a1-146">Windows:</span></span>

      <span data-ttu-id="744a1-147">鍵盤快速鍵： Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="744a1-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="744a1-148">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="744a1-148">Mac OSX:</span></span>

      <span data-ttu-id="744a1-149">鍵盤快速鍵： Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="744a1-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="744a1-150">Linux</span><span class="sxs-lookup"><span data-stu-id="744a1-150">Linux:</span></span>

      <span data-ttu-id="744a1-151">鍵盤快速鍵： Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="744a1-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="744a1-152">調試記錄會自動下載到下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="744a1-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="744a1-153">Windows：% userprofile% \\ 下載</span><span class="sxs-lookup"><span data-stu-id="744a1-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="744a1-154">Mac OSX： ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="744a1-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="744a1-155">Linux： ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="744a1-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="744a1-156">瀏覽器：系統會提示您將調試記錄儲存到預設的儲存位置</span><span class="sxs-lookup"><span data-stu-id="744a1-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="744a1-157">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="744a1-157">Media logs</span></span>
---------------------------

<span data-ttu-id="744a1-158">媒體記錄包含有關團隊會議中音訊、影片和螢幕共用的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="744a1-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="744a1-159">它們對於連結至通話相關問題的支援案例是必要的。</span><span class="sxs-lookup"><span data-stu-id="744a1-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="744a1-160">媒體記錄會預設為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="744a1-160">Media logging is turned off by default.</span></span> <span data-ttu-id="744a1-161">若要記錄團隊會議的診斷資料，使用者必須開啟團隊用戶端中的選項。</span><span class="sxs-lookup"><span data-stu-id="744a1-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="744a1-162">移至  >  **[設定一般**]，選取 [**啟用會議診斷記錄] (需要重新開機團隊**) 核取方塊、重新開機團隊，然後再現問題。</span><span class="sxs-lookup"><span data-stu-id="744a1-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="744a1-163">下表列出媒體記錄位置。</span><span class="sxs-lookup"><span data-stu-id="744a1-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="744a1-164">當您將記錄檔傳送給 Microsoft 支援時，請確認記錄檔的時間戳記，以確保記錄在您再現問題時能覆蓋時間範圍。</span><span class="sxs-lookup"><span data-stu-id="744a1-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="744a1-165">用戶端</span><span class="sxs-lookup"><span data-stu-id="744a1-165">Client</span></span> |<span data-ttu-id="744a1-166">位置</span><span class="sxs-lookup"><span data-stu-id="744a1-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="744a1-167">Windows</span><span class="sxs-lookup"><span data-stu-id="744a1-167">Windows</span></span>     |<span data-ttu-id="744a1-168">%appdata%\Microsoft\Teams\media-stack \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="744a1-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="744a1-169">%appdata%\Microsoft\Teams\skylib \\ \*. 博客</span><span class="sxs-lookup"><span data-stu-id="744a1-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="744a1-170">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="744a1-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="744a1-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="744a1-171">Mac OSX</span></span>     |<span data-ttu-id="744a1-172">~ 路徑/library/application support 支援/Microsoft/團隊/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="744a1-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="744a1-173">~ 路徑/library/application support 支援/Microsoft/團隊/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="744a1-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="744a1-174">Linux</span><span class="sxs-lookup"><span data-stu-id="744a1-174">Linux</span></span>       |<span data-ttu-id="744a1-175">~/.config/Microsoft/Microsoft 團隊/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="744a1-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="744a1-176">~/.config/Microsoft/Microsoft 團隊/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="744a1-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="744a1-177">以下列出所產生的記錄檔及其包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="744a1-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="744a1-178">記錄檔案名</span><span class="sxs-lookup"><span data-stu-id="744a1-178">Log file name</span></span>  |<span data-ttu-id="744a1-179">描述</span><span class="sxs-lookup"><span data-stu-id="744a1-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="744a1-180">Msrtc-0-s1039525249。</span><span class="sxs-lookup"><span data-stu-id="744a1-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="744a1-181">包含媒體堆疊的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="744a1-181">Contains information related to the media stack.</span></span> <span data-ttu-id="744a1-182">這包括通道狀態（例如解析度、使用的解碼器和編碼器），以及傳送和接收的畫面數，以及攝影機與影片螢幕共用 (VBSS) 會話狀態。</span><span class="sxs-lookup"><span data-stu-id="744a1-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="744a1-183">rtmcontrol msrtc-0-2415069487. 博客</span><span class="sxs-lookup"><span data-stu-id="744a1-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="744a1-184">記錄與遠端控制動作相關的資訊，例如控制權的時間戳記，以及滑鼠指標資訊。</span><span class="sxs-lookup"><span data-stu-id="744a1-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="744a1-185">Teams_MediaStackETW-2-U-xr-U</span><span class="sxs-lookup"><span data-stu-id="744a1-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="744a1-186">記錄媒體堆疊追蹤事件。</span><span class="sxs-lookup"><span data-stu-id="744a1-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="744a1-187">調試-0-s2790420889。</span><span class="sxs-lookup"><span data-stu-id="744a1-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="744a1-188">包含媒體代理程式的相關資訊，包括轉譯品質。</span><span class="sxs-lookup"><span data-stu-id="744a1-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="744a1-189">tscalling-0-2061129496</span><span class="sxs-lookup"><span data-stu-id="744a1-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="744a1-190">在 ts 呼叫 API 中記錄事件。</span><span class="sxs-lookup"><span data-stu-id="744a1-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="744a1-191">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="744a1-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="744a1-192">桌面記錄（也稱為引導程式記錄）包含在桌面用戶端與瀏覽器之間所發生的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="744a1-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="744a1-193">就像媒體記錄一樣，只有 Microsoft 要求時才需要這些記錄。</span><span class="sxs-lookup"><span data-stu-id="744a1-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="744a1-194">這些記錄是以文字為基礎的，而且可以使用以自上而下格式為基礎的任何文字編輯器來閱讀。</span><span class="sxs-lookup"><span data-stu-id="744a1-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="744a1-195">時間</span><span class="sxs-lookup"><span data-stu-id="744a1-195">Windows:</span></span>

 - <span data-ttu-id="744a1-196">以滑鼠右鍵按一下系統託盤中的 [ **Microsoft 團隊** ] 圖示，然後選取 [ **取得記錄**]。</span><span class="sxs-lookup"><span data-stu-id="744a1-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="744a1-197">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="744a1-197">Mac OsX:</span></span>

 - <span data-ttu-id="744a1-198">從 **[說明] 下拉式功能表中** 選擇 [**取得記錄**]。</span><span class="sxs-lookup"><span data-stu-id="744a1-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="744a1-199">Linux</span><span class="sxs-lookup"><span data-stu-id="744a1-199">Linux:</span></span>

 - <span data-ttu-id="744a1-200">按一下系統託盤中的 [ **Microsoft 團隊** ] 圖示，然後選取 [ **取得記錄**]。</span><span class="sxs-lookup"><span data-stu-id="744a1-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="744a1-201">用戶端</span><span class="sxs-lookup"><span data-stu-id="744a1-201">Client</span></span> |<span data-ttu-id="744a1-202">位置</span><span class="sxs-lookup"><span data-stu-id="744a1-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="744a1-203">Windows</span><span class="sxs-lookup"><span data-stu-id="744a1-203">Windows</span></span>     |<span data-ttu-id="744a1-204">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="744a1-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="744a1-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="744a1-205">Mac OSX</span></span>     |<span data-ttu-id="744a1-206">~ 路徑/library/application support 支援/Microsoft/團隊/logs.txt</span><span class="sxs-lookup"><span data-stu-id="744a1-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="744a1-207">Linux</span><span class="sxs-lookup"><span data-stu-id="744a1-207">Linux</span></span>       |<span data-ttu-id="744a1-208">~/.config/Microsoft/Microsoft 小組/logs.txt</span><span class="sxs-lookup"><span data-stu-id="744a1-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="744a1-209">相關主題</span><span class="sxs-lookup"><span data-stu-id="744a1-209">Related topics</span></span>

[<span data-ttu-id="744a1-210">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="744a1-210">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
