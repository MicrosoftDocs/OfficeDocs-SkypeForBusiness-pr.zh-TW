---
title: 從 SharePoint Online 網站或頁面建立團隊 [內部網路入口網站] 應用程式
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 使用現有的 SharePoint Online 網站或頁面，並建立獨立靜態索引標籤，以作為貴組織的內部網路入口網站。
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106630"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="82e09-103">從 SharePoint Online 網站或頁面建立團隊 [內部網路入口網站] 應用程式</span><span class="sxs-lookup"><span data-stu-id="82e09-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="82e09-104">您可以使用本文中的步驟，在連結至您組織內部網路內網站的小組內建立獨立和靜態的 app。</span><span class="sxs-lookup"><span data-stu-id="82e09-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="82e09-105">隨即會建立 SharePoint 內聯網網站的*小組個人應用程式*，並顯示為小組中的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="82e09-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="82e09-106">此索引標籤可包含您所有團隊使用者的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="82e09-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="82e09-107">只要按一下索引標籤，就能快速且方便地讓團隊使用者存取更新。</span><span class="sxs-lookup"><span data-stu-id="82e09-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="82e09-108">請注意，所顯示的處理常式\**必須使用\*\*\*新式*的 SharePoint 網站或頁面才能運作。</span><span class="sxs-lookup"><span data-stu-id="82e09-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="82e09-109">此流程不適用於*傳統*網站或頁面。</span><span class="sxs-lookup"><span data-stu-id="82e09-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82e09-110">請確定已針對您的租使用者啟用團隊 app 的側載。</span><span class="sxs-lookup"><span data-stu-id="82e09-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="82e09-111">根據您在 [團隊管理入口網站] 的遷移程式中所處的位置，您可能需要在 [團隊 > 系統管理員] 或 [管理員] > 設定] 下啟用該 > 選項，> Microsoft 團隊 > 應用程式在舊版的入口網站中使用。</span><span class="sxs-lookup"><span data-stu-id="82e09-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span> 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="82e09-112">使用 App Studio 建立您獨立的 SharePoint Online 應用程式</span><span class="sxs-lookup"><span data-stu-id="82e09-112">Use App Studio to create your standalone SharePoint Online app</span></span>
<span data-ttu-id="82e09-113">在您開始之前：</span><span class="sxs-lookup"><span data-stu-id="82e09-113">''' Before you begin:</span></span>
1. <span data-ttu-id="82e09-114">您必須知道 SharePoint Online 新式通訊或小組網站或頁面的 URL。</span><span class="sxs-lookup"><span data-stu-id="82e09-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="82e09-115">這些網站在其路徑中永遠都是 */teams/* 或 */sites/* 。</span><span class="sxs-lookup"><span data-stu-id="82e09-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="82e09-116">您必須知道租使用者的子域，這會在預留位置 **{{子域}}** 中使用。</span><span class="sxs-lookup"><span data-stu-id="82e09-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="82e09-117">本文將為您選擇的網站或頁面的*URL*使用 **{{siteUrl}}** 預留位置。</span><span class="sxs-lookup"><span data-stu-id="82e09-117">This article will use **{{siteUrl}}** placeholder for your the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="82e09-118">範例*url*： https://contoso.sharepoint.com/teams/Contoso*或*   https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="82e09-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span> 
4. <span data-ttu-id="82e09-119">此外， **{{sitePath}}** 將用來代表 URL 的*路徑*（例如：/teams/Contoso）。</span><span class="sxs-lookup"><span data-stu-id="82e09-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="82e09-120">範例*路徑*：/Teams/Contoso*或*/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="82e09-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span> 

<span data-ttu-id="82e09-121">首先，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="82e09-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="82e09-122">移至 [團隊] 商店。</span><span class="sxs-lookup"><span data-stu-id="82e09-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="82e09-123">安裝或開啟 App Studio。</span><span class="sxs-lookup"><span data-stu-id="82e09-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="82e09-124">按一下 App 選項旁的 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="82e09-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="82e09-125">在 App Studio 開啟的情況下，按一下 [**資訊清單編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="82e09-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="82e09-126">**建立新的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="82e09-126">**Create a new app**.</span></span>

6. <span data-ttu-id="82e09-127">填入所有**App 的詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="82e09-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="82e09-128">按一下 **[功能]** 底下的 [索引標籤]。</span><span class="sxs-lookup"><span data-stu-id="82e09-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="82e09-129">按一下 [個人] 索引標籤的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="82e09-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="82e09-130">填入**名稱**，然後選擇**新的唯一實體識別碼**。</span><span class="sxs-lookup"><span data-stu-id="82e09-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="82e09-131">填入**contentURL 和網站 URL**。</span><span class="sxs-lookup"><span data-stu-id="82e09-131">Fill in the **contentURL and Website URL**.</span></span> 

- <span data-ttu-id="82e09-132">**contentUrl**： {{siteUrl}}/_layouts/15/teamslogon.aspx？SPFX = true&dest = {{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="82e09-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="82e09-133">**web'iteUrl**： {{siteUrl}} ' "範例**contentURL**：https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="82e09-133">**web'iteUrl**: {{siteUrl}} ''   Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span> 

11. <span data-ttu-id="82e09-134">流覽至 [**網域與 Permissi'ns**]。</span><span class="sxs-lookup"><span data-stu-id="82e09-134">Navigate to **Domains and Permissi'ns**.</span></span> <span data-ttu-id="82e09-135">請確定有效的網域區段包含您的 SharePoint online 網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="82e09-135">Make sure the valid domains section contains your SharePoint online domain name.</span></span>
<span data-ttu-id="82e09-136">' ' 範例： contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="82e09-136">'' Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="82e09-137">新增下列 web 應用程式**單一登入**屬性： "Example：" "" " **AAD 應用程式識別碼**： 00000003-0000-0ff1-ce00-000000000000**資源 Url**： {{子域}}. 使用 ID 和 Url 的![web app 單一登入。](media/personal-app.png)</span><span class="sxs-lookup"><span data-stu-id="82e09-137">Add the following web app **single sign-on** properties:  ''  Example:''''  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com' '' ![Web app single sign-on, with ID and URL.](media/personal-app.png)</span></span>

13. <span data-ttu-id="82e09-138">**儲存**這些屬性，然後流覽到 [**測試] 和 [發佈**]。</span><span class="sxs-lookup"><span data-stu-id="82e09-138">**Save** these properties and then navigate to **Test and distribute**.</span></span> 

14. <span data-ttu-id="82e09-139">安裝 app 以親自測試應用程式。</span><span class="sxs-lookup"><span data-stu-id="82e09-139">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82e09-140">如果您使用的不是團隊 App Studio，您將必須 .zip 資訊清單。JSON 檔案，請流覽至 [團隊] 中的應用程式商店，然後按一下 [**上傳自訂應用程式**連結] （位於 App Store 的右下方）。</span><span class="sxs-lookup"><span data-stu-id="82e09-140">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="82e09-141">這將讓您能使用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="82e09-141">This will make the app available to you.</span></span>

15. <span data-ttu-id="82e09-142">現在，您可以使用應用程式作為靜態索引標籤，讓您在團隊中載入及查看。</span><span class="sxs-lookup"><span data-stu-id="82e09-142">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="82e09-143">測試並查看新的靜態索引標籤</span><span class="sxs-lookup"><span data-stu-id="82e09-143">Test and view your new static tab</span></span>

<span data-ttu-id="82e09-144">若要在 [團隊桌面] 上查看 [新增] 索引標籤，請流覽至應用程式行左側的**省略號（[...]**）。</span><span class="sxs-lookup"><span data-stu-id="82e09-144">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="82e09-145">尋找您的新應用程式、載入它，並在團隊中測試您的獨立應用程式。</span><span class="sxs-lookup"><span data-stu-id="82e09-145">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="82e09-146">如果您想讓新 app 在較高位置的左側功能表中提供，您必須使用 app 原則設定。</span><span class="sxs-lookup"><span data-stu-id="82e09-146">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="82e09-147">您可以在 [團隊管理員] 區段 > 應用程式原則 > 新增釘選的應用程式中找到此設定。</span><span class="sxs-lookup"><span data-stu-id="82e09-147">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="82e09-148">當您將原則指派給使用者進行測試時，此變更將會在24小時之後顯示。</span><span class="sxs-lookup"><span data-stu-id="82e09-148">When you assign the policy to a user for testing, the change will appear 24 hours later.</span></span> <span data-ttu-id="82e09-149">考慮到這個想法，請在您最早的便利中決定應用程式應該顯示的位置，以協助避免延遲。</span><span class="sxs-lookup"><span data-stu-id="82e09-149">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="82e09-150">若要在行動裝置上查看和測試新的應用程式，請在畫面底部附近之索引卷**^** 標列上方的 v 形（），以開啟應用程式抽屜。</span><span class="sxs-lookup"><span data-stu-id="82e09-150">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="82e09-151">尋找您的 app，並在行動裝置上流覽至該應用程式。</span><span class="sxs-lookup"><span data-stu-id="82e09-151">Find your app and navigate to it on your mobile device.</span></span>
        
> [!CAUTION]
> <span data-ttu-id="82e09-152">行動支援目前在開發人員預覽版中。</span><span class="sxs-lookup"><span data-stu-id="82e09-152">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="82e09-153">若要啟用開發人員預覽版，請流覽至 [設定] >，然後啟用 [開發人員預覽] 模式。</span><span class="sxs-lookup"><span data-stu-id="82e09-153">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="82e09-154">範例資訊清單. JSON 檔案</span><span class="sxs-lookup"><span data-stu-id="82e09-154">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="82e09-155">您產生的 JSO 檔案看起來會像下面這樣。</span><span class="sxs-lookup"><span data-stu-id="82e09-155">The JSO        file you generate will look something like the one below.</span></span>

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
''
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