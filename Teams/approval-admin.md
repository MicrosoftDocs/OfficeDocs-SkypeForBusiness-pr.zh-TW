---
title: Teams 中的核准應用程式可用性
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解 Microsoft Teams 中的核准應用程式可用性。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e03ad5c562f7fd31599bbb86f08e411dfa4b415
ms.sourcegitcommit: fb87d64c6f98041a1da50cf4ef6ff54cdc8d1d29
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902567"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="64f7b-103">Teams 核准應用程式可用性</span><span class="sxs-lookup"><span data-stu-id="64f7b-103">Teams Approvals app availability</span></span>

<span data-ttu-id="64f7b-104">核准應用程式可以個人應用程式形式供所有 Microsoft Teams 使用者使用。</span><span class="sxs-lookup"><span data-stu-id="64f7b-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="64f7b-105">核准應用程式提供一個簡單的方法，將稽核、合規性、責任和工作流程帶到 Teams 中的結構化和非結構化核准。</span><span class="sxs-lookup"><span data-stu-id="64f7b-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![顯示核准應用程式](media/approvals-selection.png)

<span data-ttu-id="64f7b-107">使用者可以釘選核准應用程式，以將其儲存到功能表列。</span><span class="sxs-lookup"><span data-stu-id="64f7b-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![顯示具有釘選選項的核准應用程式](media/approvalApp-pin.png)

<span data-ttu-id="64f7b-109">從核准應用程式建立的第一個核准，會觸發在預設 Common Data Service (CDS) 環境中提供核准解決方案。</span><span class="sxs-lookup"><span data-stu-id="64f7b-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="64f7b-110">從核准應用程式建立的核准將會儲存在預設的 CDS 環境中。</span><span class="sxs-lookup"><span data-stu-id="64f7b-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="64f7b-111">本文章說明核准應用程式的需求和角色。</span><span class="sxs-lookup"><span data-stu-id="64f7b-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="64f7b-112">這項功能尚未發行給政府社群雲端 (GCC) 、政府社群雲端高 (GCCH) ，以及美國 (DOD) 使用者。</span><span class="sxs-lookup"><span data-stu-id="64f7b-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="64f7b-113">必要的權限和授權</span><span class="sxs-lookup"><span data-stu-id="64f7b-113">Required permissions and licenses</span></span>

<span data-ttu-id="64f7b-114">若要使用核准應用程式，您需要下列項目的權限：</span><span class="sxs-lookup"><span data-stu-id="64f7b-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="64f7b-115">建立 Microsoft CDS 資料庫的權限。</span><span class="sxs-lookup"><span data-stu-id="64f7b-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="64f7b-116">位於 [flow.microsoft.com](https://flow.microsoft.com/) 的帳戶</span><span class="sxs-lookup"><span data-stu-id="64f7b-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="64f7b-117">目標環境中的系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="64f7b-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="64f7b-118">[Power Automate](/power-automate/get-started-approvals)、Office 365 或 Dynamics 365 的授權。</span><span class="sxs-lookup"><span data-stu-id="64f7b-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="64f7b-119">CDS 的儲存空間</span><span class="sxs-lookup"><span data-stu-id="64f7b-119">Storage with CDS</span></span>

<span data-ttu-id="64f7b-120">Common Data Model (CDN) 是 CDS 中商務和分析應用程式所使用的共用資料語言。</span><span class="sxs-lookup"><span data-stu-id="64f7b-120">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="64f7b-121">它由 Microsoft 和我們的合作夥伴所發佈的一組標準化、可擴展的資料架構所組成，可讓資料在應用程式和商務程式間保持一致性及其意義。</span><span class="sxs-lookup"><span data-stu-id="64f7b-121">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners, that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="64f7b-122">深入了解 [Microsoft Power Platform 的 Common Data Model](/power-automate/get-started-approvals)。</span><span class="sxs-lookup"><span data-stu-id="64f7b-122">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="64f7b-123">深入了解[核准工作流程](/power-automate/modern-approvals)。</span><span class="sxs-lookup"><span data-stu-id="64f7b-123">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="64f7b-124">核准 Teams 應用程式權限</span><span class="sxs-lookup"><span data-stu-id="64f7b-124">Approvals Teams app permissions</span></span>

<span data-ttu-id="64f7b-125">核准 Teams 應用程式可讓您存取下列功能：</span><span class="sxs-lookup"><span data-stu-id="64f7b-125">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="64f7b-126">接收您提供的訊息和資料。</span><span class="sxs-lookup"><span data-stu-id="64f7b-126">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="64f7b-127">傳送訊息和通知給您。</span><span class="sxs-lookup"><span data-stu-id="64f7b-127">Send you messages and notifications.</span></span>

- <span data-ttu-id="64f7b-128">在沒有 Teams 提供的標頭的情況下，呈現個人應用程式和對話方塊。</span><span class="sxs-lookup"><span data-stu-id="64f7b-128">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="64f7b-129">存取您的設定檔資訊，例如您的姓名、電子郵件地址、公司名稱和偏好的語言。</span><span class="sxs-lookup"><span data-stu-id="64f7b-129">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="64f7b-130">接收小組成員在頻道中提供的訊息和資料。</span><span class="sxs-lookup"><span data-stu-id="64f7b-130">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="64f7b-131">在頻道中傳送訊息和通知。</span><span class="sxs-lookup"><span data-stu-id="64f7b-131">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="64f7b-132">存取小組的資訊：</span><span class="sxs-lookup"><span data-stu-id="64f7b-132">Access your team's information:</span></span>
  - <span data-ttu-id="64f7b-133">小組名稱</span><span class="sxs-lookup"><span data-stu-id="64f7b-133">team name</span></span>
  - <span data-ttu-id="64f7b-134">頻道清單</span><span class="sxs-lookup"><span data-stu-id="64f7b-134">channel list</span></span>
  - <span data-ttu-id="64f7b-135">名冊 (小組成員的名稱和電子郵件地址)。</span><span class="sxs-lookup"><span data-stu-id="64f7b-135">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="64f7b-136">使用小組的資訊來連絡他們。</span><span class="sxs-lookup"><span data-stu-id="64f7b-136">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="64f7b-137">停用核准應用程式</span><span class="sxs-lookup"><span data-stu-id="64f7b-137">Disable the Approvals app</span></span>

<span data-ttu-id="64f7b-138">核准應用程式預設可供使用。</span><span class="sxs-lookup"><span data-stu-id="64f7b-138">The Approvals app is available by default.</span></span> <span data-ttu-id="64f7b-139">您可以在 Teams 系統管理中心停用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="64f7b-139">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="64f7b-140">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="64f7b-140">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="64f7b-141">展開 [Teams 應用程式 **]**，然後選取 [管理應用程式 **]**。</span><span class="sxs-lookup"><span data-stu-id="64f7b-141">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="64f7b-142">搜尋核准應用程式。</span><span class="sxs-lookup"><span data-stu-id="64f7b-142">Search for the Approvals app.</span></span>

![顯示系統管理中心瀏覽，並強調顯示 [Teams 應用程式] > [管理應用程式]](media/manage-approval-apps.png)

  4. <span data-ttu-id="64f7b-144">選取 [核准]。</span><span class="sxs-lookup"><span data-stu-id="64f7b-144">Select Approvals.</span></span>

  5. <span data-ttu-id="64f7b-145">選取切換以為組織停用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="64f7b-145">Select the toggle to disable the app for your organization.</span></span>

![顯示核准應用程式的詳細資料](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="64f7b-147">保留原則</span><span class="sxs-lookup"><span data-stu-id="64f7b-147">Retention policy</span></span>

<span data-ttu-id="64f7b-148">從核准應用程式建立的核准會儲存在預設 CDS 環境中，該選項目前不支援備份。</span><span class="sxs-lookup"><span data-stu-id="64f7b-148">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="64f7b-149">深入了解如何[備份和還原環境 - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments)。</span><span class="sxs-lookup"><span data-stu-id="64f7b-149">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="64f7b-150">稽核</span><span class="sxs-lookup"><span data-stu-id="64f7b-150">Auditing</span></span>

<span data-ttu-id="64f7b-151">核准應用程式會記錄 Microsoft 365 安全性與合規性中心內的稽核事件。</span><span class="sxs-lookup"><span data-stu-id="64f7b-151">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="64f7b-152">您可以檢視稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="64f7b-152">You can view the audit log.</span></span>

1. <span data-ttu-id="64f7b-153">移至 Microsoft 365 合規性網站。</span><span class="sxs-lookup"><span data-stu-id="64f7b-153">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="64f7b-154">選取 [稽核 **]** 區段。</span><span class="sxs-lookup"><span data-stu-id="64f7b-154">Select the **Audit** section.</span></span>

3. <span data-ttu-id="64f7b-155">在 [Microsoft Teams 核准活動 **]** 下搜尋活動。</span><span class="sxs-lookup"><span data-stu-id="64f7b-155">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="64f7b-156">您可以搜尋下列活動：</span><span class="sxs-lookup"><span data-stu-id="64f7b-156">You can search for the following activities:</span></span>

- <span data-ttu-id="64f7b-157">建立新核准要求</span><span class="sxs-lookup"><span data-stu-id="64f7b-157">Create new approval request</span></span>

- <span data-ttu-id="64f7b-158">檢視核准要求詳細資料</span><span class="sxs-lookup"><span data-stu-id="64f7b-158">View approval request details</span></span>

- <span data-ttu-id="64f7b-159">核准的核准要求</span><span class="sxs-lookup"><span data-stu-id="64f7b-159">Approved approval request</span></span>

- <span data-ttu-id="64f7b-160">拒絕的核准要求</span><span class="sxs-lookup"><span data-stu-id="64f7b-160">Rejected approval request</span></span>

- <span data-ttu-id="64f7b-161">取消的核准要求</span><span class="sxs-lookup"><span data-stu-id="64f7b-161">Canceled approval request</span></span>

- <span data-ttu-id="64f7b-162">共用的核准要求</span><span class="sxs-lookup"><span data-stu-id="64f7b-162">Shared approval request</span></span>

- <span data-ttu-id="64f7b-163">已附加到核准要求的檔案</span><span class="sxs-lookup"><span data-stu-id="64f7b-163">File attached to approval request</span></span>

- <span data-ttu-id="64f7b-164">重新指派的核准要求</span><span class="sxs-lookup"><span data-stu-id="64f7b-164">Reassigned approval request</span></span>

- <span data-ttu-id="64f7b-165">已新增至核准要求的電子簽章</span><span class="sxs-lookup"><span data-stu-id="64f7b-165">Added e-signature to approval request</span></span>

<span data-ttu-id="64f7b-166">若要存取流程內的更多稽核核准，請針對主要核准實體「核准」、「核准要求」和「核准回應」，在預設環境中啟用和設定稽核。</span><span class="sxs-lookup"><span data-stu-id="64f7b-166">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="64f7b-167">建立、更新和刪除作業是核准記錄的可稽核事件。</span><span class="sxs-lookup"><span data-stu-id="64f7b-167">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="64f7b-168">深入了解[安全性與合規性的稽核資料和使用者活動 - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity)。</span><span class="sxs-lookup"><span data-stu-id="64f7b-168">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="64f7b-169">您可以在 [Microsoft 365 安全性與合規性中心](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)進一步自訂稽核。</span><span class="sxs-lookup"><span data-stu-id="64f7b-169">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="64f7b-170">若要使用預先設定的報告，請登入 Microsoft 365 安全性與合規性。</span><span class="sxs-lookup"><span data-stu-id="64f7b-170">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="64f7b-171">選取 [搜尋與調查 **]**。</span><span class="sxs-lookup"><span data-stu-id="64f7b-171">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="64f7b-172">搜尋稽核記錄，並選取 [Dynamics 365 活動 **]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="64f7b-172">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="64f7b-173">深入了解 [Microsoft Dataverse 和模型導向的應用程式活動記錄 - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)。</span><span class="sxs-lookup"><span data-stu-id="64f7b-173">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="64f7b-174">安全性</span><span class="sxs-lookup"><span data-stu-id="64f7b-174">Security</span></span>

<span data-ttu-id="64f7b-175">使用者可以從 Teams 核准應用程式建立新的核准，並檢視他們已傳送和接收的核准。</span><span class="sxs-lookup"><span data-stu-id="64f7b-175">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="64f7b-176">使用者無法存取其他人所建立的核准，除非他們是回應者或要求的檢視者。</span><span class="sxs-lookup"><span data-stu-id="64f7b-176">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="64f7b-177">如果使用者是建立核准所在的聊天或頻道的一部分，就會獲授與要求的檢視者角色。</span><span class="sxs-lookup"><span data-stu-id="64f7b-177">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="64f7b-178">如果在建立核准時未提供他們該角色，他們即無法對要求採取動作。</span><span class="sxs-lookup"><span data-stu-id="64f7b-178">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>