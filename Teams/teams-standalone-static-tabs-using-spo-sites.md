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
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>從 SharePoint Online 網站或頁面建立團隊 [內部網路入口網站] 應用程式

您可以使用本文中的步驟，在連結至您組織內部網路內網站的小組內建立獨立和靜態的 app。

隨即會建立 SharePoint 內聯網網站的*小組個人應用程式*，並顯示為小組中的索引標籤。 此索引標籤可包含您所有團隊使用者的重要資訊。 只要按一下索引標籤，就能快速且方便地讓團隊使用者存取更新。

請注意，所顯示的處理常式**必須使用***新式*的 SharePoint 網站或頁面才能運作。 此流程不適用於*傳統*網站或頁面。

> [!IMPORTANT]
> 請確定已針對您的租使用者啟用團隊 app 的側載。 根據您在 [團隊管理入口網站] 的遷移程式中所處的位置，您可能需要在 [團隊 > 系統管理員] 或 [管理員] > 設定] 下啟用該 > 選項，> Microsoft 團隊 > 應用程式在舊版的入口網站中使用。 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>使用 App Studio 建立您獨立的 SharePoint Online 應用程式
在您開始之前：
1. 您必須知道 SharePoint Online 新式通訊或小組網站或頁面的 URL。
    - 這些網站在其路徑中永遠都是 */teams/* 或 */sites/* 。

2. 您必須知道租使用者的子域，這會在預留位置 **{{子域}}** 中使用。

3. 本文將為您選擇的網站或頁面的*URL*使用 **{{siteUrl}}** 預留位置。
    - 範例*url*： https://contoso.sharepoint.com/teams/Contoso*或*   https://contoso.sharepoint.com/sites/Contoso 
4. 此外， **{{sitePath}}** 將用來代表 URL 的*路徑*（例如：/teams/Contoso）。
    - 範例*路徑*：/Teams/Contoso*或*/sites/Contoso 

首先，請遵循下列步驟：

1. 移至 [團隊] 商店。

2. 安裝或開啟 App Studio。

3. 按一下 App 選項旁的 [**開啟**]。

4. 在 App Studio 開啟的情況下，按一下 [**資訊清單編輯器**]。

5. **建立新的應用程式**。

6. 填入所有**App 的詳細資料**。

7. 按一下 **[功能]** 底下的 [索引標籤]。

8. 按一下 [個人] 索引標籤的 [**新增**]。

9. 填入**名稱**，然後選擇**新的唯一實體識別碼**。

10. 填入**contentURL 和網站 URL**。 

- **contentUrl**： {{siteUrl}}/_layouts/15/teamslogon.aspx？SPFX = true&dest = {{sitePath}}  
- **web'iteUrl**： {{siteUrl}} ' "範例**contentURL**：https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. 流覽至 [**網域與 Permissi'ns**]。 請確定有效的網域區段包含您的 SharePoint online 網功能變數名稱稱。
' ' 範例： contoso.sharepoint.com

12. 新增下列 web 應用程式**單一登入**屬性： "Example：" "" " **AAD 應用程式識別碼**： 00000003-0000-0ff1-ce00-000000000000**資源 Url**： {{子域}}. 使用 ID 和 Url 的![web app 單一登入。](media/personal-app.png)

13. **儲存**這些屬性，然後流覽到 [**測試] 和 [發佈**]。 

14. 安裝 app 以親自測試應用程式。

> [!IMPORTANT]
> 如果您使用的不是團隊 App Studio，您將必須 .zip 資訊清單。JSON 檔案，請流覽至 [團隊] 中的應用程式商店，然後按一下 [**上傳自訂應用程式**連結] （位於 App Store 的右下方）。 這將讓您能使用該應用程式。

15. 現在，您可以使用應用程式作為靜態索引標籤，讓您在團隊中載入及查看。

## <a name="test-and-view-your-new-static-tab"></a>測試並查看新的靜態索引標籤

若要在 [團隊桌面] 上查看 [新增] 索引標籤，請流覽至應用程式行左側的**省略號（[...]**）。 尋找您的新應用程式、載入它，並在團隊中測試您的獨立應用程式。

如果您想讓新 app 在較高位置的左側功能表中提供，您必須使用 app 原則設定。 您可以在 [團隊管理員] 區段 > 應用程式原則 > 新增釘選的應用程式中找到此設定。 當您將原則指派給使用者進行測試時，此變更將會在24小時之後顯示。 考慮到這個想法，請在您最早的便利中決定應用程式應該顯示的位置，以協助避免延遲。

若要在行動裝置上查看和測試新的應用程式，請在畫面底部附近之索引卷**^** 標列上方的 v 形（），以開啟應用程式抽屜。 尋找您的 app，並在行動裝置上流覽至該應用程式。
        
> [!CAUTION]
> 行動支援目前在開發人員預覽版中。 若要啟用開發人員預覽版，請流覽至 [設定] >，然後啟用 [開發人員預覽] 模式。

## <a name="a-sample-manifestjson-file"></a>範例資訊清單. JSON 檔案

您產生的 JSO 檔案看起來會像下面這樣。

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