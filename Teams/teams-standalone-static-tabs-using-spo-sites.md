---
title: 從 SharePoint Online 網站或頁面建立 Teams「內部網路入口網站應用程式」
author: cichur
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
ms.openlocfilehash: 080adc58059a88e585f5c975972399e552640e3d
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923805"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>從 SharePoint Online 網站或頁面建立 Teams「內部網路入口網站應用程式」

請使用本文中的步驟，在連結至組織內部網路網站的 Teams 內部建立獨立且靜態的應用程式。

系統會為您的 SharePoint 內部網路網站建立 *「Teams 個人版應用程式」*，並顯示為 Teams 內部的索引標籤。 此索引標籤會包含所有 Teams 使用者的重要資訊。 這種方式既快速又便利，Teams 使用者只要按一下索引標籤就能存取更新。

請注意，所顯示的程序 **必須使用***「新式」* SharePoint 網站或頁面才能運作。 此程序不適用於 *「傳統」* 網站或頁面。

> [!IMPORTANT]
> 請確定您已為租用戶啟用 Teams 應用程式側載功能。 視您在 Teams 系統管理入口網站移轉程序中所處的位置而定，您可能要在 [Teams] > [系統管理] 底下啟用此功能；如果是舊版入口網站，則要在 [系統管理] > [設定] > [服務與增益集] > [Microsoft Teams] > [應用程式] > [外部應用程式] 底下啟用。

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>使用 App Studio 來建立獨立的 SharePoint Online 應用程式

開始之前：

1. 您必須知道 SharePoint Online 新式通訊或 Teams 網站或頁面的 URL。
    - 這些網站的路徑中一律會有 */teams/* 或 */sites/*。

2. 您必須知道租用戶的子網域，以便用於預留位置 **{{subdomain}}**。

3. 本文會使用 **{{siteUrl}}** 作為預留位置來指出您所選網站或頁面的 *URL*。
    - 範例 *URL*：`https://contoso.sharepoint.com/teams/Contoso`
        *或*`https://contoso.sharepoint.com/sites/Contoso`
4. 此外，會使用 **{{sitePath}}** 來表示 URL 的 *「路徑」* (例如：/teams/Contoso)。
    - 範例 *「路徑」*：/teams/Contoso *或*/sites/Contoso

請遵循下列步驟來開始：

1. 移至 Teams Store。

2. 安裝或開啟 App Studio。

3. 按一下 [應用程式] 選項旁的 **[開啟]**。

4. 在 App Studio 已開啟時，按一下 **[資訊清單編輯器]**。

5. **建立新的應用程式**。

6. 填寫所有 **[應用程式詳細資料]**。

7. 按一下 [功能] 底下的 **[索引標籤]**。

8. 按一下 [個人] 索引標籤底下的 **[新增]**。

9. 填寫 **[名稱]**，然後選擇 **[新的唯一實體識別碼]**。

10. 填寫 **contentURL 和網站 URL**。

- **contentUrl**：{{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
- **websiteUrl**：{{siteUrl}}

    範例 **contentURL**：`https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. 瀏覽至 **[網域和權限]**。 請確定有效的網域區段包含了您的 SharePoint Online 網域名稱。

    範例：`contoso.sharepoint.com`

12. 新增下列 Web應用程式 **單一登入** 屬性：

     範例：**AAD 應用程式識別碼**：00000003-0000-0ff1-ce00-000000000000  **Resource Url**：{{subdomain}}.sharepoint.com

    ![含有識別碼和 URL 的 Web 應用程式單一登入。](media/personal-app.png)

13. **儲存** 這些屬性，然後瀏覽至 **[儲存及散發]**。

14. 安裝應用程式以親自測試應用程式。

> [!IMPORTANT]
> 如果您使用的不是 Teams App Studio，則必須先將剛才建立的 manifest.JSON 檔案壓縮成 Zip 檔、瀏覽至 Teams 中的 App Store，然後按一下 **[上傳自訂應用程式]** 連結 (位於 App Store 右下角)。 這會讓您可以使用應用程式。

15. 現在，應用程式便能以靜態索引標籤的形式供您在 Teams 中載入和檢視。

## <a name="test-and-view-your-new-static-tab"></a>測試和檢視新的靜態索引標籤

若要檢視 Teams 桌面上的新索引標籤，請瀏覽至應用程式列左側的省略號 (**...**)。 尋找您的新應用程式、加以載入，然後在 Teams 中測試您的獨立應用程式。

如果您想讓新的應用程式出現在左側功能表中的較高位置，則必須使用應用程式原則設定來進行。 您可以在 [Teams 管理員] 區段 > [應用程式原則] > [新增釘選的應用程式] 底下找到此設定。 當您指派原則給使用者以進行測試時，此變更會在數小時後才顯示。 在了解這一點的情況下，請盡早決定應用程式的顯示位置以免造成延遲。

若要在行動裝置上檢視並測試新的應用程式，請點選畫面底部附近索引標籤列上方的＞形箭號 (**^**)，以開啟應用程式選單。 尋找您的應用程式，並在您的行動裝置上瀏覽至該應用程式。

## <a name="a-sample-manifestjson-file"></a>範例 Manifest.JSON 檔案

您所產生的 JSON 檔案會如下所示。

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
