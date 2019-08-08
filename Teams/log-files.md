---
title: 在 Microsoft 團隊的疑難排解中使用記錄檔
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: 瞭解 Microsoft 團隊所產生的調試、媒體和桌面記錄, 以及可在哪裡找到這些記錄, 以及如何協助疑難排解。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6af503206118b03d9d86fdaf2491e92c69cf9716
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245087"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="f86c9-103">在 Microsoft 團隊的疑難排解中使用記錄檔</span><span class="sxs-lookup"><span data-stu-id="f86c9-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="f86c9-104">用戶端自動產生三種類型的記錄檔案, 可利用這些檔案來協助您針對 Microsoft 團隊進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="f86c9-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="f86c9-105">調試記錄</span><span class="sxs-lookup"><span data-stu-id="f86c9-105">Debug logs</span></span>

-   <span data-ttu-id="f86c9-106">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="f86c9-106">Media logs</span></span>

-   <span data-ttu-id="f86c9-107">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="f86c9-107">Desktop logs</span></span>

<span data-ttu-id="f86c9-108">建立含 Microsoft 支援的支援要求時, 支援工程師將需要調試記錄。</span><span class="sxs-lookup"><span data-stu-id="f86c9-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="f86c9-109">建立支援要求之前, 請先將這些記錄放在手邊, 讓 Microsoft 能夠快速開始疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="f86c9-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="f86c9-110">媒體或桌面記錄只有 Microsoft 要求時才是必要的。</span><span class="sxs-lookup"><span data-stu-id="f86c9-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="f86c9-111">下表列出各種用戶端及其相關記錄。</span><span class="sxs-lookup"><span data-stu-id="f86c9-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="f86c9-112">記錄檔案會儲存在用戶端與作業系統專用的位置。</span><span class="sxs-lookup"><span data-stu-id="f86c9-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="f86c9-113">端</span><span class="sxs-lookup"><span data-stu-id="f86c9-113">Client</span></span> |<span data-ttu-id="f86c9-114">Debug</span><span class="sxs-lookup"><span data-stu-id="f86c9-114">Debug</span></span>|<span data-ttu-id="f86c9-115">桌面</span><span class="sxs-lookup"><span data-stu-id="f86c9-115">Desktop</span></span>|<span data-ttu-id="f86c9-116">媒體</span><span class="sxs-lookup"><span data-stu-id="f86c9-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="f86c9-117">網站</span><span class="sxs-lookup"><span data-stu-id="f86c9-117">Web</span></span>    |<span data-ttu-id="f86c9-118">X</span><span class="sxs-lookup"><span data-stu-id="f86c9-118">X</span></span>         |-         |-         |
|<span data-ttu-id="f86c9-119">時間</span><span class="sxs-lookup"><span data-stu-id="f86c9-119">Windows</span></span>     |<span data-ttu-id="f86c9-120">X</span><span class="sxs-lookup"><span data-stu-id="f86c9-120">X</span></span>         |<span data-ttu-id="f86c9-121">X</span><span class="sxs-lookup"><span data-stu-id="f86c9-121">X</span></span>         |<span data-ttu-id="f86c9-122">X</span><span class="sxs-lookup"><span data-stu-id="f86c9-122">X</span></span>         |
|<span data-ttu-id="f86c9-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f86c9-123">Mac OSX</span></span>     |<span data-ttu-id="f86c9-124">X</span><span class="sxs-lookup"><span data-stu-id="f86c9-124">X</span></span>         |<span data-ttu-id="f86c9-125">X</span><span class="sxs-lookup"><span data-stu-id="f86c9-125">X</span></span>         |<span data-ttu-id="f86c9-126">X</span><span class="sxs-lookup"><span data-stu-id="f86c9-126">X</span></span>         |
|<span data-ttu-id="f86c9-127">且</span><span class="sxs-lookup"><span data-stu-id="f86c9-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="f86c9-128">Android</span><span class="sxs-lookup"><span data-stu-id="f86c9-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="f86c9-129">如需支援的作業系統和瀏覽器的完整清單, 請參閱[取得 Microsoft 團隊的用戶端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="f86c9-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="f86c9-130">調試記錄</span><span class="sxs-lookup"><span data-stu-id="f86c9-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="f86c9-131">這些是最常見的記錄, 而且對於所有 Microsoft 支援案例都是必要的。</span><span class="sxs-lookup"><span data-stu-id="f86c9-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="f86c9-132">[調試記錄] 是由 Windows 和 Mac 桌面用戶端以及瀏覽器的用戶端所產生。</span><span class="sxs-lookup"><span data-stu-id="f86c9-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="f86c9-133">這些記錄都是以文字為基礎, 並從底部開始閱讀。</span><span class="sxs-lookup"><span data-stu-id="f86c9-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="f86c9-134">他們可以使用任何以文字為基礎的編輯器讀取, 並在登入用戶端時建立新的記錄。</span><span class="sxs-lookup"><span data-stu-id="f86c9-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="f86c9-135">[調試記錄] 會顯示下列資料流程程:</span><span class="sxs-lookup"><span data-stu-id="f86c9-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="f86c9-136">Id</span><span class="sxs-lookup"><span data-stu-id="f86c9-136">Login</span></span>

-   <span data-ttu-id="f86c9-137">中介層服務的連線要求</span><span class="sxs-lookup"><span data-stu-id="f86c9-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="f86c9-138">通話/交談</span><span class="sxs-lookup"><span data-stu-id="f86c9-138">Call/conversation</span></span>

<span data-ttu-id="f86c9-139">調試記錄是使用下列 OS 特定方法產生:</span><span class="sxs-lookup"><span data-stu-id="f86c9-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="f86c9-140">時間</span><span class="sxs-lookup"><span data-stu-id="f86c9-140">Windows:</span></span>

      <span data-ttu-id="f86c9-141">鍵盤快速鍵: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="f86c9-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="f86c9-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="f86c9-142">Mac OSX:</span></span>

      <span data-ttu-id="f86c9-143">鍵盤快速鍵: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="f86c9-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="f86c9-144">調試記錄會自動下載到下列資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f86c9-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="f86c9-145">Windows:% userprofile%\\下載</span><span class="sxs-lookup"><span data-stu-id="f86c9-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="f86c9-146">Mac OSX: 下載</span><span class="sxs-lookup"><span data-stu-id="f86c9-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="f86c9-147">瀏覽器: 系統會提示您將調試記錄儲存到預設的儲存位置</span><span class="sxs-lookup"><span data-stu-id="f86c9-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="f86c9-148">媒體記錄</span><span class="sxs-lookup"><span data-stu-id="f86c9-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="f86c9-149">媒體記錄包含音訊、影片和螢幕共用的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="f86c9-149">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="f86c9-150">只有在要求且只能由 Microsoft 檢查時, 才需要支援案例。</span><span class="sxs-lookup"><span data-stu-id="f86c9-150">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="f86c9-151">下表列出記錄位置。</span><span class="sxs-lookup"><span data-stu-id="f86c9-151">The following table outlines the log location.</span></span>


|<span data-ttu-id="f86c9-152">端</span><span class="sxs-lookup"><span data-stu-id="f86c9-152">Client</span></span> |<span data-ttu-id="f86c9-153">位置</span><span class="sxs-lookup"><span data-stu-id="f86c9-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="f86c9-154">時間</span><span class="sxs-lookup"><span data-stu-id="f86c9-154">Windows</span></span>     |<span data-ttu-id="f86c9-155">%appdata%\Microsoft\Teams\media-stack\\*. 博客</span><span class="sxs-lookup"><span data-stu-id="f86c9-155">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="f86c9-156">%appdata%\Microsoft\Teams\skylib\\*. 博客</span><span class="sxs-lookup"><span data-stu-id="f86c9-156">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="f86c9-157">%appdata%\Microsoft\Teams\media-stack\\* .etl</span><span class="sxs-lookup"><span data-stu-id="f86c9-157">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="f86c9-158">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f86c9-158">Mac OSX</span></span>     |<span data-ttu-id="f86c9-159">~ 路徑/library/application support 支援/Microsoft/團隊/media-stack/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="f86c9-159">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="f86c9-160">~ 路徑/library/application support 支援/Microsoft/團隊/skylib/\*. 博客</span><span class="sxs-lookup"><span data-stu-id="f86c9-160">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="f86c9-161">桌面記錄</span><span class="sxs-lookup"><span data-stu-id="f86c9-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="f86c9-162">桌面記錄 (也稱為引導程式記錄) 包含在桌面用戶端與瀏覽器之間所發生的記錄資料。</span><span class="sxs-lookup"><span data-stu-id="f86c9-162">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="f86c9-163">就像媒體記錄一樣, 只有 Microsoft 要求時才需要這些記錄。</span><span class="sxs-lookup"><span data-stu-id="f86c9-163">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="f86c9-164">這些記錄是以文字為基礎的, 而且可以使用任何以文字為基礎的編輯器, 以最高的格式閱讀。</span><span class="sxs-lookup"><span data-stu-id="f86c9-164">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="f86c9-165">時間</span><span class="sxs-lookup"><span data-stu-id="f86c9-165">Windows:</span></span>

1.  <span data-ttu-id="f86c9-166">以滑鼠右鍵按一下應用程式紙盒**中的 [Microsoft 團隊] 圖示**, 然後選取 [**取得記錄**]</span><span class="sxs-lookup"><span data-stu-id="f86c9-166">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

<span data-ttu-id="f86c9-167">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="f86c9-167">Mac OsX:</span></span>

1.  <span data-ttu-id="f86c9-168">從 [說明] 下拉式\*\*\*\* 功能表中選擇 [**取得記錄**]</span><span class="sxs-lookup"><span data-stu-id="f86c9-168">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="f86c9-169">端</span><span class="sxs-lookup"><span data-stu-id="f86c9-169">Client</span></span> |<span data-ttu-id="f86c9-170">位置</span><span class="sxs-lookup"><span data-stu-id="f86c9-170">Location</span></span> |
|---------|---------|
|<span data-ttu-id="f86c9-171">時間</span><span class="sxs-lookup"><span data-stu-id="f86c9-171">Windows</span></span>     |<span data-ttu-id="f86c9-172">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="f86c9-172">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="f86c9-173">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="f86c9-173">Mac OSX</span></span>     |<span data-ttu-id="f86c9-174">~ 路徑/library/application support 支援/Microsoft/團隊/記錄 .txt</span><span class="sxs-lookup"><span data-stu-id="f86c9-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
