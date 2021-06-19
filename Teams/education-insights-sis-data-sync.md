---
title: 將學生資訊系統 (SIS) 資料與 Education Insights 同步處理
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 將學生資訊系統 (SIS) 資料與 Microsoft Teams 中的 Education Insights 同步處理。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997732"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="79d1b-103">將學生資訊系統 (SIS) 資料與 Education Insights 同步處理</span><span class="sxs-lookup"><span data-stu-id="79d1b-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="79d1b-104">送入 [Education Insights](class-insights.md) 中的資料越多，授課者更能夠支援其學生，且教育領導者也更能夠支援授課者。</span><span class="sxs-lookup"><span data-stu-id="79d1b-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="79d1b-105">若要提供組織層級 Insights，我們必須使用[學校資料同步處理 (SDS)](/SchoolDataSync) 來連線到學生資訊系統 (SIS)，使得 Insights 會有正確對應的教育系統階層結構。</span><span class="sxs-lookup"><span data-stu-id="79d1b-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="79d1b-106">以班級授課者身分檢視班級層級的 Insights 並 *不需要* 此同步動作，因為我們會使用 Teams 的班級結構和權限。</span><span class="sxs-lookup"><span data-stu-id="79d1b-106">Viewing class-level Insights as the class educator *does not* require this sync because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-school-data-sync-integration"></a><span data-ttu-id="79d1b-107">規劃您的學校資料同步處理整合</span><span class="sxs-lookup"><span data-stu-id="79d1b-107">Plan your School Data Sync integration</span></span>
<span data-ttu-id="79d1b-108">Microsoft 學校資料同步處理 (又名 SDS) 可提供學校資訊系統 (又名 SIS) 資料及其教育系統的階層結構，並且會對應使用者被指派的位置，以及提供有關學生和組織階層結構的其他資料。</span><span class="sxs-lookup"><span data-stu-id="79d1b-108">The Microsoft School Data Sync (a.k.a SDS) provides the School Information System (a.k.a SIS) data and it’s hierarchical structure of the educational system and maps which user is assigned where, as well as provides additional data on the student and organizational hierarchy.</span></span>

<span data-ttu-id="79d1b-109">Insights 搭配使用 [SDS V2 檔案格式](/schooldatasync/sds-v2-csv-file-format)或以上版本時效果最好，但也支援 *有限功能* 的 [SDS V1 檔案格式](/schooldatasync/school-data-sync-format-csv-files-for-sds)。</span><span class="sxs-lookup"><span data-stu-id="79d1b-109">Insights works best when using [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format) and up, but also supports [SDS V1 file format](/schooldatasync/school-data-sync-format-csv-files-for-sds) *with limited functionality*.</span></span>


### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="79d1b-110">SDS V1 和 V2 檔案格式之間的差異</span><span class="sxs-lookup"><span data-stu-id="79d1b-110">Differences between SDS V1 and V2 file formats</span></span>

<span data-ttu-id="79d1b-111">若要充分利用深入解析，建議使用檔案格式 v2 或 v2.1 (即將推出)</span><span class="sxs-lookup"><span data-stu-id="79d1b-111">To get the most out of insights it is recommended to use file format v2 or v2.1 (Coming soon)</span></span>

| <span data-ttu-id="79d1b-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="79d1b-112">Data type</span></span> | <span data-ttu-id="79d1b-113">V1</span><span class="sxs-lookup"><span data-stu-id="79d1b-113">V1</span></span> | <span data-ttu-id="79d1b-114">V2</span><span class="sxs-lookup"><span data-stu-id="79d1b-114">V2</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="79d1b-115">**使用者**</span><span class="sxs-lookup"><span data-stu-id="79d1b-115">**Users**</span></span> | <span data-ttu-id="79d1b-116">V1 格式包含的 **僅有授課者**，因此若要為教育領導者設定組織層級權限，您需要手動定義每個人的權限。</span><span class="sxs-lookup"><span data-stu-id="79d1b-116">The V1 format contains **only educators**, so to set org-level permissions for your education leaders, you need to define each one's permission manually.</span></span> | <span data-ttu-id="79d1b-117">V2 格式包含 **所有角色**，因此您可以指派以角色為基礎的權限。</span><span class="sxs-lookup"><span data-stu-id="79d1b-117">The V2 format contains **all the roles** so that you can assign role-based permissions.</span></span> |
| <span data-ttu-id="79d1b-118">**組織**</span><span class="sxs-lookup"><span data-stu-id="79d1b-118">**Orgs**</span></span> | <span data-ttu-id="79d1b-119">V1 格式包含 **僅學校**，因此只能看到一個彙總層級 (所有學校)。</span><span class="sxs-lookup"><span data-stu-id="79d1b-119">The V1 format contains **only schools**, so you see only one aggregation level (all your schools).</span></span> <span data-ttu-id="79d1b-120">您可以使用一般清單放大至特定學校，但此清單可能包含大量學校或包含難以比較的不同類型學校 (如小學到中學或科學到藝術學校)。</span><span class="sxs-lookup"><span data-stu-id="79d1b-120">You can zoom in to a specific school using a flat list, but this list may have a large number of schools or contain different types of schools that are hard to compare (such as primary to secondary school or science to art school).</span></span><br/><br/> <span data-ttu-id="79d1b-121">當有階層結構時，您可以建立易辨識的層級，例如科學或藝術系。</span><span class="sxs-lookup"><span data-stu-id="79d1b-121">When there is a hierarchy in place, you can create levels that make sense, such as a science or art department.</span></span>| <span data-ttu-id="79d1b-122">V2 格式包含 **您所在地區或機構的完整階層結構**，包括大學、學院、學系、校區、地區、計劃等。</span><span class="sxs-lookup"><span data-stu-id="79d1b-122">The V2 format contains **the full hierarchy of your district or institution**, including universities, colleges, faculties, campuses, regions, programs, and so on.</span></span><br/><br/> <span data-ttu-id="79d1b-123">使用階層圖，您可以按階層結構的每個層級查看相關彙總，快速比較每個層級的組織單位，為特定層級指派權限，按組織層級設定目標，等等。</span><span class="sxs-lookup"><span data-stu-id="79d1b-123">With a hierarchy, you can see relevant aggregation by each level of the hierarchy, quickly compare between organizational units at each level, assign permission to specific levels, set goals by org level, and so on.</span></span>|

> [!NOTE]
> <span data-ttu-id="79d1b-124">從 2021 年 7 月 15 日開始，客戶將無法上線檔案格式 v2，且必須改為使用 v2.1 格式，所有未來的升級和新功能都會以 v2.1 格式完成，而且會完全向下相容於檔案格式 v1。</span><span class="sxs-lookup"><span data-stu-id="79d1b-124">Customers will not be able on onboard file format v2 starting July 15th 2021, and will need to use the v2.1 format instead, all future upgrades and new capabilitie will be done on the v2.1 format and it will be fully backward compatible to file format v1.</span></span>

## <a name="best-practices"></a><span data-ttu-id="79d1b-125">最佳做法</span><span class="sxs-lookup"><span data-stu-id="79d1b-125">Best practices</span></span>
<span data-ttu-id="79d1b-126">階層的精確對應以及每個人在該階層中所屬的位置，使 Insights 能够為不同類型的教育領導者提供準確的資料和更精確和相關的深入解析。</span><span class="sxs-lookup"><span data-stu-id="79d1b-126">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy, enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="79d1b-127">在這裡提供的詳細資料越多，報告和焦點就越詳細、越相關。</span><span class="sxs-lookup"><span data-stu-id="79d1b-127">The more detail you provide, the better and more relevant the reports and spotlights will be.</span></span>

<span data-ttu-id="79d1b-128">以下是一些確保 SDS 順利部署的最佳做法，以讓您的使用者能够充分利用 Insights。</span><span class="sxs-lookup"><span data-stu-id="79d1b-128">Here are some best practices to ensure the smooth deployment of SDS so that your users can make the most out of Insights.</span></span>

### <a name="file-format-version-to-ue"></a><span data-ttu-id="79d1b-129">至 ue 的檔案格式版本</span><span class="sxs-lookup"><span data-stu-id="79d1b-129">File format version to ue</span></span>
*   <span data-ttu-id="79d1b-130">使用檔案格式 V2.1 (即將推出) 並同步教育版 Insights 所使用的選擇性資料</span><span class="sxs-lookup"><span data-stu-id="79d1b-130">Use file format V2.1 (coming soon) and sync the optional data used by Education Insights</span></span>

### <a name="users-and-roles"></a><span data-ttu-id="79d1b-131">使用者與角色</span><span class="sxs-lookup"><span data-stu-id="79d1b-131">Users and Roles</span></span>
*   <span data-ttu-id="79d1b-132">確認 **所有使用者都列在您提供並同步處理的檔案中**。</span><span class="sxs-lookup"><span data-stu-id="79d1b-132">Make sure **all users are listed in the files** you provide and synced.</span></span> <span data-ttu-id="79d1b-133">這包括所有需要查看所涵蓋組織單位資料的學生和教職員。</span><span class="sxs-lookup"><span data-stu-id="79d1b-133">This includes all students and staff that need to see data for the organizational units they cover.</span></span>
    <span data-ttu-id="79d1b-134">如果目前只有授課者列在 SIS 中，請在將檔案上傳至 SIS 並同步資料之前手動新增其他使用者。</span><span class="sxs-lookup"><span data-stu-id="79d1b-134">If you currently only have educators listed in the SIS, add the other users manually before uploading the files to SDS and syncing the data.</span></span>
    <span data-ttu-id="79d1b-135">Insights 收集的統計資料只來自註冊的學生，如果遺漏某些學生，這會使資料和結論產生誤導。</span><span class="sxs-lookup"><span data-stu-id="79d1b-135">The stats gathered by Insights is only from the registered students, if some students re missing, that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="79d1b-136">確保 **提供每位使用者的名字和姓氏**。</span><span class="sxs-lookup"><span data-stu-id="79d1b-136">Make sure to **provide the first and last name of each user**.</span></span> <span data-ttu-id="79d1b-137">否則，可由電子郵件地址參照它們，這在報告和焦點 (具有學生活動或表現之深入解析的卡片) 中提供非最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="79d1b-137">Otherwise, they will be referenced by their email address, and this provides a non-optimal experience in the reports and spotlights (cards with Insights on student activity or performance).</span></span>

*   <span data-ttu-id="79d1b-138">成績/年級必須依據此[對應清單](#supported-grade-level-values)。</span><span class="sxs-lookup"><span data-stu-id="79d1b-138">The grade/year level must be based on this [mapping list](#supported-grade-level-values).</span></span> 

*   <span data-ttu-id="79d1b-139">請務必將 **年級/成績新增到所有學生**，才能彙整並篩選活動資料。</span><span class="sxs-lookup"><span data-stu-id="79d1b-139">It's important to **add the year/grade level to all students** so that the activity data can be aggregated and filtered by it.</span></span>    

*   <span data-ttu-id="79d1b-140">請確保 **將每位使用者指派到其相關的組織單位**。</span><span class="sxs-lookup"><span data-stu-id="79d1b-140">Make sure to **assign each user to their relevant organizational unit**.</span></span> <span data-ttu-id="79d1b-141">如此一來，教育版 Insights 將不會在教育版 Inisghts 焦點中顯示誤導的資料。</span><span class="sxs-lookup"><span data-stu-id="79d1b-141">That way, Education Insights will not show misleading data in the Education Inisghts spotlights.</span></span>

    *   <span data-ttu-id="79d1b-142">一位學生可以與多個組織單元相關聯，例如，在特殊課程或兩個學院註冊的學生。</span><span class="sxs-lookup"><span data-stu-id="79d1b-142">A student can be associated to more than one organizational unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="79d1b-143">如果學生擁有多個組織單位，請在學生的使用者檔案中各提供一行。</span><span class="sxs-lookup"><span data-stu-id="79d1b-143">In case the student has more hte one organizational unit, provide a line for each in the users file for that student.</span></span>
    
    *   <span data-ttu-id="79d1b-144">IT 系統管理員可以根據組織單位為教職員授予權限。</span><span class="sxs-lookup"><span data-stu-id="79d1b-144">IT admin can grant permissions based on organizational unit for staff.</span></span> <span data-ttu-id="79d1b-145">**確保教職員與正確的單元層級相關聯**，以便它們取得所需的權限。</span><span class="sxs-lookup"><span data-stu-id="79d1b-145">**Make sure staff members are associated with the correct unit level**, so they receive the permissions they need.</span></span> <span data-ttu-id="79d1b-146">例如，指派到四所學校的輔導員需要查看這些學校的所有年級；校長需要查看他們學校的所有班級。</span><span class="sxs-lookup"><span data-stu-id="79d1b-146">For example, a counselor assigned to four schools needs to see all the grades in those schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="79d1b-147">**這個角色至關重要**。</span><span class="sxs-lookup"><span data-stu-id="79d1b-147">**The role is vital**.</span></span> <span data-ttu-id="79d1b-148">雖然此清單為封閉式，請嘗試將[此清單](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)的角色與您上傳的每位使用者的實際角色相對應。</span><span class="sxs-lookup"><span data-stu-id="79d1b-148">Although this list is closed, try to match the role from [the list](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="79d1b-149">這樣，您就可以相應地指派以角色為基礎的權限。</span><span class="sxs-lookup"><span data-stu-id="79d1b-149">This will enable you to assign role-based permissions accordingly.</span></span> <span data-ttu-id="79d1b-150">例如，為所有校長提供查看其學校班級的權限，或為所有教授提供查看其教職員的權限。</span><span class="sxs-lookup"><span data-stu-id="79d1b-150">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

### <a name="organizations"></a><span data-ttu-id="79d1b-151">組織</span><span class="sxs-lookup"><span data-stu-id="79d1b-151">Organizations</span></span>

* <span data-ttu-id="79d1b-152">確保 **反映出組織的真實完整階層圖**。</span><span class="sxs-lookup"><span data-stu-id="79d1b-152">Make sure to **reflect the real and full hierarchy of your organization**.</span></span> <span data-ttu-id="79d1b-153">這可以透過手動新增檔案來實現。</span><span class="sxs-lookup"><span data-stu-id="79d1b-153">This can be achieved by manually adding the file.</span></span> <span data-ttu-id="79d1b-154">在某些情况下，SIS 中沒有反映這種階層。</span><span class="sxs-lookup"><span data-stu-id="79d1b-154">In some cases, this hierarchy is not reflected in the SIS.</span></span> <span data-ttu-id="79d1b-155">不過，這裡可能需要按階層結構的每個層級查看相關的彙總，為特定層級指派權限，按組織層級設定目標等等。</span><span class="sxs-lookup"><span data-stu-id="79d1b-155">Still, it may be necessary  to see the relevant aggregation by each level of the hierarchy, assign permission to specific levels, set goals by organization level, and so on.</span></span> 

* <span data-ttu-id="79d1b-156">確保 **組織樹狀目錄下的所有組織單元都包含學生或班級**，以便為他們彙總學生資料。</span><span class="sxs-lookup"><span data-stu-id="79d1b-156">Ensure that **all organization units down the organization tree include students or classes** to aggregate student data for them.</span></span> <span data-ttu-id="79d1b-157">我們建議學生處於樹的最低支。</span><span class="sxs-lookup"><span data-stu-id="79d1b-157">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="79d1b-158">有關 SDS 部署的更多詳細資訊，請造訪[規劃 SDS](/schooldatasync/planning-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="79d1b-158">For more details about SDS deployment, visit [Planning SDS](/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-data-using-sds"></a><span data-ttu-id="79d1b-159">使用 SDS 整合 SIS 資料</span><span class="sxs-lookup"><span data-stu-id="79d1b-159">Integrate SIS data using SDS</span></span>

<span data-ttu-id="79d1b-160">學校資料同步處理 (SDS) 隨附於 Office 365 教育版中。</span><span class="sxs-lookup"><span data-stu-id="79d1b-160">School Data Sync (SDS) is provided with Office 365 for Education.</span></span> <span data-ttu-id="79d1b-161">SDS 會從教育機構的學生資訊系統 (SIS) 讀取資料，並將其與類似 Teams 的 Microsoft 應用程式整合，以自動建立線上教室和使用者。</span><span class="sxs-lookup"><span data-stu-id="79d1b-161">SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Microsoft applications like Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="79d1b-162">它還會將 SIS 資料與 Insights 同步。</span><span class="sxs-lookup"><span data-stu-id="79d1b-162">It also synchronizes the SIS data with Insights.</span></span>

<span data-ttu-id="79d1b-163">做為 IT 系統管理員，您可以選擇將 SDS 僅用於佈建、僅用於 Insights，或兩者。</span><span class="sxs-lookup"><span data-stu-id="79d1b-163">As an IT Admin, you can choose to use SDS for provisioning only, Insights only or for both.</span></span>

<span data-ttu-id="79d1b-164">若要將 SIS 資訊與教育版 Insights 同步，請遵循[如何部署 SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights)。</span><span class="sxs-lookup"><span data-stu-id="79d1b-164">To Sync your SIS information with Educations Insights follow the instructions in [How to deploy SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights).</span></span>

### <a name="deploy-sds"></a><span data-ttu-id="79d1b-165">部署SDS</span><span class="sxs-lookup"><span data-stu-id="79d1b-165">Deploy SDS</span></span>
<span data-ttu-id="79d1b-166">**如果您已經使用 SDS**，我們建議您遵循我們的 [最佳做法](#best-practices)。</span><span class="sxs-lookup"><span data-stu-id="79d1b-166">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="79d1b-167">**如果您尚未使用 SDS**，那麼您需要 [部署它](/schooldatasync/deploying-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="79d1b-167">**If you don't use SDS yet**, you now need to [deploy it](/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="79d1b-168">在部署過程中，您可以决定要使用 SDS 在 Teams 中佈建使用者和班級，還是只使用 SDS 向 Insights 提供組織階層。</span><span class="sxs-lookup"><span data-stu-id="79d1b-168">During the deployment process, you can decide if you want to use SDS for provisioning users and classes to Teams or to use it only to provide user and organizational hierarchy to Insights as well.</span></span>

> [!NOTE]
> <span data-ttu-id="79d1b-169">如果現在是年中，而您已經手動建立了團隊，請只使用 SDS 為 Insights 提供使用者及組織階層資料，並在明年考慮使用 SDS 為 Teams 佈建使用者和班級。</span><span class="sxs-lookup"><span data-stu-id="79d1b-169">If it's the middle of the year and you already created teams manually, use SDS only to provide the user and organizational hierarchy data to Insights, and next year consider using SDS for provisioning users and classes for Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="79d1b-170">驗證同步處理程序</span><span class="sxs-lookup"><span data-stu-id="79d1b-170">Verify the sync process</span></span>
<span data-ttu-id="79d1b-171">若要驗證同步處理狀態進度，請遵循 [SDS for Insights 資料健康情況與監控](/schooldatasync/sds-for-insights-data-health-and-monitoring) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="79d1b-171">To verify the sync status progress follow the instructions in [SDS for Insights Data Health and Monitoring](/schooldatasync/sds-for-insights-data-health-and-monitoring).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79d1b-172">如果您遇到任何問題，[客戶支援](https://aka.ms/edusupport)會協助您。</span><span class="sxs-lookup"><span data-stu-id="79d1b-172">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>

## <a name="supported-grade-level-values"></a><span data-ttu-id="79d1b-173">支援的年級值</span><span class="sxs-lookup"><span data-stu-id="79d1b-173">Supported grade level values</span></span>

<span data-ttu-id="79d1b-174">在 SDS 檔案中，年級/學年等級會定義為列舉值，表示您只能在 CSV 檔案內提供一組選取的值。</span><span class="sxs-lookup"><span data-stu-id="79d1b-174">In the SDS files, grade/year level defined as Enumerated values, which means you can only provide a selected set of values within the CSV file.</span></span> <span data-ttu-id="79d1b-175">指定值以外的任何值，都會導致同步處理期間發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="79d1b-175">Anything other than values specified will result in an error during sync processing.</span></span>

<span data-ttu-id="79d1b-176">下列小節定義使用者檔案中支援的值。</span><span class="sxs-lookup"><span data-stu-id="79d1b-176">The section below defines the supported values in the users file.</span></span>

### <a name="united-states--worldwide-grade-levels"></a><span data-ttu-id="79d1b-177">美國/全球年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-177">United States / worldwide grade levels</span></span>
|<span data-ttu-id="79d1b-178">檔案中的值 (成績欄)</span><span class="sxs-lookup"><span data-stu-id="79d1b-178">Value in file (Grade column)</span></span> | <span data-ttu-id="79d1b-179">Insights 中的標籤</span><span class="sxs-lookup"><span data-stu-id="79d1b-179">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="79d1b-180">IT</span><span class="sxs-lookup"><span data-stu-id="79d1b-180">IT</span></span>|<span data-ttu-id="79d1b-181">嬰兒</span><span class="sxs-lookup"><span data-stu-id="79d1b-181">Infant</span></span>|
|<span data-ttu-id="79d1b-182">PR</span><span class="sxs-lookup"><span data-stu-id="79d1b-182">PR</span></span>|<span data-ttu-id="79d1b-183">學齡前</span><span class="sxs-lookup"><span data-stu-id="79d1b-183">Pre-school</span></span>|
|<span data-ttu-id="79d1b-184">PK</span><span class="sxs-lookup"><span data-stu-id="79d1b-184">PK</span></span>|<span data-ttu-id="79d1b-185">幼稚園前</span><span class="sxs-lookup"><span data-stu-id="79d1b-185">Pre-kindergarten</span></span>|
|<span data-ttu-id="79d1b-186">TK</span><span class="sxs-lookup"><span data-stu-id="79d1b-186">TK</span></span>|<span data-ttu-id="79d1b-187">過渡幼稚園</span><span class="sxs-lookup"><span data-stu-id="79d1b-187">Transitional Kindergarten</span></span>|
|<span data-ttu-id="79d1b-188">KG</span><span class="sxs-lookup"><span data-stu-id="79d1b-188">KG</span></span>|<span data-ttu-id="79d1b-189">幼稚園</span><span class="sxs-lookup"><span data-stu-id="79d1b-189">Kindergarten</span></span>|
|<span data-ttu-id="79d1b-190">01 或 1</span><span class="sxs-lookup"><span data-stu-id="79d1b-190">01 or 1</span></span>|<span data-ttu-id="79d1b-191">一年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-191">First grade</span></span>|
|<span data-ttu-id="79d1b-192">02 或 2</span><span class="sxs-lookup"><span data-stu-id="79d1b-192">02 or 2</span></span>|<span data-ttu-id="79d1b-193">二年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-193">Second grade</span></span>|
|<span data-ttu-id="79d1b-194">03 或 3</span><span class="sxs-lookup"><span data-stu-id="79d1b-194">03 or 3</span></span>|<span data-ttu-id="79d1b-195">三年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-195">Third grade</span></span>|
|<span data-ttu-id="79d1b-196">04 或 4</span><span class="sxs-lookup"><span data-stu-id="79d1b-196">04 or 4</span></span>|<span data-ttu-id="79d1b-197">四年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-197">Fourth grade</span></span>|
|<span data-ttu-id="79d1b-198">05 或 5</span><span class="sxs-lookup"><span data-stu-id="79d1b-198">05 or 5</span></span>|<span data-ttu-id="79d1b-199">五年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-199">Fifth grade</span></span>|
|<span data-ttu-id="79d1b-200">06 或 6</span><span class="sxs-lookup"><span data-stu-id="79d1b-200">06 or 6</span></span>|<span data-ttu-id="79d1b-201">六年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-201">Sixth grade</span></span>|
|<span data-ttu-id="79d1b-202">07 或 7</span><span class="sxs-lookup"><span data-stu-id="79d1b-202">07 or 7</span></span>|<span data-ttu-id="79d1b-203">七年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-203">Seventh grade</span></span>|
|<span data-ttu-id="79d1b-204">08 或 8</span><span class="sxs-lookup"><span data-stu-id="79d1b-204">08 or 8</span></span>|<span data-ttu-id="79d1b-205">八年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-205">Eighth grade</span></span>|
|<span data-ttu-id="79d1b-206">09 或 9</span><span class="sxs-lookup"><span data-stu-id="79d1b-206">09 or 9</span></span>|<span data-ttu-id="79d1b-207">九年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-207">Ninth grade</span></span>|
|<span data-ttu-id="79d1b-208">10</span><span class="sxs-lookup"><span data-stu-id="79d1b-208">10</span></span>|<span data-ttu-id="79d1b-209">十年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-209">Tenth grade</span></span>|
|<span data-ttu-id="79d1b-210">11</span><span class="sxs-lookup"><span data-stu-id="79d1b-210">11</span></span>|<span data-ttu-id="79d1b-211">十一年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-211">Eleventh grade</span></span>|
|<span data-ttu-id="79d1b-212">12</span><span class="sxs-lookup"><span data-stu-id="79d1b-212">12</span></span>|<span data-ttu-id="79d1b-213">十二年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-213">Twelfth grade</span></span>|
|<span data-ttu-id="79d1b-214">PS</span><span class="sxs-lookup"><span data-stu-id="79d1b-214">PS</span></span>|<span data-ttu-id="79d1b-215">後高中</span><span class="sxs-lookup"><span data-stu-id="79d1b-215">Postsecondary</span></span>|
|<span data-ttu-id="79d1b-216">PS1</span><span class="sxs-lookup"><span data-stu-id="79d1b-216">PS1</span></span>|<span data-ttu-id="79d1b-217">後高中新鮮人</span><span class="sxs-lookup"><span data-stu-id="79d1b-217">Postsecondary freshman</span></span>|
|<span data-ttu-id="79d1b-218">PS2</span><span class="sxs-lookup"><span data-stu-id="79d1b-218">PS2</span></span>|<span data-ttu-id="79d1b-219">後高中二年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-219">Postsecondary sophomore</span></span>|
|<span data-ttu-id="79d1b-220">PS3</span><span class="sxs-lookup"><span data-stu-id="79d1b-220">PS3</span></span>|<span data-ttu-id="79d1b-221">後高中三年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-221">Postsecondary junior</span></span>|
|<span data-ttu-id="79d1b-222">PS4</span><span class="sxs-lookup"><span data-stu-id="79d1b-222">PS4</span></span>|<span data-ttu-id="79d1b-223">後高中四年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-223">Postsecondary senior</span></span>|
|<span data-ttu-id="79d1b-224">undergraduate</span><span class="sxs-lookup"><span data-stu-id="79d1b-224">undergraduate</span></span>|<span data-ttu-id="79d1b-225">大學</span><span class="sxs-lookup"><span data-stu-id="79d1b-225">Undergraduate</span></span>|
|<span data-ttu-id="79d1b-226">graduate</span><span class="sxs-lookup"><span data-stu-id="79d1b-226">graduate</span></span>|<span data-ttu-id="79d1b-227">研究生</span><span class="sxs-lookup"><span data-stu-id="79d1b-227">Graduate</span></span>|
|<span data-ttu-id="79d1b-228">postgraduate</span><span class="sxs-lookup"><span data-stu-id="79d1b-228">postgraduate</span></span>|<span data-ttu-id="79d1b-229">研究生 (具有重點研究的研究生)</span><span class="sxs-lookup"><span data-stu-id="79d1b-229">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="79d1b-230">alumni</span><span class="sxs-lookup"><span data-stu-id="79d1b-230">alumni</span></span>|<span data-ttu-id="79d1b-231">校友</span><span class="sxs-lookup"><span data-stu-id="79d1b-231">Alumni</span></span>|
|<span data-ttu-id="79d1b-232">adultEducation</span><span class="sxs-lookup"><span data-stu-id="79d1b-232">adultEducation</span></span>|<span data-ttu-id="79d1b-233">成人教育</span><span class="sxs-lookup"><span data-stu-id="79d1b-233">Adult Education</span></span>|
|<span data-ttu-id="79d1b-234">UG</span><span class="sxs-lookup"><span data-stu-id="79d1b-234">UG</span></span>|<span data-ttu-id="79d1b-235">未分級</span><span class="sxs-lookup"><span data-stu-id="79d1b-235">Ungraded</span></span>|
|<span data-ttu-id="79d1b-236">Other</span><span class="sxs-lookup"><span data-stu-id="79d1b-236">Other</span></span>|<span data-ttu-id="79d1b-237">其他</span><span class="sxs-lookup"><span data-stu-id="79d1b-237">Other</span></span>|

### <a name="united-kingdom-year-groups"></a><span data-ttu-id="79d1b-238">英國年級群組</span><span class="sxs-lookup"><span data-stu-id="79d1b-238">United Kingdom year groups</span></span>
|<span data-ttu-id="79d1b-239">檔案中的值 (成績欄)</span><span class="sxs-lookup"><span data-stu-id="79d1b-239">Value in file (Grade column)</span></span> | <span data-ttu-id="79d1b-240">Insights 中的標籤</span><span class="sxs-lookup"><span data-stu-id="79d1b-240">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="79d1b-241">IT</span><span class="sxs-lookup"><span data-stu-id="79d1b-241">IT</span></span>|<span data-ttu-id="79d1b-242">幼托</span><span class="sxs-lookup"><span data-stu-id="79d1b-242">Nursery</span></span>|
|<span data-ttu-id="79d1b-243">PR</span><span class="sxs-lookup"><span data-stu-id="79d1b-243">PR</span></span>|<span data-ttu-id="79d1b-244">學齡前</span><span class="sxs-lookup"><span data-stu-id="79d1b-244">Pre-school</span></span>|
|<span data-ttu-id="79d1b-245">PK</span><span class="sxs-lookup"><span data-stu-id="79d1b-245">PK</span></span>|<span data-ttu-id="79d1b-246">接待處</span><span class="sxs-lookup"><span data-stu-id="79d1b-246">Reception</span></span>|
|<span data-ttu-id="79d1b-247">01 或 1</span><span class="sxs-lookup"><span data-stu-id="79d1b-247">01 or 1</span></span>|<span data-ttu-id="79d1b-248">1 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-248">Year 1</span></span>|
|<span data-ttu-id="79d1b-249">02 或 2</span><span class="sxs-lookup"><span data-stu-id="79d1b-249">02 or 2</span></span>|<span data-ttu-id="79d1b-250">2 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-250">Year 2</span></span>|
|<span data-ttu-id="79d1b-251">03 或 3</span><span class="sxs-lookup"><span data-stu-id="79d1b-251">03 or 3</span></span>|<span data-ttu-id="79d1b-252">3 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-252">Year 3</span></span>|
|<span data-ttu-id="79d1b-253">04 或 4</span><span class="sxs-lookup"><span data-stu-id="79d1b-253">04 or 4</span></span>|<span data-ttu-id="79d1b-254">4 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-254">Year 4</span></span>|
|<span data-ttu-id="79d1b-255">05 或 5</span><span class="sxs-lookup"><span data-stu-id="79d1b-255">05 or 5</span></span>|<span data-ttu-id="79d1b-256">5 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-256">Year 5</span></span>|
|<span data-ttu-id="79d1b-257">06 或 6</span><span class="sxs-lookup"><span data-stu-id="79d1b-257">06 or 6</span></span>|<span data-ttu-id="79d1b-258">6 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-258">Year 6</span></span>|
|<span data-ttu-id="79d1b-259">07 或 7</span><span class="sxs-lookup"><span data-stu-id="79d1b-259">07 or 7</span></span>|<span data-ttu-id="79d1b-260">7 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-260">Year 7</span></span>|
|<span data-ttu-id="79d1b-261">08 或 8</span><span class="sxs-lookup"><span data-stu-id="79d1b-261">08 or 8</span></span>|<span data-ttu-id="79d1b-262">8 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-262">Year 8</span></span>|
|<span data-ttu-id="79d1b-263">09 或 9</span><span class="sxs-lookup"><span data-stu-id="79d1b-263">09 or 9</span></span>|<span data-ttu-id="79d1b-264">9 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-264">Year 9</span></span>|
|<span data-ttu-id="79d1b-265">10</span><span class="sxs-lookup"><span data-stu-id="79d1b-265">10</span></span>|<span data-ttu-id="79d1b-266">10 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-266">Year 10</span></span>|
|<span data-ttu-id="79d1b-267">11</span><span class="sxs-lookup"><span data-stu-id="79d1b-267">11</span></span>|<span data-ttu-id="79d1b-268">11 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-268">Year 11</span></span>|
|<span data-ttu-id="79d1b-269">12</span><span class="sxs-lookup"><span data-stu-id="79d1b-269">12</span></span>|<span data-ttu-id="79d1b-270">12 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-270">Year 12</span></span>|
|<span data-ttu-id="79d1b-271">13</span><span class="sxs-lookup"><span data-stu-id="79d1b-271">13</span></span>|<span data-ttu-id="79d1b-272">13 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-272">Year 13</span></span>|
|<span data-ttu-id="79d1b-273">PS</span><span class="sxs-lookup"><span data-stu-id="79d1b-273">PS</span></span>|<span data-ttu-id="79d1b-274">後高中</span><span class="sxs-lookup"><span data-stu-id="79d1b-274">Postsecondary</span></span>|
|<span data-ttu-id="79d1b-275">PS1</span><span class="sxs-lookup"><span data-stu-id="79d1b-275">PS1</span></span>|<span data-ttu-id="79d1b-276">後高中 1 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-276">Postsecondary Year 1</span></span>|
|<span data-ttu-id="79d1b-277">PS2</span><span class="sxs-lookup"><span data-stu-id="79d1b-277">PS2</span></span>|<span data-ttu-id="79d1b-278">後高中 2 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-278">Postsecondary Year 2</span></span>|
|<span data-ttu-id="79d1b-279">PS3</span><span class="sxs-lookup"><span data-stu-id="79d1b-279">PS3</span></span>|<span data-ttu-id="79d1b-280">後高中 3 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-280">Postsecondary Year 3</span></span>|
|<span data-ttu-id="79d1b-281">PS4</span><span class="sxs-lookup"><span data-stu-id="79d1b-281">PS4</span></span>|<span data-ttu-id="79d1b-282">後高中 4 年級</span><span class="sxs-lookup"><span data-stu-id="79d1b-282">Postsecondary Year 4</span></span>|
|<span data-ttu-id="79d1b-283">undergraduate</span><span class="sxs-lookup"><span data-stu-id="79d1b-283">undergraduate</span></span>|<span data-ttu-id="79d1b-284">大學</span><span class="sxs-lookup"><span data-stu-id="79d1b-284">Undergraduate</span></span>|
|<span data-ttu-id="79d1b-285">graduate</span><span class="sxs-lookup"><span data-stu-id="79d1b-285">graduate</span></span>|<span data-ttu-id="79d1b-286">研究生</span><span class="sxs-lookup"><span data-stu-id="79d1b-286">Graduate</span></span>|
|<span data-ttu-id="79d1b-287">postgraduate</span><span class="sxs-lookup"><span data-stu-id="79d1b-287">postgraduate</span></span>|<span data-ttu-id="79d1b-288">研究生 (具有重點研究的研究生)</span><span class="sxs-lookup"><span data-stu-id="79d1b-288">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="79d1b-289">alumni</span><span class="sxs-lookup"><span data-stu-id="79d1b-289">alumni</span></span>|<span data-ttu-id="79d1b-290">校友</span><span class="sxs-lookup"><span data-stu-id="79d1b-290">Alumni</span></span>|
|<span data-ttu-id="79d1b-291">adultEducation</span><span class="sxs-lookup"><span data-stu-id="79d1b-291">adultEducation</span></span>|<span data-ttu-id="79d1b-292">成人教育</span><span class="sxs-lookup"><span data-stu-id="79d1b-292">Adult Education</span></span>|
|<span data-ttu-id="79d1b-293">UG</span><span class="sxs-lookup"><span data-stu-id="79d1b-293">UG</span></span>|<span data-ttu-id="79d1b-294">未分級</span><span class="sxs-lookup"><span data-stu-id="79d1b-294">Ungraded</span></span>|
|<span data-ttu-id="79d1b-295">Other</span><span class="sxs-lookup"><span data-stu-id="79d1b-295">Other</span></span>|<span data-ttu-id="79d1b-296">其他</span><span class="sxs-lookup"><span data-stu-id="79d1b-296">Other</span></span>|

