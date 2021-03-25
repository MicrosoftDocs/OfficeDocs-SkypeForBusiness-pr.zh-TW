---
title: 使用記錄檔案疑難排解 Microsoft Teams
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
description: 瞭解 Microsoft Teams 所製作的 Debug、Media 和桌面記錄，以及這些記錄可以在哪裡找到，以及如何協助進行疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112189"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="fb2ff-103">使用記錄檔案疑難排解 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb2ff-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="fb2ff-104">用戶端自動產生的記錄檔案類型有三種，可運用這些記錄檔案以協助 Microsoft Teams 進行疑難排解：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="fb2ff-105">調試記錄</span><span class="sxs-lookup"><span data-stu-id="fb2ff-105">Debug logs</span></span>

-   <span data-ttu-id="fb2ff-106">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="fb2ff-106">Media logs</span></span>

-   <span data-ttu-id="fb2ff-107">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="fb2ff-107">Desktop logs</span></span>

<span data-ttu-id="fb2ff-108">使用 Microsoft 支援服務建立支援要求時，支援工程師需要調試記錄。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="fb2ff-109">建立支援要求之前，先將調試記錄放在手邊，Microsoft 就會快速開始疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="fb2ff-110">**媒體** 或 **桌面** 記錄只有在 Microsoft 要求時才能使用。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-110">**Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="fb2ff-111">在本文中，" **調試記錄** "一詞是指用於疑難排解的記錄。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="fb2ff-112">不過，這些記錄產生的檔案名稱中會包含診斷 **記錄** 一詞。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="fb2ff-113">下表概述各種用戶端及其相關聯的記錄。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="fb2ff-114">記錄檔案會儲存在用戶端和作業系統的特定位置。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="fb2ff-115">用戶端</span><span class="sxs-lookup"><span data-stu-id="fb2ff-115">Client</span></span> |<span data-ttu-id="fb2ff-116">調試</span><span class="sxs-lookup"><span data-stu-id="fb2ff-116">Debug</span></span>|<span data-ttu-id="fb2ff-117">桌面</span><span class="sxs-lookup"><span data-stu-id="fb2ff-117">Desktop</span></span>|<span data-ttu-id="fb2ff-118">媒體</span><span class="sxs-lookup"><span data-stu-id="fb2ff-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="fb2ff-119">Web</span><span class="sxs-lookup"><span data-stu-id="fb2ff-119">Web</span></span>    |<span data-ttu-id="fb2ff-120">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-120">X</span></span>         |-         |-         |
|<span data-ttu-id="fb2ff-121">Windows</span><span class="sxs-lookup"><span data-stu-id="fb2ff-121">Windows</span></span>     |<span data-ttu-id="fb2ff-122">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-122">X</span></span>         |<span data-ttu-id="fb2ff-123">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-123">X</span></span>         |<span data-ttu-id="fb2ff-124">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-124">X</span></span>         |
|<span data-ttu-id="fb2ff-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fb2ff-125">Mac OSX</span></span>     |<span data-ttu-id="fb2ff-126">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-126">X</span></span>         |<span data-ttu-id="fb2ff-127">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-127">X</span></span>         |<span data-ttu-id="fb2ff-128">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-128">X</span></span>         |
|<span data-ttu-id="fb2ff-129">Linux</span><span class="sxs-lookup"><span data-stu-id="fb2ff-129">Linux</span></span>     |<span data-ttu-id="fb2ff-130">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-130">X</span></span>         |<span data-ttu-id="fb2ff-131">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-131">X</span></span>         |<span data-ttu-id="fb2ff-132">X</span><span class="sxs-lookup"><span data-stu-id="fb2ff-132">X</span></span>         |
|<span data-ttu-id="fb2ff-133">iOS</span><span class="sxs-lookup"><span data-stu-id="fb2ff-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="fb2ff-134">Android</span><span class="sxs-lookup"><span data-stu-id="fb2ff-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="fb2ff-135">有關支援的作業系統和瀏覽器的完整清單，請參閱取得 Microsoft [Teams 的用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="fb2ff-136">調試記錄</span><span class="sxs-lookup"><span data-stu-id="fb2ff-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="fb2ff-137">這些是最常見的記錄，且所有 Microsoft 支援案例都需要這些記錄。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="fb2ff-138">調試記錄是由 Windows 和 Mac 桌面用戶端以及瀏覽器型用戶端所產生。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="fb2ff-139">記錄是以文字為基礎，由下而上讀取。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="fb2ff-140">您可以使用任何文字型編輯器來讀取，登入用戶端時會建立新記錄。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="fb2ff-141">調試記錄會顯示下列資料流程：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="fb2ff-142">登錄</span><span class="sxs-lookup"><span data-stu-id="fb2ff-142">Login</span></span>

-   <span data-ttu-id="fb2ff-143">到中介層服務的連接要求</span><span class="sxs-lookup"><span data-stu-id="fb2ff-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="fb2ff-144">通話/交談</span><span class="sxs-lookup"><span data-stu-id="fb2ff-144">Call/conversation</span></span>

<span data-ttu-id="fb2ff-145">使用下列 OS 特定方法產生調試記錄：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="fb2ff-146">窗戶：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-146">Windows:</span></span>

      <span data-ttu-id="fb2ff-147">鍵盤快速鍵：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="fb2ff-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="fb2ff-148">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-148">Mac OSX:</span></span>

      <span data-ttu-id="fb2ff-149">鍵盤快速鍵：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="fb2ff-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="fb2ff-150">Linux：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-150">Linux:</span></span>

      <span data-ttu-id="fb2ff-151">鍵盤快速鍵：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="fb2ff-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="fb2ff-152">系統會自動將調試記錄下載到下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="fb2ff-153">Windows：%userprofile% \\ 下載</span><span class="sxs-lookup"><span data-stu-id="fb2ff-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="fb2ff-154">Mac OSX：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="fb2ff-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="fb2ff-155">Linux：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="fb2ff-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="fb2ff-156">瀏覽器：系統會提示您將調試記錄儲存到預設儲存位置</span><span class="sxs-lookup"><span data-stu-id="fb2ff-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="fb2ff-157">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="fb2ff-157">Media logs</span></span>
---------------------------

<span data-ttu-id="fb2ff-158">媒體記錄包含 Teams 會議中音訊、視像和螢幕分享的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="fb2ff-159">當支援案例與通話相關問題連結時，這些案例是必填專案。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="fb2ff-160">媒體記錄預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-160">Media logging is turned off by default.</span></span> <span data-ttu-id="fb2ff-161">若要記錄 Teams 會議的診斷資料，使用者必須開啟 Teams 用戶端中的選項。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="fb2ff-162">前往設定一般，選取啟用會議診斷記錄 (需要重新開機 Teams) 核取方塊、重新開機  >  \*\*\*\* Teams，然後重現問題。 </span><span class="sxs-lookup"><span data-stu-id="fb2ff-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="fb2ff-163">下表概述媒體記錄位置。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="fb2ff-164">當您將記錄檔案傳送給 Microsoft 支援人員時，請確認記錄檔案的時間戳記，以確保記錄在您重現問題時涵蓋時間範圍。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="fb2ff-165">用戶端</span><span class="sxs-lookup"><span data-stu-id="fb2ff-165">Client</span></span> |<span data-ttu-id="fb2ff-166">位置</span><span class="sxs-lookup"><span data-stu-id="fb2ff-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fb2ff-167">Windows</span><span class="sxs-lookup"><span data-stu-id="fb2ff-167">Windows</span></span>     |<span data-ttu-id="fb2ff-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="fb2ff-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="fb2ff-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="fb2ff-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="fb2ff-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fb2ff-171">Mac OSX</span></span>     |<span data-ttu-id="fb2ff-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="fb2ff-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="fb2ff-174">Linux</span><span class="sxs-lookup"><span data-stu-id="fb2ff-174">Linux</span></span>       |<span data-ttu-id="fb2ff-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="fb2ff-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="fb2ff-177">以下是產生的記錄檔案清單及其包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="fb2ff-178">記錄檔案名</span><span class="sxs-lookup"><span data-stu-id="fb2ff-178">Log file name</span></span>  |<span data-ttu-id="fb2ff-179">說明</span><span class="sxs-lookup"><span data-stu-id="fb2ff-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fb2ff-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="fb2ff-181">包含媒體堆疊相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-181">Contains information related to the media stack.</span></span> <span data-ttu-id="fb2ff-182">這包括頻道狀態，例如解析度、使用的解碼器及編碼器，以及接收和接收的畫面數量，以及視 (VBSS) 會話狀態。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="fb2ff-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="fb2ff-184">記錄與遠端控制動作相關的資訊，例如提供控制項時時間戳記，以及滑鼠指標資訊。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="fb2ff-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="fb2ff-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="fb2ff-186">記錄媒體堆疊追蹤事件。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="fb2ff-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="fb2ff-188">包含媒體代理程式相關資訊，包括呈現品質。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="fb2ff-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="fb2ff-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="fb2ff-190">在 ts-calling API 中記錄事件。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="fb2ff-191">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="fb2ff-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="fb2ff-192">桌面記錄 ，也稱為 bootstrapper 記錄，包含桌面用戶端與瀏覽器之間發生的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="fb2ff-193">與媒體記錄一樣，這些記錄只有在 Microsoft 要求時才能使用。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="fb2ff-194">記錄是以文字為基礎，而且可以使用由上而下格式的任何文字型編輯器來讀取。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="fb2ff-195">窗戶：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-195">Windows:</span></span>

 - <span data-ttu-id="fb2ff-196">以滑鼠右鍵按一下 **系統工作列** 中的 Microsoft Teams 圖示，然後選取 [ **取得記錄記錄**> 。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="fb2ff-197">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-197">Mac OsX:</span></span>

 - <span data-ttu-id="fb2ff-198">從 **説明下拉式功能表\*\*\*\*選擇取得記錄**。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="fb2ff-199">Linux：</span><span class="sxs-lookup"><span data-stu-id="fb2ff-199">Linux:</span></span>

 - <span data-ttu-id="fb2ff-200">按一下系統工作列 **中的 Microsoft Teams** 圖示，然後選取 [ **取得記錄記錄**> 。</span><span class="sxs-lookup"><span data-stu-id="fb2ff-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="fb2ff-201">用戶端</span><span class="sxs-lookup"><span data-stu-id="fb2ff-201">Client</span></span> |<span data-ttu-id="fb2ff-202">位置</span><span class="sxs-lookup"><span data-stu-id="fb2ff-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fb2ff-203">Windows</span><span class="sxs-lookup"><span data-stu-id="fb2ff-203">Windows</span></span>     |<span data-ttu-id="fb2ff-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="fb2ff-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="fb2ff-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fb2ff-205">Mac OSX</span></span>     |<span data-ttu-id="fb2ff-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="fb2ff-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="fb2ff-207">Linux</span><span class="sxs-lookup"><span data-stu-id="fb2ff-207">Linux</span></span>       |<span data-ttu-id="fb2ff-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="fb2ff-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="fb2ff-209">相關主題</span><span class="sxs-lookup"><span data-stu-id="fb2ff-209">Related topics</span></span>

[<span data-ttu-id="fb2ff-210">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="fb2ff-210">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)