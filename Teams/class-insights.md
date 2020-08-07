---
title: 適用於 IT 系統管理員的 Microsoft Teams 教育版深入解析
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams 教育版深入解析的 IT 系統管理員指南。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75d9396bf5f537f965493bb0db317a1286b2f950
ms.sourcegitcommit: b14ad0a6c454b20f34fccbd1d312de24379faef0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572368"
---
# <a name="insights-in-teams-for-education-for-it-admins"></a><span data-ttu-id="86115-103">適用於 IT 系統管理員 Teams 教育版深入解析</span><span class="sxs-lookup"><span data-stu-id="86115-103">Insights in Teams for Education for IT Admins</span></span>

<span data-ttu-id="86115-104">透過 Microsoft Teams 教育版深入解析，教育版和領導者可以存取有關數位參與、作業工作負載、成績、通訊等的分析資料。</span><span class="sxs-lookup"><span data-stu-id="86115-104">With Insights in Microsoft Teams for Education, educators and leaders can access analytics data about digital engagement, assignment workload, grades, communications and more.</span></span>

<span data-ttu-id="86115-105">深入解析會在 Office 365 教育版 SKU A1、A3 和 A5 中使用。</span><span class="sxs-lookup"><span data-stu-id="86115-105">Insights is active in Office 365 Education SKUs A1, A3, and A5.</span></span>

> [!NOTE]
> <span data-ttu-id="86115-106">授課者請於[此處](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)了解如何使用深入解析。</span><span class="sxs-lookup"><span data-stu-id="86115-106">Educators, learn how to use Insights [here](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc).</span></span>

## <a name="permissions"></a><span data-ttu-id="86115-107">權限</span><span class="sxs-lookup"><span data-stu-id="86115-107">Permissions</span></span>

- <span data-ttu-id="86115-108">學生是由其授權所識別，而 **無權存取 [深入分析] 索引標籤** （即使他們是小組的擁有者）。</span><span class="sxs-lookup"><span data-stu-id="86115-108">Students are identified by their license and **do not have access to the Insights tab** (even if they are an owner of the team).</span></span>
- <span data-ttu-id="86115-109">授課者是透過教職員授權所定義。</span><span class="sxs-lookup"><span data-stu-id="86115-109">Educators are defined by faculty licenses.</span></span> <span data-ttu-id="86115-110">授課者必須擁有教職員授權，並成為班級小組擁有者，才能新增和查看 [深入解析] 索引標籤。該索引標籤會反映來自班級小組中不是擁有者 (包括不是小組擁有者的授課者) 的每個人的活動。</span><span class="sxs-lookup"><span data-stu-id="86115-110">Educators must have a faculty license and be a class team owner to add and see the Insights tab. The tab reflects activity from everyone in the class team who isn’t an owner (including educators who aren’t owners of the team).</span></span>
- <span data-ttu-id="86115-111">領導者的基本定義是透過教職員授權。</span><span class="sxs-lookup"><span data-stu-id="86115-111">Leader’s basic definition is by faculty license.</span></span> <span data-ttu-id="86115-112">全域系統管理員是由其角色識別。</span><span class="sxs-lookup"><span data-stu-id="86115-112">IT global admin is identified by its role.</span></span> <span data-ttu-id="86115-113">領導者必須具備教職員授權，並取得 IT 全域系統管理員的明確授與的權限，才能檢視深入解析應用程式中的報告。</span><span class="sxs-lookup"><span data-stu-id="86115-113">Leaders must have a faculty license and be given explicit permissions from the IT global admin to view the reports in the Insights app.</span></span>

<span data-ttu-id="86115-114">我們透過兩個形式提供深入解析：</span><span class="sxs-lookup"><span data-stu-id="86115-114">We provide Insights in two forms:</span></span>
- <span data-ttu-id="86115-115">索引標籤 - 授課者可以透過瀏覽至 Teams 應用程式列中的 [應用程式]，並搜尋「深入解析」，將「深入解析」新增至班級小組內的公開頻道。</span><span class="sxs-lookup"><span data-stu-id="86115-115">Tabs - educators can add Insights to a public channel within a class team by navigating to Apps in the Teams app bar and searching for Insights.</span></span>
- <span data-ttu-id="86115-116">個人應用程式 - 領導者可以透過瀏覽至 Teams 應用程式列中的 [應用程式]，並搜尋「深入解析」，將「深入解析」應用程式新增為個人應用程式 (顯示在 Teams 左側功能表上)。</span><span class="sxs-lookup"><span data-stu-id="86115-116">Personal app - leaders can add the Insights app as a personal app (appears on Teams left menu) by navigating to Apps in the Teams app bar and searching for Insights.</span></span>

## <a name="compliance"></a><span data-ttu-id="86115-117">合規性</span><span class="sxs-lookup"><span data-stu-id="86115-117">Compliance</span></span>

<span data-ttu-id="86115-118">深入解析具備產業領先的合規性承諾，並被分類為 Office 365 合規性架構內的 C 層服務。</span><span class="sxs-lookup"><span data-stu-id="86115-118">Insights has industry-leading compliance commitments, and is classified as a Tier-C service within the Office 365 Compliance Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="86115-119">若要深入瞭解 Microsoft 如何保護您的資料，請造訪 [Microsoft 信任中心](https://www.microsoft.com/trust-center)。</span><span class="sxs-lookup"><span data-stu-id="86115-119">Visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center) to learn more about how Microsoft protects your data.</span></span>

## <a name="privacy"></a><span data-ttu-id="86115-120">隱私權</span><span class="sxs-lookup"><span data-stu-id="86115-120">Privacy</span></span>

<span data-ttu-id="86115-121">透過深入解析收集和顯示的資訊，符合 90 多個監管和產業標準，其中包括 GDPR 和針對學生與兒童的「家庭教育權和隱私權法案 (FERPA)」，以及其他類似的、以隱私權為導向法規。</span><span class="sxs-lookup"><span data-stu-id="86115-121">The information collected and shown through Insights does meets more than 90 regulatory and industry standards, including GDPR and the Family Education Rights and Privacy Act (FERPA) for the security of students and children and other, similar, privacy-oriented regulations.</span></span> <span data-ttu-id="86115-122">IT 系統管理員務必知道，以每個學生為基礎所收集的資訊僅限用於班級環境，以允許授課者和領導者判斷班級行為。</span><span class="sxs-lookup"><span data-stu-id="86115-122">It's important for ITAdmins to know that the information collected on a per-student basis is intended to be used in a class context only, to allow educators and leaders to determine class behavior.</span></span> <span data-ttu-id="86115-123">收集這些資訊是為了提供有意義的學習活動，例如班級會議出席者、發布訊息、回應同學的貼文、寫作業、編輯檔案等等。</span><span class="sxs-lookup"><span data-stu-id="86115-123">The information is collected for meaningful learning activities, such as class meetings attendance, posting messages, responding to classmates' posts, working on assignments, editing files, and more.</span></span> <span data-ttu-id="86115-124">比如，我們不會顯示私人交談或 Teams 登入的資訊。</span><span class="sxs-lookup"><span data-stu-id="86115-124">We don't show information about private chat or a Teams login, as an example.</span></span>

<span data-ttu-id="86115-125">我們的目標是協助授課者瞭解參與情況，並聚焦在學生學習上。</span><span class="sxs-lookup"><span data-stu-id="86115-125">Our goal is to help educators to understand engagement and shine a spotlight on student learning.</span></span> <span data-ttu-id="86115-126">雖然這些課程活動可以集中到學生層級的動作上，但 Microsoft Teams 對這些動作沒有意見評判，而且也不會根據準則對個別學生有身分判斷識別。</span><span class="sxs-lookup"><span data-stu-id="86115-126">While these class activities can be focussed down to actions at the student level, there is no positive or negative value assigned to these actions by Microsoft Teams, and there is no judgmental identification of individual students based on criteria.</span></span> <span data-ttu-id="86115-127">深入解析中的資訊會通知授課者，例如，某個學生在某段期間內未在工具中處於使用中狀態，或他們已準時完成上週的所有作業。</span><span class="sxs-lookup"><span data-stu-id="86115-127">The information in  Insights informs an educator that, for example, a student has not been active in the tool during a certain period in time, or has completed all their assignments last week on-time.</span></span> <span data-ttu-id="86115-128">授課者則得負責與學生和學生的家長或監護人進行互動，以找出任何有使用或沒有使用的基本原因。</span><span class="sxs-lookup"><span data-stu-id="86115-128">It remains the responsibility of the educator to interact with the student and that student's family or guardians to determine the underlying reason for any activity or inactivity detected.</span></span>

## <a name="data-collection"></a><span data-ttu-id="86115-129">資料收集</span><span class="sxs-lookup"><span data-stu-id="86115-129">Data collection</span></span>

<span data-ttu-id="86115-130">為租用戶開啟「教育版分析」時，我們會收集「深入解析」的資料。</span><span class="sxs-lookup"><span data-stu-id="86115-130">We collect data for Insights when Education Analytics is turned on for the tenant.</span></span> <span data-ttu-id="86115-131">資料會從 Teams 活動收集而來，以呈現可用於教學和學習的可操作資訊。</span><span class="sxs-lookup"><span data-stu-id="86115-131">The data is collected from Teams activity in order to surface actionable insights for teaching and learning.</span></span>

<span data-ttu-id="86115-132">根據預設，[教育分析] **開啟**了。</span><span class="sxs-lookup"><span data-stu-id="86115-132">By default, Education Analytics is turned **On**.</span></span>

<span data-ttu-id="86115-133">目前，這項資料從課程小組中的學生和教師活動的以下方面提取的：</span><span class="sxs-lookup"><span data-stu-id="86115-133">Currently, this data is pulled from the following areas of student and educator activity in class teams:</span></span>

|<span data-ttu-id="86115-134">Teams 元件</span><span class="sxs-lookup"><span data-stu-id="86115-134">Teams component</span></span>  |<span data-ttu-id="86115-135">收集的資料</span><span class="sxs-lookup"><span data-stu-id="86115-135">Data collected</span></span>  |
|-----------------|------------------------|------------------------|
|<span data-ttu-id="86115-136">作業</span><span class="sxs-lookup"><span data-stu-id="86115-136">Assignments</span></span> |<span data-ttu-id="86115-137">打開、成交和評分作業。</span><span class="sxs-lookup"><span data-stu-id="86115-137">Opening, turning in, and grade on assignments.</span></span> |
|<span data-ttu-id="86115-138">頻道參與</span><span class="sxs-lookup"><span data-stu-id="86115-138">Channel engagement</span></span> |<span data-ttu-id="86115-139">造訪頻道、建立貼文、回復貼文並按讚（不包括聊天內容）。</span><span class="sxs-lookup"><span data-stu-id="86115-139">Visiting a channel, creating a post, replying to and liking a post (not including chat content).</span></span> |
|<span data-ttu-id="86115-140">檔案</span><span class="sxs-lookup"><span data-stu-id="86115-140">Files</span></span> |<span data-ttu-id="86115-141">上傳、下載、存取、修改、批註及共用檔案（不包括檔案內容）。</span><span class="sxs-lookup"><span data-stu-id="86115-141">Uploading, downloading, accessing, modifying, commenting on, and sharing a file (not including file content).</span></span> |
|<span data-ttu-id="86115-142">會議</span><span class="sxs-lookup"><span data-stu-id="86115-142">Meetings</span></span> |<span data-ttu-id="86115-143">出席（不含會議內容）。</span><span class="sxs-lookup"><span data-stu-id="86115-143">Attendance (not including meeting content).</span></span> |

## <a name="data-location"></a><span data-ttu-id="86115-144">資料位置</span><span class="sxs-lookup"><span data-stu-id="86115-144">Data location</span></span>

<span data-ttu-id="86115-145">以歐洲租用戶為基礎的深入解析資料，會儲存在歐洲的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="86115-145">Insights data for European-based tenants is stored on servers in Europe.</span></span> <span data-ttu-id="86115-146">以美國租用戶為基礎的資料，則會儲存在美國的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="86115-146">Data for US-based tenants is stored on servers in the United States.</span></span> <span data-ttu-id="86115-147">如果您使用深入解析，而您的 Office 365 租用戶位於歐洲或美國以外的地區，則您的資料會儲存在適當的地理區域。</span><span class="sxs-lookup"><span data-stu-id="86115-147">If you use Insights and your Office 365 tenant is in a region outside of Europe or the United States, your data will be stored in the appropriate geographic region.</span></span>

## <a name="performance-and-reliability"></a><span data-ttu-id="86115-148">效能和可靠性</span><span class="sxs-lookup"><span data-stu-id="86115-148">Performance and reliability</span></span>

<span data-ttu-id="86115-149">深入解析的設計目的在於處理從 Teams 活動收集的大量資料，並具有最佳效能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="86115-149">Insights is designed to handle a high volume of data collected from Teams activity with optimal performance and reliability.</span></span>

<span data-ttu-id="86115-150">無論 Teams 是否有安裝 [深入解析] 索引標籤，資料收集程序都會在不同的伺服器上進行。</span><span class="sxs-lookup"><span data-stu-id="86115-150">The data collection process takes place on separate servers regardless of the installation of the Insights tab in Teams.</span></span> <span data-ttu-id="86115-151">[深入解析] 索引標籤或個人應用程式不會影響授課者和學生使用其餘 Teams 功能的應用程式效能或網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="86115-151">The Insights tab or personal app does not affect application performance or network bandwidth for educators and students using the rest of Teams functionality.</span></span>

> [!TIP]
> <span data-ttu-id="86115-152">若要瞭解如何在頻寬不足時使用 [教育用 Teams]，請參閱 [這裡](edu-remote-low-bandwidth.md)。</span><span class="sxs-lookup"><span data-stu-id="86115-152">Read [here](edu-remote-low-bandwidth.md) about using Teams for Education when bandwidth is low.</span></span>

## <a name="how-to-delete-your-data"></a><span data-ttu-id="86115-153">如何刪除資料</span><span class="sxs-lookup"><span data-stu-id="86115-153">How to delete your data</span></span>

<span data-ttu-id="86115-154">[教育] 服務會儲存課程小組上下文中的學生和教師動作。</span><span class="sxs-lookup"><span data-stu-id="86115-154">Education services stores student and educator actions performed in the context of a class team.</span></span> <span data-ttu-id="86115-155">這項資料視為是混合資料集，因此，一旦從組織中刪除了學生或授課者的使用者帳戶，就不會自動從服務中刪除了。</span><span class="sxs-lookup"><span data-stu-id="86115-155">This data is considered a co-mingled data set and therefore isn't automatically deleted from the service once student or educator user accounts are deleted from your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="86115-156">刪除資料會對 [深入分析] 分析班級團隊參與度的能力產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="86115-156">Deleting data has a negative impact on Insights' ability to analyze class team engagement over time.</span></span>

- <span data-ttu-id="86115-157">在[[這裡]](https://edusupport.microsoft.com/support)開啟支援票證。</span><span class="sxs-lookup"><span data-stu-id="86115-157">Open a support ticket [here](https://edusupport.microsoft.com/support).</span></span> <span data-ttu-id="86115-158">支援票證必須明確聲明對 [GDPR Delete DSR] 操作的請求，並包含要刪除的使用者物件識別碼。</span><span class="sxs-lookup"><span data-stu-id="86115-158">The support ticket must state clearly the request for a GDPR Delete DSR operation and contain the user object ID to be deleted.</span></span> <span data-ttu-id="86115-159">無法限制刪除的資料集或時間窗口。</span><span class="sxs-lookup"><span data-stu-id="86115-159">There is no ability to limit the data set or time window of the deletion.</span></span>
- <span data-ttu-id="86115-160">一旦歸檔，支援票證就會在佇列中等候一周，以符合合規性最低保留原則。</span><span class="sxs-lookup"><span data-stu-id="86115-160">Once filed, the support ticket waits in the queue for one week in order to meet compliance minimal retention policy.</span></span> <span data-ttu-id="86115-161">您可以在此期間取消該作業。</span><span class="sxs-lookup"><span data-stu-id="86115-161">You have the opportunity to cancel the operation during this time.</span></span>
- <span data-ttu-id="86115-162">一周之後，[教育分析] 小組會採取行動，以確保與該使用者識別碼相關的所有資料都已從服務中刪除。</span><span class="sxs-lookup"><span data-stu-id="86115-162">After one week, the Education Analytics team takes action to ensure all data related to the user ID is deleted from the service.</span></span> <span data-ttu-id="86115-163">Microsoft 支援服務會監視 ICM 票證，並會在刪除程序完成後28天內通知您。</span><span class="sxs-lookup"><span data-stu-id="86115-163">Microsoft support monitors the ICM ticket and will notify you once the deletion process is complete, in no more than 28 days.</span></span>

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a><span data-ttu-id="86115-164">使用學校資料同步處理 (SDS) 關閉和開啟 [深入分析]。</span><span class="sxs-lookup"><span data-stu-id="86115-164">Turn Insights off and on using School Data Sync (SDS)</span></span>

<span data-ttu-id="86115-165">學校資料同步處理 (SDS) 會協助自動化匯入和同步處理學生資訊系統 (SIS) 資料與 Office 365 的程序。</span><span class="sxs-lookup"><span data-stu-id="86115-165">School Data Sync (SDS) helps to automate the process of importing and synchronizing Student Information System (SIS) data with Office 365.</span></span>

<span data-ttu-id="86115-166">使用深入解析不需要使用 SDS。</span><span class="sxs-lookup"><span data-stu-id="86115-166">The use of Insights does not require the use of SDS.</span></span> <span data-ttu-id="86115-167">不過，您可以隨時通過關閉 SDS 管理中心 **[設定]** > **[管理教育分析]** 下的切換選項來退出 [教育分析]。</span><span class="sxs-lookup"><span data-stu-id="86115-167">However, you may choose to opt out from Education Analytics at any time by turning off the toggle in the SDS Admin Center under **Settings** > **Manage Education Analytics**.</span></span>

:::image type="content" source="media/class-insights-on-off.png" alt-text="用來啟用或停用深入解析的切換。":::

<span data-ttu-id="86115-169">預設會開啟「教育版分析」和「深入解析」。</span><span class="sxs-lookup"><span data-stu-id="86115-169">By default, Education Analytics, and therefore Insights, is turned on.</span></span> <span data-ttu-id="86115-170">當您選擇退出 [分析] 時，我們會刪除針對 [深入解析] 索引標籤收集的所有資料。重新開啟 [分析]，我們便會從重新啟用的時間開始收集資料。</span><span class="sxs-lookup"><span data-stu-id="86115-170">When you opt out of Analytics, we delete all data collected for the Insights tab. Turn Analytics back on, and we start collecting data from the time it's re-enabled.</span></span>

<span data-ttu-id="86115-171">深入了解：[適用於授課者的深入解析](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)</span><span class="sxs-lookup"><span data-stu-id="86115-171">Learn more: [Insights for educators](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)</span></span>
