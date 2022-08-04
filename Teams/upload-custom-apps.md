---
title: 在 Microsoft Teams 系統管理中心上傳您的自訂應用程式
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: high
search.appverid: MET150
description: 瞭解如何將您的自訂應用程式上傳到您組織的 Microsoft Teams 系統管理中心中的應用程式市集。
ms.openlocfilehash: 6c4c32ce747f0da17d010f8ba3f4bedd6112a51d
ms.sourcegitcommit: a64574da14969a33a77c7d979ffde452b5b3a531
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175657"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>透過上傳應用程式套件發佈自訂應用程式

> [!NOTE]
> 當您發佈自訂的 Teams 應用程式後，它就可以在貴組織的應用程式市集中供使用者使用。 發佈自訂應用程式的方式有兩種，使用方式取決於您取得應用程式的方式。 **本文著重於如何透過上傳開發人員傳送給您的應用程式套件 (.zip 格式) 來發佈自訂應用程式**。 另一個核准自訂應用程式的方法，會在當開發人員透過 Teams 應用程式提交 API 直接將應用程式提交到 [[管理應用程式]](manage-apps.md) 頁面時使用。 若要深入了解該方法，請參閱 [透過 Teams 應用程式提交 API 發佈自訂應用程式](submit-approve-custom-apps.md)。

本文提供端對端指導方針，說明如何將您的 Teams 應用程式從開發到部署到探索。 此指導方針著重於應用程式的 Teams 層面，適用於系統管理員和 IT 專業人員。 如需開發 Teams 應用程式的詳細資訊，請參閱 [Teams 開發人員文件](/microsoftteams/platform/)。

![從開發到部署的應用程式概觀。](media/upload-custom-apps.png)

## <a name="create-your-app"></a>建立您的應用程式

Microsoft Teams 開發人員平台可讓開發人員輕鬆整合您自己的應用程式與服務，以提升生產力、更快速地做出決策，以及針對現有內容和工作流程建立共同作業。 建置在 Teams 平台上的應用程式是 Teams 用戶端與您的服務和工作流程之間的橋樑，可將它們直接帶入共同作業平台的內容。 如需詳細資訊，請移至 [Teams 開發人員文件](/microsoftteams/platform/)。

## <a name="validate"></a>驗證

### <a name="get-the-app-package"></a>取得應用程式套件

當應用程式準備好在生產環境中使用時，開發人員應該產生應用程式套件。 他們可以使用 [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview)。 他們會將檔案以.zip 格式傳送給您。

Teams 市集中的所有應用程式都會通過必要的[應用程式驗證](overview-of-app-validation.md)，以符合全域 Teams 應用程式市集的品質和安全性標準。 此外，Microsoft 也強烈建議應用程式開發人員參與選用的[應用程式合規性計畫](overview-of-app-certification.md)，其代表提升合規性、安全性和隱私權控制。 如需詳細資訊，請參閱 [Teams 應用程式驗證指導方針](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)。

### <a name="allow-trusted-users-to-upload-custom-apps"></a>允許信任的使用者上傳自訂應用程式

若要驗證應用程式在您的生產租用戶中正常運作，您必須允許自己和/或信任的使用者在生產租用戶中上傳自訂應用程式。 您可以使用[應用程式設定原則](teams-app-setup-policies.md)來執行此動作。

> [!NOTE]
> 如果您對上傳應用程式到生產租用戶以進行驗證感到不自在，即使是您自己或信任的使用者，您也可以略過此步驟，然後依照[上傳](#upload)和[設定及管理](#set-up-and-manage)章節中的步驟，將未經驗證的應用程式發佈到貴組織的應用程式市集。 然後，將該應用程式的存取權限限制為僅您自己和您信任的使用者。 這些使用者就可以從貴組織的應用程式市集取得應用程式，以執行驗證。 應用程式經過驗證後，請使用相同的權限原則來開啟存取，並將應用程式推出以供生產使用。

若要允許信任的使用者上傳自訂應用程式，請遵循下列步驟：

1. 開啟 **[允許與自訂應用程式互動]** 的全組織設定。 若要執行此動作：

    1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**，然後選取 **[全組織應用程式設定]**。

    1. 在 **[自訂應用程式]** 底下，開啟 **[允許與自訂應用程式互動]**，然後按一下 **[儲存]**。

1. 關閉全域應用程式設定原則中的 **[上傳自訂應用程式]** 設定。 若要執行此動作：

    1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **[Teams 應用程式]** > **[設定原則]**，然後按一下 **[全域] (全組織預設)** 原則。

    1. 關閉 **[上傳自訂應用程式]**，然後按一下 **[儲存]**。

1. 建立新的應用程式設定原則，允許上傳自訂應用程式，並將它指派給您信任的使用者集合。 若要執行此動作：

    1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **[Teams 應用程式]** > **[設定原則]**，然後按一下 **[新增]**。 為新原則命名和描述，開啟 **[上傳自訂應用程式]**，然後按一下 **[儲存]**。

    1. 選取您建立的新原則，然後按一下 **[管理使用者]**。 搜尋使用者，按一下 **[新增]**，然後按一下 **[套用]**。 重複此步驟，將原則指派給所有您信任的使用者。

       ![[新增應用程式設定原則] 頁面的螢幕擷取畫面](media/manage-your-lob-apps-new-app-setup-policy.png)

這些使用者現在可以上傳應用程式資訊清單，以驗證應用程式在生產租用戶中是否正常運作。

## <a name="upload"></a>上傳

若要將應用程式提供給貴組織應用程式市集中的使用者，請上傳應用程式。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **[Teams 應用程式]** > **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 選取 **[上傳]**，按一下 **[上傳]**，選取您從開發人員收到的應用程式套件，然後選取 **[開啟]**。

   ![在系統管理中心上傳應用程式的螢幕擷取畫面。](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>設定及管理

### <a name="control-access-to-the-app"></a>控制應用程式的存取權

根據預設，貴組織中的所有使用者都可以存取貴組織應用程式市集中的應用程式。 若要限制及控制誰有權使用應用程式，您可以建立並指派應用程式權限原則。 若要深入了解，請參閱[管理 Teams 中的應用程式權限原則](teams-app-permission-policies.md)。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>釘選並安裝應用程式，以供使用者探索

根據預設，使用者必須前往貴組織的應用程式市集並瀏覽或搜尋應用程式，才能找到該應用程式。 若要讓使用者輕鬆存取應用程式，您可以將應用程式釘選到 Teams 中的應用程式列。 若要這麼做，請建立應用程式設定原則，並將它指派給使用者。 若要深入了解，請參閱[管理 Teams 中的應用程式設定原則](teams-app-setup-policies.md)。

### <a name="search-the-audit-log-for-teams-app-events"></a>搜尋 Teams 應用程式事件的稽核記錄

您可以搜尋稽核記錄來檢視貴組織的 Teams 應用程式活動。 若要深入了解稽核 Teams 活動，請參閱 [搜尋 Teams 中事件的稽核記錄](audit-app-management-activities.md)。

在您可以搜尋稽核記錄檔之前，您必須先在[安全性與合規性中心](https://sip.protection.office.com/homepage)中開啟稽核。 如需深入了解，請參閱[開啟或關閉稽核記錄](/microsoft-365/compliance/turn-audit-log-search-on-or-off)。 請記住，只有當您開啟稽核時，才能使用稽核資料。

## <a name="discover-and-adopt"></a>探索並採用

擁有該應用程式權限的使用者可以在貴組織的應用程式市集中找到它。 移至 [應用程式] 頁面上 **[為您的組織名稱 *建立]***，以尋找貴組織的自訂應用程式。

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="顯示針對組織發佈的自訂應用程式 Teams 市集的螢幕擷取畫面" lightbox="media/custom-app-lifecycle-discovery.png":::

如果您已建立並指派了應用程式設定原則，應用程式會釘選到 Teams 中的應用程式列，以便獲指派原則的使用者輕鬆存取。

## <a name="update"></a>更新

若要更新應用程式，開發人員必須依照 [建立您的應用程式](#create-your-app) 和 [驗證](#validate) 區段中的步驟進行。

您可以在 Microsoft Teams 系統管理中心的管理應用程式頁面上更新應用程式。 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **[Teams 應用程式]** > **[管理應用程式]**。 按一下應用程式名稱，然後按一下 **[更新]**。 這樣做會取代現有的應用程式，而且更新的應用程式仍會強制執行所有應用程式權限原則和應用程式設定原則。

### <a name="end-user-update-experience"></a>使用者更新體驗

在大多數情況下，當您完成應用程式更新後，新版本會自動向使用者顯示。 如需詳細資訊，請參閱 [使用者更新體驗](apps-update-experience.md)。

## <a name="remove"></a>移除

若要移除應用程式，請遵循下列步驟：

1. 登入 Teams 系統管理中心。
1. 前往 **[Teams 應用程式]** > **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)** 頁面。
1. 按一下應用程式名稱以開啟應用程式詳細資料頁面。
1. 在應用程式橫幅旁，選取 **[動作]** > **[刪除]**。
1. 在對話方塊中，選取 **[刪除]**。

## <a name="related-articles"></a>相關文章

* [透過 Teams 應用程式提交 API 發佈自訂應用程式](submit-approve-custom-apps.md)
* [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
* [在 Teams 中管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)
* [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
* [在 Teams 中管理應用程式設定原則](teams-app-setup-policies.md)
