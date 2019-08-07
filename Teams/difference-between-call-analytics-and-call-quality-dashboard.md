---
title: '[通話分析] 和 [通話品質儀表板]'
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 瞭解 [通話分析] 和 [通話品質儀表板], 以及何時使用它們監視及排除通話品質問題。
ms.openlocfilehash: 535d3bf6ce2abf69143fb270e01bf4f0c2e230dc
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36183747"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="ccdc4-103">[通話分析] 和 [通話品質儀表板]</span><span class="sxs-lookup"><span data-stu-id="ccdc4-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="ccdc4-104">Microsoft 團隊和商務用 Skype 提供兩種監視及疑難排解通話品質問題的方法: [通話分析] 和 [通話品質儀表板] (CQD)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="ccdc4-105">本文將說明這兩者, 並告訴您何時使用每一個專案。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-105">This article describes both and tells you when to use each one.</span></span>

<span data-ttu-id="ccdc4-106">呼叫分析與 CQD 會並存執行, 而且可以獨立地或一起使用。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-106">Call Analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="ccdc4-107">例如, 說通訊支援專家認為他們需要進一步協助疑難排解通話問題。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-107">For example, say a communications support specialist determines that they need more help troubleshooting a call problem.</span></span> <span data-ttu-id="ccdc4-108">通訊支援專家將呼叫傳遞給通訊支援工程師, 使用者可以存取呼叫分析中的其他資訊, 而不是通訊支援專家。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-108">The communications support specialist passes the call to a communications support engineer, who has access to more information in Call Analytics than the communications support specialist.</span></span> <span data-ttu-id="ccdc4-109">接著, 通訊支援工程師可以提醒網路工程師發生問題。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-109">In turn, the communications support engineer can alert a network engineer to an issue.</span></span> <span data-ttu-id="ccdc4-110">網路工程師可能會檢查 CQD, 以查看總體網站相關問題是否可能是引起呼叫問題的問題。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-110">The network engineer might check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>

## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="ccdc4-111">什麼是呼叫分析, 何時應該使用它？</span><span class="sxs-lookup"><span data-stu-id="ccdc4-111">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="ccdc4-112">**[通話分析] 現已提供給[Microsoft [團隊管理中心](https://admin.teams.microsoft.com)]。**</span><span class="sxs-lookup"><span data-stu-id="ccdc4-112">**Call Analytics is now available in the [Microsoft Teams admin center](https://admin.teams.microsoft.com).**</span></span> <span data-ttu-id="ccdc4-113">若要查看使用者的所有通話資訊和資料, 請使用 [**通話記錄**] 索引標籤。您可以查看使用者的設定檔頁面面, 方法是從儀表板搜尋使用者, 或從左側流覽中的**使用者**尋找使用者。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-113">To see all of the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by either searching for the user from the dashboard or finding the user from **Users** in the left navigation.</span></span>

<span data-ttu-id="ccdc4-114">[通話分析] 會顯示與 Microsoft 團隊或商務用 Skype 帳戶中每位使用者的特定通話與會議相關的裝置、網路及連線性的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-114">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="ccdc4-115">為什麼此使用者的通話不佳？</span><span class="sxs-lookup"><span data-stu-id="ccdc4-115">Why did this user have a poor call this afternoon?</span></span> <span data-ttu-id="ccdc4-116">使用呼叫分析, Office 365 系統管理員或訓練有素的支援者代理程式可以調查與其通話相關的裝置、網路、連線及其他因素, 以解決 Microsoft 團隊與商務用 Skype 中的通話品質和連線問題。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-116">Using Call Analytics, an Office 365 admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to his call to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

<span data-ttu-id="ccdc4-117">若要在 Microsoft 團隊系統管理中心查看使用者的這項資訊, 請在 [使用者詳細資料] 頁面中按一下該使用者的 [**通話記錄**] 索引標籤, 並顯示使用者在過去30天內參與的所有通話和會議。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-117">To see this information for a user in the Microsoft Teams admin center, click the **Call History** tab for that user in the user detail page, showing all the calls and meetings that user has participated in for the last 30 days.</span></span>

![所有分析使用者資料的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="ccdc4-119">若要取得特定會話的其他相關資訊, 包括詳細的媒體和網路統計資料, 請按一下會話以查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-119">To get additional information about a given session including detailed media and networking statistics, click on a session to see the details.</span></span>

![通話分析使用者會話資料的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

<span data-ttu-id="ccdc4-121">如果您想要非系統管理員 (例如來自外部廠商的支援人員) 使用呼叫分析, 您可以指派許可權, 讓他們可以使用呼叫分析, 但他們無法存取 Microsoft 團隊系統管理中心的其他部分:</span><span class="sxs-lookup"><span data-stu-id="ccdc4-121">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics, but they can't access the rest of the Microsoft Teams admin center:</span></span> 
  
- <span data-ttu-id="ccdc4-122">**提供通訊支援專家許可權的支援人員**: 代理程式會在通話分析中看到一組有限的資料和個人辨識資訊 (PII)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-122">**Helpdesk agents with communications support specialist permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics.</span></span> <span data-ttu-id="ccdc4-123">他們可以對通話進行疑難排解, 但他們會將會議問題移交給通訊支援工程師。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-123">They can troubleshoot calls, but they will hand off problems with meetings to a communications support engineer.</span></span>
    
- <span data-ttu-id="ccdc4-124">**含通訊支援工程師許可權的支援人員代理**: 代理程式會查看通話分析中所有可用的資料, 並同時為通話與會議進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-124">**Helpdesk agents with communications support engineer permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings.</span></span> <span data-ttu-id="ccdc4-125">他們擁有通話記錄及客戶資訊的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-125">They have full access to call logs and customer information.</span></span>

> [!NOTE]
> <span data-ttu-id="ccdc4-126">通訊支援專家角色相當於預覽入口網站中的第1層支援角色, 且通訊支援工程師角色相當於預覽入口網站中的第2層支援角色。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-126">The communications support specialist role is equivalent to tier 1 support role from the preview portal and the communications support engineer role is equivalent to tier 2 support role from the preview portal.</span></span>

<span data-ttu-id="ccdc4-127">如需溝通支援專家和通訊支援工程師角色的詳細資訊, 請參閱[使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-127">For more information about the communications support specialist and communications support engineer roles, see [Use Microsoft Teams admin roles to manage teams](using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccdc4-128">Microsoft 團隊系統管理中心提供服務台代理許可權和網路拓撲上傳。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-128">Helpdesk agent permissions and network topology upload are available in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ccdc4-129">溝通支援專家和溝通支援工程師可以使用此入口網站存取通話分析和通話品質儀表板。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-129">Communications Support Specialists and Communications Support Engineers can use this portal to access Call Analytics and the Call Quality Dashboard.</span></span>
    
<span data-ttu-id="ccdc4-130">如需設定撥號分析的詳細資料, 請參閱[設定商務用 Skype 通話分析](set-up-call-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-130">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="ccdc4-131">如需説明台代理程式如何使用呼叫分析的詳細資訊, 請參閱[使用通話分析來診斷不佳通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-131">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="ccdc4-132">什麼是通話品質儀表板, 我該如何使用？</span><span class="sxs-lookup"><span data-stu-id="ccdc4-132">What's the Call Quality Dashboard, and when should I use it?</span></span>
  
<span data-ttu-id="ccdc4-133">[通話分析] 的設計目的是協助系統管理員和支援人員診斷特定通話的通話品質問題, 通話品質儀表板 (CQD) 是專門用來協助團隊管理員、商務用 Skype 系統管理員和網路工程師優化網路。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-133">Whereas Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Teams admins, Skype for Business admins, and network engineers optimize a network.</span></span> <span data-ttu-id="ccdc4-134">CQD 會將焦點從特定的使用者轉移, 而不是查看整個團隊或商務用 Skype 組織的匯總資訊。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-134">CQD shifts focus from specific users and instead looks at aggregate information for an entire Teams or Skype for Business organization.</span></span> <span data-ttu-id="ccdc4-135">如需詳細資訊, 請參閱[適用于團隊和商務用 Skype Online 的通話品質儀表板功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-135">For more details, see [Features of the Call Quality Dashboard for Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="ccdc4-136">使用者的通話品質可能不佳, 因為網路問題也會影響許多其他使用者。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-136">Maybe the user's poor call quality is due to a network issue that's also affecting many other users.</span></span> <span data-ttu-id="ccdc4-137">在 CQD 中看不到個別通話體驗, 但會捕獲使用 Microsoft 團隊或商務用 Skype 所做的整體品質。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-137">The individual call experience isn't visible in CQD, but the overall quality of calls made using Microsoft Teams or Skype for Business is captured.</span></span> <span data-ttu-id="ccdc4-138">使用 CQD 時, 整個模式可能會變得很明顯, 讓網路工程師能作出及時的通話品質評估。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-138">With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality.</span></span> <span data-ttu-id="ccdc4-139">CQD 提供通話品質度量的報告, 可讓您深入瞭解整個通話品質、伺服器用戶端資料流程、用戶端資料流程及語音品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-139">CQD provides reports of call quality metrics that give you insights into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>
  
![通話品質儀表板的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="ccdc4-141">有了 CQD 的位置改良報表的說明, 您可以評估匯總式通話品質與使用者組建中的可靠性, 以判斷問題是獨立在單一使用者, 還是會影響較大的使用者區段。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-141">With the help of CQD's Location-Enhanced Reports, aggregate call quality and reliability within the user's building can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span>

![[通話品質儀表板] 的位置改良報告的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> <span data-ttu-id="ccdc4-143">若要在 CQD 中啟用組建或端點專用的視圖, 系統管理員必須在 CQD 的租使用者資料上傳頁面上[傳建築物或端點資訊](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-143">To enable building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) on CQD's Tenant Data Upload page.</span></span> 

<span data-ttu-id="ccdc4-144">如果您想要使用非系統管理員 (例如支援者代理程式) 來使用 [通話品質儀表板], 您可以將這些使用者指派給**團隊通訊支援工程師**、**團隊溝通支援專家**或**報表閱讀**者角色。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-144">If you want non-admins, such as helpdesk agents, to use Call Quality Dashboard, you can assign those users the **Teams Communications Support Engineer**, **Teams Communications Support Specialist**, or **Reports Reader** role.</span></span> <span data-ttu-id="ccdc4-145">具有下列角色的使用者可以存取通話品質儀表板:</span><span class="sxs-lookup"><span data-stu-id="ccdc4-145">Users with the following roles can access Call Quality Dashboard:</span></span>

- <span data-ttu-id="ccdc4-146">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="ccdc4-146">Global Administrator</span></span>
- <span data-ttu-id="ccdc4-147">全域閱讀程式</span><span class="sxs-lookup"><span data-stu-id="ccdc4-147">Global Reader</span></span>
- <span data-ttu-id="ccdc4-148">商務用 Skype 系統管理員</span><span class="sxs-lookup"><span data-stu-id="ccdc4-148">Skype for Business Administrator</span></span>
- <span data-ttu-id="ccdc4-149">團隊服務管理員</span><span class="sxs-lookup"><span data-stu-id="ccdc4-149">Teams Service Administrator</span></span>
- <span data-ttu-id="ccdc4-150">團隊溝通系統管理員</span><span class="sxs-lookup"><span data-stu-id="ccdc4-150">Teams Communications Administrator</span></span>
- <span data-ttu-id="ccdc4-151">團隊溝通支援工程師</span><span class="sxs-lookup"><span data-stu-id="ccdc4-151">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="ccdc4-152">團隊溝通支援專家</span><span class="sxs-lookup"><span data-stu-id="ccdc4-152">Teams Communications Support Specialist</span></span>
- <span data-ttu-id="ccdc4-153">報表閱讀程式</span><span class="sxs-lookup"><span data-stu-id="ccdc4-153">Reports Reader</span></span>

> [!NOTE]
> <span data-ttu-id="ccdc4-154">團隊通訊支援工程師、團隊溝通支援專家及報告閱讀者角色無法在 CQD 的租使用者上修改檔案, 也無法在租使用者啟用 CQD。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-154">The Teams Communications Support Engineer, Teams Communications Support Specialist, and Reports Reader roles cannot modify files on CQD's Tenant Data Upload page nor activate CQD for a tenant.</span></span>

<span data-ttu-id="ccdc4-155">如需有關這些角色的詳細資訊, 請參閱[關於 Office 365 系統管理員角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-155">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="ccdc4-156">如需有關 CQD 的詳細資訊, 請參閱[開啟與使用 Microsoft 團隊和商務用 Skype online 的通話品質儀表板](turning-on-and-using-call-quality-dashboard.md), 以及[Microsoft 團隊和商務用 Skype Online 的通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdc4-156">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ccdc4-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="ccdc4-157">Related topics</span></span>

[<span data-ttu-id="ccdc4-158">影片: 通話品質概覽</span><span class="sxs-lookup"><span data-stu-id="ccdc4-158">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="ccdc4-159">設定通話分析</span><span class="sxs-lookup"><span data-stu-id="ccdc4-159">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="ccdc4-160">使用呼叫分析來排查不佳的通話品質問題</span><span class="sxs-lookup"><span data-stu-id="ccdc4-160">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="ccdc4-161">開啟並使用 Microsoft 團隊及商務用 Skype Online 的通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="ccdc4-161">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>](turning-on-and-using-call-quality-dashboard.md)
