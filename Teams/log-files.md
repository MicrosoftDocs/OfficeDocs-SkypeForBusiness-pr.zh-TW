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
description: 瞭解由 Microsoft Teams 產生的 Debug、Media 和桌面記錄、可以在哪裡找到記錄，以及這些記錄如何協助監控和疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337740"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="fe74b-103">使用記錄檔案來監控和疑難排解Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe74b-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="fe74b-104">用戶端自動產生的記錄檔案有三種類型，可運用這些記錄檔案以協助監控和疑難排解Teams：</span><span class="sxs-lookup"><span data-stu-id="fe74b-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="fe74b-105">調試記錄</span><span class="sxs-lookup"><span data-stu-id="fe74b-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="fe74b-106">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="fe74b-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="fe74b-107">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="fe74b-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="fe74b-108">本文將說明三個記錄及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="fe74b-108">This article describes the three logs and how they are used.</span></span> 

<span data-ttu-id="fe74b-109">有關疑難排解特定問題的資訊，請參閱：Teams[疑難排解](/MicrosoftTeams/troubleshoot/teams)。</span><span class="sxs-lookup"><span data-stu-id="fe74b-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="fe74b-110">如需如何與支援人員聯繫的資訊，請參閱 [取得支援](/microsoft-365/business-video/get-help-support)。</span><span class="sxs-lookup"><span data-stu-id="fe74b-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span>

<span data-ttu-id="fe74b-111">使用 Microsoft 支援服務建立支援要求時，支援工程師需要調試記錄。</span><span class="sxs-lookup"><span data-stu-id="fe74b-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="fe74b-112">建立支援要求之前，先將調試記錄放在手邊，Microsoft 就會快速開始疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="fe74b-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="fe74b-113">**媒體** 或 **桌面** 記錄只有在 Microsoft 要求時才能使用。</span><span class="sxs-lookup"><span data-stu-id="fe74b-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="fe74b-114">在本文中，" **調試記錄** "一詞是指用於疑難排解的記錄。</span><span class="sxs-lookup"><span data-stu-id="fe74b-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="fe74b-115">不過，這些記錄產生的檔案名稱中會包含診斷 **記錄** 一詞。</span><span class="sxs-lookup"><span data-stu-id="fe74b-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="fe74b-116">下表概述各種用戶端及其相關聯的記錄。</span><span class="sxs-lookup"><span data-stu-id="fe74b-116">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="fe74b-117">記錄檔案會儲存在用戶端和作業系統的特定位置。</span><span class="sxs-lookup"><span data-stu-id="fe74b-117">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="fe74b-118">用戶端</span><span class="sxs-lookup"><span data-stu-id="fe74b-118">Client</span></span> |<span data-ttu-id="fe74b-119">調試</span><span class="sxs-lookup"><span data-stu-id="fe74b-119">Debug</span></span>|<span data-ttu-id="fe74b-120">桌面</span><span class="sxs-lookup"><span data-stu-id="fe74b-120">Desktop</span></span>|<span data-ttu-id="fe74b-121">媒體</span><span class="sxs-lookup"><span data-stu-id="fe74b-121">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="fe74b-122">Web</span><span class="sxs-lookup"><span data-stu-id="fe74b-122">Web</span></span>    |<span data-ttu-id="fe74b-123">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-123">X</span></span>         |-         |-         |
|<span data-ttu-id="fe74b-124">Windows</span><span class="sxs-lookup"><span data-stu-id="fe74b-124">Windows</span></span>     |<span data-ttu-id="fe74b-125">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-125">X</span></span>         |<span data-ttu-id="fe74b-126">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-126">X</span></span>         |<span data-ttu-id="fe74b-127">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-127">X</span></span>         |
|<span data-ttu-id="fe74b-128">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fe74b-128">Mac OSX</span></span>     |<span data-ttu-id="fe74b-129">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-129">X</span></span>         |<span data-ttu-id="fe74b-130">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-130">X</span></span>         |<span data-ttu-id="fe74b-131">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-131">X</span></span>         |
|<span data-ttu-id="fe74b-132">Linux</span><span class="sxs-lookup"><span data-stu-id="fe74b-132">Linux</span></span>     |<span data-ttu-id="fe74b-133">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-133">X</span></span>         |<span data-ttu-id="fe74b-134">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-134">X</span></span>         |<span data-ttu-id="fe74b-135">X</span><span class="sxs-lookup"><span data-stu-id="fe74b-135">X</span></span>         |
|<span data-ttu-id="fe74b-136">iOS</span><span class="sxs-lookup"><span data-stu-id="fe74b-136">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="fe74b-137">Android</span><span class="sxs-lookup"><span data-stu-id="fe74b-137">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="fe74b-138">有關支援的作業系統和瀏覽器的完整清單，請參閱取得[用戶端Microsoft Teams。](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="fe74b-138">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="fe74b-139">調試記錄</span><span class="sxs-lookup"><span data-stu-id="fe74b-139">Debug logs</span></span>

<span data-ttu-id="fe74b-140">這些是最常見的記錄，且所有 Microsoft 支援案例都需要這些記錄。</span><span class="sxs-lookup"><span data-stu-id="fe74b-140">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="fe74b-141">調試記錄是由 Windows Mac 桌面用戶端，以及瀏覽器型用戶端所產生。</span><span class="sxs-lookup"><span data-stu-id="fe74b-141">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="fe74b-142">記錄是以文字為基礎，由下而上讀取。</span><span class="sxs-lookup"><span data-stu-id="fe74b-142">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="fe74b-143">您可以使用任何文字型編輯器來讀取，登入用戶端時會建立新記錄。</span><span class="sxs-lookup"><span data-stu-id="fe74b-143">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="fe74b-144">調試記錄會顯示下列資料流程：</span><span class="sxs-lookup"><span data-stu-id="fe74b-144">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="fe74b-145">登錄</span><span class="sxs-lookup"><span data-stu-id="fe74b-145">Login</span></span>

-   <span data-ttu-id="fe74b-146">到中介層服務的連接要求</span><span class="sxs-lookup"><span data-stu-id="fe74b-146">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="fe74b-147">通話/交談</span><span class="sxs-lookup"><span data-stu-id="fe74b-147">Call/conversation</span></span>

<span data-ttu-id="fe74b-148">使用下列 OS 特定方法產生調試記錄：</span><span class="sxs-lookup"><span data-stu-id="fe74b-148">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="fe74b-149">Windows：</span><span class="sxs-lookup"><span data-stu-id="fe74b-149">Windows:</span></span>

      <span data-ttu-id="fe74b-150">鍵盤快速鍵：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="fe74b-150">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="fe74b-151">Mac OSX：</span><span class="sxs-lookup"><span data-stu-id="fe74b-151">Mac OSX:</span></span>

      <span data-ttu-id="fe74b-152">鍵盤快速鍵：Option + Command + Shift+1</span><span class="sxs-lookup"><span data-stu-id="fe74b-152">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="fe74b-153">Linux：</span><span class="sxs-lookup"><span data-stu-id="fe74b-153">Linux:</span></span>

      <span data-ttu-id="fe74b-154">鍵盤快速鍵：Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="fe74b-154">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="fe74b-155">系統會自動將調試記錄下載到下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="fe74b-155">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="fe74b-156">Windows：%userprofile% \\ 下載</span><span class="sxs-lookup"><span data-stu-id="fe74b-156">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="fe74b-157">Mac OSX：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="fe74b-157">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="fe74b-158">Linux：~/Downloads</span><span class="sxs-lookup"><span data-stu-id="fe74b-158">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="fe74b-159">瀏覽器：系統會提示您儲存調試記錄至預設儲存位置</span><span class="sxs-lookup"><span data-stu-id="fe74b-159">Browser: You will be prompted to save the debug log to default save location</span></span>

## <a name="media-logs"></a><span data-ttu-id="fe74b-160">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="fe74b-160">Media logs</span></span>

<span data-ttu-id="fe74b-161">媒體記錄包含會議中音訊、視像和螢幕Teams資料。</span><span class="sxs-lookup"><span data-stu-id="fe74b-161">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="fe74b-162">當支援案例與通話相關問題連結時，這些案例是必填專案。</span><span class="sxs-lookup"><span data-stu-id="fe74b-162">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="fe74b-163">媒體記錄預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="fe74b-163">Media logging is turned off by default.</span></span> <span data-ttu-id="fe74b-164">若要記錄會議Teams診斷資料，使用者必須在用戶端中開啟Teams選項。</span><span class="sxs-lookup"><span data-stu-id="fe74b-164">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="fe74b-165">請 **設定** 一般，選取啟用會議診斷記錄 (需要重新開機  >  \*\*\*\* **Teams)** 核取方塊、重新開機 Teams，然後重現問題。</span><span class="sxs-lookup"><span data-stu-id="fe74b-165">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="fe74b-166">下表概述媒體記錄位置。</span><span class="sxs-lookup"><span data-stu-id="fe74b-166">The following table outlines the media log locations.</span></span> <span data-ttu-id="fe74b-167">當您將記錄檔案傳送給 Microsoft 支援人員時，請確認記錄檔案的時間戳記，以確保記錄在您重現問題時涵蓋時間範圍。</span><span class="sxs-lookup"><span data-stu-id="fe74b-167">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="fe74b-168">用戶端</span><span class="sxs-lookup"><span data-stu-id="fe74b-168">Client</span></span> |<span data-ttu-id="fe74b-169">位置</span><span class="sxs-lookup"><span data-stu-id="fe74b-169">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fe74b-170">Windows</span><span class="sxs-lookup"><span data-stu-id="fe74b-170">Windows</span></span>     |<span data-ttu-id="fe74b-171">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="fe74b-172">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="fe74b-173">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="fe74b-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="fe74b-174">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fe74b-174">Mac OSX</span></span>     |<span data-ttu-id="fe74b-175">~/Library/Application Support/microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="fe74b-176">~/Library/Application Support/microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="fe74b-177">Linux</span><span class="sxs-lookup"><span data-stu-id="fe74b-177">Linux</span></span>       |<span data-ttu-id="fe74b-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="fe74b-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="fe74b-180">以下是產生的記錄檔案清單及其包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="fe74b-180">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="fe74b-181">記錄檔案名</span><span class="sxs-lookup"><span data-stu-id="fe74b-181">Log file name</span></span>  |<span data-ttu-id="fe74b-182">描述</span><span class="sxs-lookup"><span data-stu-id="fe74b-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fe74b-183">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-183">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="fe74b-184">包含媒體堆疊相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fe74b-184">Contains information related to the media stack.</span></span> <span data-ttu-id="fe74b-185">這包括頻道狀態，例如解析度、使用的解碼器及編碼器，以及接收和接收的畫面數量，以及視 (VBSS) 會話狀態。</span><span class="sxs-lookup"><span data-stu-id="fe74b-185">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="fe74b-186">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-186">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="fe74b-187">記錄與遠端控制動作相關的資訊，例如提供控制項時時間戳記，以及滑鼠指標資訊。</span><span class="sxs-lookup"><span data-stu-id="fe74b-187">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="fe74b-188">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="fe74b-188">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="fe74b-189">記錄媒體堆疊追蹤事件。</span><span class="sxs-lookup"><span data-stu-id="fe74b-189">Records media stack trace events.</span></span>         |
|<span data-ttu-id="fe74b-190">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-190">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="fe74b-191">包含媒體代理程式相關資訊，包括呈現品質。</span><span class="sxs-lookup"><span data-stu-id="fe74b-191">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="fe74b-192">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="fe74b-192">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="fe74b-193">在 ts-calling API 中記錄事件。</span><span class="sxs-lookup"><span data-stu-id="fe74b-193">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="fe74b-194">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="fe74b-194">Desktop logs</span></span>

<span data-ttu-id="fe74b-195">桌面記錄 ，也稱為 bootstrapper 記錄，包含桌面用戶端與瀏覽器之間發生的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="fe74b-195">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="fe74b-196">與媒體記錄一樣，這些記錄只有在 Microsoft 要求時才能使用。</span><span class="sxs-lookup"><span data-stu-id="fe74b-196">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="fe74b-197">記錄是以文字為基礎，而且可以使用由上而下格式的任何文字型編輯器來讀取。</span><span class="sxs-lookup"><span data-stu-id="fe74b-197">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="fe74b-198">Windows：</span><span class="sxs-lookup"><span data-stu-id="fe74b-198">Windows:</span></span>

 - <span data-ttu-id="fe74b-199">以滑鼠 **右鍵Microsoft Teams** 系統工作列中的 [取得記錄記錄> 圖示 **。**</span><span class="sxs-lookup"><span data-stu-id="fe74b-199">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="fe74b-200">Mac OsX：</span><span class="sxs-lookup"><span data-stu-id="fe74b-200">Mac OsX:</span></span>

 - <span data-ttu-id="fe74b-201">從 **説明下拉式功能表\*\*\*\*選擇取得記錄**。</span><span class="sxs-lookup"><span data-stu-id="fe74b-201">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="fe74b-202">Linux：</span><span class="sxs-lookup"><span data-stu-id="fe74b-202">Linux:</span></span>

 - <span data-ttu-id="fe74b-203">按一下 **系統Microsoft Teams中的**[取得記錄記錄>**圖示。**</span><span class="sxs-lookup"><span data-stu-id="fe74b-203">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="fe74b-204">用戶端</span><span class="sxs-lookup"><span data-stu-id="fe74b-204">Client</span></span> |<span data-ttu-id="fe74b-205">位置</span><span class="sxs-lookup"><span data-stu-id="fe74b-205">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fe74b-206">Windows</span><span class="sxs-lookup"><span data-stu-id="fe74b-206">Windows</span></span>     |<span data-ttu-id="fe74b-207">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="fe74b-207">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="fe74b-208">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fe74b-208">Mac OSX</span></span>     |<span data-ttu-id="fe74b-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="fe74b-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="fe74b-210">Linux</span><span class="sxs-lookup"><span data-stu-id="fe74b-210">Linux</span></span>       |<span data-ttu-id="fe74b-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="fe74b-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="browser-trace"></a><span data-ttu-id="fe74b-212">瀏覽器追蹤</span><span class="sxs-lookup"><span data-stu-id="fe74b-212">Browser trace</span></span>

<span data-ttu-id="fe74b-213">針對某些類別的錯誤，Microsoft 支援服務可能會要求您收集瀏覽器追蹤。</span><span class="sxs-lookup"><span data-stu-id="fe74b-213">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="fe74b-214">這項資訊可提供發生錯誤時Teams用戶端狀態的重要詳細資料。</span><span class="sxs-lookup"><span data-stu-id="fe74b-214">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="fe74b-215">在啟動瀏覽器追蹤之前，請確認您已Teams。</span><span class="sxs-lookup"><span data-stu-id="fe74b-215">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="fe74b-216">在啟動追蹤之前，執行這項工作非常重要，這樣追蹤就不包含敏感性的登錄資訊。</span><span class="sxs-lookup"><span data-stu-id="fe74b-216">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="fe74b-217">在您登錄後，請選取下列其中一個連結 ，以適合您的瀏覽器使用，然後遵循所提供的步驟。</span><span class="sxs-lookup"><span data-stu-id="fe74b-217">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="fe74b-218">Chrome & Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="fe74b-218">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="fe74b-219">邊緣</span><span class="sxs-lookup"><span data-stu-id="fe74b-219">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="fe74b-220">Safari</span><span class="sxs-lookup"><span data-stu-id="fe74b-220">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="fe74b-221">火狐</span><span class="sxs-lookup"><span data-stu-id="fe74b-221">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="fe74b-222">在步驟中，將 Azure 入口網站的所有參照取代為Teams用戶端。</span><span class="sxs-lookup"><span data-stu-id="fe74b-222">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="fe74b-223">相關主題</span><span class="sxs-lookup"><span data-stu-id="fe74b-223">Related topics</span></span>

[<span data-ttu-id="fe74b-224">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="fe74b-224">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
