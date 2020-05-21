---
title: 從 SharePoint Online 網站或頁面建立 Teams「內部網路入口網站應用程式」
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: 取得現有的 SharePoint Online 網站或頁面，並建立獨立的靜態索引標籤，以作為組織的內部網路入口網站。
localization_priority: Priority
ms.openlocfilehash: 4777b744d76415f45718cb274f402556e1e28240
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326580"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="cc057-103">從 SharePoint Online 網站或頁面建立 Teams「內部網路入口網站應用程式」</span><span class="sxs-lookup"><span data-stu-id="cc057-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="cc057-104">請使用本文中的步驟，在連結至組織內部網路網站的 Teams 內部建立獨立且靜態的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc057-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="cc057-105">系統會為您的 SharePoint 內部網路網站建立「Teams 個人版應用程式」\*\*，並顯示為 Teams 內部的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cc057-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="cc057-106">此索引標籤會包含所有 Teams 使用者的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="cc057-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="cc057-107">這種方式既快速又便利，Teams 使用者只要按一下索引標籤就能存取更新。</span><span class="sxs-lookup"><span data-stu-id="cc057-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="cc057-108">請注意，所顯示的程序**必須使用**「新式」\*\* SharePoint 網站或頁面才能運作。</span><span class="sxs-lookup"><span data-stu-id="cc057-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="cc057-109">此程序不適用於「傳統」\*\* 網站或頁面。</span><span class="sxs-lookup"><span data-stu-id="cc057-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc057-110">請確定您已為租用戶啟用 Teams 應用程式側載功能。</span><span class="sxs-lookup"><span data-stu-id="cc057-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="cc057-111">視您在 Teams 系統管理入口網站移轉程序中所處的位置而定，您可能要在 [Teams] > [系統管理] 底下啟用此功能；如果是舊版入口網站，則要在 [系統管理] > [設定] > [服務與增益集] > [Microsoft Teams] > [應用程式] > [外部應用程式] 底下啟用。</span><span class="sxs-lookup"><span data-stu-id="cc057-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="cc057-112">使用 App Studio 來建立獨立的 SharePoint Online 應用程式</span><span class="sxs-lookup"><span data-stu-id="cc057-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="cc057-113">開始之前：</span><span class="sxs-lookup"><span data-stu-id="cc057-113">Before you begin:</span></span>

1. <span data-ttu-id="cc057-114">您必須知道 SharePoint Online 新式通訊或 Teams 網站或頁面的 URL。</span><span class="sxs-lookup"><span data-stu-id="cc057-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="cc057-115">這些網站的路徑中一律會有 /teams/\*\* 或 /sites/\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc057-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="cc057-116">您必須知道租用戶的子網域，以便用於預留位置 **{{subdomain}}**。</span><span class="sxs-lookup"><span data-stu-id="cc057-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="cc057-117">本文會使用 **{{siteUrl}}** 作為預留位置來指出您所選網站或頁面的 *URL*。</span><span class="sxs-lookup"><span data-stu-id="cc057-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="cc057-118">範例 URL\*\*：https://contoso.sharepoint.com/teams/Contoso 或 \*\*https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="cc057-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span>
4. <span data-ttu-id="cc057-119">此外，會使用 **{{sitePath}}** 來表示 URL 的「路徑」\*\* (例如：/teams/Contoso)。</span><span class="sxs-lookup"><span data-stu-id="cc057-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="cc057-120">範例「路徑」\*\*：/teams/Contoso 或 \*\*/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="cc057-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span>

<span data-ttu-id="cc057-121">請遵循下列步驟來開始：</span><span class="sxs-lookup"><span data-stu-id="cc057-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="cc057-122">移至 Teams Store。</span><span class="sxs-lookup"><span data-stu-id="cc057-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="cc057-123">安裝或開啟 App Studio。</span><span class="sxs-lookup"><span data-stu-id="cc057-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="cc057-124">按一下 [應用程式] 選項旁的 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc057-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="cc057-125">在 App Studio 已開啟時，按一下 [資訊清單編輯器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc057-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="cc057-126">**建立新的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="cc057-126">**Create a new app**.</span></span>

6. <span data-ttu-id="cc057-127">填寫所有 [應用程式詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc057-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="cc057-128">按一下 [功能] 底下的 [索引標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc057-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="cc057-129">按一下 [個人] 索引標籤底下的 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc057-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="cc057-130">填寫 [名稱]\*\*\*\*，然後選擇 [新的唯一實體識別碼]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc057-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="cc057-131">填寫 **contentURL 和網站 URL**。</span><span class="sxs-lookup"><span data-stu-id="cc057-131">Fill in the **contentURL and Website URL**.</span></span>

- <span data-ttu-id="cc057-132">**contentUrl**：{{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="cc057-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="cc057-133">**websiteUrl**：{{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="cc057-133">**websiteUrl**: {{siteUrl}}</span></span>

    <span data-ttu-id="cc057-134">範例 **contentURL**：https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="cc057-134">Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span>

11. <span data-ttu-id="cc057-135">瀏覽至 [網域和權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc057-135">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="cc057-136">請確定有效的網域區段包含了您的 SharePoint Online 網域名稱。</span><span class="sxs-lookup"><span data-stu-id="cc057-136">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="cc057-137">範例：contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="cc057-137">Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="cc057-138">新增下列 Web應用程式**單一登入**屬性：</span><span class="sxs-lookup"><span data-stu-id="cc057-138">Add the following web app **single sign-on** properties:</span></span>

     <span data-ttu-id="cc057-139">範例：**AAD 應用程式識別碼**：00000003-0000-0ff1-ce00-000000000000  **Resource Url**：{{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="cc057-139">Example:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span></span>

    ![含有識別碼和 URL 的 Web 應用程式單一登入。](media/personal-app.png)

13. <span data-ttu-id="cc057-141">**儲存**這些屬性，然後瀏覽至 [儲存及散發]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc057-141">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="cc057-142">安裝應用程式以親自測試應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc057-142">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc057-143">如果您使用的不是 Teams App Studio，則必須先將剛才建立的 manifest.JSON 檔案壓縮成 Zip 檔、瀏覽至 Teams 中的 App Store，然後按一下 [上傳自訂應用程式]\*\*\*\* 連結 (位於 App Store 右下角)。</span><span class="sxs-lookup"><span data-stu-id="cc057-143">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="cc057-144">這會讓您可以使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc057-144">This will make the app available to you.</span></span>

15. <span data-ttu-id="cc057-145">現在，應用程式便能以靜態索引標籤的形式供您在 Teams 中載入和檢視。</span><span class="sxs-lookup"><span data-stu-id="cc057-145">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="cc057-146">測試和檢視新的靜態索引標籤</span><span class="sxs-lookup"><span data-stu-id="cc057-146">Test and view your new static tab</span></span>

<span data-ttu-id="cc057-147">若要檢視 Teams 桌面上的新索引標籤，請瀏覽至應用程式列左側的省略號 (**...**)。</span><span class="sxs-lookup"><span data-stu-id="cc057-147">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="cc057-148">尋找您的新應用程式、加以載入，然後在 Teams 中測試您的獨立應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc057-148">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="cc057-149">如果您想讓新的應用程式出現在左側功能表中的較高位置，則必須使用應用程式原則設定來進行。</span><span class="sxs-lookup"><span data-stu-id="cc057-149">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="cc057-150">您可以在 [Teams 管理員] 區段 > [應用程式原則] > [新增釘選的應用程式] 底下找到此設定。</span><span class="sxs-lookup"><span data-stu-id="cc057-150">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="cc057-151">當您指派原則給使用者以進行測試時，此變更會在數小時後才顯示。</span><span class="sxs-lookup"><span data-stu-id="cc057-151">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="cc057-152">在了解這一點的情況下，請盡早決定應用程式的顯示位置以免造成延遲。</span><span class="sxs-lookup"><span data-stu-id="cc057-152">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="cc057-153">若要在行動裝置上檢視並測試新的應用程式，請點選畫面底部附近索引標籤列上方的＞形箭號 (**^**)，以開啟應用程式選單。</span><span class="sxs-lookup"><span data-stu-id="cc057-153">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="cc057-154">尋找您的應用程式，並在您的行動裝置上瀏覽至該應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc057-154">Find your app and navigate to it on your mobile device.</span></span>

> [!CAUTION]
> <span data-ttu-id="cc057-155">目前已在開發人員預覽中支援行動裝置。</span><span class="sxs-lookup"><span data-stu-id="cc057-155">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="cc057-156">若要啟用「開發人員預覽」，請瀏覽至 [設定] > [關於]，然後啟用 [開發人員預覽] 模式。</span><span class="sxs-lookup"><span data-stu-id="cc057-156">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="cc057-157">範例 Manifest.JSON 檔案</span><span class="sxs-lookup"><span data-stu-id="cc057-157">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="cc057-158">您所產生的 JSO 檔案會如下所示。</span><span class="sxs-lookup"><span data-stu-id="cc057-158">The JSO        file you generate will look something like the one below.</span></span>

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

            "name": "Contoso Net",

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/",

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet",

            "scopes": [

                "personal"

            ]

        },

        {

            "entityId": "teamSiteTab",

            "name": "Team Contoso",

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/",

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso",

            "scopes": [

                "personal"

            ]

        }

    ],

    "permissions": [

        "identity",

        "messageTeamMembers"

    ],

    "validDomains": [

        "contoso.sharepoint.com"

    ],

    "webApplicationInfo": {

        "id": "00000003-0000-0ff1-ce00-000000000000",

        "resource": "https://contoso.sharepoint.com"

    }

}
```
