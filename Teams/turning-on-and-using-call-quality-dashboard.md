---
title: '設定通話品質儀表板 (CQD) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
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
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 瞭解如何開啟並使用通話品質儀表板，並取得通話品質摘要報告。
ms.openlocfilehash: c71cb25732a99f207467a988ad0db54c959d15f4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52254217"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="52a88-103">設定通話品質儀表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="52a88-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="52a88-104">使用系統管理員認證 (在 CQD) 開啟 microsoft 通話品質儀表板 (以您的系統管理員認證 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)) 。</span><span class="sxs-lookup"><span data-stu-id="52a88-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="52a88-105">或前往系統管理Teams，然後選取通話 **品質儀表板**。</span><span class="sxs-lookup"><span data-stu-id="52a88-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="系統管理中心中通話品質儀表板按鈕Teams螢幕擷取畫面":::

<span data-ttu-id="52a88-107">在開啟的頁面上 **，按一下**[登錄並輸入您的全域系統管理員帳戶Microsoft Teams系統管理員帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="52a88-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Administrator account information.</span></span> <span data-ttu-id="52a88-108">在您第一次登錄之後，CQD 會開始收集和處理資料。</span><span class="sxs-lookup"><span data-stu-id="52a88-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="52a88-109">請記住，可能需要一或多個小時處理足夠的資料，才能在報告中顯示有意義的結果。</span><span class="sxs-lookup"><span data-stu-id="52a88-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="52a88-110">CQD 會顯示 2019 年 2019 Microsoft Teams、商務用 Skype線上商務用 Skype Server通話和會議品質。</span><span class="sxs-lookup"><span data-stu-id="52a88-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="52a88-111">若要在 2019 商務用 Skype Server使用 CQD，您必須[設定通話資料連線器](/skypeforbusiness/hybrid/configure-call-data-connector)。</span><span class="sxs-lookup"><span data-stu-id="52a88-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="52a88-112">在 [啟動前，請參閱規劃通話](/skypeforbusiness/hybrid/plan-call-data-connector) 資料連線器。</span><span class="sxs-lookup"><span data-stu-id="52a88-112">See [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="52a88-113">指派系統管理員角色以存取 CQD</span><span class="sxs-lookup"><span data-stu-id="52a88-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="52a88-114">將 [存取](/microsoft-365/admin/add-users/about-admin-roles) CQD 的角色指派給需要使用它的人。</span><span class="sxs-lookup"><span data-stu-id="52a88-114">Assign [roles](/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="52a88-115">如果您希望非系統管理員使用者 (例如支援工程師和技術支援人員) 使用通話品質儀表板，您可以指派下列其中一個角色來存取 CQD。</span><span class="sxs-lookup"><span data-stu-id="52a88-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="52a88-116">查看報表</span><span class="sxs-lookup"><span data-stu-id="52a88-116">View reports</span></span>  |<span data-ttu-id="52a88-117">查看 EUII 欄位</span><span class="sxs-lookup"><span data-stu-id="52a88-117">View EUII fields</span></span>  |<span data-ttu-id="52a88-118">建立報表</span><span class="sxs-lookup"><span data-stu-id="52a88-118">Create reports</span></span>  |<span data-ttu-id="52a88-119">Upload建立資料</span><span class="sxs-lookup"><span data-stu-id="52a88-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="52a88-120">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="52a88-120">Global Administrator</span></span>     |<span data-ttu-id="52a88-121">是</span><span class="sxs-lookup"><span data-stu-id="52a88-121">Yes</span></span>         |<span data-ttu-id="52a88-122">是</span><span class="sxs-lookup"><span data-stu-id="52a88-122">Yes</span></span>         |<span data-ttu-id="52a88-123">是</span><span class="sxs-lookup"><span data-stu-id="52a88-123">Yes</span></span>         |<span data-ttu-id="52a88-124">是</span><span class="sxs-lookup"><span data-stu-id="52a88-124">Yes</span></span>         |
|<span data-ttu-id="52a88-125">Teams 系統管理員</span><span class="sxs-lookup"><span data-stu-id="52a88-125">Teams Administrator</span></span>     |<span data-ttu-id="52a88-126">是</span><span class="sxs-lookup"><span data-stu-id="52a88-126">Yes</span></span>         |<span data-ttu-id="52a88-127">是</span><span class="sxs-lookup"><span data-stu-id="52a88-127">Yes</span></span>         |<span data-ttu-id="52a88-128">是</span><span class="sxs-lookup"><span data-stu-id="52a88-128">Yes</span></span>         |<span data-ttu-id="52a88-129">是</span><span class="sxs-lookup"><span data-stu-id="52a88-129">Yes</span></span>         |
|<span data-ttu-id="52a88-130">Teams 通訊系統管理員</span><span class="sxs-lookup"><span data-stu-id="52a88-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="52a88-131">是</span><span class="sxs-lookup"><span data-stu-id="52a88-131">Yes</span></span>         |<span data-ttu-id="52a88-132">是</span><span class="sxs-lookup"><span data-stu-id="52a88-132">Yes</span></span>         |<span data-ttu-id="52a88-133">是</span><span class="sxs-lookup"><span data-stu-id="52a88-133">Yes</span></span>         |<span data-ttu-id="52a88-134">是</span><span class="sxs-lookup"><span data-stu-id="52a88-134">Yes</span></span>         |
|<span data-ttu-id="52a88-135">Teams 通訊支援工程師</span><span class="sxs-lookup"><span data-stu-id="52a88-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="52a88-136">是</span><span class="sxs-lookup"><span data-stu-id="52a88-136">Yes</span></span>         |<span data-ttu-id="52a88-137">是</span><span class="sxs-lookup"><span data-stu-id="52a88-137">Yes</span></span>         |<span data-ttu-id="52a88-138">是</span><span class="sxs-lookup"><span data-stu-id="52a88-138">Yes</span></span>         |<span data-ttu-id="52a88-139">否</span><span class="sxs-lookup"><span data-stu-id="52a88-139">No</span></span>         |
|<span data-ttu-id="52a88-140">Teams通訊支援專家</span><span class="sxs-lookup"><span data-stu-id="52a88-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="52a88-141">是</span><span class="sxs-lookup"><span data-stu-id="52a88-141">Yes</span></span>         |<span data-ttu-id="52a88-142">否</span><span class="sxs-lookup"><span data-stu-id="52a88-142">No</span></span>         |<span data-ttu-id="52a88-143">是</span><span class="sxs-lookup"><span data-stu-id="52a88-143">Yes</span></span>         |<span data-ttu-id="52a88-144">否</span><span class="sxs-lookup"><span data-stu-id="52a88-144">No</span></span>         |
|<span data-ttu-id="52a88-145">商務用 Skype管理員</span><span class="sxs-lookup"><span data-stu-id="52a88-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="52a88-146">是</span><span class="sxs-lookup"><span data-stu-id="52a88-146">Yes</span></span>         |<span data-ttu-id="52a88-147">是</span><span class="sxs-lookup"><span data-stu-id="52a88-147">Yes</span></span>         |<span data-ttu-id="52a88-148">是</span><span class="sxs-lookup"><span data-stu-id="52a88-148">Yes</span></span>         |<span data-ttu-id="52a88-149">是</span><span class="sxs-lookup"><span data-stu-id="52a88-149">Yes</span></span>         |
|<span data-ttu-id="52a88-150">全域閱讀程式</span><span class="sxs-lookup"><span data-stu-id="52a88-150">Global Reader</span></span> |<span data-ttu-id="52a88-151">是</span><span class="sxs-lookup"><span data-stu-id="52a88-151">Yes</span></span>         |<span data-ttu-id="52a88-152">是</span><span class="sxs-lookup"><span data-stu-id="52a88-152">Yes</span></span>         |<span data-ttu-id="52a88-153">是</span><span class="sxs-lookup"><span data-stu-id="52a88-153">Yes</span></span>         |<span data-ttu-id="52a88-154">否</span><span class="sxs-lookup"><span data-stu-id="52a88-154">No</span></span>         |
|<span data-ttu-id="52a88-155">報表閱讀<sup>程式 1</sup></span><span class="sxs-lookup"><span data-stu-id="52a88-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="52a88-156">是</span><span class="sxs-lookup"><span data-stu-id="52a88-156">Yes</span></span>         |<span data-ttu-id="52a88-157">否</span><span class="sxs-lookup"><span data-stu-id="52a88-157">No</span></span>         |<span data-ttu-id="52a88-158">是</span><span class="sxs-lookup"><span data-stu-id="52a88-158">Yes</span></span>         |<span data-ttu-id="52a88-159">否</span><span class="sxs-lookup"><span data-stu-id="52a88-159">No</span></span>         |

<span data-ttu-id="52a88-160"><sup>1</sup>除了閱讀 CQD 報告之外，報表閱讀程式還可以在[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)系統管理中心中查看所有活動報告，以及來自採用內容套件Microsoft 365[報告](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)。</span><span class="sxs-lookup"><span data-stu-id="52a88-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="52a88-161">如果您沒有看到 [EUII (](CQD-data-and-reports.md#euii-data) 使用者識別資訊) 且您擁有允許查看此資訊的其中一個角色，請記住，CQD 只會讓 EUII 保留 28 天。</span><span class="sxs-lookup"><span data-stu-id="52a88-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="52a88-162">任何超過 28 天都將會刪除。</span><span class="sxs-lookup"><span data-stu-id="52a88-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="52a88-163">有關這些角色的資訊，請參閱[關於Office 365角色。](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="52a88-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="52a88-164">在您第一次登錄之後，CQD 會開始收集和處理資料。</span><span class="sxs-lookup"><span data-stu-id="52a88-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="52a88-165">自 2019 年 12 月起，您仍可存取舊版 CQD (cqd.lync.com) ，雖然舊版入口網站提供您最新 CQD (cqd.teams.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="52a88-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="52a88-166">最後，較舊版本的 CQD 將會解除授權。</span><span class="sxs-lookup"><span data-stu-id="52a88-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="52a88-167">自 2020 年 7 月 1 日起，舊版 CQD 會存取最新 CQD 的資料。</span><span class="sxs-lookup"><span data-stu-id="52a88-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="52a88-168">從先前版本的 CQD 遷移建築物資料和報表</span><span class="sxs-lookup"><span data-stu-id="52a88-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52a88-169">自 2020 年 7 月 1 日起，您無法再從舊的 CQD 資料庫移轉建築物資料 https://CQD.lync.com) (。</span><span class="sxs-lookup"><span data-stu-id="52a88-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="52a88-170">使用 Power BI分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="52a88-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="52a88-171">2020 年 1[月新增：下載 Power BI CQD 的查詢範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="52a88-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="52a88-172">您可以Power BI自訂範本，以分析及報告您的 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="52a88-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="52a88-173">請參閱[使用 Power BI分析 CQD 資料](CQD-Power-BI-query-templates.md)以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="52a88-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="52a88-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="52a88-174">Related topics</span></span>

[<span data-ttu-id="52a88-175">改善及監控通話品質Teams</span><span class="sxs-lookup"><span data-stu-id="52a88-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="52a88-176">什麼是 CQD？</span><span class="sxs-lookup"><span data-stu-id="52a88-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="52a88-177">Upload租使用者和建築物資料</span><span class="sxs-lookup"><span data-stu-id="52a88-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="52a88-178">CQD 資料和報表</span><span class="sxs-lookup"><span data-stu-id="52a88-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="52a88-179">使用 CQD 管理通話和會議品質</span><span class="sxs-lookup"><span data-stu-id="52a88-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="52a88-180">CQD 中可用的維度和度量</span><span class="sxs-lookup"><span data-stu-id="52a88-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="52a88-181">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="52a88-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="52a88-182">使用 Power BI分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="52a88-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)