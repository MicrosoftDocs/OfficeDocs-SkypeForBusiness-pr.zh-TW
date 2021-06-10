---
title: 在系統管理中心中查看應用程式許可權並Microsoft Teams系統管理員同意
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在系統管理中心的管理應用程式頁面上，查看應用程式要求的許可權，並授予Microsoft Teams同意。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2833a548ccf66b327d9feb71155f1ed33a671f1c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094655"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a32b0-103">在系統管理中心中查看應用程式許可權並Microsoft Teams系統管理員同意</span><span class="sxs-lookup"><span data-stu-id="a32b0-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

<span data-ttu-id="a32b0-104">系統[管理中心](manage-apps.md)中的Microsoft Teams頁面，就是您查看及管理組織Teams應用程式的地方。</span><span class="sxs-lookup"><span data-stu-id="a32b0-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="a32b0-105">例如，您可以查看應用程式的組織層級狀態和屬性、核准或上傳新的自訂應用程式至組織的 App Store、封鎖或允許組織層級的應用程式，以及管理整個組織的 App 設定。</span><span class="sxs-lookup"><span data-stu-id="a32b0-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="a32b0-106">在這裡，您也可以將全組織系統管理員同意授權給要求存取資料的許可權，並針對應用程式的許可權來 (資源) 同意。</span><span class="sxs-lookup"><span data-stu-id="a32b0-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="a32b0-107">將全組織系統管理員同意授予應用程式</span><span class="sxs-lookup"><span data-stu-id="a32b0-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="a32b0-108">如果您是全域系統管理員，您可以為代表貴組織中所有使用者要求許可權的應用程式進行審查並授予同意。</span><span class="sxs-lookup"><span data-stu-id="a32b0-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="a32b0-109">如此一來，使用者就不需要在啟動 App 時，查看並接受應用程式要求的許可權。</span><span class="sxs-lookup"><span data-stu-id="a32b0-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="a32b0-110">此外，根據 Azure AD [](/azure/active-directory/manage-apps/configure-user-consent) Azure Active Directory (中的使用者同意) ，某些使用者可能無法將同意授予存取公司資料的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a32b0-110">Additionally, depending on the user's [consent settings](/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="a32b0-111">應用程式要求的許可權範例包括讀取儲存在小組的資訊、讀取使用者的設定檔，以及代表使用者傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a32b0-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="a32b0-112">若要深入瞭解，請參閱端點中的許可權[Microsoft 身分識別平臺同意](/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="a32b0-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="a32b0-113">許可權 **欄** 會指出應用程式是否有需要同意的許可權。</span><span class="sxs-lookup"><span data-stu-id="a32b0-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="a32b0-114">針對在 Azure  AD 中註冊並擁有需要同意的許可權的每個應用程式，您會看到一個 View 詳細資料連結。</span><span class="sxs-lookup"><span data-stu-id="a32b0-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="a32b0-115">請記住，這僅適用于自訂和協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="a32b0-115">Keep in mind that this applies only to custom and third-party apps.</span></span> <span data-ttu-id="a32b0-116">您不會看到此連結，或需要針對 Microsoft 發佈的 App 授予系統管理員同意。</span><span class="sxs-lookup"><span data-stu-id="a32b0-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="管理應用程式頁面上的許可權欄螢幕擷取畫面":::

<span data-ttu-id="a32b0-118">若要將應用程式授予全組織同意，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a32b0-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="a32b0-119">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="a32b0-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="a32b0-120">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a32b0-120">Do one of the following:</span></span>
    - <span data-ttu-id="a32b0-121">搜尋您想要的應用程式，按一下應用程式名稱以前往應用程式詳細資料頁面，然後選取 [ **許可權> 索引** 鍵。</span><span class="sxs-lookup"><span data-stu-id="a32b0-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="a32b0-122">以遞 **減** 順序排序許可權欄以尋找應用程式，然後選取 View **Details**。</span><span class="sxs-lookup"><span data-stu-id="a32b0-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="a32b0-123">這麼做會帶您到 **應用程式詳細** 資料頁面的許可權選項卡。</span><span class="sxs-lookup"><span data-stu-id="a32b0-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="a32b0-124">在 **全組織許可權下**，選取審查 **許可權和同意**。</span><span class="sxs-lookup"><span data-stu-id="a32b0-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="應用程式之許可權之全組織許可權的螢幕擷取畫面":::

    <span data-ttu-id="a32b0-126">您必須是全域系統管理員才能這麼做。</span><span class="sxs-lookup"><span data-stu-id="a32b0-126">You must be a global admin to do this.</span></span> <span data-ttu-id="a32b0-127">服務系統管理員無法Teams這個選項。</span><span class="sxs-lookup"><span data-stu-id="a32b0-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="a32b0-128">在許可權 **選項卡** 上，查看應用程式要求的許可權。</span><span class="sxs-lookup"><span data-stu-id="a32b0-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="應用程式要求的許可權螢幕擷取畫面":::

    > [!IMPORTANT]
    > <span data-ttu-id="a32b0-130">將整個組織同意授予應用程式，可讓應用程式存取貴組織的資料。</span><span class="sxs-lookup"><span data-stu-id="a32b0-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="a32b0-131">在您授予同意之前，請仔細查看應用程式要求的許可權。</span><span class="sxs-lookup"><span data-stu-id="a32b0-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="a32b0-132">如果您同意應用程式要求的許可權，請按一下 **[接受** 以授予同意。</span><span class="sxs-lookup"><span data-stu-id="a32b0-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="a32b0-133">頁面頂端暫時會出現橫幅，讓您知道已針對應用程式授予要求的許可權。</span><span class="sxs-lookup"><span data-stu-id="a32b0-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="a32b0-134">應用程式現在可存取貴組織中所有使用者的指定資源，系統不會提示其他人檢查許可權。</span><span class="sxs-lookup"><span data-stu-id="a32b0-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="a32b0-135">接受許可權之後，您將在應用程式詳細資料頁面上的全組織許可權下看到一則訊息，讓您知道已授予同意。</span><span class="sxs-lookup"><span data-stu-id="a32b0-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="a32b0-136">若要查看應用程式許可權的詳細資訊，請按一下 [Azure Active Directory **連結，** 以前往 Azure AD 入口網站中的應用程式頁面。</span><span class="sxs-lookup"><span data-stu-id="a32b0-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="已同意時顯示之訊息的螢幕擷取畫面":::

<span data-ttu-id="a32b0-138">如果貴組織中允許使用者授予同意，且有一或多個使用者已授予特定應用程式同意，您也會看到相同的訊息，讓您知道已授予同意，以及 Azure AD 入口網站中應用程式的 Azure Active Directory 連結。</span><span class="sxs-lookup"><span data-stu-id="a32b0-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="a32b0-139">雖然 Teams服務系統管理員無法使用審查許可權和同意選項，且無法將整個組織系統管理員同意給應用程式，Teams 服務系統管理員可以在應用程式的 "許可權" 選項卡上查看內容。 </span><span class="sxs-lookup"><span data-stu-id="a32b0-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="a32b0-140">例如，Teams系統管理員可以按一下 [Azure Active Directory **連結以** 在 Azure AD 入口網站中查看應用程式許可權詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a32b0-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="a32b0-141">查看應用程式的資源特定同意許可權</span><span class="sxs-lookup"><span data-stu-id="a32b0-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="a32b0-142">RSC 許可權允許團隊擁有者同意應用程式存取及修改小組的資料。</span><span class="sxs-lookup"><span data-stu-id="a32b0-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="a32b0-143">RSC 許可權是精細Teams特定許可權，可定義應用程式可在特定小組中執行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="a32b0-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="a32b0-144">RSC 許可權的範例包括建立和刪除頻道、取得團隊的設定，以及建立和移除頻道標籤。</span><span class="sxs-lookup"><span data-stu-id="a32b0-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="a32b0-145">RSC 許可權在應用程式清單中定義，而不是在 Azure AD 中定義。</span><span class="sxs-lookup"><span data-stu-id="a32b0-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="a32b0-146">當您將應用程式新增到團隊時，即表示您同意 RSC 許可權。</span><span class="sxs-lookup"><span data-stu-id="a32b0-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="a32b0-147">若要深入瞭解，請參閱[RSC (特定) 。](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)</span><span class="sxs-lookup"><span data-stu-id="a32b0-147">To learn more, see [Resource-specific consent (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="a32b0-148">全域系統管理員Teams服務系統管理員可以在應用程式詳細資料頁面的 "許可權" 選項卡上，查看應用程式的RSC 許可權。</span><span class="sxs-lookup"><span data-stu-id="a32b0-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="a32b0-149">若要查看應用程式的 RSC 許可權，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a32b0-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="a32b0-150">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="a32b0-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="a32b0-151">搜尋您想要的應用程式，按一下應用程式名稱以前往應用程式詳細資料頁面，然後選取 [ **許可權> 索引** 鍵。</span><span class="sxs-lookup"><span data-stu-id="a32b0-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="a32b0-152">在 **Microsoft Graph特定資源同意 (RSC**) 許可權下，請審查應用程式要求 RSC 許可權。</span><span class="sxs-lookup"><span data-stu-id="a32b0-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="應用程式 RSC 許可權的螢幕擷取畫面":::

## <a name="known-issues"></a><span data-ttu-id="a32b0-154">已知問題</span><span class="sxs-lookup"><span data-stu-id="a32b0-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="a32b0-155">要求許可權的一些協力廠商 App 的 「許可權」 欄不會顯示 「查看詳細資料」連結</span><span class="sxs-lookup"><span data-stu-id="a32b0-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="a32b0-156">目前，在 Azure AD 中註冊的所有要求許可權的協力廠商應用程式，無法審查許可權並授予同意。</span><span class="sxs-lookup"><span data-stu-id="a32b0-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="a32b0-157">除了查看 **詳細資料** 連結外，您也會在許可權欄中 **--** 看到。</span><span class="sxs-lookup"><span data-stu-id="a32b0-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="a32b0-158">我們正在與 ISV 合作，為應用程式啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="a32b0-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a32b0-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="a32b0-159">Related topics</span></span>

- [<span data-ttu-id="a32b0-160">在系統管理中心管理Microsoft Teams應用程式</span><span class="sxs-lookup"><span data-stu-id="a32b0-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="a32b0-161">端點中的許可權Microsoft 身分識別平臺同意</span><span class="sxs-lookup"><span data-stu-id="a32b0-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="a32b0-162">中特定資源Teams</span><span class="sxs-lookup"><span data-stu-id="a32b0-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="a32b0-163">RSC (特定) </span><span class="sxs-lookup"><span data-stu-id="a32b0-163">Resource-specific consent (RSC)</span></span>](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- <span data-ttu-id="a32b0-164">[流覽 Teams App 生命週期 (](https://aka.ms/PR132)點 2020 會話) </span><span class="sxs-lookup"><span data-stu-id="a32b0-164">[Navigating the Teams app lifecycle](https://aka.ms/PR132) (Ignite 2020 session)</span></span>