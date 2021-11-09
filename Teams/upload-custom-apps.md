---
title: Upload系統管理中心中Microsoft Teams自訂應用程式
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在系統管理中心將自訂應用程式上傳到Microsoft Teams市。
ms.openlocfilehash: 3869019d9becaf85da9c54ebc0ccca801980ec8a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846006"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>上傳應用程式套件來發佈自訂應用程式

> [!NOTE]
> 當您發佈自訂 Teams應用程式時，組織 App Store 中的使用者可以使用自訂應用程式。 發佈自訂應用程式的方法有兩種，而使用方式取決於您取得應用程式的方式。 **本文著重瞭解如何** 以開發人員傳送 (格式.zip應用程式套件) 發佈自訂應用程式。 當開發人員透過應用程式提交 API 將應用程式直接提交到管理應用程式頁面時，會Teams<a href="/microsoftteams/manage-apps" target="_blank"></a>自訂應用程式。 若要深入瞭解這個方法，請參閱發佈透過應用程式提交 API 提交的Teams<a href="/microsoftteams/submit-approve-custom-apps" target="_blank">應用程式</a>。

本文提供端對端指南，瞭解如何將應用程式從開發Teams部署到探索。 本指南著重于應用程式Teams，適用于系統管理員和 IT 專業人員。 有關開發應用程式Teams，請參閱開發人員Teams<a href="/microsoftteams/platform" target="_blank">檔</a>。

![從開發到部署的應用程式概觀。](media/upload-custom-apps.png)

## <a name="develop"></a>開發

### <a name="create-your-app"></a>建立您的應用程式

開發人員Microsoft Teams平臺，讓開發人員能輕鬆整合您自己的應用程式和服務，以提高生產力、更快速地做出決策，並圍繞現有內容和工作流程建立共同作業。 以平臺Teams的應用程式是用戶端Teams服務與工作流程之間的橋樑，直接將其納入您的共同合作平臺中。 若要詳細資訊，請參閱開發人員Teams<a href="/microsoftteams/platform" target="_blank">檔</a>。

## <a name="validate"></a>驗證

### <a name="get-the-app-package"></a>取得應用程式套件

當應用程式準備好用於生產時，開發人員應產生應用程式套件。 他們可以使用<a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio。</a> 他們會以新的格式傳送.zip檔案。

Microsoft<a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">會使用這些指導方針</a>，確保應用程式符合全球應用程式市Teams的品質和安全性標準。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>允許信任的使用者上傳自訂應用程式

若要驗證應用程式在生產租使用者中是否正確工作，您必須允許您自己和/或信任的使用者在生產租使用者中上傳自訂應用程式。 您可以使用 <a href="/microsoftteams/teams-app-setup-policies" target="_blank">應用程式設定策略</a> 執行此操作。

> [!NOTE]
> 如果您不喜歡將應用程式上傳到生產租使用者進行驗證，即使您自己或信任的使用者也一樣，您可以略過此步驟，並按照 Upload 和[設定](#upload)及管理節中的步驟，將未驗證的應用程式[](#set-up-and-manage)發佈到組織的 App Store。 接著，將該應用程式的存取許可權制為只有您自己和您信任的使用者。 這些使用者接著可以從組織的 App Store 取得應用程式來執行驗證。 應用程式驗證之後，請使用相同的權限原則來開啟存取，並推出應用程式供生產使用。

若要允許信任的使用者上傳自訂應用程式，請遵循下列步驟：

1. 開啟允許 **與自訂應用程式** 全組織 App 互動設定。 若要這麼做：
    1. 在系統管理中心的左側導Microsoft Teams，前往 [Teams **應用程式**  >  **管理應用程式**，然後按一下 [**全組織應用程式設定**> 。
    2. 在 **[自訂應用程式」** 下，開啟 [ **允許與自訂應用程式互動**，然後按一下 [ **儲存**> 。
2. 關閉全域 **Upload** 設定策略中的自訂應用程式設定。 若要這麼做：
    1. 在系統管理中心的左側導Microsoft Teams，前往 [Teams **應用程式** 設定政策，然後按一下 [全域 ( >  ******全組織** 的預設) 規則。
    2. 關閉自訂 **Upload** 應用程式，然後按一下 [**儲存**。
3. 建立新的應用程式設定策略，允許上傳自訂應用程式，並將它指派給一組信任的使用者。 若要這麼做：
    1. 在系統管理中心的左側導Microsoft Teams，請Teams **應用程式設定** 政策，然後按一下 [  >  ******新增**。 為新政策命名和描述，開啟自訂 **Upload應用程式，** 然後按一下 [**儲存**。
    2. 選取您建立的新策略，然後按一下 [ **管理使用者**。 搜尋使用者，按一下 [**新增**，然後按一下 **[Apply.** 重複此步驟，將策略指派給所有信任的使用者。

        ![「新增應用程式設定政策」頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-setup-policy.png)

    這些使用者現在可以上傳應用程式清單，以驗證應用程式在生產租使用者中是否正確工作。

## <a name="upload"></a>Upload

若要讓應用程式可供貴組織 App Store 中的使用者使用，請上傳應用程式。 您可以在系統管理中心的管理應用程式<a href="/microsoftteams/manage-apps" target="_blank">頁面上Microsoft Teams</a>這項功能。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 按一下 **Upload**，按一下 [**選取檔案**，然後選取您從開發人員收到的應用程式套件。

   ![在系統管理中心上傳應用程式的螢幕擷取畫面。](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>設定和管理

### <a name="control-access-to-the-app"></a>控制應用程式的存取權

根據預設，貴組織的所有使用者都可以存取貴組織 App Store 中的應用程式。 若要限制及控制誰有權使用應用程式，您可以建立並指派應用程式權限原則。 若要深入了解，請參閱<a href="/microsoftteams/teams-app-permission-policies" target="_blank">管理 Teams 中的應用程式權限原則</a>。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>釘上並安裝應用程式供使用者探索

根據預設，使用者若要尋找應用程式，必須前往貴組織的 App Store 並流覽或搜尋。 若要讓使用者輕鬆取得應用程式，您可以將應用程式釘到 Teams。 若要這麼做，請建立應用程式設定策略並指派給使用者。 若要深入了解，請參閱<a href="/microsoftteams/teams-app-setup-policies" target="_blank">管理 Teams 中的應用程式設定原則</a>。

### <a name="search-the-audit-log-for-teams-app-events"></a>搜尋稽核記錄Teams應用程式事件

您可以搜尋稽核記錄來Teams組織中應用程式活動。 若要深入瞭解如何搜尋稽核記錄，以及查看記錄在稽核記錄中的 Teams 活動清單，請參閱在 Teams 中搜尋稽核<a href="/microsoftteams/audit-log-events" target="_blank">記錄</a>。

在您可以搜尋稽核記錄檔之前，您必須先在<a href="https://protection.office.com" target="_blank">安全性與合規性中心</a>中開啟稽核。 如需深入了解，請參閱<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">開啟或關閉稽核記錄</a>。 請記住，只有當您開啟稽核時，才能使用稽核資料。

## <a name="discover-and-adopt"></a>探索及採用

擁有應用程式許可權的使用者可以在貴組織的 App Store 中找到它。 前往 **應用程式頁面上 *的*** 專為您的組織名稱建立，以尋找貴組織的自訂應用程式。

![顯示已發佈應用程式之應用程式之應用程式頁面的螢幕擷取畫面。](media/custom-app-lifecycle-discovery.png)

如果您建立並指派應用程式設定策略，應用程式會釘到 Teams 中的應用程式欄，以便指派該策略的使用者輕鬆存取。

## <a name="update"></a>更新

若要更新應用程式，開發人員應該繼續遵循開發和驗證[區段](#develop)[的步驟](#validate)。

您可以在系統管理中心的管理應用程式頁面上更新Microsoft Teams應用程式。 若要這麼做，在系統管理中心的左側導Microsoft Teams，請前往 **管理** Teams  >  **應用程式**。 按一下應用程式名稱，然後按一下 [ **更新**。 這麼做會取代現有的應用程式，而且所有應用程式權限原則及應用程式設定策略會持續為更新的應用程式強制執行。

### <a name="end-user-update-experience"></a>使用者更新體驗

在大多數情況下，完成應用程式更新後，系統會自動為使用者顯示新版本。 不過，系統對 Microsoft Teams<a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">清單有</a>一些更新需要使用者接受才能完成：

* 已新增或移除 Bot
* 現有 Bot 的「botId」屬性已變更
* 已變更現有 Bot 的 "isNotificationOnly" 屬性
* Bot 的「支援檔」屬性已變更
* 已新增或移除訊息擴充功能
* 已新增連接器
* 已新增靜態定位停駐點
* 已新增可配置的選項卡
* 「webApplicationInfo」中的屬性已變更

![應用程式清單的螢幕擷取畫面，顯示提供新版本的應用程式。](media/manage-your-custom-apps-update1.png)

![應用程式升級選項的螢幕擷取畫面。](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>相關主題

- [發佈透過應用程式提交 API Teams提交的自訂應用程式](submit-approve-custom-apps.md)
- [在系統管理中心管理Microsoft Teams應用程式](manage-apps.md)
- [在 Teams 中管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
- [在 Teams 中管理應用程式設定原則](teams-app-setup-policies.md)