---
title: 在 Microsoft 團隊系統管理中心上傳您的自訂應用程式
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何將自訂應用程式上傳到 Microsoft 團隊系統管理中心的組織 app 存放區。
ms.openlocfilehash: d43b19f4ada3ce6f0424a324cdea6f194575325b
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583642"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>透過上傳應用程式套件發佈自訂應用程式

> [!NOTE]
> 當您發佈自訂團隊 app 時，您組織的 app store 中的使用者就能使用該應用程式。 發佈自訂應用程式的方式有兩種，您使用的方式取決於您取得 app 的方式。 **本文將重點說明如何發佈自訂應用程式，方法是使用開發人員傳送給您的 .zip 格式) 來上傳應用程式套件 (。** 當開發人員透過團隊 App 提交 API 直接向 [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理應用</a>程式] 頁面提交應用程式時，就會使用另一個方法（核准自訂的應用程式）。 若要深入瞭解該方法，請參閱<a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">發佈透過團隊 App 提交 API 提交的自訂應用程式</a>。

本文提供如何將您的小組 app 從開發移至部署到探索的端對端指導方針。 本指南主要說明 app 的小組各部分，且適用于系統管理員和 IT 專業人員。 如需開發小組 app 的詳細資訊，請參閱<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">團隊開發人員檔</a>。

![從開發到部署的應用程式概覽](media/upload-custom-apps.png)

## <a name="develop"></a>開發

### <a name="create-your-app"></a>建立您的應用程式

Microsoft 團隊開發人員平臺可讓開發人員輕鬆地整合您自己的 app 與服務，以提高生產力、更快速地作出決策，以及在現有的內容和工作流程中建立共同作業。 在團隊平臺上建立的應用程式是團隊用戶端與您的服務與工作流程之間的橋樑，可直接將它們納入共同作業平臺的內容。 如需詳細資訊，請移至<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">團隊開發人員檔</a>。

## <a name="validate"></a>核實

### <a name="get-the-app-package"></a>取得應用程式套件

當應用程式準備好在生產中使用時，開發人員應該會產生應用程式套件。 他們可以使用<a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">應用程式 Studio</a>來執行此程式。 他們會以 .zip 格式傳送檔案。

Microsoft 使用<a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">這些指導方針</a>，以確保 app 符合全域團隊 app store 的品質與安全性標準。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>允許信任的使用者上傳自訂應用程式

若要驗證 app 在您的生產租使用者中是否正常運作，您必須允許自己和/或受信任的使用者上傳生產租使用者中的自訂應用程式。 您可以使用<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">應用程式設定原則</a>來執行這項作業。

> [!NOTE]
> 如果您不滿意將 app 上傳到您的生產租使用者進行驗證，即使您是自己或信任的使用者，您也可以略過此步驟，並遵循[上傳](#upload)和[設定及管理](#set-up-and-manage)區段中的步驟，將 unvalidated 應用程式發佈到貴組織的 app store。 然後，將該 app 的存取許可權制為只有您自己和您信任的使用者。 然後，這些使用者就可以從貴組織的 app store 取得 app 來執行驗證。 驗證應用程式後，請使用相同的許可權原則來開啟 access，並將 app 滾出以供生產使用。

若要允許信任的使用者上傳自訂應用程式，請依照下列步驟執行：

1. 開啟 [**允許與自訂應用程式互動**] 全組織性應用程式設定。 若要執行此動作：
    1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理 app**]，然後按一下 [**全組織式應用程式設定**]。
    2. 開啟 [**自訂應用程式**] 底下的 [**允許與自訂應用程式互動**]，然後按一下 [**儲存**]。
2. 關閉全域 app 設定原則中的 [**上傳自訂應用程式**] 設定。 若要執行此動作：
    1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **設定原則**]，然後按一下 [**全域 (組織範圍的預設) **原則。
    2. 關閉 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。
3. 建立新的應用程式設定原則，以允許上傳自訂應用程式，並將它指派給您的一組受信任的使用者。 若要執行此動作：
    1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **設定原則**]，然後按一下 [**新增**]。 提供新原則的名稱和描述、開啟 **[上傳自訂應用程式**]，然後按一下 [**儲存**]。
    2. 選取您建立的新原則，然後按一下 [**管理使用者**]。 搜尋使用者 **，按一下 [****新增**]，然後按一下 [套用]。 重複此步驟，將原則指派給所有信任的使用者。

        ![[新增應用程式設定原則] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-setup-policy.png)

    這些使用者現在可以上傳應用程式資訊清單，以驗證 app 在生產租使用者中是否正常運作。

## <a name="upload"></a>將

若要讓貴組織 app store 中的使用者使用該應用程式，請上傳 app。 您可以在 Microsoft 團隊系統管理中心的 [<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理應用程式</a>] 頁面上執行此動作。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。
2. 按一下 **[上傳**]，按一下 [**選取**檔案]，然後選取您從開發人員收到的應用程式套件。

   ![在系統管理中心上傳應用程式的螢幕擷取畫面](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>設定和管理

### <a name="control-access-to-the-app"></a>控制對應用程式的存取權

根據預設，貴組織中的所有使用者都可以存取貴組織 app store 中的 app。 若要限制及控制誰有權使用該應用程式，您可以建立並指派應用程式許可權原則。 若要深入瞭解，請參閱<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">在團隊中管理 app 許可權原則</a>。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>釘選並安裝應用程式供使用者探索

根據預設，使用者可以找到您組織的 app 商店所需的 app，然後流覽或搜尋該應用程式。 若要讓使用者能夠輕鬆存取應用程式，您可以將應用程式釘選到 [團隊] 中的應用程式行。 若要這樣做，請建立應用程式設定原則，並將它指派給使用者。 若要深入瞭解，請參閱<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">管理團隊中的 app 設定原則</a>。

### <a name="search-the-audit-log-for-teams-app-events"></a>搜尋小組 app 事件的審核記錄

您可以搜尋 [審核記錄]，以查看貴組織中的 [小組 app] 活動。 若要進一步瞭解如何搜尋審核記錄，以及查看在審核記錄中記錄的小組活動清單，請參閱<a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">在審核記錄中搜尋小組中的事件</a>。

在您可以搜尋審核記錄之前，您必須先在<a href="https://protection.office.com" target="_blank">安全性 & 合規性中心</a>開啟審核。 若要深入瞭解，請參閱<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">開啟或關閉審核記錄搜尋</a>。 請記住，審核資料只能從您開啟審核的位置取得。

## <a name="discover-and-adopt"></a>探索與採納

擁有 app 許可權的使用者可以在您組織的 app store 中找到該應用程式。 移至 [應用程式] 頁面上的 [**針對*您的組織名稱*建立**]，以尋找貴組織的自訂應用程式。

![顯示已發佈 app 之 [應用程式] 頁面的螢幕擷取畫面 ](media/custom-app-lifecycle-discovery.png)

如果您已建立並指派應用程式設定原則，應用程式會釘選在團隊中的應用程式行上，輕鬆存取指派了原則的使用者。

## <a name="update"></a>時更新

若要更新應用程式，開發人員應該繼續遵循[開發](#develop)和[驗證](#validate)區段中的步驟。

您可以在 Microsoft 團隊系統管理中心的 [管理應用程式] 頁面上更新應用程式。 若要這樣做，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。 按一下應用程式名稱，然後按一下 [**更新**]。 這麼做會取代現有的 app，而且所有 app 許可權原則和 app 設定原則都會針對更新的 app 保持強制執行。

### <a name="end-user-update-experience"></a>最終使用者更新體驗

在大多數情況下，當您完成應用程式更新後，系統會自動針對最終使用者顯示新版本。 不過， <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 團隊資訊清單</a>有一些更新需要使用者驗收才能完成：

* 已新增或移除 bot
* 現有 bot 的 "botId" 屬性已變更
* 現有 bot 的 "isNotificationOnly" 屬性已變更
* Bot 的 "supportsFiles" 屬性已變更
* 已新增或移除訊息延伸
* 已新增新的連接器
* 新增了 [靜態] 索引標籤
* 新增 [可設定] 索引標籤
* "WebApplicationInfo" 中的屬性已變更

![[應用程式清單] 的螢幕擷取畫面，顯示已推出新版本的 app](media/manage-your-custom-apps-update1.png)

![App 之升級選項的螢幕擷取畫面](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>相關主題

- [發佈透過團隊 App 提交 API 提交的自訂應用程式](submit-approve-custom-apps.md)
- [在 Microsoft 團隊系統管理中心管理您的應用程式](manage-apps.md)
- [在 Teams 中管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)
- [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
- [在 Teams 中管理應用程式設定原則](teams-app-setup-policies.md)
