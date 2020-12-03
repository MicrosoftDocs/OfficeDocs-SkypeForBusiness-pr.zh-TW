---
title: 團隊作業
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561049"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="45f15-103">Teams 教育版中的作業</span><span class="sxs-lookup"><span data-stu-id="45f15-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="45f15-104">作業是指派給課程中的學生或團隊成員的工作或工作單位，成為其研究的一部分。</span><span class="sxs-lookup"><span data-stu-id="45f15-104">Assignments are tasks or units of work assigned to a student or team member in a class as part of their study.</span></span> <span data-ttu-id="45f15-105">您可以在團隊類別中建立作業。</span><span class="sxs-lookup"><span data-stu-id="45f15-105">You can create assignments within your Teams class.</span></span>

<span data-ttu-id="45f15-106">[深入瞭解作業](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。</span><span class="sxs-lookup"><span data-stu-id="45f15-106">[Learn more about Assignments](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="45f15-107">如需不同平臺上團隊作業的詳細資料，請參閱 [依平臺的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="45f15-107">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="45f15-108">Microsoft 團隊系統管理中心中的作業</span><span class="sxs-lookup"><span data-stu-id="45f15-108">Assignments in the Microsoft Teams admin center</span></span>

<span data-ttu-id="45f15-109">使用 Microsoft 團隊系統管理中心的 [管理員設定]，您可以開啟或關閉下列功能，以供貴組織內的學生和教師使用。</span><span class="sxs-lookup"><span data-stu-id="45f15-109">With the admin settings in Microsoft Teams admin center, you can turn the following features on or off to be available for students and teachers within your organization.</span></span> <span data-ttu-id="45f15-110">以下是與作業相關的設定：</span><span class="sxs-lookup"><span data-stu-id="45f15-110">The following are settings related to Assignments:</span></span>

<span data-ttu-id="45f15-111"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="45f15-111"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="45f15-112">每週監護人電子郵件摘要</span><span class="sxs-lookup"><span data-stu-id="45f15-112">Weekly guardian email digest</span></span>

<span data-ttu-id="45f15-113">該電子郵件將會包含上周的工作分派及未來一周的作業相關資訊，並將于週末傳送。</span><span class="sxs-lookup"><span data-stu-id="45f15-113">The emails will contain information about assignments from the previous week and for the upcoming week, and will be sent over the weekend.</span></span> <span data-ttu-id="45f15-114">您可以在這裡找到有關電子郵件內容的資訊。</span><span class="sxs-lookup"><span data-stu-id="45f15-114">Information about the email content can be found here.</span></span> <span data-ttu-id="45f15-115">您必須使用 [學校資料同步處理 (SDS) ](https://docs.microsoft.com/schooldatasync/)，才能由管理員設定並更新電子郵件。</span><span class="sxs-lookup"><span data-stu-id="45f15-115">The emails need to be set up and updated by the admins by using [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/).</span></span> <span data-ttu-id="45f15-116">此功能會自動使用學校的學生資訊系統 (SIS) 中的 [學生 rosters]，為小組填入課程。</span><span class="sxs-lookup"><span data-stu-id="45f15-116">This feature automatically populates classes for Teams with student rosters from the school's student information system (SIS).</span></span> <span data-ttu-id="45f15-117">啟用此功能的步驟如下：</span><span class="sxs-lookup"><span data-stu-id="45f15-117">The steps to enable this feature are:</span></span>

1. <span data-ttu-id="45f15-118">透過父母和監護人同步處理 SDS 中的家長連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="45f15-118">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="45f15-119">如需如何啟用家長和監護人同步處理的指示，請參閱 [啟用家長和監護人同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)處理。</span><span class="sxs-lookup"><span data-stu-id="45f15-119">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="45f15-120">在 Microsoft 團隊系統管理中心開啟監護人設定，因為預設會關閉設定。</span><span class="sxs-lookup"><span data-stu-id="45f15-120">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="45f15-121">這可讓教師傳送每週摘要。</span><span class="sxs-lookup"><span data-stu-id="45f15-121">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="45f15-122">教師可以選擇不使用摘要，方法是在自己的個人班級小組中取消選擇該設定， ([ **作業設定] > 家長/監護人電子郵件**) 。</span><span class="sxs-lookup"><span data-stu-id="45f15-122">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="45f15-123">若要確認家長會收到電子郵件，必須成立下列三個專案：</span><span class="sxs-lookup"><span data-stu-id="45f15-123">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="45f15-124">附加至 SDS 中的學生個人檔案並將其標記為 _家長_ 或 _監護人_ 的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="45f15-124">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="45f15-125">如需詳細資訊，請參閱 [家長和監護人同步處理檔案格式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)。</span><span class="sxs-lookup"><span data-stu-id="45f15-125">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="45f15-126">學生至少屬於一個課程，該課程中的電子郵件未由教師在 [作業設定](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)中停用。</span><span class="sxs-lookup"><span data-stu-id="45f15-126">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="45f15-127">該電子郵件將會包含前一周或下周的到期日作業的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="45f15-127">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="45f15-128">此設定預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="45f15-128">This setting is off by default.</span></span>


<span data-ttu-id="45f15-129"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="45f15-129"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="45f15-130">MakeCode</span><span class="sxs-lookup"><span data-stu-id="45f15-130">MakeCode</span></span>
<span data-ttu-id="45f15-131">Microsoft MakeCode 是一種區塊式編碼平臺，可讓所有學生都能使用電腦科學。</span><span class="sxs-lookup"><span data-stu-id="45f15-131">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="45f15-132">MakeCode 是一種受 Microsoft [使用條款](https://go.microsoft.com/fwlink/?LinkID=206977) 與 [隱私權](https://go.microsoft.com/fwlink/?LinkId=521839) 原則制約的 microsoft 產品。</span><span class="sxs-lookup"><span data-stu-id="45f15-132">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="45f15-133">此設定預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="45f15-133">This setting is off by default.</span></span> <span data-ttu-id="45f15-134">若要在小組中啟用 MakeCode 作業，請在 [ **團隊管理中心**] 中，流覽至 [ **作業** ] 區段，然後將 [MakeCode 切換] 選項關閉為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="45f15-134">To enable MakeCode assignments in Teams, in the **Teams Admin Center**, navigate to the **Assignments** section and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="45f15-135">按一下 [ **儲存** ] 並允許幾個小時，這些設定才會生效。</span><span class="sxs-lookup"><span data-stu-id="45f15-135">Click **Save** and allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="45f15-136">如需此功能的運作方式的詳細資訊，請參閱此 [視頻示範](https://makecode.com/blog/teams/teams-assignments)。</span><span class="sxs-lookup"><span data-stu-id="45f15-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="45f15-137">[深入瞭解 MakeCode](https://aka.ms/makecode)。</span><span class="sxs-lookup"><span data-stu-id="45f15-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="45f15-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="45f15-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="45f15-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="45f15-139">Turnitin</span></span>

<span data-ttu-id="45f15-140">Turnitin 是 plagiarism 偵測服務。</span><span class="sxs-lookup"><span data-stu-id="45f15-140">Turnitin is a plagiarism detection service.</span></span> <span data-ttu-id="45f15-141">這是協力廠商產品或服務，受限於它本身的條款與隱私權原則。</span><span class="sxs-lookup"><span data-stu-id="45f15-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="45f15-142">您負責使用任何協力廠商產品和服務。</span><span class="sxs-lookup"><span data-stu-id="45f15-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="45f15-143">此設定預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="45f15-143">This setting is off by default.</span></span>

<span data-ttu-id="45f15-144">若要為您的組織成功啟用 Turnitin，您必須已經擁有 Turnitin 訂閱。</span><span class="sxs-lookup"><span data-stu-id="45f15-144">In order to successfully enable Turnitin for your organization, you will need to already have a Turnitin subscription.</span></span> <span data-ttu-id="45f15-145">您必須輸入下列其他資訊，這些資訊可在您的 Turnitin 系統管理主控台中找到：</span><span class="sxs-lookup"><span data-stu-id="45f15-145">You will need to enter the following additional information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="45f15-146">**TurnitinApiKey**：這是在系統管理主控台中的 [整合] 下找到的32字元 GUID。</span><span class="sxs-lookup"><span data-stu-id="45f15-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="45f15-147">**TurnitinApiUrl**：這是您 Turnitin 系統管理主控台的 HTTPS URL。</span><span class="sxs-lookup"><span data-stu-id="45f15-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="45f15-148">以下是協助您取得此資訊的一些指示。</span><span class="sxs-lookup"><span data-stu-id="45f15-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="45f15-149">**TurnitinApiUrl** 是系統管理員主控台的主機位址。</span><span class="sxs-lookup"><span data-stu-id="45f15-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="45f15-150">範例 `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="45f15-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="45f15-151">系統管理主控台是您可以在其中建立整合與整合相關聯的 API 金鑰。</span><span class="sxs-lookup"><span data-stu-id="45f15-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="45f15-152">從側邊功能表選取 [整合]， **然後選取 [** **新增整合** ] 並提供名稱的整合。</span><span class="sxs-lookup"><span data-stu-id="45f15-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![顯示新增整合的螢幕擷取畫面](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="45f15-154">在您遵循提示之後，系統會為您提供 **TurnitinApiKey** 。</span><span class="sxs-lookup"><span data-stu-id="45f15-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="45f15-155">複製 API 金鑰並貼到 Microsoft 團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="45f15-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="45f15-156">這只是您可以查看金鑰的唯一時機。</span><span class="sxs-lookup"><span data-stu-id="45f15-156">This is the only time you can view the key.</span></span>

![螢幕擷取畫面顯示覆制 API 金鑰](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="45f15-158">按一下系統管理中心的 [ **儲存** ] 按鈕時，請等候幾小時，這些設定才會生效。</span><span class="sxs-lookup"><span data-stu-id="45f15-158">Upon clicking the **Save** button in the admin center for this setting, please allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="45f15-159">準備好開始使用團隊中的 Turnitin 整合了嗎？</span><span class="sxs-lookup"><span data-stu-id="45f15-159">Ready to start using the Turnitin integration in Teams?</span></span> <span data-ttu-id="45f15-160">註冊 [早期的存取計畫](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)。</span><span class="sxs-lookup"><span data-stu-id="45f15-160">Sign up for the [early access program](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span></span>
