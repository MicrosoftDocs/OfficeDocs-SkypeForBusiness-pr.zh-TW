---
title: 使用記錄檔案疑難排解Microsoft Teams
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
description: 瞭解由 Microsoft Teams 產生的 Debug、Media 和桌面記錄、可以在哪裡找到記錄，以及這些記錄如何協助進行疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264873"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="d7607-103">使用記錄檔案疑難排解Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7607-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="d7607-104">用戶端自動產生的記錄檔案類型有三種，可運用這些記錄Microsoft Teams：</span><span class="sxs-lookup"><span data-stu-id="d7607-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="d7607-105">調試記錄</span><span class="sxs-lookup"><span data-stu-id="d7607-105">Debug logs</span></span>

-   <span data-ttu-id="d7607-106">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="d7607-106">Media logs</span></span>

-   <span data-ttu-id="d7607-107">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="d7607-107">Desktop logs</span></span>

<span data-ttu-id="d7607-108">使用 Microsoft 支援服務建立支援要求時，支援工程師需要調試記錄。</span><span class="sxs-lookup"><span data-stu-id="d7607-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="d7607-109">建立支援要求之前，先將調試記錄放在手邊，Microsoft 就會快速開始疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="d7607-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="d7607-110">**媒體** 或 **桌面** 記錄只有在 Microsoft 要求時才能使用。</span><span class="sxs-lookup"><span data-stu-id="d7607-110">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="d7607-111">在本文中，" **調試記錄** "一詞是指用於疑難排解的記錄。</span><span class="sxs-lookup"><span data-stu-id="d7607-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="d7607-112">不過，這些記錄產生的檔案名稱中會包含診斷 **記錄** 一詞。</span><span class="sxs-lookup"><span data-stu-id="d7607-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="d7607-113">下表概述各種用戶端及其相關聯的記錄。</span><span class="sxs-lookup"><span data-stu-id="d7607-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="d7607-114">記錄檔案會儲存在用戶端和作業系統的特定位置。</span><span class="sxs-lookup"><span data-stu-id="d7607-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="d7607-115">用戶端</span><span class="sxs-lookup"><span data-stu-id="d7607-115">Client</span></span> |<span data-ttu-id="d7607-116">調試</span><span class="sxs-lookup"><span data-stu-id="d7607-116">Debug</span></span>|<span data-ttu-id="d7607-117">桌面</span><span class="sxs-lookup"><span data-stu-id="d7607-117">Desktop</span></span>|<span data-ttu-id="d7607-118">媒體</span><span class="sxs-lookup"><span data-stu-id="d7607-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="d7607-119">Web</span><span class="sxs-lookup"><span data-stu-id="d7607-119">Web</span></span>    |<span data-ttu-id="d7607-120">X</span><span class="sxs-lookup"><span data-stu-id="d7607-120">X</span></span>         |-         |-         |
|<span data-ttu-id="d7607-121">Windows</span><span class="sxs-lookup"><span data-stu-id="d7607-121">Windows</span></span>     |<span data-ttu-id="d7607-122">X</span><span class="sxs-lookup"><span data-stu-id="d7607-122">X</span></span>         |<span data-ttu-id="d7607-123">X</span><span class="sxs-lookup"><span data-stu-id="d7607-123">X</span></span>         |<span data-ttu-id="d7607-124">X</span><span class="sxs-lookup"><span data-stu-id="d7607-124">X</span></span>         |
|<span data-ttu-id="d7607-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d7607-125">Mac OSX</span></span>     |<span data-ttu-id="d7607-126">X</span><span class="sxs-lookup"><span data-stu-id="d7607-126">X</span></span>         |<span data-ttu-id="d7607-127">X</span><span class="sxs-lookup"><span data-stu-id="d7607-127">X</span></span>         |<span data-ttu-id="d7607-128">X</span><span class="sxs-lookup"><span data-stu-id="d7607-128">X</span></span>         |
|<span data-ttu-id="d7607-129">Linux</span><span class="sxs-lookup"><span data-stu-id="d7607-129">Linux</span></span>     |<span data-ttu-id="d7607-130">X</span><span class="sxs-lookup"><span data-stu-id="d7607-130">X</span></span>         |<span data-ttu-id="d7607-131">X</span><span class="sxs-lookup"><span data-stu-id="d7607-131">X</span></span>         |<span data-ttu-id="d7607-132">X</span><span class="sxs-lookup"><span data-stu-id="d7607-132">X</span></span>         |
|<span data-ttu-id="d7607-133">iOS</span><span class="sxs-lookup"><span data-stu-id="d7607-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="d7607-134">Android</span><span class="sxs-lookup"><span data-stu-id="d7607-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="d7607-135">有關支援的作業系統和瀏覽器的完整清單，請參閱取得[用戶端Microsoft Teams。](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="d7607-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="d7607-136">調試記錄</span><span class="sxs-lookup"><span data-stu-id="d7607-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="d7607-137">這些是最常見的記錄，且所有 Microsoft 支援案例都需要這些記錄。</span><span class="sxs-lookup"><span data-stu-id="d7607-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="d7607-138">調試記錄是由 Windows Mac 桌面用戶端，以及瀏覽器型用戶端所產生。</span><span class="sxs-lookup"><span data-stu-id="d7607-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="d7607-139">記錄是以文字為基礎，由下而上讀取。</span><span class="sxs-lookup"><span data-stu-id="d7607-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="d7607-140">您可以使用任何文字型編輯器來讀取，登入用戶端時會建立新記錄。</span><span class="sxs-lookup"><span data-stu-id="d7607-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="d7607-141">調試記錄會顯示下列資料流程：</span><span class="sxs-lookup"><span data-stu-id="d7607-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="d7607-142">登錄</span><span class="sxs-lookup"><span data-stu-id="d7607-142">Login</span></span>

-   <span data-ttu-id="d7607-143">到中介層服務的連接要求</span><span class="sxs-lookup"><span data-stu-id="d7607-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="d7607-144">通話/交談</span><span class="sxs-lookup"><span data-stu-id="d7607-144">Call/conversation</span></span>

<span data-ttu-id="d7607-145">使用下列 OS 特定方法產生調試記錄：</span><span class="sxs-lookup"><span data-stu-id="d7607-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="d7607-146">Windows：</span><span class="sxs-lookup"><span data-stu-id="d7607-146">Windows:</span></span>

      <span data-ttu-id="d7607-147">鍵盤快速鍵：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="d7607-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="d7607-148">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="d7607-148">Mac OSX:</span></span>

      <span data-ttu-id="d7607-149">鍵盤快速鍵：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="d7607-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="d7607-150">Linux：</span><span class="sxs-lookup"><span data-stu-id="d7607-150">Linux:</span></span>

      <span data-ttu-id="d7607-151">鍵盤快速鍵：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="d7607-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="d7607-152">系統會自動將調試記錄下載到下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="d7607-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="d7607-153">Windows：%userprofile% \\ 下載</span><span class="sxs-lookup"><span data-stu-id="d7607-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="d7607-154">Mac OSX：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="d7607-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="d7607-155">Linux：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="d7607-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="d7607-156">瀏覽器：系統會提示您將調試記錄儲存到預設儲存位置</span><span class="sxs-lookup"><span data-stu-id="d7607-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="d7607-157">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="d7607-157">Media logs</span></span>
---------------------------

<span data-ttu-id="d7607-158">媒體記錄包含會議中音訊、視像和螢幕Teams資料。</span><span class="sxs-lookup"><span data-stu-id="d7607-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="d7607-159">當支援案例與通話相關問題連結時，這些案例是必填專案。</span><span class="sxs-lookup"><span data-stu-id="d7607-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="d7607-160">媒體記錄預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="d7607-160">Media logging is turned off by default.</span></span> <span data-ttu-id="d7607-161">若要記錄會議Teams診斷資料，使用者必須在用戶端中開啟Teams選項。</span><span class="sxs-lookup"><span data-stu-id="d7607-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="d7607-162">請 **設定** 一般，選取啟用會議診斷記錄 (需要重新開機  >  \*\*\*\* **Teams)** 核取方塊、重新開機 Teams，然後重現問題。</span><span class="sxs-lookup"><span data-stu-id="d7607-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="d7607-163">下表概述媒體記錄位置。</span><span class="sxs-lookup"><span data-stu-id="d7607-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="d7607-164">當您將記錄檔案傳送給 Microsoft 支援人員時，請確認記錄檔案的時間戳記，以確保記錄在您重現問題時涵蓋時間範圍。</span><span class="sxs-lookup"><span data-stu-id="d7607-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="d7607-165">用戶端</span><span class="sxs-lookup"><span data-stu-id="d7607-165">Client</span></span> |<span data-ttu-id="d7607-166">位置</span><span class="sxs-lookup"><span data-stu-id="d7607-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="d7607-167">Windows</span><span class="sxs-lookup"><span data-stu-id="d7607-167">Windows</span></span>     |<span data-ttu-id="d7607-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="d7607-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="d7607-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="d7607-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="d7607-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d7607-171">Mac OSX</span></span>     |<span data-ttu-id="d7607-172">~/Library/Application Support/microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="d7607-173">~/Library/Application Support/microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="d7607-174">Linux</span><span class="sxs-lookup"><span data-stu-id="d7607-174">Linux</span></span>       |<span data-ttu-id="d7607-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="d7607-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="d7607-177">以下是產生的記錄檔案清單及其包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="d7607-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="d7607-178">記錄檔案名</span><span class="sxs-lookup"><span data-stu-id="d7607-178">Log file name</span></span>  |<span data-ttu-id="d7607-179">描述</span><span class="sxs-lookup"><span data-stu-id="d7607-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d7607-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="d7607-181">包含媒體堆疊相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d7607-181">Contains information related to the media stack.</span></span> <span data-ttu-id="d7607-182">這包括頻道狀態，例如解析度、使用的解碼器及編碼器，以及接收和接收的畫面數量，以及視 (VBSS) 會話狀態。</span><span class="sxs-lookup"><span data-stu-id="d7607-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="d7607-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="d7607-184">記錄與遠端控制動作相關的資訊，例如提供控制項時時間戳記，以及滑鼠指標資訊。</span><span class="sxs-lookup"><span data-stu-id="d7607-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="d7607-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="d7607-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="d7607-186">記錄媒體堆疊追蹤事件。</span><span class="sxs-lookup"><span data-stu-id="d7607-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="d7607-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="d7607-188">包含與媒體代理程式有關的資訊，包括呈現品質。</span><span class="sxs-lookup"><span data-stu-id="d7607-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="d7607-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="d7607-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="d7607-190">在 ts-calling API 中記錄事件。</span><span class="sxs-lookup"><span data-stu-id="d7607-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="d7607-191">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="d7607-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="d7607-192">桌面記錄 ，也稱為 bootstrapper 記錄，包含桌面用戶端與瀏覽器之間發生的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="d7607-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="d7607-193">與媒體記錄一樣，這些記錄只有在 Microsoft 要求時才能使用。</span><span class="sxs-lookup"><span data-stu-id="d7607-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="d7607-194">記錄是以文字為基礎，而且可以使用由上而下格式的任何文字型編輯器來讀取。</span><span class="sxs-lookup"><span data-stu-id="d7607-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="d7607-195">Windows：</span><span class="sxs-lookup"><span data-stu-id="d7607-195">Windows:</span></span>

 - <span data-ttu-id="d7607-196">以滑鼠 **右鍵Microsoft Teams** 系統工作列中的 [取得記錄記錄> 圖示 **。**</span><span class="sxs-lookup"><span data-stu-id="d7607-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="d7607-197">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="d7607-197">Mac OsX:</span></span>

 - <span data-ttu-id="d7607-198">從 **説明下拉式功能表\*\*\*\*選擇取得記錄**。</span><span class="sxs-lookup"><span data-stu-id="d7607-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="d7607-199">Linux：</span><span class="sxs-lookup"><span data-stu-id="d7607-199">Linux:</span></span>

 - <span data-ttu-id="d7607-200">按一下 **系統Microsoft Teams中的**[取得記錄記錄>**圖示。**</span><span class="sxs-lookup"><span data-stu-id="d7607-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="d7607-201">用戶端</span><span class="sxs-lookup"><span data-stu-id="d7607-201">Client</span></span> |<span data-ttu-id="d7607-202">位置</span><span class="sxs-lookup"><span data-stu-id="d7607-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="d7607-203">Windows</span><span class="sxs-lookup"><span data-stu-id="d7607-203">Windows</span></span>     |<span data-ttu-id="d7607-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="d7607-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="d7607-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="d7607-205">Mac OSX</span></span>     |<span data-ttu-id="d7607-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="d7607-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="d7607-207">Linux</span><span class="sxs-lookup"><span data-stu-id="d7607-207">Linux</span></span>       |<span data-ttu-id="d7607-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="d7607-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


<a name="browser-trace"></a><span data-ttu-id="d7607-209">瀏覽器追蹤</span><span class="sxs-lookup"><span data-stu-id="d7607-209">Browser trace</span></span>
---------------------------

<span data-ttu-id="d7607-210">針對某些錯誤類別，Microsoft 支援服務可能會要求您收集瀏覽器追蹤。</span><span class="sxs-lookup"><span data-stu-id="d7607-210">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="d7607-211">這項資訊可提供發生錯誤時Teams用戶端狀態的重要詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d7607-211">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="d7607-212">開始瀏覽器追蹤之前，請確認您已Teams。</span><span class="sxs-lookup"><span data-stu-id="d7607-212">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="d7607-213">在啟動追蹤之前，執行這項工作非常重要，這樣追蹤就不包含敏感性的登錄資訊。</span><span class="sxs-lookup"><span data-stu-id="d7607-213">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="d7607-214">在您登錄後，請選取下列其中一個連結 ，以適合您的瀏覽器使用，然後按照提供的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d7607-214">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="d7607-215">Chrome & Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="d7607-215">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="d7607-216">邊緣</span><span class="sxs-lookup"><span data-stu-id="d7607-216">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="d7607-217">Safari</span><span class="sxs-lookup"><span data-stu-id="d7607-217">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="d7607-218">火狐</span><span class="sxs-lookup"><span data-stu-id="d7607-218">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="d7607-219">在步驟中，將 Azure 入口網站的所有參照取代為Teams用戶端。</span><span class="sxs-lookup"><span data-stu-id="d7607-219">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d7607-220">相關主題</span><span class="sxs-lookup"><span data-stu-id="d7607-220">Related topics</span></span>

[<span data-ttu-id="d7607-221">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="d7607-221">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
