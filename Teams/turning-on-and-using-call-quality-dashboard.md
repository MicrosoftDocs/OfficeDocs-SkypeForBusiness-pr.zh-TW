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
description: 瞭解如何開啟和使用通話品質儀表板，並取得通話品質的摘要報告。
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112839"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="f8958-103">設定通話品質儀表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="f8958-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="f8958-104">開啟 Microsoft 通話品質儀表板 (CQD) 在 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (使用您的管理員認證登入) 。</span><span class="sxs-lookup"><span data-stu-id="f8958-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="f8958-105">或移至 [團隊管理中心]，然後選取 [ **通話品質儀表板**]。</span><span class="sxs-lookup"><span data-stu-id="f8958-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="[團隊管理中心] 中 [通話品質儀表板] 按鈕的螢幕擷取畫面":::

<span data-ttu-id="f8958-107">在開啟的頁面上，按一下 [登 **入** ]，然後輸入您的全域系統管理員帳戶或 Microsoft 團隊服務系統管理員帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="f8958-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Administrator account information.</span></span> <span data-ttu-id="f8958-108">第一次登入時，CQD 會開始收集及處理資料。</span><span class="sxs-lookup"><span data-stu-id="f8958-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="f8958-109">請記住，可能需要一或幾個小時的時間來處理足夠的資料，才能在報表中顯示有意義的結果。</span><span class="sxs-lookup"><span data-stu-id="f8958-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="f8958-110">CQD 會顯示通話與會議品質，在組織範圍中，針對 Microsoft 團隊、商務用 Skype Online 及商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="f8958-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f8958-111">若要在商務用 Skype Server 2019 中使用 CQD，您必須 [設定 [呼叫資料連線器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)]。</span><span class="sxs-lookup"><span data-stu-id="f8958-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="f8958-112">請參閱 [規劃通話資料連線器](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) ，然後再開始進行。</span><span class="sxs-lookup"><span data-stu-id="f8958-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="f8958-113">指派管理員角色來存取 CQD</span><span class="sxs-lookup"><span data-stu-id="f8958-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="f8958-114">指派 [角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) ，以存取 CQD 給需要使用的人員。</span><span class="sxs-lookup"><span data-stu-id="f8958-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="f8958-115">如果您想要非系統管理員的使用者 (例如支援工程師和支援者代理) 使用 [通話品質儀表板]，您可以為這些使用者指派下列其中一個角色，提供 CQD 的存取權。</span><span class="sxs-lookup"><span data-stu-id="f8958-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="f8958-116">查看報表</span><span class="sxs-lookup"><span data-stu-id="f8958-116">View reports</span></span>  |<span data-ttu-id="f8958-117">[查看 EUII] 欄位</span><span class="sxs-lookup"><span data-stu-id="f8958-117">View EUII fields</span></span>  |<span data-ttu-id="f8958-118">建立報表</span><span class="sxs-lookup"><span data-stu-id="f8958-118">Create reports</span></span>  |<span data-ttu-id="f8958-119">上傳資料</span><span class="sxs-lookup"><span data-stu-id="f8958-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="f8958-120">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="f8958-120">Global Administrator</span></span>     |<span data-ttu-id="f8958-121">是</span><span class="sxs-lookup"><span data-stu-id="f8958-121">Yes</span></span>         |<span data-ttu-id="f8958-122">是</span><span class="sxs-lookup"><span data-stu-id="f8958-122">Yes</span></span>         |<span data-ttu-id="f8958-123">是</span><span class="sxs-lookup"><span data-stu-id="f8958-123">Yes</span></span>         |<span data-ttu-id="f8958-124">是</span><span class="sxs-lookup"><span data-stu-id="f8958-124">Yes</span></span>         |
|<span data-ttu-id="f8958-125">Teams 服務管理員</span><span class="sxs-lookup"><span data-stu-id="f8958-125">Teams Service Administrator</span></span>     |<span data-ttu-id="f8958-126">是</span><span class="sxs-lookup"><span data-stu-id="f8958-126">Yes</span></span>         |<span data-ttu-id="f8958-127">是</span><span class="sxs-lookup"><span data-stu-id="f8958-127">Yes</span></span>         |<span data-ttu-id="f8958-128">是</span><span class="sxs-lookup"><span data-stu-id="f8958-128">Yes</span></span>         |<span data-ttu-id="f8958-129">是</span><span class="sxs-lookup"><span data-stu-id="f8958-129">Yes</span></span>         |
|<span data-ttu-id="f8958-130">Teams 通訊系統管理員</span><span class="sxs-lookup"><span data-stu-id="f8958-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="f8958-131">是</span><span class="sxs-lookup"><span data-stu-id="f8958-131">Yes</span></span>         |<span data-ttu-id="f8958-132">是</span><span class="sxs-lookup"><span data-stu-id="f8958-132">Yes</span></span>         |<span data-ttu-id="f8958-133">是</span><span class="sxs-lookup"><span data-stu-id="f8958-133">Yes</span></span>         |<span data-ttu-id="f8958-134">是</span><span class="sxs-lookup"><span data-stu-id="f8958-134">Yes</span></span>         |
|<span data-ttu-id="f8958-135">Teams 通訊支援工程師</span><span class="sxs-lookup"><span data-stu-id="f8958-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="f8958-136">是</span><span class="sxs-lookup"><span data-stu-id="f8958-136">Yes</span></span>         |<span data-ttu-id="f8958-137">是</span><span class="sxs-lookup"><span data-stu-id="f8958-137">Yes</span></span>         |<span data-ttu-id="f8958-138">是</span><span class="sxs-lookup"><span data-stu-id="f8958-138">Yes</span></span>         |<span data-ttu-id="f8958-139">否</span><span class="sxs-lookup"><span data-stu-id="f8958-139">No</span></span>         |
|<span data-ttu-id="f8958-140">團隊溝通支援專家</span><span class="sxs-lookup"><span data-stu-id="f8958-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="f8958-141">是</span><span class="sxs-lookup"><span data-stu-id="f8958-141">Yes</span></span>         |<span data-ttu-id="f8958-142">否</span><span class="sxs-lookup"><span data-stu-id="f8958-142">No</span></span>         |<span data-ttu-id="f8958-143">是</span><span class="sxs-lookup"><span data-stu-id="f8958-143">Yes</span></span>         |<span data-ttu-id="f8958-144">否</span><span class="sxs-lookup"><span data-stu-id="f8958-144">No</span></span>         |
|<span data-ttu-id="f8958-145">商務用 Skype 系統管理員</span><span class="sxs-lookup"><span data-stu-id="f8958-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="f8958-146">是</span><span class="sxs-lookup"><span data-stu-id="f8958-146">Yes</span></span>         |<span data-ttu-id="f8958-147">是</span><span class="sxs-lookup"><span data-stu-id="f8958-147">Yes</span></span>         |<span data-ttu-id="f8958-148">是</span><span class="sxs-lookup"><span data-stu-id="f8958-148">Yes</span></span>         |<span data-ttu-id="f8958-149">是</span><span class="sxs-lookup"><span data-stu-id="f8958-149">Yes</span></span>         |
|<span data-ttu-id="f8958-150">全域閱讀程式</span><span class="sxs-lookup"><span data-stu-id="f8958-150">Global Reader</span></span> |<span data-ttu-id="f8958-151">是</span><span class="sxs-lookup"><span data-stu-id="f8958-151">Yes</span></span>         |<span data-ttu-id="f8958-152">是</span><span class="sxs-lookup"><span data-stu-id="f8958-152">Yes</span></span>         |<span data-ttu-id="f8958-153">是</span><span class="sxs-lookup"><span data-stu-id="f8958-153">Yes</span></span>         |<span data-ttu-id="f8958-154">否</span><span class="sxs-lookup"><span data-stu-id="f8958-154">No</span></span>         |
|<span data-ttu-id="f8958-155">報告讀取器<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f8958-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="f8958-156">是</span><span class="sxs-lookup"><span data-stu-id="f8958-156">Yes</span></span>         |<span data-ttu-id="f8958-157">否</span><span class="sxs-lookup"><span data-stu-id="f8958-157">No</span></span>         |<span data-ttu-id="f8958-158">是</span><span class="sxs-lookup"><span data-stu-id="f8958-158">Yes</span></span>         |<span data-ttu-id="f8958-159">否</span><span class="sxs-lookup"><span data-stu-id="f8958-159">No</span></span>         |

<span data-ttu-id="f8958-160"><sup>1</sup> 除了讀取 CQD 報表之外，報表閱讀者還可以查看系統管理中心的所有 [活動報告](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) ，以及 [Microsoft 365 採用內容套件](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)中的所有報告。</span><span class="sxs-lookup"><span data-stu-id="f8958-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="f8958-161">如果您沒有看到 [EUII (使用者可辨識的資訊) ](CQD-data-and-reports.md#euii-data) ，且您擁有允許其查看這項資訊的角色，請記住 CQD 只能在28天內保留 EUII。</span><span class="sxs-lookup"><span data-stu-id="f8958-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="f8958-162">已刪除超過28天的任何專案。</span><span class="sxs-lookup"><span data-stu-id="f8958-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="f8958-163">如需有關這些角色的詳細資訊，請參閱 [關於 Office 365 系統管理員角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="f8958-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="f8958-164">第一次登入時，CQD 會開始收集及處理資料。</span><span class="sxs-lookup"><span data-stu-id="f8958-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="f8958-165">從2019年12月之後，您仍然可以存取舊版的 CQD (cqd.lync.com) ，不過舊版入口網站提供了最新 CQD (cqd.teams.microsoft.com) 的連結。</span><span class="sxs-lookup"><span data-stu-id="f8958-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="f8958-166">最後，將會解除舊版的 CQD。</span><span class="sxs-lookup"><span data-stu-id="f8958-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="f8958-167">從2020年7月1日起，較舊版本的 CQD 會存取最新 CQD 的資料。</span><span class="sxs-lookup"><span data-stu-id="f8958-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="f8958-168">從舊版 CQD 遷移資料和報表</span><span class="sxs-lookup"><span data-stu-id="f8958-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8958-169">從2020年7月1日起，您將無法再從舊的 CQD (中開始建立資料和報表 https://CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="f8958-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="f8958-170">使用 Power BI 來分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="f8958-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="f8958-171">2020年1月 [的新功能：下載 POWER BI 查詢範本以進行 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="f8958-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="f8958-172">可自訂的 Power BI 範本，您可以用來分析及報告您的 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="f8958-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="f8958-173">已閱讀 [ [使用 POWER BI 分析 CQD 資料](CQD-Power-BI-query-templates.md) ] 以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="f8958-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f8958-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="f8958-174">Related topics</span></span>

[<span data-ttu-id="f8958-175">改善及監視團隊的通話品質</span><span class="sxs-lookup"><span data-stu-id="f8958-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="f8958-176">什麼是 CQD？</span><span class="sxs-lookup"><span data-stu-id="f8958-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="f8958-177">上傳租使用者及組建資料</span><span class="sxs-lookup"><span data-stu-id="f8958-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="f8958-178">CQD 資料和報表</span><span class="sxs-lookup"><span data-stu-id="f8958-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="f8958-179">使用 CQD 管理通話與會議品質</span><span class="sxs-lookup"><span data-stu-id="f8958-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="f8958-180">CQD 中可用的維度與量值</span><span class="sxs-lookup"><span data-stu-id="f8958-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="f8958-181">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="f8958-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="f8958-182">使用 Power BI 來分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="f8958-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
