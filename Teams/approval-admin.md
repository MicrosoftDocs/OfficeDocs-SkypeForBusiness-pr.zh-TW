---
title: 在團隊中核准應用程式可用性
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 瞭解 Microsoft 團隊中的 [核准應用程式可用性]。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675171"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="f7180-103">團隊核准應用程式可用性</span><span class="sxs-lookup"><span data-stu-id="f7180-103">Teams Approvals app availability</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="f7180-104">[核准] 應用程式可作為個人 app 提供給所有 Microsoft 團隊使用者使用。</span><span class="sxs-lookup"><span data-stu-id="f7180-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="f7180-105">核准 app 提供一種簡單的方法，可將審核、合規性、責任及工作流程帶入小組中的結構化和非結構化核准。</span><span class="sxs-lookup"><span data-stu-id="f7180-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![顯示核准應用程式](media/approvals-selection.png)

<span data-ttu-id="f7180-107">使用者可以釘選 [核准] 應用程式，將其儲存至功能表列。</span><span class="sxs-lookup"><span data-stu-id="f7180-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![顯示具有 [pin] 選項的 [核准] 應用程式](media/approvalApp-pin.png)

<span data-ttu-id="f7180-109">從核准 app 建立的第一次核准將會觸發在預設的一般資料服務 (光碟) 環境中提供核准方案。</span><span class="sxs-lookup"><span data-stu-id="f7180-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="f7180-110">從核准 app 建立的核准將會儲存在預設的 CD 環境中。</span><span class="sxs-lookup"><span data-stu-id="f7180-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="f7180-111">本文將說明核准 app 需求與角色。</span><span class="sxs-lookup"><span data-stu-id="f7180-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="f7180-112">所需的許可權和授權</span><span class="sxs-lookup"><span data-stu-id="f7180-112">Required permissions and licenses</span></span>

<span data-ttu-id="f7180-113">若要使用 [核准] 應用程式，您需要下列專案的許可權：</span><span class="sxs-lookup"><span data-stu-id="f7180-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="f7180-114">建立 Microsoft CD 資料庫的許可權。</span><span class="sxs-lookup"><span data-stu-id="f7180-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="f7180-115">[Flow.microsoft.com](https://flow.microsoft.com/)上的帳戶</span><span class="sxs-lookup"><span data-stu-id="f7180-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="f7180-116">目標環境中的系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="f7180-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="f7180-117">[ [電源自動化](https://docs.microsoft.com/power-automate/get-started-approvals)]、[Office 365] 或 [Dynamics 365] 的授權。</span><span class="sxs-lookup"><span data-stu-id="f7180-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="f7180-118">使用光碟儲存檔案</span><span class="sxs-lookup"><span data-stu-id="f7180-118">Storage with CDS</span></span>

<span data-ttu-id="f7180-119">常見的資料模型 (CDM) 是在 CD 中的商務與分析應用程式所使用的共用資料語言。</span><span class="sxs-lookup"><span data-stu-id="f7180-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="f7180-120">它包含由 Microsoft 和合作夥伴所發佈的一組標準化、可擴展資料架構，可在應用程式和業務程式之間一致資料及其意義。</span><span class="sxs-lookup"><span data-stu-id="f7180-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="f7180-121">進一步瞭解 [Microsoft Power Platform 的一般資料模型](https://docs.microsoft.com/power-automate/get-started-approvals)。</span><span class="sxs-lookup"><span data-stu-id="f7180-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="f7180-122">深入瞭解 [核准工作流程](https://docs.microsoft.com/power-automate/modern-approvals)。</span><span class="sxs-lookup"><span data-stu-id="f7180-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="f7180-123">核准小組 app 許可權</span><span class="sxs-lookup"><span data-stu-id="f7180-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="f7180-124">[核准團隊] 應用程式可讓您存取下列功能：</span><span class="sxs-lookup"><span data-stu-id="f7180-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="f7180-125">接收您提供給它的訊息和資料。</span><span class="sxs-lookup"><span data-stu-id="f7180-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="f7180-126">傳送訊息和通知給您。</span><span class="sxs-lookup"><span data-stu-id="f7180-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="f7180-127">在沒有團隊提供的標頭的情況下，轉譯個人 app 與對話方塊。</span><span class="sxs-lookup"><span data-stu-id="f7180-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="f7180-128">存取您的個人檔案資訊，例如您的名稱、電子郵件地址、公司名稱及喜好語言。</span><span class="sxs-lookup"><span data-stu-id="f7180-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="f7180-129">接收小組成員在頻道中提供給它的訊息和資料。</span><span class="sxs-lookup"><span data-stu-id="f7180-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="f7180-130">傳送頻道中的訊息和通知。</span><span class="sxs-lookup"><span data-stu-id="f7180-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="f7180-131">存取您團隊的資訊：</span><span class="sxs-lookup"><span data-stu-id="f7180-131">Access your team's information:</span></span>
  - <span data-ttu-id="f7180-132">團隊名稱</span><span class="sxs-lookup"><span data-stu-id="f7180-132">team name</span></span>
  - <span data-ttu-id="f7180-133">頻道清單</span><span class="sxs-lookup"><span data-stu-id="f7180-133">channel list</span></span>
  - <span data-ttu-id="f7180-134">[名單] (小組成員的名稱和電子郵件地址) 。</span><span class="sxs-lookup"><span data-stu-id="f7180-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="f7180-135">使用小組的資訊來與他們取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="f7180-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="f7180-136">停用核准應用程式</span><span class="sxs-lookup"><span data-stu-id="f7180-136">Disable the Approvals app</span></span>

<span data-ttu-id="f7180-137">預設會提供 [核准] app。</span><span class="sxs-lookup"><span data-stu-id="f7180-137">The Approvals app is available by default.</span></span> <span data-ttu-id="f7180-138">您可以在 [團隊系統管理中心] 中停用應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7180-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="f7180-139">登入團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="f7180-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="f7180-140">展開 [ **團隊 app** ]，然後選取 [ **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="f7180-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="f7180-141">搜尋 [核准] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7180-141">Search for the Approvals app.</span></span>

![顯示 [系統管理中心導覽] 與 [團隊 App] > [管理應用程式] 醒目提示](media/manage-approval-apps.png)

  4. <span data-ttu-id="f7180-143">選取 [核准]。</span><span class="sxs-lookup"><span data-stu-id="f7180-143">Select Approvals.</span></span>

  5. <span data-ttu-id="f7180-144">選取 [切換] 來針對您的組織停用應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7180-144">Select the toggle to disable the app for your organization.</span></span>

![顯示核准 app 的詳細資料](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="f7180-146">保留原則</span><span class="sxs-lookup"><span data-stu-id="f7180-146">Retention policy</span></span>

<span data-ttu-id="f7180-147">從核准 App 建立的核准會儲存在預設的 CD 環境中，這項功能目前不支援備份。</span><span class="sxs-lookup"><span data-stu-id="f7180-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="f7180-148">深入瞭解如何 [備份及還原環境-Power Platform \| Microsoft 文檔](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)。</span><span class="sxs-lookup"><span data-stu-id="f7180-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="f7180-149">表明</span><span class="sxs-lookup"><span data-stu-id="f7180-149">Auditing</span></span>

<span data-ttu-id="f7180-150">核准 App 會在 Microsoft 365 安全性與合規性中心內記錄審核事件。</span><span class="sxs-lookup"><span data-stu-id="f7180-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="f7180-151">您可以查看審核記錄。</span><span class="sxs-lookup"><span data-stu-id="f7180-151">You can view the audit log.</span></span>

1. <span data-ttu-id="f7180-152">移至 M365 規範網站。</span><span class="sxs-lookup"><span data-stu-id="f7180-152">Go to the M365 Compliance Site.</span></span>

2. <span data-ttu-id="f7180-153">選取 [ **審計** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="f7180-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="f7180-154">搜尋 **Microsoft 團隊核准活動** 下的活動。</span><span class="sxs-lookup"><span data-stu-id="f7180-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="f7180-155">您可以搜尋下列活動：</span><span class="sxs-lookup"><span data-stu-id="f7180-155">You can search for the following activities:</span></span>

- <span data-ttu-id="f7180-156">建立新的核准要求</span><span class="sxs-lookup"><span data-stu-id="f7180-156">Create new approval request</span></span>

- <span data-ttu-id="f7180-157">查看核准要求詳細資料</span><span class="sxs-lookup"><span data-stu-id="f7180-157">View approval request details</span></span>

- <span data-ttu-id="f7180-158">核准核准要求</span><span class="sxs-lookup"><span data-stu-id="f7180-158">Approved approval request</span></span>

- <span data-ttu-id="f7180-159">拒絕核准要求</span><span class="sxs-lookup"><span data-stu-id="f7180-159">Rejected approval request</span></span>

- <span data-ttu-id="f7180-160">已取消核准要求</span><span class="sxs-lookup"><span data-stu-id="f7180-160">Canceled approval request</span></span>

- <span data-ttu-id="f7180-161">共用核准要求</span><span class="sxs-lookup"><span data-stu-id="f7180-161">Shared approval request</span></span>

- <span data-ttu-id="f7180-162">附加至核准要求的檔案</span><span class="sxs-lookup"><span data-stu-id="f7180-162">File attached to approval request</span></span>

- <span data-ttu-id="f7180-163">指派核准要求</span><span class="sxs-lookup"><span data-stu-id="f7180-163">Reassigned approval request</span></span>

- <span data-ttu-id="f7180-164">已將電子簽名新增至核准要求</span><span class="sxs-lookup"><span data-stu-id="f7180-164">Added e-signature to approval request</span></span>

<span data-ttu-id="f7180-165">若要存取流程中的更多審核核准，請在主要核准實體核准、核准要求和核准回應的預設環境中啟用和設定審核。</span><span class="sxs-lookup"><span data-stu-id="f7180-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="f7180-166">[建立]、[更新] 和 [刪除] 作業是核准記錄的可審核事件。</span><span class="sxs-lookup"><span data-stu-id="f7180-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="f7180-167">深入瞭解有關 [安全性與合規性的審核資料和使用者活動-Power Platform \| Microsoft](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)檔。</span><span class="sxs-lookup"><span data-stu-id="f7180-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="f7180-168">您可以在 [Microsoft 365 安全性與合規性中心](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)中進一步自訂審核。</span><span class="sxs-lookup"><span data-stu-id="f7180-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="f7180-169">若要使用預先設定的報告，請登入 Office 365 安全性與合規性。</span><span class="sxs-lookup"><span data-stu-id="f7180-169">To use the preconfigured reports, sign in to Office 365 Security and Compliance.</span></span>

2. <span data-ttu-id="f7180-170">選取 [ **搜尋 & 調查**]。</span><span class="sxs-lookup"><span data-stu-id="f7180-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="f7180-171">搜尋 [審計記錄]，然後選取 [ **Dynamics 365 活動** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f7180-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="f7180-172">深入瞭解 [Microsoft Dataverse 及模型驅動的 app 活動記錄-Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)。</span><span class="sxs-lookup"><span data-stu-id="f7180-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="f7180-173">安全性</span><span class="sxs-lookup"><span data-stu-id="f7180-173">Security</span></span>

<span data-ttu-id="f7180-174">在團隊核准應用程式中，使用者有權建立新核准並查看他們已傳送和接收的核准。</span><span class="sxs-lookup"><span data-stu-id="f7180-174">From the Teams Approval App, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="f7180-175">使用者無法存取其他人所建立的核准，除非他們是要求的回應者或查看者。</span><span class="sxs-lookup"><span data-stu-id="f7180-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="f7180-176">如果使用者是已建立核准的聊天或頻道的一部分，就會有該要求的查看者角色。</span><span class="sxs-lookup"><span data-stu-id="f7180-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="f7180-177">如果您在建立核准時沒有取得該角色，他們就不能在要求上採取動作。</span><span class="sxs-lookup"><span data-stu-id="f7180-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
