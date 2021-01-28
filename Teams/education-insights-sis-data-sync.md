---
title: 將學生資訊系統 (SIS) 資料與 Education Insights 同步處理。
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 在 Microsoft Teams 中將學生資訊系統 (SIS) 資料與 Education Insights 同步處理。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7570368a6b9bd889bc5ed632cd1d057d70ae791a
ms.sourcegitcommit: 086d27c9381fc1f1c6523d4c48dea275dea917b7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "49986420"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="38f62-103">將學生資訊系統 (SIS) 資料與 Education Insights 同步處理。</span><span class="sxs-lookup"><span data-stu-id="38f62-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="38f62-104">送入 [Education Insights](class-insights.md) 中的資料越多，授課者更能夠支援其學生，且教育領導者也更能夠支援授課者。</span><span class="sxs-lookup"><span data-stu-id="38f62-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="38f62-105">若要提供組織層級 Insights，我們必須使用[學校資料同步處理 (SDS)](https://docs.microsoft.com/SchoolDataSync) 來連線到學生資訊系統 (SIS)，使得 Insights 會有正確對應的教育系統階層結構。</span><span class="sxs-lookup"><span data-stu-id="38f62-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="38f62-106">以班級授課者的身份檢視班級層級的 Insights 並 *不需要* 這樣做，因為我們使用 Teams 的班級結構和權限。</span><span class="sxs-lookup"><span data-stu-id="38f62-106">Viewing class-level Insights as the class educator *does not* require this because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-sis-integration"></a><span data-ttu-id="38f62-107">規劃 SIS 整合</span><span class="sxs-lookup"><span data-stu-id="38f62-107">Plan your SIS integration</span></span>
<span data-ttu-id="38f62-108">SIS 資料提供了教育系統的階層結構，並對應了指派給使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="38f62-108">The SIS data provides the hierarchical structure of the educational system and maps which user is assigned where.</span></span>

<span data-ttu-id="38f62-109">Insights 在使用 [SDS V2 檔案格式](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format)時效果最好，但也支援功能有 *限制* 的 [SDS V1 檔案格式](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds)。</span><span class="sxs-lookup"><span data-stu-id="38f62-109">Insights works best when using [SDS V2 file format](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format) but also supports [SDS V1 file format](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) with *limited* functionality.</span></span>

### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="38f62-110">SDS V1 和 V2 檔案格式之間的差异</span><span class="sxs-lookup"><span data-stu-id="38f62-110">Differences between SDS V1 and V2 file formats</span></span>

| <span data-ttu-id="38f62-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="38f62-111">Data type</span></span> |   <span data-ttu-id="38f62-112">V1</span><span class="sxs-lookup"><span data-stu-id="38f62-112">V1</span></span> | <span data-ttu-id="38f62-113">V2 (建議)</span><span class="sxs-lookup"><span data-stu-id="38f62-113">V2 (recommended)</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="38f62-114">**使用者**</span><span class="sxs-lookup"><span data-stu-id="38f62-114">**Users**</span></span> | <span data-ttu-id="38f62-115">V1 格式包含 **僅授課者**，因此要為教育領導者設定組織層級權限，您需要搜尋他們並手動定義每個人的權限。</span><span class="sxs-lookup"><span data-stu-id="38f62-115">The V1 format contains **only educators**, so to set org-level permissions for your education leaders, you need to search for them and define each one's permission manually.</span></span> | <span data-ttu-id="38f62-116">V2 格式包含 **所有角色**，因此您可以指派以角色為基礎的權限。</span><span class="sxs-lookup"><span data-stu-id="38f62-116">The V2 format contains **all the roles** so that you can assign role-based permissions.</span></span> |
| <span data-ttu-id="38f62-117">**組織**</span><span class="sxs-lookup"><span data-stu-id="38f62-117">**Orgs**</span></span> | <span data-ttu-id="38f62-118">V1 格式包含 **僅學校**，因此只能看到一個彙總層級 (所有學校)。</span><span class="sxs-lookup"><span data-stu-id="38f62-118">The V1 format contains **only schools**, so you see only one aggregation level (all your schools).</span></span> <span data-ttu-id="38f62-119">您可以使用一般清單放大至特定學校，但此清單可能包含大量學校或包含難以比較的不同類型學校 (如小學到中學或科學到藝術學校)。</span><span class="sxs-lookup"><span data-stu-id="38f62-119">You can zoom in to a specific school using a flat list, but this list may have a large number of schools or contain different types of schools that are hard to compare (such as primary to secondary school or science to art school).</span></span><br/><br/> <span data-ttu-id="38f62-120">當有階層結構時，您可以建立易辨識的層級，例如科學或藝術系。</span><span class="sxs-lookup"><span data-stu-id="38f62-120">When there is a hierarchy in place, you can create levels that make sense, such as a science or art department.</span></span>| <span data-ttu-id="38f62-121">V2 格式包含 **您所在地區或機构的完整階層結構**，包括大學、學院、教職員、校園、地區、項目等。</span><span class="sxs-lookup"><span data-stu-id="38f62-121">The V2 format contains **the full hierarchy of your district or institution**, including universities, colleges, faculties, campuses, regions, programs and so on.</span></span><br/><br/> <span data-ttu-id="38f62-122">使用階層圖，您可以按階層結構的每個層級查看相關彙總，快速比較每個層級的組織單位，為特定層級指派權限，按組織層級設定目標，等等。</span><span class="sxs-lookup"><span data-stu-id="38f62-122">With a hierarchy, you can see relevant aggregation by each level of the hierarchy, quickly compare between organizational units at each level, assign permission to specific levels, set goals by org level, and so on.</span></span>|

### <a name="type-of-data-required"></a><span data-ttu-id="38f62-123">要求的資料類型</span><span class="sxs-lookup"><span data-stu-id="38f62-123">Type of data required</span></span>
<span data-ttu-id="38f62-124">下表格提供了充分利用 Insights 所需的資料類型。</span><span class="sxs-lookup"><span data-stu-id="38f62-124">The following table provides the type of data required to get the best out of Insights.</span></span>

| <span data-ttu-id="38f62-125">資料類型</span><span class="sxs-lookup"><span data-stu-id="38f62-125">Data type</span></span> | <span data-ttu-id="38f62-126">您需要提供的範例</span><span class="sxs-lookup"><span data-stu-id="38f62-126">Examples for what you need to provide</span></span>|<span data-ttu-id="38f62-127">為什麼重要？</span><span class="sxs-lookup"><span data-stu-id="38f62-127">Why it's important?</span></span>|
|:--- |:--- |:--- |
| <span data-ttu-id="38f62-128">**使用者**</span><span class="sxs-lookup"><span data-stu-id="38f62-128">**Users**</span></span> |   <span data-ttu-id="38f62-129">角色 (例如學生)</span><span class="sxs-lookup"><span data-stu-id="38f62-129">Role (such as student)</span></span><br/> <span data-ttu-id="38f62-130">年級/年層級 (如 10)</span><span class="sxs-lookup"><span data-stu-id="38f62-130">Grade/Year level (such as 10)</span></span><br/> <span data-ttu-id="38f62-131">組織 (名稱)</span><span class="sxs-lookup"><span data-stu-id="38f62-131">Org (name)</span></span> | <span data-ttu-id="38f62-132">當我們正確地將每個人指派給他們的角色、年級/年層級以及組織時，我們可以確保摘要和彙總是正確的。</span><span class="sxs-lookup"><span data-stu-id="38f62-132">When we correctly assign each person to their role, grade/year level, and organization, we can ensure that the summaries and aggregations are correct.</span></span>|
| <span data-ttu-id="38f62-133">**組織**</span><span class="sxs-lookup"><span data-stu-id="38f62-133">**Orgs**</span></span> | <span data-ttu-id="38f62-134">組織類型 (例如學院)</span><span class="sxs-lookup"><span data-stu-id="38f62-134">Org type (such as college)</span></span> |   <span data-ttu-id="38f62-135">此處的階層十分重要。</span><span class="sxs-lookup"><span data-stu-id="38f62-135">The hierarchy here is important.</span></span> <span data-ttu-id="38f62-136">例如，學校可能屬於一個地區，而該地區可能屬於一個州。</span><span class="sxs-lookup"><span data-stu-id="38f62-136">For example, schools may belong to a district, and that district may belong to a state.</span></span><br/> <span data-ttu-id="38f62-137">當一個地區的教育領導被允許查看資料時，只能查看該地區學校的資料。</span><span class="sxs-lookup"><span data-stu-id="38f62-137">When a district education leader is permitted to see data, it's only for the schools in that district.</span></span>|
| <span data-ttu-id="38f62-138">**班級**</span><span class="sxs-lookup"><span data-stu-id="38f62-138">**Classes**</span></span> | <span data-ttu-id="38f62-139">標題 (例如電腦科學 101)</span><span class="sxs-lookup"><span data-stu-id="38f62-139">Title (such as Computer science 101)</span></span> | <span data-ttu-id="38f62-140">這將詳細說明組織中的班級。</span><span class="sxs-lookup"><span data-stu-id="38f62-140">This details which classes are held in the organization.</span></span> <span data-ttu-id="38f62-141">這必須正確對應，這樣我們才能將學生指派到正確的班級。</span><span class="sxs-lookup"><span data-stu-id="38f62-141">This must be correctly mapped so that we can assign the student to the correct class.</span></span> |
| <span data-ttu-id="38f62-142">**註冊**</span><span class="sxs-lookup"><span data-stu-id="38f62-142">**Enrollment**</span></span> | <span data-ttu-id="38f62-143">角色 (例如學生)</span><span class="sxs-lookup"><span data-stu-id="38f62-143">Role (such as student)</span></span> | <span data-ttu-id="38f62-144">這針對學生和教育工作者，使我們能够知道他們在哪個班級注册。</span><span class="sxs-lookup"><span data-stu-id="38f62-144">This is for students and educators and enables us to know in which class they are registered.</span></span> |

> [!NOTE]
> <span data-ttu-id="38f62-145">在部署過程中，您可以决定是使用 SDS 在 Teams 中設定使用者和班級，還是只使用 SDS 向 Insights 提供資料。</span><span class="sxs-lookup"><span data-stu-id="38f62-145">During the deployment process, you can decide if you want to use SDS for provisioning users and classes in Teams or to use it only to provide data to Insights.</span></span>

## <a name="best-practices"></a><span data-ttu-id="38f62-146">最佳做法</span><span class="sxs-lookup"><span data-stu-id="38f62-146">Best practices</span></span>
<span data-ttu-id="38f62-147">階層的精確對應以及每個人在該階層中所屬的位置使 Insights 能够為不同類型的教育領導者提供準確的資料和更精確和相關的深入解析。</span><span class="sxs-lookup"><span data-stu-id="38f62-147">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="38f62-148">在這裡提供的詳細資料越多，報告和焦點就越好、越相關。</span><span class="sxs-lookup"><span data-stu-id="38f62-148">The more detail you provide here, the better and more relevant the reports and spotlights will be.</span></span>
<span data-ttu-id="38f62-149">以下是一些確保 SDS 順利部署的最佳做法，從而使您的使用者能够充分利用這些深入解析。</span><span class="sxs-lookup"><span data-stu-id="38f62-149">Here are some best practices based to ensure the smooth deployment of SDS so that your users can make the most out of Insights.</span></span>

### <a name="users"></a><span data-ttu-id="38f62-150">使用者</span><span class="sxs-lookup"><span data-stu-id="38f62-150">Users</span></span>
*   <span data-ttu-id="38f62-151">確保 *所有使用者* 都列在您提供並同步處理的檔案中。</span><span class="sxs-lookup"><span data-stu-id="38f62-151">Make sure *all users* are listed in the files you provide and synced.</span></span> <span data-ttu-id="38f62-152">這包括所有需要查看所涵蓋組織單位資料的學生和員工。</span><span class="sxs-lookup"><span data-stu-id="38f62-152">This includes all students and staff that need to see data for the organizational units they cover.</span></span>

    <span data-ttu-id="38f62-153">如果當前只有授課者列在 SIS 中，請在將文件上載到 SIS 並同步資料之前手動新增其他使用者。</span><span class="sxs-lookup"><span data-stu-id="38f62-153">If you currently only have educators listed in the SIS, add the other users manually before uploading the files to SIS and syncing the data.</span></span>

    <span data-ttu-id="38f62-154">如果遺漏某些學生，Insights 收集的資料只來自注册的學生，這會使資料和結論產生誤導。</span><span class="sxs-lookup"><span data-stu-id="38f62-154">If some students are missing, the stats gathered by Insights is only from the registered students, and that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="38f62-155">確保 *提供每個使用者的名字和姓氏*。</span><span class="sxs-lookup"><span data-stu-id="38f62-155">Make sure to *provide the first and last name of each user*.</span></span> <span data-ttu-id="38f62-156">若無則可由電子郵件地址參照它們，這在報告和焦點中提供了不太積極的體驗 (具有學生活動或表現之深入解析的卡片)。</span><span class="sxs-lookup"><span data-stu-id="38f62-156">If not, they are referenced by their email address, and this provides a less than positive experience in the reports and spotlights (cards with Insights on student activity or performance).</span></span>

*   <span data-ttu-id="38f62-157">*必須以 2 位數輸入年級/年層級* (例如，7 年級為 07)。</span><span class="sxs-lookup"><span data-stu-id="38f62-157">The *grade/year level must be input as 2 digits* (for example, 07 for Year 7).</span></span> <span data-ttu-id="38f62-158">查看[對應清單](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)。</span><span class="sxs-lookup"><span data-stu-id="38f62-158">Check out the [mapping list](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported).</span></span> 

*   <span data-ttu-id="38f62-159">*將年級/年層級新增到所有學生* 十分重要，以便年級/年層級可以過濾資料。</span><span class="sxs-lookup"><span data-stu-id="38f62-159">It's important to *add the year/grade level to all students* so that a grade/year level can filter the data.</span></span>    

*   <span data-ttu-id="38f62-160">請確保 *將每個使用者指派到其相關的組織單位*。</span><span class="sxs-lookup"><span data-stu-id="38f62-160">Make sure to *assign each user to their relevant organizational unit*.</span></span> <span data-ttu-id="38f62-161">這樣，我們就不會在以每個單位爲依據的彙總資料之焦點中顯示誤導性資料。</span><span class="sxs-lookup"><span data-stu-id="38f62-161">In this way, we won't show misleading data in our spotlights based on aggregated data for each unit.</span></span>

    *   <span data-ttu-id="38f62-162">一個學生可以與多個組織單元相關聯，例如，在一個特殊項目或兩個教職員中注冊的學生。</span><span class="sxs-lookup"><span data-stu-id="38f62-162">A student can be associated with more than one org unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="38f62-163">在這種情況下，在使用者檔案中為該學生提供兩行 – 每個組織一行。</span><span class="sxs-lookup"><span data-stu-id="38f62-163">In such a case, provide two lines in the users file for that student – one for each organization.</span></span>
    
    *   <span data-ttu-id="38f62-164">根據員工的組織單元，您可以定義相關的權限。</span><span class="sxs-lookup"><span data-stu-id="38f62-164">Based on the org unit for staff, you will be able to define the relevant permissions.</span></span> <span data-ttu-id="38f62-165">確保它們與正確的單元層級相關聯，以便它們取得所需的權限。</span><span class="sxs-lookup"><span data-stu-id="38f62-165">Make sure they are associated with the correct unit level, so they receive the permissions they need.</span></span> <span data-ttu-id="38f62-166">例如，指派到四所學校的輔導員需要查看這些學校的所有班級；校長需要查看他們學校的所有班級。</span><span class="sxs-lookup"><span data-stu-id="38f62-166">For example, a counselor assigned to four schools needs to see all the classes in these schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="38f62-167">這個角色至關重要。</span><span class="sxs-lookup"><span data-stu-id="38f62-167">The role is vital.</span></span> <span data-ttu-id="38f62-168">雖然這是封閉清單，但請嘗試將[清單中](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)的角色與上載的每個使用者的真實角色相比對。</span><span class="sxs-lookup"><span data-stu-id="38f62-168">Although this is a closed list, try to match the role from [the list](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="38f62-169">這樣，就可以相應地指派以角色為基礎的權限。</span><span class="sxs-lookup"><span data-stu-id="38f62-169">In this way, you can assign role-based permissions accordingly.</span></span> <span data-ttu-id="38f62-170">例如，為所有校長提供查看其學校班級的權限，或為所有教授提供查看其教職員的權限。</span><span class="sxs-lookup"><span data-stu-id="38f62-170">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

### <a name="organizations"></a><span data-ttu-id="38f62-171">組織</span><span class="sxs-lookup"><span data-stu-id="38f62-171">Organizations</span></span>

* <span data-ttu-id="38f62-172">確保 *反映出組織的真實階層圖*。</span><span class="sxs-lookup"><span data-stu-id="38f62-172">Make sure to *reflect the real hierarchy of your organization*.</span></span> <span data-ttu-id="38f62-173">這可以透過手動新增檔案來實現。</span><span class="sxs-lookup"><span data-stu-id="38f62-173">This can be achieved by manually adding the file.</span></span> <span data-ttu-id="38f62-174">在某些情况下，SIS 中沒有反映這種階層。</span><span class="sxs-lookup"><span data-stu-id="38f62-174">In some cases, this hierarchy is not reflected in the SIS.</span></span> <span data-ttu-id="38f62-175">不過，這裡可能需要按階層結構的每個層級查看相關的彙總，為特定層級指派權限，按組織層級設定目標等等。</span><span class="sxs-lookup"><span data-stu-id="38f62-175">Still, it may be necessary here to see the relevant aggregation by each level of the hierarchy, assign permission to specific levels, set goals by org level, and so on.</span></span> 

* <span data-ttu-id="38f62-176">確保 *組織樹下的所有組織單元都包含學生或班級*，以便為他們彙總學生資料。</span><span class="sxs-lookup"><span data-stu-id="38f62-176">Ensure that *all org units down the org tree include students or classes* to aggregate student data for them.</span></span> <span data-ttu-id="38f62-177">我們建議學生處於樹的最低支。</span><span class="sxs-lookup"><span data-stu-id="38f62-177">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="38f62-178">有關 SDS 部署的更多詳細資訊，請造訪[規劃 SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="38f62-178">For more details about SDS deployment, visit [Planning SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-using-sds"></a><span data-ttu-id="38f62-179">使用 SDS 整合 SIS</span><span class="sxs-lookup"><span data-stu-id="38f62-179">Integrate SIS using SDS</span></span>

<span data-ttu-id="38f62-180">學校資料同步處理 (SDS) 與 Office 365 教育版一起提供。</span><span class="sxs-lookup"><span data-stu-id="38f62-180">School Data Sync (SDS) is provided with Office 365 for Education.</span></span> <span data-ttu-id="38f62-181">SDS 從教育機構的學生資訊系統 (SIS) 讀取資料，並將其與 Teams 整合以實現線上教室和使用者的自動建立。</span><span class="sxs-lookup"><span data-stu-id="38f62-181">SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="38f62-182">它還將 SIS 資料與 Insights 同步。</span><span class="sxs-lookup"><span data-stu-id="38f62-182">It also synchronizes the SIS data with Insights.</span></span>

### <a name="sync-with-insights"></a><span data-ttu-id="38f62-183">與 Insights 同步</span><span class="sxs-lookup"><span data-stu-id="38f62-183">Sync with Insights</span></span>

<span data-ttu-id="38f62-184">首先，需要開啟 Insights 切換以啟動同步處理程序。</span><span class="sxs-lookup"><span data-stu-id="38f62-184">First, you need to turn the Insights toggle on to start the sync process.</span></span>

* <span data-ttu-id="38f62-185">在 [**SDS 入口網站**](https://sds.microsoft.com)上，前往 **[設定]**，向下捲動至 **[收集 Insights 資料]**，並檢查其是否已啟用 (預設為 *啟用*)。</span><span class="sxs-lookup"><span data-stu-id="38f62-185">On the [**SDS portal**](https://sds.microsoft.com), go to **Settings**, scroll down to **Collect data for Insights** and check that it's enabled (it's turned *on* by default).</span></span>

* <span data-ttu-id="38f62-186">向下捲動到下一個開關，**從 SDS 同步組織資料 (預覽)**，然後啟用。</span><span class="sxs-lookup"><span data-stu-id="38f62-186">Scroll down to the next switch, **Sync organizational data from SDS (preview)**, and turn on.</span></span>

<span data-ttu-id="38f62-187">如果您在 [設定] 頁上沒有看到 *[從 SDS 同步組織資料 (預覽)]* 選項，請前往[注册頁](https://aka.ms/insights/join)以提供您的資訊，小組成員將與您聯系。</span><span class="sxs-lookup"><span data-stu-id="38f62-187">If you do not see the option for *Sync organizational data from SDS (preview)* on the Settings page, go to the [sign-up page](https://aka.ms/insights/join) to provide your information, and a team member will reach out to you.</span></span>

:::image type="content" source="media/insights-sds-settings.png" alt-text="與 Insights 同步切換開關":::

### <a name="deploy-sds"></a><span data-ttu-id="38f62-189">部署SDS</span><span class="sxs-lookup"><span data-stu-id="38f62-189">Deploy SDS</span></span>
<span data-ttu-id="38f62-190">**如果您已經使用 SDS**，我們建議您遵循我們的[最佳做法](#best-practices)。</span><span class="sxs-lookup"><span data-stu-id="38f62-190">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="38f62-191">要將目前設定檔與 Insights 同步處理，請前往 **[同步設定檔]**，按一下 **[編輯]**，然後選取 **[從 SDS 同步組織資料]**。</span><span class="sxs-lookup"><span data-stu-id="38f62-191">To sync your current profiles with Insights, go to your **Sync Profile(s)**, click **Edit**, and select **Sync organizational data from SDS**.</span></span> <span data-ttu-id="38f62-192">對於初始同步處理，我們建議在從 SIS 重新整理資料後等待 24 小時，以便報告可用。</span><span class="sxs-lookup"><span data-stu-id="38f62-192">For the initial sync, we recommend waiting 24 hours for the reports to be available after the data is refreshed from your SIS.</span></span>  

<span data-ttu-id="38f62-193">**如果您尚未使用 SDS**，那麼您需要[部署它](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="38f62-193">**If you don't use SDS yet**, you now need to [deploy it](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="38f62-194">在部署過程中，您可以决定是使用 SDS 在 Teams 中設定使用者和班級，還是只使用 SDS 向 Insights 提供資料。</span><span class="sxs-lookup"><span data-stu-id="38f62-194">During the deployment process, you can decide if you want to use SDS for provisioning users and classes in Teams or to use it only to provide data to Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="38f62-195">如果現在是年中，並且您已經手動建立了小組，那麼只使用 SDS 為 Insights 提供資料，明年考慮使用 SDS 為小組中的使用者和班級提供資料。</span><span class="sxs-lookup"><span data-stu-id="38f62-195">If it's the middle of the year and you already created teams manually, use SDS only to provide the data to Insights, and next year consider to use SDS for provisioning users and classes in Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="38f62-196">驗證同步處理程序</span><span class="sxs-lookup"><span data-stu-id="38f62-196">Verify the sync process</span></span>
<span data-ttu-id="38f62-197">同步組織資料旁邊會出現新的狀態區域 – [設定] 頁上的預覽。</span><span class="sxs-lookup"><span data-stu-id="38f62-197">A new status area appears next to Sync organizational data – Preview on the Settings page.</span></span>
 
*   <span data-ttu-id="38f62-198">如果狀態為 **進行中**，請在部署 SDS 設定檔後等待最多 24 小時。</span><span class="sxs-lookup"><span data-stu-id="38f62-198">If the status is **In progress**, please wait up to 24 hours after deployment of the SDS profile.</span></span>

*   <span data-ttu-id="38f62-199">如果狀態為 **[完成]**，恭喜，您可以在組織層級看到 Insights ，並繼續下一步。</span><span class="sxs-lookup"><span data-stu-id="38f62-199">If the status is **Completed**, congratulations, you can see Insights at the organizational level, and continue to the next step.</span></span>

*   <span data-ttu-id="38f62-200">如果狀態為 **[完成但發生錯誤]**、**[完成但有警告]** 或 **[中止]**，請下載包含最新同步的錯誤和警告的記錄檔，並檢查是否可以修正這些錯誤。</span><span class="sxs-lookup"><span data-stu-id="38f62-200">If the status is **Completed with errors**, **Completed with warnings**, or **Aborted**, download the log file that contains the errors and warnings for the latest sync and check if you can fix these errors.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="38f62-201">如果您遇到任何問題，[客戶支援](https://aka.ms/edusupport)會協助您。</span><span class="sxs-lookup"><span data-stu-id="38f62-201">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>
