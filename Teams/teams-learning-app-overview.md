---
title: '安裝、管理及指派 Microsoft Viva Learning (私人預覽) '
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: 使用 Microsoft Viva Learning (私人預覽) 建立中央中樞，讓員工可以共用、指派及學習整個組織的內容庫。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b99cdcd49dc35a558d6217e28bf57bbb8563827
ms.sourcegitcommit: b56727299d7ea47e23807114a4f5881e289c0b6a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/17/2021
ms.locfileid: "51880333"
---
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a><span data-ttu-id="7d215-103">安裝、管理及指派 Microsoft Viva Learning (私人預覽) </span><span class="sxs-lookup"><span data-stu-id="7d215-103">Install, manage, and assign permissions for Microsoft Viva Learning (private preview)</span></span>

<span data-ttu-id="7d215-104">*本文包含 Microsoft Viva Learning 的初步內容，內容為私人預覽版。*</span><span class="sxs-lookup"><span data-stu-id="7d215-104">*This article contains preliminary content for Microsoft Viva Learning, which is in private preview.*</span></span>

<span data-ttu-id="7d215-105">Microsoft Viva Learning (私人預覽) 讓貴組織的小組和個人能夠自然地學習一天。</span><span class="sxs-lookup"><span data-stu-id="7d215-105">Microsoft Viva Learning (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="7d215-106">應用程式在 Teams 中建立中央中樞，讓員工可以共用、指派內容庫，以及向整個組織學習。</span><span class="sxs-lookup"><span data-stu-id="7d215-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span>

<span data-ttu-id="7d215-107">系統管理員會設定許可權，並允許 Viva Learning (私人預覽) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-107">Admins set permissions and allow learning content sources for Viva Learning (private preview).</span></span> <span data-ttu-id="7d215-108">學習內容可以包含 LinkedIn 學習、Microsoft Learning、Microsoft 365 訓練、貴組織儲存在 SharePoint Online 中的內容，以及 Viva Learning (私人預覽版) 支援的協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="7d215-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by Viva Learning (private preview).</span></span>

## <a name="admin-roles"></a><span data-ttu-id="7d215-109">系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="7d215-109">Admin roles</span></span>

<span data-ttu-id="7d215-110">若要設定 Viva Learning (預覽) ，您需要許可權為：</span><span class="sxs-lookup"><span data-stu-id="7d215-110">To set up Viva Learning (private preview), you'll need permissions as:</span></span>

- <span data-ttu-id="7d215-111">Microsoft Teams 系統管理員</span><span class="sxs-lookup"><span data-stu-id="7d215-111">Microsoft Teams admin</span></span>
- <span data-ttu-id="7d215-112">Microsoft 365 全域系統管理員或 SharePoint 系統管理員</span><span class="sxs-lookup"><span data-stu-id="7d215-112">Microsoft 365 global administrator or SharePoint administrator</span></span>
- <span data-ttu-id="7d215-113">知識系統管理員 - 這是 Microsoft 365 系統管理中心的一個新角色，可指派給組織中任何人。</span><span class="sxs-lookup"><span data-stu-id="7d215-113">Knowledge admin — This is a new role in the Microsoft 365 admin center that can be assigned to anyone in the organization.</span></span> <span data-ttu-id="7d215-114">此角色透過 Microsoft 365 系統管理中心管理組織的學習內容來源。</span><span class="sxs-lookup"><span data-stu-id="7d215-114">This role manages the organization’s learning content sources through the Microsoft 365 admin center.</span></span> 

> [!TIP]
> <span data-ttu-id="7d215-115">知識系統管理員應具備適中的技術，並擁有現有的 SharePoint 系統管理員認證，最好是熟悉組織教育、學習、訓練或員工經驗的人。</span><span class="sxs-lookup"><span data-stu-id="7d215-115">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="7d215-116">在 Teams 系統管理 (管理) 管理 Viva Learning</span><span class="sxs-lookup"><span data-stu-id="7d215-116">Manage Viva Learning (private preview) in the Teams admin center</span></span>

<span data-ttu-id="7d215-117">Teams 系統管理員會從 app store (Viva Learning) 個人預覽版，然後透過 Teams 系統管理中心來適用設定、管理和許可權原則。</span><span class="sxs-lookup"><span data-stu-id="7d215-117">The Teams admin installs Viva Learning (private preview) from the app store, and then applies setup, manage, and permission policies through the Teams admin center.</span></span>

### <a name="manage-settings-for-viva-learning-private-preview"></a><span data-ttu-id="7d215-118">管理 Viva Learning (私人預覽) </span><span class="sxs-lookup"><span data-stu-id="7d215-118">Manage settings for Viva Learning (private preview)</span></span>

<span data-ttu-id="7d215-119">您必須是 Teams 系統管理中心的系統管理員，才能執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="7d215-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="7d215-120">若要管理 Viva Learning 的設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7d215-120">To manage settings for Viva Learning, follow these steps:</span></span>

1. <span data-ttu-id="7d215-121">在 Teams 系統管理中心的左側流覽中，前往 **Teams 應用程式**  >  **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="7d215-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams 系統管理中心的左側導圖顯示 Teams 應用程式和管理應用程式區段](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="7d215-123">在管理 **應用程式頁面** 的搜尋方塊中，輸入搜尋Teams Learning App (預覽) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-123">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Teams 系統管理中心中的管理應用程式頁面，顯示搜尋方塊](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="7d215-125">在學習 **頁面上** ：</span><span class="sxs-lookup"><span data-stu-id="7d215-125">On the **Learning** page:</span></span>
   1. <span data-ttu-id="7d215-126">在 **狀態\*\*\*\*下，選取** 允許開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="7d215-126">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="7d215-127">在設定 **選項卡** 的 <App **設定** > 區段，前往 Microsoft 365 系統管理中心以設定學習內容來源。</span><span class="sxs-lookup"><span data-stu-id="7d215-127">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Teams 系統管理中心的學習頁面，顯示狀態與應用程式設定區段](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="7d215-129">管理 **應用程式** 設定之後，請前往許可權和設定政策，將許可權授予應有權存取應用程式的員工，作為貴組織參與私人預覽的一部分。</span><span class="sxs-lookup"><span data-stu-id="7d215-129">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="7d215-130">如果貴組織是 Teams TAP100 計畫的一部分，在 Ring 4.0 中，您可能需要執行下列操作，才能在 Ring 3.0 中啟用核准使用者，才能存取 Viva Learning (私人預覽) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access Viva Learning (private preview).</span></span>

<span data-ttu-id="7d215-131">在私人預覽中，Viva Learning (私人預覽) 于 Ring 3.0 中發行。</span><span class="sxs-lookup"><span data-stu-id="7d215-131">As part of private preview, Viva Learning (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="7d215-132">如果貴組織位於 Ring 4.0，您就不會在 App Store 中看到該應用程式。</span><span class="sxs-lookup"><span data-stu-id="7d215-132">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="7d215-133">若要測試應用程式，您需要建立自訂應用程式權限原則，將其設定為允許所有應用程式，並將它指派給 Ring 3.0 核准使用者。</span><span class="sxs-lookup"><span data-stu-id="7d215-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![TAP-AppsPermission-Plcy 頁面顯示允許選取所有應用程式](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="7d215-135">在 Microsoft 365 系統管理中心設定學習內容來源</span><span class="sxs-lookup"><span data-stu-id="7d215-135">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="7d215-136">Microsoft 365 系統管理中心的系統管理員可以自行或指派知識系統管理員角色給貴組織中選定的人員，以管理與 Viva Learning (私人預覽版) 相關的設定，並可以設定學習內容來源。</span><span class="sxs-lookup"><span data-stu-id="7d215-136">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="7d215-137">系統管理員會選取哪些其他學習內容來源 (例如 SharePoint 或支援的協力廠商內容提供者來源) 可供 Viva Learning (私人預覽版) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-137">The administrator selects which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (private preview).</span></span> <span data-ttu-id="7d215-138">系統管理員接著會設定這些來源，以確保內容可供搜尋和探索，且可供使用 Viva Learning (私人預覽版) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-138">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (private preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="7d215-139">使用者會以瀏覽器或內嵌檢視器LinkedIn非 Microsoft 和 Learning Pro 學習。</span><span class="sxs-lookup"><span data-stu-id="7d215-139">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="7d215-140">此已配置的學習受貴組織和協力廠商之間的個別授權、隱私權和服務條款所限制，而非 Viva Learning (私人預覽) 條款。</span><span class="sxs-lookup"><span data-stu-id="7d215-140">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (private preview) terms.</span></span> <span data-ttu-id="7d215-141">選取這類學習之前，請確認貴組織與使用者已達成一致。</span><span class="sxs-lookup"><span data-stu-id="7d215-141">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="7d215-142">指派知識系統管理員角色 [選擇性]</span><span class="sxs-lookup"><span data-stu-id="7d215-142">Assign the knowledge admin role [Optional]</span></span>

<span data-ttu-id="7d215-143">您必須是 Microsoft 365 全域系統管理員才能執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="7d215-143">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

<span data-ttu-id="7d215-144">若要指派 Viva Learning 的知識系統管理員，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7d215-144">To assign a knowledge admin for Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="7d215-145">在 Microsoft 365 系統管理中心的左側流覽中， **前往角色**。</span><span class="sxs-lookup"><span data-stu-id="7d215-145">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="7d215-146">在角色 **頁面上** 的 Azure **AD 選項卡** 上，選取 **知識系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="7d215-146">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="7d215-147">在知識 **系統管理員** 頁面上的 <指派的系統管理員> 區段，選取 新增 **，然後** 新增您為角色選擇的人。</span><span class="sxs-lookup"><span data-stu-id="7d215-147">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a><span data-ttu-id="7d215-148">設定 Viva 學習版學習內容來源的設定 (預覽) </span><span class="sxs-lookup"><span data-stu-id="7d215-148">Configure settings for the learning content sources for Viva Learning (private preview)</span></span>

<span data-ttu-id="7d215-149">您必須是 Microsoft 365 全域系統管理員或知識系統管理員，才能執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="7d215-149">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="7d215-150">若要在 Viva Learning 中設定學習內容來源的設定，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7d215-150">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="7d215-151">在 Microsoft 365 系統管理中心的左側流覽中，**前往設定**  >  **組織設定**。</span><span class="sxs-lookup"><span data-stu-id="7d215-151">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="7d215-152">在組織 **設定頁面上** 的 <服務> 選項卡上，選取學習 **應用程式 (預覽) 。**</span><span class="sxs-lookup"><span data-stu-id="7d215-152">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![Microsoft 365 系統管理中心的設定頁面，其中列出學習應用程式](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="7d215-154">在學習 **應用程式** (預覽) 面板上，選取您想要為組織設定的學習內容來源，然後 **選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="7d215-154">On the **Learning app (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![Microsoft 365 系統管理中心的學習面板，顯示內容來源選項](media/learning-sharepoint-configure2.png)

<span data-ttu-id="7d215-156">在存在的所有學習來源中，有些預設會啟用。</span><span class="sxs-lookup"><span data-stu-id="7d215-156">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="7d215-157">包括：</span><span class="sxs-lookup"><span data-stu-id="7d215-157">These include:</span></span>

- <span data-ttu-id="7d215-158">LinkedIn學習 (免費) </span><span class="sxs-lookup"><span data-stu-id="7d215-158">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="7d215-159">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="7d215-159">Microsoft Learn</span></span>
- <span data-ttu-id="7d215-160">Microsoft 365 訓練</span><span class="sxs-lookup"><span data-stu-id="7d215-160">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="7d215-161">如果貴組織有 LinkedIn學習標準版或專業版訂閱，內容存放庫會針對貴組織的員工解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="7d215-161">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="7d215-162">只有擁有許可權的員工才能使用整個內容存放庫。</span><span class="sxs-lookup"><span data-stu-id="7d215-162">Only those employees who have permission will be able to use the entire content repository.</span></span> <br><span data-ttu-id="7d215-163">其他來源可能需要啟用或手動進行配置。</span><span class="sxs-lookup"><span data-stu-id="7d215-163">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="7d215-164">非 Microsoft 的學習來源會分別在貴組織和協力廠商之間獲得授權。</span><span class="sxs-lookup"><span data-stu-id="7d215-164">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="7d215-165">您必須確認您為您和使用者註冊了學習課程。</span><span class="sxs-lookup"><span data-stu-id="7d215-165">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="7d215-166">若要啟用或停用學習內容來源，請選取來源旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7d215-166">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="7d215-167">如果已啟用來源，將會顯示一個核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7d215-167">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="7d215-168">將 SharePoint 設定為學習內容來源</span><span class="sxs-lookup"><span data-stu-id="7d215-168">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="7d215-169">您可以將 SharePoint 設定為學習內容來源，讓貴組織自己的內容可在 Viva Learning (預覽) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-169">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (private preview).</span></span>

### <a name="overview"></a><span data-ttu-id="7d215-170">概觀</span><span class="sxs-lookup"><span data-stu-id="7d215-170">Overview</span></span>

<span data-ttu-id="7d215-171">知識系統管理員 (或全域系統管理員) 以結構化 SharePoint 清單的形式，提供網站 URL，讓學習服務可以在這裡建立空白的集中式位置 ，即學習應用程式內容存放庫。</span><span class="sxs-lookup"><span data-stu-id="7d215-171">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="7d215-172">貴組織可以使用此清單來提供包含學習內容的跨公司 SharePoint 資料夾連結。</span><span class="sxs-lookup"><span data-stu-id="7d215-172">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="7d215-173">系統管理員負責收集及管理資料夾的 URL 清單。</span><span class="sxs-lookup"><span data-stu-id="7d215-173">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="7d215-174">這些資料夾應只包含可在 Viva Learning 或私人預覽 (中) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-174">These folders should only include content that can be made available in Viva Learning (private preview).</span></span>

<span data-ttu-id="7d215-175">Viva Learning (私人預覽) 支援下列檔案類型：</span><span class="sxs-lookup"><span data-stu-id="7d215-175">Viva Learning (private preview) supports the following document types:</span></span>

- <span data-ttu-id="7d215-176">Word、PowerPoint、Excel、PDF</span><span class="sxs-lookup"><span data-stu-id="7d215-176">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="7d215-177">音訊 (.m4a) </span><span class="sxs-lookup"><span data-stu-id="7d215-177">Audio (.m4a)</span></span>
- <span data-ttu-id="7d215-178">影片 (.mov、.mp4、.avi) </span><span class="sxs-lookup"><span data-stu-id="7d215-178">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="7d215-179">詳細資訊，請參閱 [SharePoint Online 檔](https://docs.microsoft.com/sharepoint/introductionlink)。</span><span class="sxs-lookup"><span data-stu-id="7d215-179">For more information, see the [SharePoint Online documentation](https://docs.microsoft.com/sharepoint/introductionlink).</span></span> 

### <a name="permissions"></a><span data-ttu-id="7d215-180">權限</span><span class="sxs-lookup"><span data-stu-id="7d215-180">Permissions</span></span>

<span data-ttu-id="7d215-181">文件庫資料夾 URL 可以從組織的任何 SharePoint 網站收集。</span><span class="sxs-lookup"><span data-stu-id="7d215-181">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="7d215-182">Viva Learning (私人預覽) 遵循所有現有的內容許可權。</span><span class="sxs-lookup"><span data-stu-id="7d215-182">Viva Learning (private preview) follows all existing content permissions.</span></span> <span data-ttu-id="7d215-183">因此，只有使用者有權存取的內容，才能在 Viva Learning 中搜尋 (私人預覽) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-183">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (private preview).</span></span> <span data-ttu-id="7d215-184">這些資料夾中的任何內容都可以搜尋，但只能使用個別員工有權使用的內容。</span><span class="sxs-lookup"><span data-stu-id="7d215-184">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="7d215-185">目前不支援從貴組織存放庫刪除內容。</span><span class="sxs-lookup"><span data-stu-id="7d215-185">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="7d215-186">若要移除不小心浮出的內容，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7d215-186">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="7d215-187">若要限制文件庫的存取權，請選取 **顯示動作** 選項，然後選取管理 **存取** 權。</span><span class="sxs-lookup"><span data-stu-id="7d215-187">To restrict access on the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![SharePoint 中的文件庫頁面顯示顯示動作選項，並設定了管理存取權。](media/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="7d215-189">刪除文件庫中的原始檔案。</span><span class="sxs-lookup"><span data-stu-id="7d215-189">Delete the original document within the document library.</span></span>

<span data-ttu-id="7d215-190">詳細資訊，請參閱 SharePoint 新式體驗中的 [共用和許可權](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)。</span><span class="sxs-lookup"><span data-stu-id="7d215-190">For more information, see [Sharing and permissions in the SharePoint modern experience](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span> 

### <a name="learning-service"></a><span data-ttu-id="7d215-191">學習服務</span><span class="sxs-lookup"><span data-stu-id="7d215-191">Learning Service</span></span>

<span data-ttu-id="7d215-192">學習服務會使用所提供的資料夾 URL，從儲存在這些資料夾中的所有內容取得中繼資料。</span><span class="sxs-lookup"><span data-stu-id="7d215-192">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="7d215-193">在集中式存放庫中提供資料夾 URL 的 24 小時內，員工可以在 Viva Learning (私人預覽版) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-193">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (private preview).</span></span> <span data-ttu-id="7d215-194">內容的所有變更 ，包括更新的中繼資料和許可權，也會在 24 小時內于學習服務中適用。</span><span class="sxs-lookup"><span data-stu-id="7d215-194">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="7d215-195">將 SharePoint 設定為來源</span><span class="sxs-lookup"><span data-stu-id="7d215-195">Configure SharePoint as a source</span></span>

<span data-ttu-id="7d215-196">您必須是 Microsoft 365 全域系統管理員、SharePoint 系統管理員或知識系統管理員，才能執行這些工作。</span><span class="sxs-lookup"><span data-stu-id="7d215-196">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="7d215-197">若要將 SharePoint 設定為 Viva Learning 中的學習內容來源 (私人預覽) ，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7d215-197">To configure SharePoint as a learning content sources in for Viva Learning (private preview), follow these steps:</span></span>

1.  <span data-ttu-id="7d215-198">在 Microsoft 365 系統管理中心的左側流覽中，**前往設定**  >  **組織設定**。</span><span class="sxs-lookup"><span data-stu-id="7d215-198">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="7d215-199">在組織 **設定頁面上** 的 <服務> 選項卡上，選取學習 **應用程式 (預覽) 。**</span><span class="sxs-lookup"><span data-stu-id="7d215-199">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![Microsoft 365 系統管理中心的設定頁面，其中列出 Viva Learning。](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="7d215-201">在學習 **應用程式** (預覽) 面板的 **SharePoint** 下，提供 SharePoint 網站的網站 URL，讓 Viva Learning 建立集中式存放庫。</span><span class="sxs-lookup"><span data-stu-id="7d215-201">On the **Learning app (Preview)** panel, under **SharePoint**, provide the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![Microsoft 365 系統管理中心的學習面板顯示已選取 SharePoint。](media/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="7d215-203">SharePoint 清單會在提供的 SharePoint 網站內自動建立。</span><span class="sxs-lookup"><span data-stu-id="7d215-203">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![SharePoint 網站中新建立 SharePoint 清單。](media/learning-sharepoint-configure3.png)

     <span data-ttu-id="7d215-205">在 SharePoint 網站的左側流覽中，選取 **網站內容**  >  **學習應用程式內容存放庫**。</span><span class="sxs-lookup"><span data-stu-id="7d215-205">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![顯示網站內容流覽和學習應用程式內容存放區段的 SharePoint 清單。](media/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="7d215-207">在學習 **應用程式內容存放庫頁面上** ，使用 URL 填入 SharePoint 清單至學習內容資料夾。</span><span class="sxs-lookup"><span data-stu-id="7d215-207">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="7d215-208">選取 **新增** 以查看 **新增專案** 面板。</span><span class="sxs-lookup"><span data-stu-id="7d215-208">Select **New** to view the **New item** panel.</span></span> 

       ![SharePoint 中的學習內容存放庫頁面顯示新增選項。](media/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="7d215-210">在新增 **專案面板** 的標題欄位中，新增您所選擇的目錄名稱。</span><span class="sxs-lookup"><span data-stu-id="7d215-210">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="7d215-211">在資料夾 **URL** 欄位中，將 URL 新增到學習內容資料夾。</span><span class="sxs-lookup"><span data-stu-id="7d215-211">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="7d215-212">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="7d215-212">Select **Save**.</span></span>

       ![SharePoint 中的新增專案面板顯示標題和資料夾 URL 欄位。](media/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="7d215-214">學習 **應用程式內容存放庫頁面** 會以新的學習內容更新。</span><span class="sxs-lookup"><span data-stu-id="7d215-214">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![SharePoint 中的學習內容存放庫頁面顯示更新的資訊。](media/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="7d215-216">若要允許更多人存取學習應用程式內容存放庫，Viva Learning (私人預覽) 介面即將提供清單連結，使用者可以在這裡要求存取，並最終協助填入清單。</span><span class="sxs-lookup"><span data-stu-id="7d215-216">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (private preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="7d215-217">網站擁有者和全域系統管理員必須授予清單的存取權。</span><span class="sxs-lookup"><span data-stu-id="7d215-217">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="7d215-218">Access 僅適用于清單，不適用於儲存清單的網站。</span><span class="sxs-lookup"><span data-stu-id="7d215-218">Access is specific to the list only and does not apply to the site where the list is stored.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="7d215-219">資料夾 URL 文件庫的策展</span><span class="sxs-lookup"><span data-stu-id="7d215-219">Folder URL document library curation</span></span>

<span data-ttu-id="7d215-220">預設中繼資料 (例如修改日期、建立者、檔案名稱、內容類型及組織名稱) ，Microsoft Graph API 會自動拉入 Viva Learning (私人預覽) 。</span><span class="sxs-lookup"><span data-stu-id="7d215-220">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (private preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="7d215-221">若要改善內容的整體探索和搜尋相關性，建議您新增描述 **欄** 。</span><span class="sxs-lookup"><span data-stu-id="7d215-221">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="7d215-222">若要 **新增描述列** 至文件庫頁面，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7d215-222">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="7d215-223">在檔 **頁面上** ，選取 新增 **欄**。</span><span class="sxs-lookup"><span data-stu-id="7d215-223">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="7d215-224">選取顯示 **動作** 選項，然後選取 **單行文字**。</span><span class="sxs-lookup"><span data-stu-id="7d215-224">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![SharePoint 中的檔頁面，顯示以單行文字為標號的顯示動作選項。](media/learning-sharepoint-curation1.png)

3. <span data-ttu-id="7d215-226">在建立 **欄面板的**<名稱>欄位中，新增欄的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="7d215-226">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="7d215-227">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="7d215-227">Select **Save**.</span></span>

     ![在 SharePoint 中建立欄面板，顯示名稱和其他欄位。](media/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="7d215-229">在檔 **頁面上** 的 <描述 **>** 欄中，新增每個專案的自訂描述。</span><span class="sxs-lookup"><span data-stu-id="7d215-229">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="7d215-230">如果沒有提供描述，Viva Learning (私人預覽) 會提供一則預設訊息，將內容強調為來自您自己的 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="7d215-230">If no description is supplied, Viva Learning (private preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![SharePoint 中的檔頁面，顯示描述列中的描述。](media/learning-sharepoint-curation3.png)
 
