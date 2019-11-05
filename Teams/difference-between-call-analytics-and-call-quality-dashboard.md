---
title: 通話分析和通話品質儀表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 瞭解 [通話分析] 和 [通話品質儀表板]，以及何時使用它們監視及排除通話品質問題。
ms.openlocfilehash: 70efd7f17189d9aac2236383a07cfc5fc0a37096
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972464"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="d1721-103">通話分析和通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="d1721-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="d1721-104">Microsoft 團隊和商務用 Skype 提供兩種監視及疑難排解通話品質問題的方法： [通話分析] 和 [通話品質儀表板] （CQD）。</span><span class="sxs-lookup"><span data-stu-id="d1721-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="d1721-105">本文將說明這兩者，並告訴您何時使用每一個專案。</span><span class="sxs-lookup"><span data-stu-id="d1721-105">This article describes both and tells you when to use each one.</span></span>

<span data-ttu-id="d1721-106">呼叫分析與 CQD 會並存執行，而且可以獨立地或一起使用。</span><span class="sxs-lookup"><span data-stu-id="d1721-106">Call Analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="d1721-107">例如，假設通訊支援專家認為他們需要進一步協助疑難排解通話問題。</span><span class="sxs-lookup"><span data-stu-id="d1721-107">For example, say that a communications support specialist determines that they need more help troubleshooting a call problem.</span></span> <span data-ttu-id="d1721-108">通訊支援專家將呼叫傳遞給通訊支援工程師，使用者可以存取呼叫分析中的其他資訊，而不是通訊支援專家。</span><span class="sxs-lookup"><span data-stu-id="d1721-108">The communications support specialist passes the call to a communications support engineer, who has access to more information in Call Analytics than the communications support specialist.</span></span> <span data-ttu-id="d1721-109">接著，通訊支援工程師可以提醒網路工程師發生問題。</span><span class="sxs-lookup"><span data-stu-id="d1721-109">In turn, the communications support engineer can alert a network engineer to an issue.</span></span> <span data-ttu-id="d1721-110">網路工程師可以檢查 CQD，以查看總體網站相關問題是否可能是引起呼叫問題的問題。</span><span class="sxs-lookup"><span data-stu-id="d1721-110">The network engineer can check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>

## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="d1721-111">什麼是呼叫分析，何時應該使用它？</span><span class="sxs-lookup"><span data-stu-id="d1721-111">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="d1721-112">**[通話分析] 現已提供給[Microsoft [團隊管理中心](https://admin.teams.microsoft.com)]。**</span><span class="sxs-lookup"><span data-stu-id="d1721-112">**Call Analytics is now available in the [Microsoft Teams admin center](https://admin.teams.microsoft.com).**</span></span> <span data-ttu-id="d1721-113">若要查看使用者的所有呼叫資訊和資料，請使用使用者設定檔頁面上的 [**通話記錄**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d1721-113">To see all call information and data for a user, use the **Call History** tab on a user's profile page.</span></span> <span data-ttu-id="d1721-114">若要查看索引標籤，請從 [儀表板] 搜尋使用者，或從左側導覽列的 [**使用者**] 索引標籤尋找使用者。</span><span class="sxs-lookup"><span data-stu-id="d1721-114">To see the tab, either search for the user from the dashboard or find the user from the **Users** tab in the left navigation bar.</span></span>

<span data-ttu-id="d1721-115">[通話分析] 會顯示與 Microsoft 團隊或商務用 Skype 租使用者帳戶中每位使用者的通話與會議相關的裝置、網路及連線能力的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d1721-115">Call Analytics shows detailed information about the devices, networks, and connectivity related to the calls and meetings for each user in a Microsoft Teams or Skype for Business tenant account.</span></span> <span data-ttu-id="d1721-116">為什麼此使用者的通話不佳？</span><span class="sxs-lookup"><span data-stu-id="d1721-116">Why did this user have a poor call this afternoon?</span></span> <span data-ttu-id="d1721-117">使用呼叫分析，Office 365 系統管理員或訓練有素的支援者代理程式可以調查裝置、網路、連線，以及在 Microsoft 團隊與商務用 Skype 中呼叫品質和連線問題的通話相關的其他因素。</span><span class="sxs-lookup"><span data-stu-id="d1721-117">With Call Analytics, an Office 365 admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to a call to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

<span data-ttu-id="d1721-118">若要在 Microsoft 團隊系統管理中心查看使用者的這項資訊，請按一下 [使用者詳細資料] 頁面中該使用者的 [**通話記錄**] 索引標籤，即可查看該使用者在過去30天內的所有通話與會議。</span><span class="sxs-lookup"><span data-stu-id="d1721-118">To see this information for a user in the Microsoft Teams admin center, click the **Call History** tab for that user in the user detail page to see all calls and meetings for that user in the last 30 days.</span></span>

![所有分析使用者資料的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="d1721-120">若要取得特定會話的其他相關資訊，包括詳細的媒體和網路統計資料，請按一下某個會話查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d1721-120">To get additional information about a given session including detailed media and networking statistics, click a session to see the details.</span></span>

![呼叫分析使用者會話資料的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

<span data-ttu-id="d1721-122">如果您希望非系統管理員（例如外部廠商提供的支援人員）使用呼叫分析，您可以指派許可權，讓他們可以使用呼叫分析，但他們無法存取 Microsoft 團隊系統管理中心的其他部分：</span><span class="sxs-lookup"><span data-stu-id="d1721-122">If you want non-admins (such as helpdesk agents from an external vendor) to use Call Analytics, you can assign permissions so that they can use Call Analytics, but they can't access the rest of the Microsoft Teams admin center:</span></span>
  
- <span data-ttu-id="d1721-123">**提供通訊支援專家許可權的支援人員**：代理程式會在通話分析中看到一組有限的資料和個人辨識資訊（PII）。</span><span class="sxs-lookup"><span data-stu-id="d1721-123">**Helpdesk agents with communications support specialist permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics.</span></span> <span data-ttu-id="d1721-124">他們可以對通話進行疑難排解，但他們會將會議問題提升至通訊支援工程師。</span><span class="sxs-lookup"><span data-stu-id="d1721-124">They can troubleshoot calls, but they escalate problems with meetings to a communications support engineer.</span></span>
- <span data-ttu-id="d1721-125">**含通訊支援工程師許可權的支援人員代理**：代理程式會查看通話分析中所有可用的資料，並同時為通話與會議進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="d1721-125">**Helpdesk agents with communications support engineer permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings.</span></span> <span data-ttu-id="d1721-126">他們擁有通話記錄及客戶資訊的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="d1721-126">They have full access to call logs and customer information.</span></span>

> [!NOTE]
> <span data-ttu-id="d1721-127">通訊支援專家角色相當於預覽入口網站中的第1層支援角色，且通訊支援工程師角色相當於預覽入口網站中的第2層支援角色。</span><span class="sxs-lookup"><span data-stu-id="d1721-127">The communications support specialist role is equivalent to tier 1 support role from the preview portal and the communications support engineer role is equivalent to tier 2 support role from the preview portal.</span></span>

<span data-ttu-id="d1721-128">如需溝通支援專家和通訊支援工程師角色的詳細資訊，請參閱[使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d1721-128">For more information about the communications support specialist and communications support engineer roles, see [Use Microsoft Teams admin roles to manage teams](using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1721-129">Microsoft 團隊系統管理中心提供服務台代理許可權和網路拓撲上傳。</span><span class="sxs-lookup"><span data-stu-id="d1721-129">Helpdesk agent permissions and network topology upload are available in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d1721-130">溝通支援專家和溝通支援工程師可以使用此入口網站存取通話分析和通話品質儀表板。</span><span class="sxs-lookup"><span data-stu-id="d1721-130">Communications Support Specialists and Communications Support Engineers can use this portal to access Call Analytics and the Call Quality Dashboard.</span></span>

<span data-ttu-id="d1721-131">如需通話分析的詳細資料，請參閱[設定商務用 Skype 通話分析](set-up-call-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="d1721-131">For details about Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="d1721-132">如需説明台代理程式如何使用呼叫分析的詳細資訊，請參閱[使用通話分析來診斷不佳通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="d1721-132">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="d1721-133">什麼是通話品質儀表板，我該如何使用？</span><span class="sxs-lookup"><span data-stu-id="d1721-133">What's the Call Quality Dashboard, and when should I use it?</span></span>
  
<span data-ttu-id="d1721-134">[通話分析] 的設計目的是協助系統管理員和技術支援人員*針對特定通話*的通話品質問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="d1721-134">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with *specific calls*.</span></span> <span data-ttu-id="d1721-135">通話品質儀表板（CQD）的設計目的是協助團隊管理員、商務用 Skype 系統管理員和網路工程師*優化網路*。</span><span class="sxs-lookup"><span data-stu-id="d1721-135">Call Quality Dashboard (CQD) is designed to help Teams admins, Skype for Business admins, and network engineers *optimize a network*.</span></span> <span data-ttu-id="d1721-136">CQD 會將焦點從特定的使用者轉移，而不是查看整個團隊或商務用 Skype 組織的匯總資訊。</span><span class="sxs-lookup"><span data-stu-id="d1721-136">CQD shifts focus from specific users and instead looks at aggregate information for an entire Teams or Skype for Business organization.</span></span> <span data-ttu-id="d1721-137">如需詳細資訊，請參閱[適用于團隊和商務用 Skype Online 的通話品質儀表板功能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)。</span><span class="sxs-lookup"><span data-stu-id="d1721-137">For more information, see [Features of the Call Quality Dashboard for Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="d1721-138">假設使用者的通話品質不佳，是因為網路問題也會影響許多其他使用者。</span><span class="sxs-lookup"><span data-stu-id="d1721-138">Suppose a user's poor call quality is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="d1721-139">在 CQD 中看不到個別通話體驗，但會捕獲使用 Microsoft 團隊或商務用 Skype 所做的整體品質。</span><span class="sxs-lookup"><span data-stu-id="d1721-139">The individual call experience isn't visible in CQD, but the overall quality of calls made using Microsoft Teams or Skype for Business is captured.</span></span> <span data-ttu-id="d1721-140">使用 CQD 時，整個模式可能會變得很明顯，因此網路工程師可以進行通話品質的及時評估。</span><span class="sxs-lookup"><span data-stu-id="d1721-140">With  CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="d1721-141">CQD 提供通話品質度量的報告，可讓您深入瞭解整個通話品質、伺服器用戶端資料流程、用戶端用戶端資料流程，以及語音品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="d1721-141">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>
  
![通話品質儀表板的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="d1721-143">CQD 的位置-改良的報表會在使用者的組建中匯總通話品質與可靠性。</span><span class="sxs-lookup"><span data-stu-id="d1721-143">CQD's Location-Enhanced Reports aggregate call quality and reliability within a user's building.</span></span> <span data-ttu-id="d1721-144">您可以評估資料來判斷問題是獨立于單一使用者，還是會影響較大的使用者區段。</span><span class="sxs-lookup"><span data-stu-id="d1721-144">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span>

![[通話品質儀表板] 的位置改良報告的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> <span data-ttu-id="d1721-146">若要在 CQD 中啟用組建或端點專用的視圖，系統管理員必須在 CQD 的租使用者資料上傳頁面上[傳建築物或端點資訊](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)。</span><span class="sxs-lookup"><span data-stu-id="d1721-146">To enable building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) on CQD's Tenant Data Upload page.</span></span>

<span data-ttu-id="d1721-147">如果您希望非系統管理員的使用者（例如支援人員）使用 [通話品質儀表板]，您可以為這些使用者指派下列其中一項角色，這些角色也具有存取通話品質儀表板所需的許可權：</span><span class="sxs-lookup"><span data-stu-id="d1721-147">If you want non-admin users (such as helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which also have permissions needed to access Call Quality Dashboard:</span></span>

- <span data-ttu-id="d1721-148">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="d1721-148">Global Administrator</span></span>
- <span data-ttu-id="d1721-149">全域閱讀程式</span><span class="sxs-lookup"><span data-stu-id="d1721-149">Global Reader</span></span>
- <span data-ttu-id="d1721-150">商務用 Skype 系統管理員</span><span class="sxs-lookup"><span data-stu-id="d1721-150">Skype for Business Administrator</span></span>
- <span data-ttu-id="d1721-151">Teams 服務管理員</span><span class="sxs-lookup"><span data-stu-id="d1721-151">Teams Service Administrator</span></span>
- <span data-ttu-id="d1721-152">Teams 通訊系統管理員</span><span class="sxs-lookup"><span data-stu-id="d1721-152">Teams Communications Administrator</span></span>
- <span data-ttu-id="d1721-153">Teams 通訊支援工程師</span><span class="sxs-lookup"><span data-stu-id="d1721-153">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="d1721-154">團隊溝通支援專家</span><span class="sxs-lookup"><span data-stu-id="d1721-154">Teams Communications Support Specialist</span></span>
- <span data-ttu-id="d1721-155">報表閱讀程式</span><span class="sxs-lookup"><span data-stu-id="d1721-155">Reports Reader</span></span>

> [!NOTE]
> <span data-ttu-id="d1721-156">團隊通訊支援工程師、團隊溝通支援專家及報告閱讀者角色無法在 CQD 的租使用者上修改檔案，也無法在租使用者啟用 CQD。</span><span class="sxs-lookup"><span data-stu-id="d1721-156">The Teams Communications Support Engineer, Teams Communications Support Specialist, and Reports Reader roles cannot modify files on CQD's Tenant Data Upload page nor activate CQD for a tenant.</span></span>

<span data-ttu-id="d1721-157">如需有關這些角色的詳細資訊，請參閱[關於 Office 365 系統管理員角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="d1721-157">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="d1721-158">如需有關 CQD 的詳細資訊，請參閱[開啟與使用 Microsoft 團隊和商務用 Skype online 的通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)，以及[Microsoft 團隊和商務用 Skype Online 的通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="d1721-158">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d1721-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="d1721-159">Related topics</span></span>

[<span data-ttu-id="d1721-160">影片：通話品質概覽</span><span class="sxs-lookup"><span data-stu-id="d1721-160">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="d1721-161">設定通話分析</span><span class="sxs-lookup"><span data-stu-id="d1721-161">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="d1721-162">使用通話分析來疑難排解不良通話品質</span><span class="sxs-lookup"><span data-stu-id="d1721-162">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="d1721-163">開啟並使用 Microsoft 團隊及商務用 Skype Online 的通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="d1721-163">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>](turning-on-and-using-call-quality-dashboard.md)
