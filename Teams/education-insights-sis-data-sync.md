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
ms.openlocfilehash: 5d5ba5c2c5179d5c333472450fd9b2e9c270a4e9
ms.sourcegitcommit: 7579dda8018691eb1a724cb0311b53333dc3ae5a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "53142839"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a><span data-ttu-id="3f14e-103">將學生資訊系統 (SIS) 資料與 Education Insights 同步處理</span><span class="sxs-lookup"><span data-stu-id="3f14e-103">Sync Student Information System (SIS) data with Education Insights</span></span>
<span data-ttu-id="3f14e-104">送入 [Education Insights](class-insights.md) 中的資料越多，授課者更能夠支援其學生，且教育領導者也更能夠支援授課者。</span><span class="sxs-lookup"><span data-stu-id="3f14e-104">The more data is fed into [Education Insights](class-insights.md), the better educators can support their students, and education leaders can support the educators.</span></span>

<span data-ttu-id="3f14e-105">若要提供組織層級 Insights，我們必須使用[學校資料同步處理 (SDS)](/SchoolDataSync) 來連線到學生資訊系統 (SIS)，使得 Insights 會有正確對應的教育系統階層結構。</span><span class="sxs-lookup"><span data-stu-id="3f14e-105">To provide organization-level Insights, we must use [School Data Sync (SDS)](/SchoolDataSync) to connect to the Student Information System (SIS) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span> 

<span data-ttu-id="3f14e-106">以班級授課者身分檢視班級層級的 Insights 並 *不需要* 此同步動作，因為我們會使用 Teams 的班級結構和權限。</span><span class="sxs-lookup"><span data-stu-id="3f14e-106">Viewing class-level Insights as the class educator *does not* require this sync because we use Teams' class structure and permissions.</span></span>

## <a name="plan-your-school-data-sync-integration"></a><span data-ttu-id="3f14e-107">規劃您的學校資料同步處理整合</span><span class="sxs-lookup"><span data-stu-id="3f14e-107">Plan your School Data Sync integration</span></span>
<span data-ttu-id="3f14e-108">Microsoft 學校資料同步處理 (又名 SDS) 可提供學校資訊系統 (又名 SIS) 資料及其教育系統的階層結構，並且會對應使用者被指派的位置，以及提供有關學生和組織階層結構的其他資料。</span><span class="sxs-lookup"><span data-stu-id="3f14e-108">The Microsoft School Data Sync (a.k.a SDS) provides the School Information System (a.k.a SIS) data and it’s hierarchical structure of the educational system and maps which user is assigned where, as well as provides additional data on the student and organizational hierarchy.</span></span>

<span data-ttu-id="3f14e-109">Insights 搭配使用 [SDS V2.1 檔案格式](/schooldatasync/sds-v2.1-csv-file-format) 時效果最好，但也支援 *有限功能* 的 [SDS V2 檔案格式](/schooldatasync/sds-v2-csv-file-format) 和 [SDS V1 檔案格式](/schooldatasync/school-data-sync-format-csv-files-for-sds)。</span><span class="sxs-lookup"><span data-stu-id="3f14e-109">Insights works best when using [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) but also supports [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format) and  [SDS V1 file format](/schooldatasync/school-data-sync-format-csv-files-for-sds) *with limited functionality*.</span></span>


### <a name="differences-between-sds-v1-and-v2-file-formats"></a><span data-ttu-id="3f14e-110">SDS V1 和 V2 檔案格式之間的差异</span><span class="sxs-lookup"><span data-stu-id="3f14e-110">Differences between SDS V1 and V2 file formats</span></span>

| <span data-ttu-id="3f14e-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="3f14e-111">Data type</span></span> | <span data-ttu-id="3f14e-112">V1</span><span class="sxs-lookup"><span data-stu-id="3f14e-112">V1</span></span> | <span data-ttu-id="3f14e-113">V2 和 V2.1</span><span class="sxs-lookup"><span data-stu-id="3f14e-113">V2 and V2.1</span></span> |
|:--- |:--- |:--- |
| <span data-ttu-id="3f14e-114">**使用者**</span><span class="sxs-lookup"><span data-stu-id="3f14e-114">**Users**</span></span> |<span data-ttu-id="3f14e-115">僅支援‘教育者’角色，因此需要手動設定教育領導者的組織層級許可權</span><span class="sxs-lookup"><span data-stu-id="3f14e-115">Supports only ‘educator’ role, as a result org-level permissions for your education leaders need to be set manually</span></span>|<span data-ttu-id="3f14e-116">支援多個角色，以便設定角色型權限</span><span class="sxs-lookup"><span data-stu-id="3f14e-116">Supports multiple roles so that role-based permissions can be set</span></span>|
| <span data-ttu-id="3f14e-117">**組織**</span><span class="sxs-lookup"><span data-stu-id="3f14e-117">**Orgs**</span></span> | <span data-ttu-id="3f14e-118">僅支援‘學校’、匯總層級。</span><span class="sxs-lookup"><span data-stu-id="3f14e-118">Supports only ‘schools’, aggregation level.</span></span><br><br><span data-ttu-id="3f14e-119">因此，不提供多重匯總層級，並提供比較不同類型學校 (例如小學與中學、科學與藝術學校) 的有限能力</span><span class="sxs-lookup"><span data-stu-id="3f14e-119">As a result, does not provide multiple aggregation levels and provide limited ability to compare different types of schools (e.g primary vs. secondary school, science vs. art school)</span></span>|<span data-ttu-id="3f14e-120">支援多層階層圖，包括學區/機構、大學、學院、教職員、校園、地區、方案等。</span><span class="sxs-lookup"><span data-stu-id="3f14e-120">Supports multi-layer hierarchy, including district/institution, universities, colleges, faculties, campuses, regions, programs, etc.</span></span><br><br><span data-ttu-id="3f14e-121">允許多個匯總層級，並輕鬆比較每個層級的組織單位、指派權限至特定層級、根據組織層級設定目標等等。</span><span class="sxs-lookup"><span data-stu-id="3f14e-121">Allows for multiple aggregation levels and to easily compare between organizational units at each level, assign permissions to specific levels, set goals by org level, etc.</span></span>|
| <span data-ttu-id="3f14e-122">**其他選用資訊**</span><span class="sxs-lookup"><span data-stu-id="3f14e-122">**Additional optional information**</span></span> |<span data-ttu-id="3f14e-123">無</span><span class="sxs-lookup"><span data-stu-id="3f14e-123">None</span></span>|<span data-ttu-id="3f14e-124">**僅 V2.1 檔案格式**</span><span class="sxs-lookup"><span data-stu-id="3f14e-124">**V2.1 file format only**</span></span><br><br><span data-ttu-id="3f14e-125">*學術課程* - 工作階段的時間範圍 (學期、學年等)</span><span class="sxs-lookup"><span data-stu-id="3f14e-125">*Academic Sessions* - timeframes of sessions (semesters, school years etc.)</span></span><br><br><span data-ttu-id="3f14e-126">人口統計和學生旗標\* - 種族、民族和性別等資料，以及特殊方案 (IEP，504)</span><span class="sxs-lookup"><span data-stu-id="3f14e-126">Demographics and student flags\* - data like race, ethnicity, and gender, as well as special programs (IEP, 504)</span></span>|

> [!NOTE]
> <span data-ttu-id="3f14e-127">從 2021 年 7 月 15 日開始，客戶將無法上線檔案格式 v2，且必須改為使用 v2.1 格式，所有未來的升級和新功能都會以 v2.1 格式完成，而且會完全向下相容於檔案格式 v1。</span><span class="sxs-lookup"><span data-stu-id="3f14e-127">Customers will not be able on onboard file format v2 starting July 15th 2021, and will need to use the v2.1 format instead, all future upgrades and new capabilitie will be done on the v2.1 format and it will be fully backward compatible to file format v1.</span></span>

### <a name="best-practices"></a><span data-ttu-id="3f14e-128">最佳做法</span><span class="sxs-lookup"><span data-stu-id="3f14e-128">Best practices</span></span>

<span data-ttu-id="3f14e-129">階層的精確對應以及每個人在該階層中所屬的位置，使 Insights 能够為不同類型的教育領導者提供準確的資料和更精確和相關的深入解析。</span><span class="sxs-lookup"><span data-stu-id="3f14e-129">The accurate mapping of the hierarchy and where everyone belongs within that hierarchy, enables Insights to provide accurate data and more precise and relevant insights for the different types of education leaders.</span></span>

<span data-ttu-id="3f14e-130">在這裡提供的詳細資料越多，報告和焦點就越詳細、越相關。</span><span class="sxs-lookup"><span data-stu-id="3f14e-130">The more detail you provide, the better and more relevant the reports and spotlights will be.</span></span>

#### <a name="file-format-version-to-use-adn-data-to-sync"></a><span data-ttu-id="3f14e-131">要使用的檔案格式版本與要同步的資料</span><span class="sxs-lookup"><span data-stu-id="3f14e-131">File format version to use adn data to sync</span></span>
*   <span data-ttu-id="3f14e-132">如 [此處](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv) 所述，使用檔案格式 V2.1 並同步教育版 Insights 所使用的選擇性資料。</span><span class="sxs-lookup"><span data-stu-id="3f14e-132">Use file format V2.1 and sync the optional data used by Education Insights as described [here](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv).</span></span>

#### <a name="users-and-roles"></a><span data-ttu-id="3f14e-133">使用者與角色</span><span class="sxs-lookup"><span data-stu-id="3f14e-133">Users and Roles</span></span>
*   <span data-ttu-id="3f14e-134">確認 **所有使用者都列在您提供並同步處理的檔案中**。</span><span class="sxs-lookup"><span data-stu-id="3f14e-134">Make sure **all users are listed in the files** you provide and synced.</span></span> <span data-ttu-id="3f14e-135">這包括所有需要查看所涵蓋組織單位資料的學生和教職員。</span><span class="sxs-lookup"><span data-stu-id="3f14e-135">This includes all students and staff that need to see data for the organizational units they cover.</span></span>
*   <span data-ttu-id="3f14e-136">如果目前只有授課者列在您的 SIS 中，請在將檔案上傳至 SIS 並同步資料之前手動新增全部其他使用者。</span><span class="sxs-lookup"><span data-stu-id="3f14e-136">If you currently only have educators listed in your SIS, add all other users manually before uploading the files to SDS and syncing the data.</span></span> <span data-ttu-id="3f14e-137">Insights 收集的統計資料僅來自註冊的學生，如果遺漏某些學生，將會使資料和結論產生誤導。</span><span class="sxs-lookup"><span data-stu-id="3f14e-137">The stats gathered by Insights will onlybe  from the registered students, if some students are missing, that will make the data and conclusions misleading.</span></span>
    
*   <span data-ttu-id="3f14e-138">如果您也使用 SDS 進行佈建，請務必 **提供每個使用者的名字和姓氏**。</span><span class="sxs-lookup"><span data-stu-id="3f14e-138">If you use SDS for provisioning as well, make sure to **provide the first and last name of each user**.</span></span> <span data-ttu-id="3f14e-139">否則，系統將會透過學生的電子郵件地址進行參照，導致非最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="3f14e-139">Otherwise, students will be referenced by their email address, resulting in a non-optimal experience.</span></span>

*   <span data-ttu-id="3f14e-140">年級/學年等級必須以此份 [對應清單](#supported-grade-level-values) 為依據。</span><span class="sxs-lookup"><span data-stu-id="3f14e-140">The grade/year level must be based on this [mapping list](#supported-grade-level-values).</span></span> 

*   <span data-ttu-id="3f14e-141">請務必 **將學年/年級等級新增至所有學生** 。</span><span class="sxs-lookup"><span data-stu-id="3f14e-141">Make sure to **add the year/grade level to all students** .</span></span>    

*   <span data-ttu-id="3f14e-142">請確保 **將每個使用者指派到其相關的組織單位**。</span><span class="sxs-lookup"><span data-stu-id="3f14e-142">Make sure to **assign each user to their relevant organizational unit**.</span></span>

    *   <span data-ttu-id="3f14e-143">一位學生可以與多個組織單元相關聯，例如，在特殊課程或兩個學院註冊的學生。</span><span class="sxs-lookup"><span data-stu-id="3f14e-143">A student can be associated to more than one organizational unit, for example, students who are registered in a special program or two faculties.</span></span> <span data-ttu-id="3f14e-144">如果學生擁有多個組織單位，請在學生的使用者檔案中各提供一行。</span><span class="sxs-lookup"><span data-stu-id="3f14e-144">In case the student has more then one organizational unit, provide a line for each in the users file for that student.</span></span>
    
    *   <span data-ttu-id="3f14e-145">IT 系統管理員可以根據組織單位為教職員授予權限。</span><span class="sxs-lookup"><span data-stu-id="3f14e-145">IT admin can grant permissions based on organizational unit for staff.</span></span> <span data-ttu-id="3f14e-146">**確保教職員與正確的單元層級相關聯**，以便它們取得所需的權限。</span><span class="sxs-lookup"><span data-stu-id="3f14e-146">**Make sure staff members are associated with the correct unit level**, so they receive the permissions they need.</span></span> <span data-ttu-id="3f14e-147">例如，指派到四所學校的輔導員需要查看這些學校的所有年級；校長需要查看他們學校的所有班級。</span><span class="sxs-lookup"><span data-stu-id="3f14e-147">For example, a counselor assigned to four schools needs to see all the grades in those schools; a principal needs to see all the classes in their school.</span></span> 
    
*   <span data-ttu-id="3f14e-148">**這個角色至關重要**。</span><span class="sxs-lookup"><span data-stu-id="3f14e-148">**The role is vital**.</span></span> <span data-ttu-id="3f14e-149">雖然此清單為封閉式，請嘗試將[此清單](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)的角色與您上傳的每位使用者的實際角色相對應。</span><span class="sxs-lookup"><span data-stu-id="3f14e-149">Although this list is closed, try to match the role from [the list](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) to the real role of each user you upload.</span></span> <span data-ttu-id="3f14e-150">這樣，您就可以相應地指派以角色為基礎的權限。</span><span class="sxs-lookup"><span data-stu-id="3f14e-150">This will enable you to assign role-based permissions accordingly.</span></span> <span data-ttu-id="3f14e-151">例如，為所有校長提供查看其學校班級的權限，或為所有教授提供查看其教職員的權限。</span><span class="sxs-lookup"><span data-stu-id="3f14e-151">For example, provide permissions for all principals to see the classes in their school, or for all professors to see their faculty.</span></span> 

#### <a name="organizations"></a><span data-ttu-id="3f14e-152">組織</span><span class="sxs-lookup"><span data-stu-id="3f14e-152">Organizations</span></span>

* <span data-ttu-id="3f14e-153">確保 **反映出組織的真實完整階層圖**。</span><span class="sxs-lookup"><span data-stu-id="3f14e-153">Make sure to **reflect the real and full hierarchy of your organization**.</span></span> <span data-ttu-id="3f14e-154">在某些情況下，此階層圖不會反映在 SIS 中，在這種情況下，需要手動新增到 CSV 檔案，以完成同步處理。</span><span class="sxs-lookup"><span data-stu-id="3f14e-154">In some cases, this hierarchy is not reflected in the SIS, in which case it needs to be added manually to the CSV file efore syncing.</span></span>

* <span data-ttu-id="3f14e-155">確保 **組織樹狀下的所有組織單元都包含學生或班級**。</span><span class="sxs-lookup"><span data-stu-id="3f14e-155">Make sure that **all organization units down the organization tree include students or classes**.</span></span> <span data-ttu-id="3f14e-156">我們建議學生處於樹的最低支。</span><span class="sxs-lookup"><span data-stu-id="3f14e-156">We recommend that students are on the lowest branch of the tree.</span></span>

> [!NOTE]
> <span data-ttu-id="3f14e-157">有關 SDS 部署的更多詳細資訊，請造訪[規劃 SDS](/schooldatasync/planning-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="3f14e-157">For more details about SDS deployment, visit [Planning SDS](/schooldatasync/planning-school-data-sync).</span></span>

## <a name="integrate-sis-data-using-sds"></a><span data-ttu-id="3f14e-158">使用 SDS 整合 SIS 資料</span><span class="sxs-lookup"><span data-stu-id="3f14e-158">Integrate SIS data using SDS</span></span>

<span data-ttu-id="3f14e-p109">學校資料同步處理 (SDS) 會與 Office 365 教育版一起提供。SDS 會從教育機構的學生資訊系統 (SIS) 讀取資料，並將其與類似 Teams 的 Microsoft 應用程式整合，以自動建立線上教室和使用者。</span><span class="sxs-lookup"><span data-stu-id="3f14e-p109">School Data Sync (SDS) is provided with Office 365 for Education. SDS reads the data from an educational institution's Student Information System (SIS) and integrates it with Microsoft applications like Teams to enable the automatic creation of online classrooms and users.</span></span>

<span data-ttu-id="3f14e-161">它還會將 SIS 資料與 Insights 同步。</span><span class="sxs-lookup"><span data-stu-id="3f14e-161">It also synchronizes the SIS data with Insights.</span></span>

<span data-ttu-id="3f14e-162">做為 IT 系統管理員，您可以選擇將 SDS 僅用於佈建、僅用於 Insights，或兩者。</span><span class="sxs-lookup"><span data-stu-id="3f14e-162">As an IT Admin, you can choose to use SDS for provisioning only, Insights only or for both.</span></span>

<span data-ttu-id="3f14e-163">若要將 SIS 資訊與教育版 Insights 同步，請遵循[如何部署 SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights)。</span><span class="sxs-lookup"><span data-stu-id="3f14e-163">To Sync your SIS information with Educations Insights follow the instructions in [How to deploy SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights).</span></span>

### <a name="deploy-sds"></a><span data-ttu-id="3f14e-164">部署SDS</span><span class="sxs-lookup"><span data-stu-id="3f14e-164">Deploy SDS</span></span>
<span data-ttu-id="3f14e-165">**如果您已經使用 SDS**，我們建議您遵循我們的 [最佳做法](#best-practices)。</span><span class="sxs-lookup"><span data-stu-id="3f14e-165">**If you already use SDS**, we recommend you follow our [best practices](#best-practices).</span></span> 

<span data-ttu-id="3f14e-166">**如果您尚未使用 SDS**，那麼您需要 [部署它](/schooldatasync/deploying-school-data-sync)。</span><span class="sxs-lookup"><span data-stu-id="3f14e-166">**If you don't use SDS yet**, you now need to [deploy it](/schooldatasync/deploying-school-data-sync).</span></span>

<span data-ttu-id="3f14e-167">在部署過程中，您可以决定要使用 SDS 在 Teams 中佈建使用者和班級，還是只使用 SDS 向 Insights 提供組織階層。</span><span class="sxs-lookup"><span data-stu-id="3f14e-167">During the deployment process, you can decide if you want to use SDS for provisioning users and classes to Teams or to use it only to provide user and organizational hierarchy to Insights as well.</span></span>

> [!NOTE]
> <span data-ttu-id="3f14e-168">如果現在是年中，而您已經手動建立了團隊，請只使用 SDS 為 Insights 提供使用者及組織階層資料，並在明年考慮使用 SDS 為 Teams 佈建使用者和班級。</span><span class="sxs-lookup"><span data-stu-id="3f14e-168">If it's the middle of the year and you already created teams manually, use SDS only to provide the user and organizational hierarchy data to Insights, and next year consider using SDS for provisioning users and classes for Teams as well.</span></span>

### <a name="verify-the-sync-process"></a><span data-ttu-id="3f14e-169">驗證同步處理程序</span><span class="sxs-lookup"><span data-stu-id="3f14e-169">Verify the sync process</span></span>
<span data-ttu-id="3f14e-170">若要驗證同步處理狀態進度，請遵循 [SDS for Insights 資料健康情況與監控](/schooldatasync/sds-for-insights-data-health-and-monitoring) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="3f14e-170">To verify the sync status progress follow the instructions in [SDS for Insights Data Health and Monitoring](/schooldatasync/sds-for-insights-data-health-and-monitoring).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f14e-171">如果您遇到任何問題，[客戶支援](https://aka.ms/edusupport)會協助您。</span><span class="sxs-lookup"><span data-stu-id="3f14e-171">If you run into any problems, [customer support](https://aka.ms/edusupport) is there to help you.</span></span>

## <a name="supported-grade-level-values"></a><span data-ttu-id="3f14e-172">支援的年級值</span><span class="sxs-lookup"><span data-stu-id="3f14e-172">Supported grade level values</span></span>

<span data-ttu-id="3f14e-173">在 SDS 檔案中，年級/學年等級會定義為列舉值，表示您只能在 CSV 檔案內提供一組選取的值。</span><span class="sxs-lookup"><span data-stu-id="3f14e-173">In the SDS files, grade/year level defined as Enumerated values, which means you can only provide a selected set of values within the CSV file.</span></span> <span data-ttu-id="3f14e-174">指定值以外的任何值，都會導致同步處理期間發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="3f14e-174">Anything other than values specified will result in an error during sync processing.</span></span>

<span data-ttu-id="3f14e-175">下列小節定義使用者檔案中支援的值。</span><span class="sxs-lookup"><span data-stu-id="3f14e-175">The section below defines the supported values in the users file.</span></span>

### <a name="united-states--worldwide-grade-levels"></a><span data-ttu-id="3f14e-176">美國/全球年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-176">United States / worldwide grade levels</span></span>
|<span data-ttu-id="3f14e-177">檔案中的值 (成績欄)</span><span class="sxs-lookup"><span data-stu-id="3f14e-177">Value in file (Grade column)</span></span> | <span data-ttu-id="3f14e-178">Insights 中的標籤</span><span class="sxs-lookup"><span data-stu-id="3f14e-178">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="3f14e-179">IT</span><span class="sxs-lookup"><span data-stu-id="3f14e-179">IT</span></span>|<span data-ttu-id="3f14e-180">嬰兒</span><span class="sxs-lookup"><span data-stu-id="3f14e-180">Infant</span></span>|
|<span data-ttu-id="3f14e-181">PR</span><span class="sxs-lookup"><span data-stu-id="3f14e-181">PR</span></span>|<span data-ttu-id="3f14e-182">學齡前</span><span class="sxs-lookup"><span data-stu-id="3f14e-182">Pre-school</span></span>|
|<span data-ttu-id="3f14e-183">PK</span><span class="sxs-lookup"><span data-stu-id="3f14e-183">PK</span></span>|<span data-ttu-id="3f14e-184">幼稚園前</span><span class="sxs-lookup"><span data-stu-id="3f14e-184">Pre-kindergarten</span></span>|
|<span data-ttu-id="3f14e-185">TK</span><span class="sxs-lookup"><span data-stu-id="3f14e-185">TK</span></span>|<span data-ttu-id="3f14e-186">過渡幼稚園</span><span class="sxs-lookup"><span data-stu-id="3f14e-186">Transitional Kindergarten</span></span>|
|<span data-ttu-id="3f14e-187">KG</span><span class="sxs-lookup"><span data-stu-id="3f14e-187">KG</span></span>|<span data-ttu-id="3f14e-188">幼稚園</span><span class="sxs-lookup"><span data-stu-id="3f14e-188">Kindergarten</span></span>|
|<span data-ttu-id="3f14e-189">01 或 1</span><span class="sxs-lookup"><span data-stu-id="3f14e-189">01 or 1</span></span>|<span data-ttu-id="3f14e-190">一年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-190">First grade</span></span>|
|<span data-ttu-id="3f14e-191">02 或 2</span><span class="sxs-lookup"><span data-stu-id="3f14e-191">02 or 2</span></span>|<span data-ttu-id="3f14e-192">二年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-192">Second grade</span></span>|
|<span data-ttu-id="3f14e-193">03 或 3</span><span class="sxs-lookup"><span data-stu-id="3f14e-193">03 or 3</span></span>|<span data-ttu-id="3f14e-194">三年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-194">Third grade</span></span>|
|<span data-ttu-id="3f14e-195">04 或 4</span><span class="sxs-lookup"><span data-stu-id="3f14e-195">04 or 4</span></span>|<span data-ttu-id="3f14e-196">四年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-196">Fourth grade</span></span>|
|<span data-ttu-id="3f14e-197">05 或 5</span><span class="sxs-lookup"><span data-stu-id="3f14e-197">05 or 5</span></span>|<span data-ttu-id="3f14e-198">五年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-198">Fifth grade</span></span>|
|<span data-ttu-id="3f14e-199">06 或 6</span><span class="sxs-lookup"><span data-stu-id="3f14e-199">06 or 6</span></span>|<span data-ttu-id="3f14e-200">六年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-200">Sixth grade</span></span>|
|<span data-ttu-id="3f14e-201">07 或 7</span><span class="sxs-lookup"><span data-stu-id="3f14e-201">07 or 7</span></span>|<span data-ttu-id="3f14e-202">七年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-202">Seventh grade</span></span>|
|<span data-ttu-id="3f14e-203">08 或 8</span><span class="sxs-lookup"><span data-stu-id="3f14e-203">08 or 8</span></span>|<span data-ttu-id="3f14e-204">八年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-204">Eighth grade</span></span>|
|<span data-ttu-id="3f14e-205">09 或 9</span><span class="sxs-lookup"><span data-stu-id="3f14e-205">09 or 9</span></span>|<span data-ttu-id="3f14e-206">九年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-206">Ninth grade</span></span>|
|<span data-ttu-id="3f14e-207">10</span><span class="sxs-lookup"><span data-stu-id="3f14e-207">10</span></span>|<span data-ttu-id="3f14e-208">十年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-208">Tenth grade</span></span>|
|<span data-ttu-id="3f14e-209">11</span><span class="sxs-lookup"><span data-stu-id="3f14e-209">11</span></span>|<span data-ttu-id="3f14e-210">十一年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-210">Eleventh grade</span></span>|
|<span data-ttu-id="3f14e-211">12</span><span class="sxs-lookup"><span data-stu-id="3f14e-211">12</span></span>|<span data-ttu-id="3f14e-212">十二年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-212">Twelfth grade</span></span>|
|<span data-ttu-id="3f14e-213">PS</span><span class="sxs-lookup"><span data-stu-id="3f14e-213">PS</span></span>|<span data-ttu-id="3f14e-214">後高中</span><span class="sxs-lookup"><span data-stu-id="3f14e-214">Postsecondary</span></span>|
|<span data-ttu-id="3f14e-215">PS1</span><span class="sxs-lookup"><span data-stu-id="3f14e-215">PS1</span></span>|<span data-ttu-id="3f14e-216">後高中新鮮人</span><span class="sxs-lookup"><span data-stu-id="3f14e-216">Postsecondary freshman</span></span>|
|<span data-ttu-id="3f14e-217">PS2</span><span class="sxs-lookup"><span data-stu-id="3f14e-217">PS2</span></span>|<span data-ttu-id="3f14e-218">後高中二年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-218">Postsecondary sophomore</span></span>|
|<span data-ttu-id="3f14e-219">PS3</span><span class="sxs-lookup"><span data-stu-id="3f14e-219">PS3</span></span>|<span data-ttu-id="3f14e-220">後高中三年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-220">Postsecondary junior</span></span>|
|<span data-ttu-id="3f14e-221">PS4</span><span class="sxs-lookup"><span data-stu-id="3f14e-221">PS4</span></span>|<span data-ttu-id="3f14e-222">後高中四年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-222">Postsecondary senior</span></span>|
|<span data-ttu-id="3f14e-223">undergraduate</span><span class="sxs-lookup"><span data-stu-id="3f14e-223">undergraduate</span></span>|<span data-ttu-id="3f14e-224">大學</span><span class="sxs-lookup"><span data-stu-id="3f14e-224">Undergraduate</span></span>|
|<span data-ttu-id="3f14e-225">graduate</span><span class="sxs-lookup"><span data-stu-id="3f14e-225">graduate</span></span>|<span data-ttu-id="3f14e-226">研究生</span><span class="sxs-lookup"><span data-stu-id="3f14e-226">Graduate</span></span>|
|<span data-ttu-id="3f14e-227">postgraduate</span><span class="sxs-lookup"><span data-stu-id="3f14e-227">postgraduate</span></span>|<span data-ttu-id="3f14e-228">研究生 (具有重點研究的研究生)</span><span class="sxs-lookup"><span data-stu-id="3f14e-228">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="3f14e-229">alumni</span><span class="sxs-lookup"><span data-stu-id="3f14e-229">alumni</span></span>|<span data-ttu-id="3f14e-230">校友</span><span class="sxs-lookup"><span data-stu-id="3f14e-230">Alumni</span></span>|
|<span data-ttu-id="3f14e-231">adultEducation</span><span class="sxs-lookup"><span data-stu-id="3f14e-231">adultEducation</span></span>|<span data-ttu-id="3f14e-232">成人教育</span><span class="sxs-lookup"><span data-stu-id="3f14e-232">Adult Education</span></span>|
|<span data-ttu-id="3f14e-233">UG</span><span class="sxs-lookup"><span data-stu-id="3f14e-233">UG</span></span>|<span data-ttu-id="3f14e-234">未分級</span><span class="sxs-lookup"><span data-stu-id="3f14e-234">Ungraded</span></span>|
|<span data-ttu-id="3f14e-235">Other</span><span class="sxs-lookup"><span data-stu-id="3f14e-235">Other</span></span>|<span data-ttu-id="3f14e-236">其他</span><span class="sxs-lookup"><span data-stu-id="3f14e-236">Other</span></span>|

### <a name="united-kingdom-year-groups"></a><span data-ttu-id="3f14e-237">英國年級群組</span><span class="sxs-lookup"><span data-stu-id="3f14e-237">United Kingdom year groups</span></span>
|<span data-ttu-id="3f14e-238">檔案中的值 (成績欄)</span><span class="sxs-lookup"><span data-stu-id="3f14e-238">Value in file (Grade column)</span></span> | <span data-ttu-id="3f14e-239">Insights 中的標籤</span><span class="sxs-lookup"><span data-stu-id="3f14e-239">Label in Insights</span></span>|
|:---|:---| 
|<span data-ttu-id="3f14e-240">IT</span><span class="sxs-lookup"><span data-stu-id="3f14e-240">IT</span></span>|<span data-ttu-id="3f14e-241">幼托</span><span class="sxs-lookup"><span data-stu-id="3f14e-241">Nursery</span></span>|
|<span data-ttu-id="3f14e-242">PR</span><span class="sxs-lookup"><span data-stu-id="3f14e-242">PR</span></span>|<span data-ttu-id="3f14e-243">學齡前</span><span class="sxs-lookup"><span data-stu-id="3f14e-243">Pre-school</span></span>|
|<span data-ttu-id="3f14e-244">PK</span><span class="sxs-lookup"><span data-stu-id="3f14e-244">PK</span></span>|<span data-ttu-id="3f14e-245">接待處</span><span class="sxs-lookup"><span data-stu-id="3f14e-245">Reception</span></span>|
|<span data-ttu-id="3f14e-246">01 或 1</span><span class="sxs-lookup"><span data-stu-id="3f14e-246">01 or 1</span></span>|<span data-ttu-id="3f14e-247">1 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-247">Year 1</span></span>|
|<span data-ttu-id="3f14e-248">02 或 2</span><span class="sxs-lookup"><span data-stu-id="3f14e-248">02 or 2</span></span>|<span data-ttu-id="3f14e-249">2 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-249">Year 2</span></span>|
|<span data-ttu-id="3f14e-250">03 或 3</span><span class="sxs-lookup"><span data-stu-id="3f14e-250">03 or 3</span></span>|<span data-ttu-id="3f14e-251">3 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-251">Year 3</span></span>|
|<span data-ttu-id="3f14e-252">04 或 4</span><span class="sxs-lookup"><span data-stu-id="3f14e-252">04 or 4</span></span>|<span data-ttu-id="3f14e-253">4 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-253">Year 4</span></span>|
|<span data-ttu-id="3f14e-254">05 或 5</span><span class="sxs-lookup"><span data-stu-id="3f14e-254">05 or 5</span></span>|<span data-ttu-id="3f14e-255">5 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-255">Year 5</span></span>|
|<span data-ttu-id="3f14e-256">06 或 6</span><span class="sxs-lookup"><span data-stu-id="3f14e-256">06 or 6</span></span>|<span data-ttu-id="3f14e-257">6 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-257">Year 6</span></span>|
|<span data-ttu-id="3f14e-258">07 或 7</span><span class="sxs-lookup"><span data-stu-id="3f14e-258">07 or 7</span></span>|<span data-ttu-id="3f14e-259">7 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-259">Year 7</span></span>|
|<span data-ttu-id="3f14e-260">08 或 8</span><span class="sxs-lookup"><span data-stu-id="3f14e-260">08 or 8</span></span>|<span data-ttu-id="3f14e-261">8 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-261">Year 8</span></span>|
|<span data-ttu-id="3f14e-262">09 或 9</span><span class="sxs-lookup"><span data-stu-id="3f14e-262">09 or 9</span></span>|<span data-ttu-id="3f14e-263">9 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-263">Year 9</span></span>|
|<span data-ttu-id="3f14e-264">10</span><span class="sxs-lookup"><span data-stu-id="3f14e-264">10</span></span>|<span data-ttu-id="3f14e-265">10 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-265">Year 10</span></span>|
|<span data-ttu-id="3f14e-266">11</span><span class="sxs-lookup"><span data-stu-id="3f14e-266">11</span></span>|<span data-ttu-id="3f14e-267">11 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-267">Year 11</span></span>|
|<span data-ttu-id="3f14e-268">12</span><span class="sxs-lookup"><span data-stu-id="3f14e-268">12</span></span>|<span data-ttu-id="3f14e-269">12 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-269">Year 12</span></span>|
|<span data-ttu-id="3f14e-270">13</span><span class="sxs-lookup"><span data-stu-id="3f14e-270">13</span></span>|<span data-ttu-id="3f14e-271">13 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-271">Year 13</span></span>|
|<span data-ttu-id="3f14e-272">PS</span><span class="sxs-lookup"><span data-stu-id="3f14e-272">PS</span></span>|<span data-ttu-id="3f14e-273">後高中</span><span class="sxs-lookup"><span data-stu-id="3f14e-273">Postsecondary</span></span>|
|<span data-ttu-id="3f14e-274">PS1</span><span class="sxs-lookup"><span data-stu-id="3f14e-274">PS1</span></span>|<span data-ttu-id="3f14e-275">後高中 1 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-275">Postsecondary Year 1</span></span>|
|<span data-ttu-id="3f14e-276">PS2</span><span class="sxs-lookup"><span data-stu-id="3f14e-276">PS2</span></span>|<span data-ttu-id="3f14e-277">後高中 2 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-277">Postsecondary Year 2</span></span>|
|<span data-ttu-id="3f14e-278">PS3</span><span class="sxs-lookup"><span data-stu-id="3f14e-278">PS3</span></span>|<span data-ttu-id="3f14e-279">後高中 3 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-279">Postsecondary Year 3</span></span>|
|<span data-ttu-id="3f14e-280">PS4</span><span class="sxs-lookup"><span data-stu-id="3f14e-280">PS4</span></span>|<span data-ttu-id="3f14e-281">後高中 4 年級</span><span class="sxs-lookup"><span data-stu-id="3f14e-281">Postsecondary Year 4</span></span>|
|<span data-ttu-id="3f14e-282">undergraduate</span><span class="sxs-lookup"><span data-stu-id="3f14e-282">undergraduate</span></span>|<span data-ttu-id="3f14e-283">大學</span><span class="sxs-lookup"><span data-stu-id="3f14e-283">Undergraduate</span></span>|
|<span data-ttu-id="3f14e-284">graduate</span><span class="sxs-lookup"><span data-stu-id="3f14e-284">graduate</span></span>|<span data-ttu-id="3f14e-285">研究生</span><span class="sxs-lookup"><span data-stu-id="3f14e-285">Graduate</span></span>|
|<span data-ttu-id="3f14e-286">postgraduate</span><span class="sxs-lookup"><span data-stu-id="3f14e-286">postgraduate</span></span>|<span data-ttu-id="3f14e-287">研究生 (具有重點研究的研究生)</span><span class="sxs-lookup"><span data-stu-id="3f14e-287">Postgraduate (graduate with an emphasis on research)</span></span>|
|<span data-ttu-id="3f14e-288">alumni</span><span class="sxs-lookup"><span data-stu-id="3f14e-288">alumni</span></span>|<span data-ttu-id="3f14e-289">校友</span><span class="sxs-lookup"><span data-stu-id="3f14e-289">Alumni</span></span>|
|<span data-ttu-id="3f14e-290">adultEducation</span><span class="sxs-lookup"><span data-stu-id="3f14e-290">adultEducation</span></span>|<span data-ttu-id="3f14e-291">成人教育</span><span class="sxs-lookup"><span data-stu-id="3f14e-291">Adult Education</span></span>|
|<span data-ttu-id="3f14e-292">UG</span><span class="sxs-lookup"><span data-stu-id="3f14e-292">UG</span></span>|<span data-ttu-id="3f14e-293">未分級</span><span class="sxs-lookup"><span data-stu-id="3f14e-293">Ungraded</span></span>|
|<span data-ttu-id="3f14e-294">Other</span><span class="sxs-lookup"><span data-stu-id="3f14e-294">Other</span></span>|<span data-ttu-id="3f14e-295">其他</span><span class="sxs-lookup"><span data-stu-id="3f14e-295">Other</span></span>|

