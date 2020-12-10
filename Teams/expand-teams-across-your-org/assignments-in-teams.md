---
title: 團隊作業
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 瞭解如何在 [教育版團隊中的 Microsoft 團隊系統管理中心] 中管理作業。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: f283a4fb2d49778f4b0e8b31f46dada46f900e6f
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616907"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="c8f92-103">Teams 教育版中的作業</span><span class="sxs-lookup"><span data-stu-id="c8f92-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="c8f92-104">在教育版團隊中的 [作業及成績] 功能可讓教師指派工作、工作或測驗給學生。</span><span class="sxs-lookup"><span data-stu-id="c8f92-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="c8f92-105">教育者可以管理作業時間軸、指示、新增資源以供使用，以及量表的成績及其他功能。</span><span class="sxs-lookup"><span data-stu-id="c8f92-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="c8f92-106">他們也可以在 [成績] 索引標籤中追蹤班級與個別學生的進度。</span><span class="sxs-lookup"><span data-stu-id="c8f92-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="c8f92-107">[深入瞭解團隊中的作業與成績教育](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。</span><span class="sxs-lookup"><span data-stu-id="c8f92-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="c8f92-108">如需不同平臺上團隊作業的詳細資料，請參閱 [依平臺的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="c8f92-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c8f92-109">Microsoft 團隊系統管理中心的作業整合</span><span class="sxs-lookup"><span data-stu-id="c8f92-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="c8f92-110">使用 Microsoft [團隊管理中心] 的 [管理員設定]，您可以開啟或關閉貴組織內部或其學生的相關功能。</span><span class="sxs-lookup"><span data-stu-id="c8f92-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="c8f92-111">以下是與作業相關的設定：</span><span class="sxs-lookup"><span data-stu-id="c8f92-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="c8f92-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="c8f92-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="c8f92-113">每週監護人電子郵件摘要</span><span class="sxs-lookup"><span data-stu-id="c8f92-113">Weekly guardian email digest</span></span>


<span data-ttu-id="c8f92-114">監護人電子郵件會在每個週末傳送給家長或監護人。</span><span class="sxs-lookup"><span data-stu-id="c8f92-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="c8f92-115">電子郵件包含上一周的作業相關資訊，以及即將到來的周。</span><span class="sxs-lookup"><span data-stu-id="c8f92-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="c8f92-116">您可以使用 [學校資料同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync)處理來設定家長和監護人同步處理。</span><span class="sxs-lookup"><span data-stu-id="c8f92-116">The Parent and Guardian Sync can be setup using [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="c8f92-117">透過父母和監護人同步處理 SDS 中的家長連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="c8f92-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="c8f92-118">如需如何啟用家長和監護人同步處理的指示，請參閱 [啟用家長和監護人同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)處理。</span><span class="sxs-lookup"><span data-stu-id="c8f92-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="c8f92-119">在 Microsoft 團隊系統管理中心開啟監護人設定，因為預設會關閉設定。</span><span class="sxs-lookup"><span data-stu-id="c8f92-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="c8f92-120">這可讓教師傳送每週摘要。</span><span class="sxs-lookup"><span data-stu-id="c8f92-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c8f92-121">教師可以選擇不使用摘要，方法是在自己的個人班級小組中取消選擇該設定， ([ **作業設定] > 家長/監護人電子郵件**) 。</span><span class="sxs-lookup"><span data-stu-id="c8f92-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="c8f92-122">若要確認家長會收到電子郵件，必須成立下列三個專案：</span><span class="sxs-lookup"><span data-stu-id="c8f92-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="c8f92-123">附加至 SDS 中的學生個人檔案並將其標記為 _家長_ 或 _監護人_ 的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="c8f92-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="c8f92-124">如需詳細資訊，請參閱 [家長和監護人同步處理檔案格式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)。</span><span class="sxs-lookup"><span data-stu-id="c8f92-124">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="c8f92-125">學生至少屬於一個課程，該課程中的電子郵件未由教師在 [作業設定](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)中停用。</span><span class="sxs-lookup"><span data-stu-id="c8f92-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="c8f92-126">該電子郵件將會包含前一周或下周的到期日作業的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c8f92-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="c8f92-127">此功能的預設設定為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="c8f92-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="c8f92-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="c8f92-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="c8f92-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="c8f92-129">MakeCode</span></span>
<span data-ttu-id="c8f92-130">Microsoft MakeCode 是一種區塊式編碼平臺，可讓所有學生都能使用電腦科學。</span><span class="sxs-lookup"><span data-stu-id="c8f92-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="c8f92-131">MakeCode 是一種受 Microsoft [使用條款](https://go.microsoft.com/fwlink/?LinkID=206977) 與 [隱私權](https://go.microsoft.com/fwlink/?LinkId=521839) 原則制約的 microsoft 產品。</span><span class="sxs-lookup"><span data-stu-id="c8f92-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="c8f92-132">此功能的預設設定為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="c8f92-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="c8f92-133">若要在 [團隊] 中啟用 MakeCode 作業，請移至 [ **團隊系統管理中心**]，流覽至 [ **作業** ] 區段，然後將 [MakeCode 切換] 選項開啟為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="c8f92-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="c8f92-134">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="c8f92-134">Click **Save**.</span></span> <span data-ttu-id="c8f92-135">等待幾個小時，這些設定才會生效。</span><span class="sxs-lookup"><span data-stu-id="c8f92-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="c8f92-136">如需此功能的運作方式的詳細資訊，請參閱此 [視頻示範](https://makecode.com/blog/teams/teams-assignments)。</span><span class="sxs-lookup"><span data-stu-id="c8f92-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="c8f92-137">[深入瞭解 MakeCode](https://aka.ms/makecode)。</span><span class="sxs-lookup"><span data-stu-id="c8f92-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="c8f92-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="c8f92-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="c8f92-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="c8f92-139">Turnitin</span></span>

<span data-ttu-id="c8f92-140">[Turnitin](https://www.turnitin.com/) 是一種學術的完整性服務。</span><span class="sxs-lookup"><span data-stu-id="c8f92-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="c8f92-141">這是協力廠商產品或服務，受限於它本身的條款與隱私權原則。</span><span class="sxs-lookup"><span data-stu-id="c8f92-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="c8f92-142">您負責使用任何協力廠商產品和服務。</span><span class="sxs-lookup"><span data-stu-id="c8f92-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="c8f92-143">此功能的預設設定為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="c8f92-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="c8f92-144">若要為您的組織啟用 Turnitin，您將需要 Turnitin 訂閱。</span><span class="sxs-lookup"><span data-stu-id="c8f92-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="c8f92-145">接著，您可以輸入下列資訊，這些資訊可在您的 Turnitin 系統管理主控台中找到：</span><span class="sxs-lookup"><span data-stu-id="c8f92-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="c8f92-146">**TurnitinApiKey**：這是在系統管理主控台中的 [整合] 下找到的32字元 GUID。</span><span class="sxs-lookup"><span data-stu-id="c8f92-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="c8f92-147">**TurnitinApiUrl**：這是您 Turnitin 系統管理主控台的 HTTPS URL。</span><span class="sxs-lookup"><span data-stu-id="c8f92-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="c8f92-148">以下是協助您取得此資訊的一些指示。</span><span class="sxs-lookup"><span data-stu-id="c8f92-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="c8f92-149">**TurnitinApiUrl** 是系統管理員主控台的主機位址。</span><span class="sxs-lookup"><span data-stu-id="c8f92-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="c8f92-150">範例 `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="c8f92-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="c8f92-151">系統管理主控台是您可以在其中建立整合與整合相關聯的 API 金鑰。</span><span class="sxs-lookup"><span data-stu-id="c8f92-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="c8f92-152">從側邊功能表選取 [整合]， **然後選取 [** **新增整合** ] 並提供名稱的整合。</span><span class="sxs-lookup"><span data-stu-id="c8f92-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![顯示新增整合的螢幕擷取畫面](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="c8f92-154">在您遵循提示之後，系統會為您提供 **TurnitinApiKey** 。</span><span class="sxs-lookup"><span data-stu-id="c8f92-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="c8f92-155">複製 API 金鑰並貼到 Microsoft 團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c8f92-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="c8f92-156">這只是您可以查看金鑰的唯一時機。</span><span class="sxs-lookup"><span data-stu-id="c8f92-156">This is the only time you can view the key.</span></span>

![螢幕擷取畫面顯示覆制 API 金鑰](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="c8f92-158">按一下系統管理中心的 [ **儲存** ] 按鈕時，設定才會生效數小時。</span><span class="sxs-lookup"><span data-stu-id="c8f92-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>

