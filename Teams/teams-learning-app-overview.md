---
title: '在 (私人預覽版] 中安裝、管理及指派小組學習 app 的許可權) '
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
description: 使用 Microsoft 團隊學習 app 來建立中央中樞，以便在員工可以在組織內共用、分派及學習內容庫。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703409"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="36a2c-103">在 (私人預覽版] 中安裝、管理及指派小組學習 app 的許可權) </span><span class="sxs-lookup"><span data-stu-id="36a2c-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="36a2c-104">*本文包含適用于 [私人預覽] 中的 [團隊學習] app 的基本內容。*</span><span class="sxs-lookup"><span data-stu-id="36a2c-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="36a2c-105">Microsoft 團隊學習 app (私人預覽版) 可讓貴組織中的小組和個人學會自己的日常參與。</span><span class="sxs-lookup"><span data-stu-id="36a2c-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="36a2c-106">應用程式會在團隊中建立一個中央中樞，員工可以在其中在整個組織中共用、分派及學習內容庫。</span><span class="sxs-lookup"><span data-stu-id="36a2c-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="36a2c-107">系統管理員設定許可權，並允許學習應用程式的內容來源。</span><span class="sxs-lookup"><span data-stu-id="36a2c-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="36a2c-108">學習內容可以包括 LinkedIn Learning、Microsoft 學會、Microsoft 365 訓練、貴組織本身的內容儲存在 SharePoint online 中，以及應用程式支援的協力廠商提供者。</span><span class="sxs-lookup"><span data-stu-id="36a2c-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="36a2c-109">若要將 [團隊學習] app 設定 (私人預覽]) ，您必須參與下列作業：</span><span class="sxs-lookup"><span data-stu-id="36a2c-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="36a2c-110">團隊系統管理中心管理員</span><span class="sxs-lookup"><span data-stu-id="36a2c-110">Teams admin center admin</span></span>
-   <span data-ttu-id="36a2c-111">Microsoft 365 系統管理中心管理員 (，也就是全域系統管理員) </span><span class="sxs-lookup"><span data-stu-id="36a2c-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="36a2c-112">知識管理員 (Microsoft 365 系統管理中心的新角色，全域系統管理員 (也稱為 IT 管理員或 Microsoft 365 管理員) 可以指派給組織中的任何人。</span><span class="sxs-lookup"><span data-stu-id="36a2c-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="36a2c-113">這個角色透過 Microsoft 365 系統管理中心管理組織的學習內容來源。 ) </span><span class="sxs-lookup"><span data-stu-id="36a2c-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="36a2c-114">在團隊系統管理中心中管理團隊學習 app (私人預覽) </span><span class="sxs-lookup"><span data-stu-id="36a2c-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="36a2c-115">[團隊管理員] 會將團隊學習 app 從應用程式商店 (私人預覽) ，並透過團隊系統管理中心套用 app 設定、管理及許可權原則。</span><span class="sxs-lookup"><span data-stu-id="36a2c-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="36a2c-116">在私人預覽版中管理團隊學習 app () </span><span class="sxs-lookup"><span data-stu-id="36a2c-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="36a2c-117">若要管理 app 的設定，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="36a2c-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="36a2c-118">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![小組系統管理中心的左側導覽，顯示 [小組 app] 和 [管理 app] 區段](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="36a2c-120">在 [ **管理應用程式** ] 頁面上的 [搜尋] 方塊中，輸入「 *學習* 」以搜尋小組學習 app (私人預覽]) 。</span><span class="sxs-lookup"><span data-stu-id="36a2c-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![[團隊管理中心] 中顯示 [搜尋] 方塊的 [管理應用程式] 頁面](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="36a2c-122">在 [ **學習** ] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="36a2c-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="36a2c-123">在 [ **狀態**] 底下，選取 [ **允許** ] 以開啟 app。</span><span class="sxs-lookup"><span data-stu-id="36a2c-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="36a2c-124">在 [ **設定** ] 索引標籤的 [ **應用程式設定** ] 區段中，移至 Microsoft 365 系統管理中心來設定學習內容來源。</span><span class="sxs-lookup"><span data-stu-id="36a2c-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![[團隊管理中心] 中的 [學習] 頁面，顯示 [狀態及應用程式設定] 區段](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="36a2c-126">**管理應用程式** 設定之後，請移至 [**許可權] 和 [設定策略**]，授權給應該有權存取應用程式的員工，該許可權必須是貴組織參與私人預覽版的一部分。</span><span class="sxs-lookup"><span data-stu-id="36a2c-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="36a2c-127">如果您的組織是作為 [團隊 TAP100] 計畫的一部分來撥打4.0，則您可能需要執行下列動作，才能在撥打3.0 中的核准使用者， (私人預覽版) 存取團隊學習 app。</span><span class="sxs-lookup"><span data-stu-id="36a2c-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="36a2c-128">在私人預覽版中，小組學習 app (私人預覽) 是在 Ring 3.0 中發行。</span><span class="sxs-lookup"><span data-stu-id="36a2c-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="36a2c-129">如果您的組織是 Ring 4.0，就不會在 app store 中看到該應用程式。</span><span class="sxs-lookup"><span data-stu-id="36a2c-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="36a2c-130">若要測試應用程式，您需要建立自訂應用程式許可權原則，將它設定為 **允許所有** 的 app，並將它指派給響鈴3.0 核准的使用者。</span><span class="sxs-lookup"><span data-stu-id="36a2c-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![AppsPermission-Plcy 頁面，顯示 [允許所有 app 已選取]](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="36a2c-132">在 Microsoft 365 系統管理中心設定學習內容來源</span><span class="sxs-lookup"><span data-stu-id="36a2c-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="36a2c-133">Microsoft 365 系統管理中心的管理員（無論是自行或指派知識管理員角色給貴組織中的選取的人員），都可以管理與團隊學習 app 相關的設定 (私人預覽) ，而且可以設定學習內容來源。</span><span class="sxs-lookup"><span data-stu-id="36a2c-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="36a2c-134">知識系統管理員應該是適度的技術，且擁有現有的 SharePoint 系統管理員認證，最好是在組織的教育、學習、訓練或員工經驗中 versed 的人員。</span><span class="sxs-lookup"><span data-stu-id="36a2c-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="36a2c-135">系統管理員會選取將在 app 中提供哪些學習內容來源 (例如 LinkedIn Learning 或 SharePoint) 。</span><span class="sxs-lookup"><span data-stu-id="36a2c-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="36a2c-136">系統管理員接著會設定這些來源，以確保內容可供搜尋和探索使用，且可供使用 app 的員工流覽。</span><span class="sxs-lookup"><span data-stu-id="36a2c-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="36a2c-137">指派知識管理員角色 [選用]</span><span class="sxs-lookup"><span data-stu-id="36a2c-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="36a2c-138">這些步驟將由 Microsoft 365 系統管理中心的管理員執行。</span><span class="sxs-lookup"><span data-stu-id="36a2c-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="36a2c-139">在 Microsoft 365 系統管理中心的左導覽中，前往 [ **角色**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="36a2c-140">在 [ **角色** ] 頁面上的 [ **Azure AD** ] 索引標籤上，選取 [ **知識庫系統管理**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="36a2c-141">在 [ **知識庫系統管理** ] 頁面上的 [ **指派的管理員** ] 區段中，選取 [ **新增**]，然後新增您針對角色所選擇的人員。</span><span class="sxs-lookup"><span data-stu-id="36a2c-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="36a2c-142">設定應用程式學習內容來源的設定</span><span class="sxs-lookup"><span data-stu-id="36a2c-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="36a2c-143">這些步驟將由 Microsoft 365 管理員或知識系統管理員執行。</span><span class="sxs-lookup"><span data-stu-id="36a2c-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="36a2c-144">在 Microsoft 365 系統管理中心的左導覽中，移至 [**設定**  >  **組織設定**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="36a2c-145">在 [ **設定** ] 頁面的 [ **服務 & [增益集** ] 索引標籤上，選取 [ **學習應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Microsoft 365 系統管理中心的 [設定] 頁面，顯示已列出的學習應用程式](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="36a2c-147">在 [ **學習 app** ] 面板上，選取您想要為組織設定的學習內容來源，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Microsoft 365 系統管理中心的學習應用程式面板，其中顯示 [內容來源] 選項](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="36a2c-149">在現有的所有學習來源中，一些預設會啟用。</span><span class="sxs-lookup"><span data-stu-id="36a2c-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="36a2c-150">這些包括：</span><span class="sxs-lookup"><span data-stu-id="36a2c-150">These include:</span></span>

- <span data-ttu-id="36a2c-151">LinkedIn Learning (免費內容) </span><span class="sxs-lookup"><span data-stu-id="36a2c-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="36a2c-152">Microsoft 學習</span><span class="sxs-lookup"><span data-stu-id="36a2c-152">Microsoft Learn</span></span>
- <span data-ttu-id="36a2c-153">Microsoft 365 訓練</span><span class="sxs-lookup"><span data-stu-id="36a2c-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="36a2c-154">如果您的組織有 LinkedIn 學習標準版或 Pro 訂閱，將會針對貴組織中的員工解除鎖定內容儲存庫。</span><span class="sxs-lookup"><span data-stu-id="36a2c-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="36a2c-155">只有擁有許可權的員工才能使用整個內容儲存庫。</span><span class="sxs-lookup"><span data-stu-id="36a2c-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="36a2c-156">其他來源可能需要手動啟用或設定。</span><span class="sxs-lookup"><span data-stu-id="36a2c-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="36a2c-157">不是來自 Microsoft 的學習來源，會在您的組織和協力廠商之間另行提供授權。</span><span class="sxs-lookup"><span data-stu-id="36a2c-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="36a2c-158">您必須確認您已為自己和您的使用者註冊自己的學習。</span><span class="sxs-lookup"><span data-stu-id="36a2c-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="36a2c-159">若要啟用或停用學習內容來源，請選取來源旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="36a2c-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="36a2c-160">如果已啟用來源，則會顯示核取記號。</span><span class="sxs-lookup"><span data-stu-id="36a2c-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="36a2c-161">將 SharePoint 設定為學習內容來源</span><span class="sxs-lookup"><span data-stu-id="36a2c-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="36a2c-162">您可以在 Microsoft 365 系統管理中心的 [私人預覽]) ，將 SharePoint 設定為 [團隊學習] (app 的學習內容來源。</span><span class="sxs-lookup"><span data-stu-id="36a2c-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="36a2c-163">概觀</span><span class="sxs-lookup"><span data-stu-id="36a2c-163">Overview</span></span>

<span data-ttu-id="36a2c-164">知識管理員提供網站 URL，讓教學服務能在結構化 SharePoint 清單的表單中建立空白的集中式學習內容儲存庫。</span><span class="sxs-lookup"><span data-stu-id="36a2c-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="36a2c-165">貴組織可以使用此清單來容納包含學習內容的跨公司 SharePoint 資料夾的連結。</span><span class="sxs-lookup"><span data-stu-id="36a2c-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="36a2c-166">系統管理員負責收集及策劃資料夾的 Url 清單。</span><span class="sxs-lookup"><span data-stu-id="36a2c-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="36a2c-167">這些資料夾應該只包含可在團隊學習 app 中提供的內容 (私人預覽版) 。</span><span class="sxs-lookup"><span data-stu-id="36a2c-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="36a2c-168">權限</span><span class="sxs-lookup"><span data-stu-id="36a2c-168">Permissions</span></span>

<span data-ttu-id="36a2c-169">您可以從組織中的任何 SharePoint 網站收集資料夾 Url。</span><span class="sxs-lookup"><span data-stu-id="36a2c-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="36a2c-170">這些資料夾中的任何內容都可供搜尋，但只有個別員工擁有許可權的內容才可以使用。</span><span class="sxs-lookup"><span data-stu-id="36a2c-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="36a2c-171">學習服務</span><span class="sxs-lookup"><span data-stu-id="36a2c-171">Learning Service</span></span>

<span data-ttu-id="36a2c-172">學習服務會使用所提供的資料夾 Url，從儲存在這些資料夾中的所有內容取得中繼資料。</span><span class="sxs-lookup"><span data-stu-id="36a2c-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="36a2c-173">在24小時內提供集中式知識庫中的資料夾 URL 之後，員工就可以在 app 中搜尋並使用公司的內容。</span><span class="sxs-lookup"><span data-stu-id="36a2c-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="36a2c-174">此時不支援從知識庫刪除內容。</span><span class="sxs-lookup"><span data-stu-id="36a2c-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="36a2c-175">無意中出現的內容，只能透過在 Microsoft 365 系統管理中心提供新的 SharePoint 網站 URL 來移除。</span><span class="sxs-lookup"><span data-stu-id="36a2c-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="36a2c-176">將 SharePoint 設定為來源</span><span class="sxs-lookup"><span data-stu-id="36a2c-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="36a2c-177">這些步驟將由 Microsoft 365 管理員或知識系統管理員執行。</span><span class="sxs-lookup"><span data-stu-id="36a2c-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="36a2c-178">在 Microsoft 365 系統管理中心的左導覽中，移至 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="36a2c-179">在 [ **設定** ] 頁面的 [ **服務 & [增益集** ] 索引標籤上，選取 [ **學習應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Microsoft 365 系統管理中心的 [設定] 頁面，顯示已列出的學習應用程式](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="36a2c-181">在 [ **學習 app** ] 面板上，提供您想要 app 建立集中式知識庫之 SharePoint 網站的網站 URL。</span><span class="sxs-lookup"><span data-stu-id="36a2c-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![顯示已選取 SharePoint 的 Microsoft 365 系統管理中心中的 [學習應用程式] 面板](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="36a2c-183">SharePoint 清單是在所提供組織的 SharePoint 網站中自動建立。</span><span class="sxs-lookup"><span data-stu-id="36a2c-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="36a2c-184">在 SharePoint 網站的左側導覽中，選取 [ **學習 App 內容儲存庫**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![SharePoint 中的左側導覽，顯示學習應用程式內容庫區段](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="36a2c-186">在 [ **學習 App 內容儲存庫** ] 頁面上，使用「學習內容」資料夾的 Url 填入 SharePoint 清單。</span><span class="sxs-lookup"><span data-stu-id="36a2c-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="36a2c-187">選取 [ **新增** ]，查看 [ **新增專案** ] 面板。</span><span class="sxs-lookup"><span data-stu-id="36a2c-187">Select **New** to view the **New item** panel.</span></span> 

   ![SharePoint 中的 [學習應用程式內容庫] 頁面，其中顯示 [新增] 選項](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="36a2c-189">在 [ **新增專案** ] 面板的 [ **標題** ] 欄位中，新增您選擇的目錄名稱。</span><span class="sxs-lookup"><span data-stu-id="36a2c-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="36a2c-190">在 [ **資料夾 URL** ] 欄位中，將 URL 新增至 [學習內容] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="36a2c-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="36a2c-191">選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="36a2c-191">Select **Save**.</span></span>

   ![SharePoint 中的 [新增專案] 面板，顯示 [標題] 和 [資料夾 URL] 欄位](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="36a2c-193">學習 App 內容儲存庫頁面會以新的學習內容更新。</span><span class="sxs-lookup"><span data-stu-id="36a2c-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![SharePoint 中的 [學習應用程式內容庫] 頁面，其中顯示更新的資訊](media/learning-app-content-repository-populated.png)


 


