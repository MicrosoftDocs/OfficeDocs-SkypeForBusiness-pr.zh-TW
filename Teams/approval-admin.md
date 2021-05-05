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
ms.openlocfilehash: 127fc2831e58e7ddea152c7754015a9126390ecc
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212166"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="07c4e-103">Teams 核准應用程式可用性</span><span class="sxs-lookup"><span data-stu-id="07c4e-103">Teams Approvals app availability</span></span>

<span data-ttu-id="07c4e-104">核准應用程式可以個人應用程式形式供所有 Microsoft Teams 使用者使用。</span><span class="sxs-lookup"><span data-stu-id="07c4e-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="07c4e-105">核准應用程式提供一個簡單的方法，將稽核、合規性、責任和工作流程帶到 Teams 中的結構化和非結構化核准。</span><span class="sxs-lookup"><span data-stu-id="07c4e-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![顯示核准應用程式](media/approvals-selection.png)

<span data-ttu-id="07c4e-107">使用者可以釘選核准應用程式，以將其儲存到功能表列。</span><span class="sxs-lookup"><span data-stu-id="07c4e-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![顯示具有釘選選項的核准應用程式](media/approvalApp-pin.png)

<span data-ttu-id="07c4e-109">從核准應用程式建立的第一個核准，會觸發在預設 Common Data Service (CDS) 環境中提供核准解決方案。</span><span class="sxs-lookup"><span data-stu-id="07c4e-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="07c4e-110">從核准應用程式建立的核准將會儲存在預設的 CDS 環境中。</span><span class="sxs-lookup"><span data-stu-id="07c4e-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="07c4e-111">本文章說明核准應用程式的需求和角色。</span><span class="sxs-lookup"><span data-stu-id="07c4e-111">This article describes the Approvals app requirements and roles.</span></span>

> [!NOTE]
> <span data-ttu-id="07c4e-112">這項功能尚未發行至 政府社群雲端 (GCC) 、政府社群雲端高 (GCCH) ，以及美國 (DOD) 使用者。</span><span class="sxs-lookup"><span data-stu-id="07c4e-112">This feature hasn't been released to Government Community Cloud (GCC), Government Community Cloud High (GCCH), and Department of Defense (DOD) users yet.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="07c4e-113">必要的權限和授權</span><span class="sxs-lookup"><span data-stu-id="07c4e-113">Required permissions and licenses</span></span>

<span data-ttu-id="07c4e-114">若要使用核准應用程式，您需要下列項目的權限：</span><span class="sxs-lookup"><span data-stu-id="07c4e-114">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="07c4e-115">建立 Microsoft CDS 資料庫的權限。</span><span class="sxs-lookup"><span data-stu-id="07c4e-115">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="07c4e-116">位於 [flow.microsoft.com](https://flow.microsoft.com/) 的帳戶</span><span class="sxs-lookup"><span data-stu-id="07c4e-116">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="07c4e-117">目標環境中的系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="07c4e-117">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="07c4e-118">[Power Automate](/power-automate/get-started-approvals)、Office 365 或 Dynamics 365 的授權。</span><span class="sxs-lookup"><span data-stu-id="07c4e-118">License for a [Power Automate](/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

- <span data-ttu-id="07c4e-119">使用者需要 Microsoft Forms 授權才能設定新的核准範本。</span><span class="sxs-lookup"><span data-stu-id="07c4e-119">License for Microsoft Forms is required for users to set up new approval templates.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="07c4e-120">CDS 的儲存空間</span><span class="sxs-lookup"><span data-stu-id="07c4e-120">Storage with CDS</span></span>

<span data-ttu-id="07c4e-121">Common Data Model (CDN) 是 CDS 中商務和分析應用程式所使用的共用資料語言。</span><span class="sxs-lookup"><span data-stu-id="07c4e-121">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="07c4e-122">它包含一組由 Microsoft 和我們的合作夥伴所發佈的標準化、可延伸資料架構，可跨應用程式和商務程序實現資料的一致性及其意義。</span><span class="sxs-lookup"><span data-stu-id="07c4e-122">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="07c4e-123">深入了解 [Microsoft Power Platform 的 Common Data Model](/power-automate/get-started-approvals)。</span><span class="sxs-lookup"><span data-stu-id="07c4e-123">Learn more about the [Common Data Model of the Microsoft Power Platform](/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="07c4e-124">深入了解[核准工作流程](/power-automate/modern-approvals)。</span><span class="sxs-lookup"><span data-stu-id="07c4e-124">Learn more about the [Approval workflow](/power-automate/modern-approvals).</span></span>

<span data-ttu-id="07c4e-125">從範本建立核准時，資料仍然會儲存在 CDS 中，例如標題、詳細資料、範本識別碼等。</span><span class="sxs-lookup"><span data-stu-id="07c4e-125">Approvals that are created from a template still store data in CDS, such as their title, details, template ID, and more.</span></span> <span data-ttu-id="07c4e-126">在核准要求上提交的回復會儲存在 Forms 中。</span><span class="sxs-lookup"><span data-stu-id="07c4e-126">Responses that are submitted on the approval request are stored in Forms.</span></span> <span data-ttu-id="07c4e-127">深入瞭解 Microsoft  [Forms 的資料儲存空間](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)。</span><span class="sxs-lookup"><span data-stu-id="07c4e-127">Learn more about  [Data storage for Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).</span></span>

>[!Note]
><span data-ttu-id="07c4e-128">如果您在 Microsoft Forms 網站上刪除表單範本，將會中斷您的核准範本，而使用者將無法啟動要求。</span><span class="sxs-lookup"><span data-stu-id="07c4e-128">If you delete the Form template on the Microsoft Forms site, it will break your Approval template and users will not be able to start the request.</span></span> <span data-ttu-id="07c4e-129">使用者嘗試開啟 Microsoft Forms 上已刪除的核准範本時，收到「CDB TableNotFound」錯誤。</span><span class="sxs-lookup"><span data-stu-id="07c4e-129">Users will get an error "CDB TableNotFound" when trying to open an Approval template that has been deleted on Microsoft Forms.</span></span>

<span data-ttu-id="07c4e-130">核准範本會儲存在 <底片資料儲存體 (SDS) ，這是一個僅于 Microsoft 內部使用的相容儲存平臺。</span><span class="sxs-lookup"><span data-stu-id="07c4e-130">The approval templates are stored in Substrate Data Storage (SDS), which is a compliant storage platform used internally only inside Microsoft.</span></span> <span data-ttu-id="07c4e-131">組織範圍的範本會儲存在 SDS 的「租使用者區」中，而小組範圍的範本則儲存在 SDS 的「群組分片」中。</span><span class="sxs-lookup"><span data-stu-id="07c4e-131">The organization-scoped templates are stored in “tenant shard” of SDS, and team-scoped templates are stored in “group shards” of SDS.</span></span> <span data-ttu-id="07c4e-132">這表示組織範圍的範本會共用租使用者相同的生命週期，而小組範圍的範本會共用團隊的相同生命週期。</span><span class="sxs-lookup"><span data-stu-id="07c4e-132">This means that the org-scoped templates share the same lifetime of the tenant and team-scoped templates share the same lifetime of the team.</span></span> <span data-ttu-id="07c4e-133">因此，永久刪除小組會刪除相關的範本。</span><span class="sxs-lookup"><span data-stu-id="07c4e-133">So, permanently deleting the team deletes the related templates.</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="07c4e-134">核准 Teams 應用程式權限</span><span class="sxs-lookup"><span data-stu-id="07c4e-134">Approvals Teams app permissions</span></span>

<span data-ttu-id="07c4e-135">核准 Teams 應用程式可讓您存取下列功能：</span><span class="sxs-lookup"><span data-stu-id="07c4e-135">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="07c4e-136">接收您提供的訊息和資料。</span><span class="sxs-lookup"><span data-stu-id="07c4e-136">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="07c4e-137">傳送訊息和通知給您。</span><span class="sxs-lookup"><span data-stu-id="07c4e-137">Send you messages and notifications.</span></span>

- <span data-ttu-id="07c4e-138">在沒有 Teams 提供的標頭的情況下，呈現個人應用程式和對話方塊。</span><span class="sxs-lookup"><span data-stu-id="07c4e-138">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="07c4e-139">存取您的設定檔資訊，例如您的姓名、電子郵件地址、公司名稱和偏好的語言。</span><span class="sxs-lookup"><span data-stu-id="07c4e-139">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="07c4e-140">接收小組成員在頻道中提供的訊息和資料。</span><span class="sxs-lookup"><span data-stu-id="07c4e-140">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="07c4e-141">在頻道中傳送訊息和通知。</span><span class="sxs-lookup"><span data-stu-id="07c4e-141">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="07c4e-142">存取小組的資訊：</span><span class="sxs-lookup"><span data-stu-id="07c4e-142">Access your team's information:</span></span>
  - <span data-ttu-id="07c4e-143">小組名稱</span><span class="sxs-lookup"><span data-stu-id="07c4e-143">team name</span></span>
  - <span data-ttu-id="07c4e-144">頻道清單</span><span class="sxs-lookup"><span data-stu-id="07c4e-144">channel list</span></span>
  - <span data-ttu-id="07c4e-145">名冊 (小組成員的名稱和電子郵件地址)。</span><span class="sxs-lookup"><span data-stu-id="07c4e-145">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="07c4e-146">使用小組的資訊來連絡他們。</span><span class="sxs-lookup"><span data-stu-id="07c4e-146">Use the team's information to contact them.</span></span>

<span data-ttu-id="07c4e-147">核准範本許可權</span><span class="sxs-lookup"><span data-stu-id="07c4e-147">Approval Template Permissions</span></span>

- <span data-ttu-id="07c4e-148">所有團隊擁有者都可以為他們擁有的團隊建立核准範本。</span><span class="sxs-lookup"><span data-stu-id="07c4e-148">All team owners can create an approval template for teams that they own.</span></span>

- <span data-ttu-id="07c4e-149">當系統管理員第一次為整個組織建立範本時，系統會自動為租使用者的所有系統管理員 ，包括全域和小組的服務系統管理員Teams建立新的 Teams 小組。</span><span class="sxs-lookup"><span data-stu-id="07c4e-149">When an Admin creates a template for their entire organization for the first time, it will automatically create a new Teams team for all admins of the tenant, including the global and Team’s service admins.</span></span> <span data-ttu-id="07c4e-150">這些系統管理員會新增為團隊的擁有者，以便共同管理組織範本。</span><span class="sxs-lookup"><span data-stu-id="07c4e-150">These admins will be added as owners of the team, so they can co-manage organizational templates.</span></span> <span data-ttu-id="07c4e-151">小組建立之後，組織的新管理員必須手動新增為團隊擁有者，以便他們擁有管理全組織範本的相同許可權。</span><span class="sxs-lookup"><span data-stu-id="07c4e-151">Admins that are new to the organization after the team has been created need to be manually added as team owners so they have the same permissions to manage organization-wide templates.</span></span>

> [!Note]
> <span data-ttu-id="07c4e-152">如果系統管理員刪除小組，您可以在 AAD Azure Active Directory (入口網站) 一個月還原該團隊，以還原所有關聯資料。</span><span class="sxs-lookup"><span data-stu-id="07c4e-152">If an admin deletes the team, you have one month to restore it within the Azure Active Directory (AAD) portal to restore all related data.</span></span> <span data-ttu-id="07c4e-153">一個月後，或如果系統管理員在回收站中刪除此小組，您將失去所有相關的資料。</span><span class="sxs-lookup"><span data-stu-id="07c4e-153">After one month, or if the admin deletes this team within the recycle bin, you will lose all the related data.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="07c4e-154">停用核准應用程式</span><span class="sxs-lookup"><span data-stu-id="07c4e-154">Disable the Approvals app</span></span>

<span data-ttu-id="07c4e-155">核准應用程式預設可供使用。</span><span class="sxs-lookup"><span data-stu-id="07c4e-155">The Approvals app is available by default.</span></span> <span data-ttu-id="07c4e-156">您可以在 Teams 系統管理中心停用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="07c4e-156">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="07c4e-157">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="07c4e-157">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="07c4e-158">展開 [Teams 應用程式 **]**，然後選取 [管理應用程式 **]**。</span><span class="sxs-lookup"><span data-stu-id="07c4e-158">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="07c4e-159">搜尋核准應用程式。</span><span class="sxs-lookup"><span data-stu-id="07c4e-159">Search for the Approvals app.</span></span>

     ![顯示系統管理中心瀏覽，並強調顯示 [Teams 應用程式] > [管理應用程式]](media/manage-approval-apps.png)

  4. <span data-ttu-id="07c4e-161">選取 [核准]。</span><span class="sxs-lookup"><span data-stu-id="07c4e-161">Select Approvals.</span></span>

  5. <span data-ttu-id="07c4e-162">選取切換以為組織停用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="07c4e-162">Select the toggle to disable the app for your organization.</span></span>

     ![顯示核准應用程式的詳細資料](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="07c4e-164">保留原則</span><span class="sxs-lookup"><span data-stu-id="07c4e-164">Retention policy</span></span>

<span data-ttu-id="07c4e-165">從核准應用程式建立的核准會儲存在預設 CDS 環境中，該選項目前不支援備份。</span><span class="sxs-lookup"><span data-stu-id="07c4e-165">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="07c4e-166">深入了解如何[備份和還原環境 - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments)。</span><span class="sxs-lookup"><span data-stu-id="07c4e-166">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](/power-platform/admin/backup-restore-environments).</span></span>

<span data-ttu-id="07c4e-167">在小組擁有者從 Microsoft Forms Web App 的刪除表單選項卡中清除之前，不會刪除儲存在 Forms 中的資料。</span><span class="sxs-lookup"><span data-stu-id="07c4e-167">Data stored in Forms will not be deleted until the team owners clean it up from the **deleted forms** tab in the Microsoft Forms web app.</span></span>

## <a name="data-limitations"></a><span data-ttu-id="07c4e-168">資料限制</span><span class="sxs-lookup"><span data-stu-id="07c4e-168">Data limitations</span></span>

<span data-ttu-id="07c4e-169">每個小組最多可以包含 400 個核准範本，而每個範本最多可以根據 Microsoft Forms 中的目前功能收集 50，000 個要求。</span><span class="sxs-lookup"><span data-stu-id="07c4e-169">Each team can contain at most 400 approvals templates, and each template can collect a maximum of 50,000 requests based on the current capability in Microsoft Forms.</span></span>

## <a name="auditing"></a><span data-ttu-id="07c4e-170">稽核</span><span class="sxs-lookup"><span data-stu-id="07c4e-170">Auditing</span></span>

<span data-ttu-id="07c4e-171">核准應用程式會記錄 Microsoft 365 安全性與合規性中心內的稽核事件。</span><span class="sxs-lookup"><span data-stu-id="07c4e-171">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="07c4e-172">您可以檢視稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="07c4e-172">You can view the audit log.</span></span>

1. <span data-ttu-id="07c4e-173">移至 Microsoft 365 合規性網站。</span><span class="sxs-lookup"><span data-stu-id="07c4e-173">Go to the Microsoft 365 Compliance Site.</span></span>

2. <span data-ttu-id="07c4e-174">選取 [稽核 **]** 區段。</span><span class="sxs-lookup"><span data-stu-id="07c4e-174">Select the **Audit** section.</span></span>

3. <span data-ttu-id="07c4e-175">在 [Microsoft Teams 核准活動 **]** 下搜尋活動。</span><span class="sxs-lookup"><span data-stu-id="07c4e-175">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="07c4e-176">您可以搜尋下列活動：</span><span class="sxs-lookup"><span data-stu-id="07c4e-176">You can search for the following activities:</span></span>

- <span data-ttu-id="07c4e-177">建立新核准要求</span><span class="sxs-lookup"><span data-stu-id="07c4e-177">Create new approval request</span></span>

- <span data-ttu-id="07c4e-178">檢視核准要求詳細資料</span><span class="sxs-lookup"><span data-stu-id="07c4e-178">View approval request details</span></span>

- <span data-ttu-id="07c4e-179">核准的核准要求</span><span class="sxs-lookup"><span data-stu-id="07c4e-179">Approved approval request</span></span>

- <span data-ttu-id="07c4e-180">拒絕的核准要求</span><span class="sxs-lookup"><span data-stu-id="07c4e-180">Rejected approval request</span></span>

- <span data-ttu-id="07c4e-181">取消的核准要求</span><span class="sxs-lookup"><span data-stu-id="07c4e-181">Canceled approval request</span></span>

- <span data-ttu-id="07c4e-182">共用的核准要求</span><span class="sxs-lookup"><span data-stu-id="07c4e-182">Shared approval request</span></span>

- <span data-ttu-id="07c4e-183">已附加到核准要求的檔案</span><span class="sxs-lookup"><span data-stu-id="07c4e-183">File attached to approval request</span></span>

- <span data-ttu-id="07c4e-184">重新指派的核准要求</span><span class="sxs-lookup"><span data-stu-id="07c4e-184">Reassigned approval request</span></span>

- <span data-ttu-id="07c4e-185">已新增至核准要求的電子簽章</span><span class="sxs-lookup"><span data-stu-id="07c4e-185">Added e-signature to approval request</span></span>

- <span data-ttu-id="07c4e-186">已查看電子簽章要求詳細資料</span><span class="sxs-lookup"><span data-stu-id="07c4e-186">Viewed e-signature request details</span></span>

- <span data-ttu-id="07c4e-187">已審查電子簽章要求</span><span class="sxs-lookup"><span data-stu-id="07c4e-187">Reviewed e-signature request</span></span>

- <span data-ttu-id="07c4e-188">已取消電子簽名要求</span><span class="sxs-lookup"><span data-stu-id="07c4e-188">Canceled e-signature request</span></span>

- <span data-ttu-id="07c4e-189">建立新範本</span><span class="sxs-lookup"><span data-stu-id="07c4e-189">Create a new template</span></span>

- <span data-ttu-id="07c4e-190">編輯現有的範本</span><span class="sxs-lookup"><span data-stu-id="07c4e-190">Edit an existing template</span></span>

- <span data-ttu-id="07c4e-191">啟用/停用範本</span><span class="sxs-lookup"><span data-stu-id="07c4e-191">Enable/disable a template</span></span>

- <span data-ttu-id="07c4e-192">已查看範本</span><span class="sxs-lookup"><span data-stu-id="07c4e-192">Viewed template</span></span>

<span data-ttu-id="07c4e-193">若要存取流程內的更多稽核核准，請針對主要核准實體「核准」、「核准要求」和「核准回應」，在預設環境中啟用和設定稽核。</span><span class="sxs-lookup"><span data-stu-id="07c4e-193">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="07c4e-194">建立、更新和刪除作業是核准記錄的可稽核事件。</span><span class="sxs-lookup"><span data-stu-id="07c4e-194">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="07c4e-195">深入了解[安全性與合規性的稽核資料和使用者活動 - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity)。</span><span class="sxs-lookup"><span data-stu-id="07c4e-195">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="07c4e-196">您可以在 [Microsoft 365 安全性與合規性中心](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)進一步自訂稽核。</span><span class="sxs-lookup"><span data-stu-id="07c4e-196">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="07c4e-197">若要使用預先設定的報告，請登入 Microsoft 365 安全性與合規性。</span><span class="sxs-lookup"><span data-stu-id="07c4e-197">To use the preconfigured reports, sign in to Microsoft 365 Security and Compliance.</span></span>

2. <span data-ttu-id="07c4e-198">選取 [搜尋與調查 **]**。</span><span class="sxs-lookup"><span data-stu-id="07c4e-198">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="07c4e-199">搜尋稽核記錄，並選取 [Dynamics 365 活動 **]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="07c4e-199">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="07c4e-200">深入了解 [Microsoft Dataverse 和模型導向的應用程式活動記錄 - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)。</span><span class="sxs-lookup"><span data-stu-id="07c4e-200">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="07c4e-201">安全性</span><span class="sxs-lookup"><span data-stu-id="07c4e-201">Security</span></span>

<span data-ttu-id="07c4e-202">使用者可以從 Teams 核准應用程式建立新的核准，並檢視他們已傳送和接收的核准。</span><span class="sxs-lookup"><span data-stu-id="07c4e-202">From the Teams Approvals app, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="07c4e-203">使用者無法存取其他人所建立的核准，除非他們是回應者或要求的檢視者。</span><span class="sxs-lookup"><span data-stu-id="07c4e-203">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="07c4e-204">如果使用者是建立核准所在的聊天或頻道的一部分，就會獲授與要求的檢視者角色。</span><span class="sxs-lookup"><span data-stu-id="07c4e-204">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="07c4e-205">如果在建立核准時未提供他們該角色，他們即無法對要求採取動作。</span><span class="sxs-lookup"><span data-stu-id="07c4e-205">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>

## <a name="approvals-e-signature-integration"></a><span data-ttu-id="07c4e-206">核准電子簽章整合</span><span class="sxs-lookup"><span data-stu-id="07c4e-206">Approvals e-signature integration</span></span>

<span data-ttu-id="07c4e-207">從核准應用程式建立的電子郵件簽章核准會儲存在所選提供者的雲端環境中。</span><span class="sxs-lookup"><span data-stu-id="07c4e-207">E-signature approvals created from the Approvals app are stored in the selected provider's cloud environment.</span></span> <span data-ttu-id="07c4e-208">有關電子簽章協定的儲存空間詳細資訊，請觀看所選提供者的儲存檔。</span><span class="sxs-lookup"><span data-stu-id="07c4e-208">For further information about storage around the e-signature agreement, view the selected provider's storage documentation.</span></span>

<span data-ttu-id="07c4e-209">若要使用核准應用程式電子簽章功能，您需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="07c4e-209">To use the Approvals app e-signature feature, you need the following items:</span></span>

- <span data-ttu-id="07c4e-210">您選擇使用的特定電子簽章提供者授權。</span><span class="sxs-lookup"><span data-stu-id="07c4e-210">License for the specific e-signature provider you're choosing to use.</span></span> <span data-ttu-id="07c4e-211">若要取得貴組織的授權，您必須前往提供者的網站。</span><span class="sxs-lookup"><span data-stu-id="07c4e-211">In order to obtain a license for your organization, you'll need to go to the provider’s site.</span></span>

<span data-ttu-id="07c4e-212">針對核准電子簽章功能，協力廠商簽章合作夥伴預設會顯示Teams核准應用程式。</span><span class="sxs-lookup"><span data-stu-id="07c4e-212">For the Approvals e-signature functionality, third-party signature partners will appear in the Teams Approvals app by default.</span></span> <span data-ttu-id="07c4e-213">您可以在系統管理中心存取應用程式設定，以停用Teams簽名提供者。</span><span class="sxs-lookup"><span data-stu-id="07c4e-213">You can disable specific e-signature providers by accessing app settings in the Teams admin center.</span></span>

1. <span data-ttu-id="07c4e-214">在 Teams系統管理中心 **，選取管理** 應用程式下的核准 **應用程式**，然後選擇 **設定。**</span><span class="sxs-lookup"><span data-stu-id="07c4e-214">In the Teams admin center, under **Manage apps**, select the **Approvals app** and choose **Settings**.</span></span>

2. <span data-ttu-id="07c4e-215">每個電子簽章提供者旁邊都有一個開關，根據預設， (右) 位置。</span><span class="sxs-lookup"><span data-stu-id="07c4e-215">Each e-signature provider has a toggle next to it that is in the on position (right) by default.</span></span> <span data-ttu-id="07c4e-216">將切換開關向左滑動以停用特定的電子簽名提供者。</span><span class="sxs-lookup"><span data-stu-id="07c4e-216">Slide the toggle to the left to disable a specific e-signature provider.</span></span> <span data-ttu-id="07c4e-217">如果Teams系統管理員停用提供者，則建立核准時，使用者不會看到提供者。</span><span class="sxs-lookup"><span data-stu-id="07c4e-217">If a Teams admin disables a provider, end users won't see the provider when creating an approval.</span></span> <span data-ttu-id="07c4e-218">使用者也無法查看該提供者提出的任何電子簽章要求。</span><span class="sxs-lookup"><span data-stu-id="07c4e-218">End users will also be unable to view any e-signature requests that were made with that provider.</span></span>

<span data-ttu-id="07c4e-219">從核准應用程式建立之電子簽章核准會儲存在所選提供者的雲端。</span><span class="sxs-lookup"><span data-stu-id="07c4e-219">E-signature Approvals created from the Approvals App are stored in the selected provider’s cloud.</span></span> <span data-ttu-id="07c4e-220">因此，您必須前往提供者的網站，才能匯出任何電子簽章資料。</span><span class="sxs-lookup"><span data-stu-id="07c4e-220">You will therefore need to go to the provider's site in order to export any data about e-signatures.</span></span> <span data-ttu-id="07c4e-221">請參閱提供者關於匯出及保留這些協定的檔。</span><span class="sxs-lookup"><span data-stu-id="07c4e-221">Refer to the provider's documentation about export and retention of these agreements.</span></span>
