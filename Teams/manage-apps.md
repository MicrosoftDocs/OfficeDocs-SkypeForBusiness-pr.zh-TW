---
title: 在 Microsoft Teams 系統管理中心管理您的應用程式
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 瞭解如何管理 Teams 應用程式。 瞭解如何允許或封鎖應用程式、檢查組織層級狀態和應用程式屬性、上傳自訂應用程式，以及管理應用程式設定。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: ca49ca15b026048d2c495d30a51eac0f809244b5
ms.sourcegitcommit: ebffec34c050421dc8d09a16907644657ce323f4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2022
ms.locfileid: "67637046"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心管理 Teams 應用程式

您可以在 Microsoft Teams 系統管理中入口網站心的 **[Teams 應用程式]** 中管理貴組織的應用程式。 使用 [管理應用程式] 頁面來檢視和管理貴組織應用程式目錄中的所有 Teams 應用程式、滿足應用程式管理的重要使用案例、使用原則定義應用程式存取權等等。

:::image type="content" source="media/manage-apps.png" alt-text="[管理應用程式] 頁面的螢幕擷取畫面。" lightbox="media/manage-apps.png":::

若要管理應用程式，您可以使用原則來控制使用者的權限、應用程式安裝，以及上傳在貴組織內建立的自訂應用程式。 若要瞭解原則，請參閱 [應用程式原則概觀](app-policies.md)。

若要使用 Teams 系統管理中心，您必須擁有全域系統管理員或 Teams 系統管理員角色。 如需詳細資料，請參閱 [Teams 系統管理員角色](./using-admin-roles.md) 和 [Microsoft 365 系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

> [!NOTE]
> Microsoft 365 政府社群雲端高 (GCCH) 或美國國防部 (DOD) Teams 部署中無法使用 [管理應用程式] 頁面。

在建立應用程式期間，開發人員會建立並新增應用程式識別碼至資訊清單檔案。 從欄位設定啟用欄位 `External app ID` 後，您可以在 [管理應用程式] 頁面上檢視此外部應用程式識別碼。 您也可以在自訂應用程式的應用程式詳細資料頁面上檢視。 此識別碼僅適用於自訂應用程式。

## <a name="app-management-use-cases-and-the-available-interfaces"></a>應用程式管理使用案例和可用的介面

Teams 系統管理中心提供可完成大部分應用程式管理使用案例的選項。 此外，其他入口網站或 Teams 系統管理中心的不同頁面中也提供了一些選項。

下表包含系統管理中心支援的應用程式管理工作。

| 應用程式管理使用案例 | 連結至介面 | 文件 |
|:----|:----|:----|
| 透過允許和封鎖應用程式，控制貴組織中的使用者可使用哪些應用程式。 您也可以上傳及核准自訂應用程式。 在此頁面上管理應用程式之後，您可以使用應用程式權限和應用程式設定原則，來設定貴組織應用程式市集中特定使用者可用的應用程式。 | [在 Teams 系統管理中心管理 Teams](https://admin.teams.microsoft.com/policies/manage-apps) | 目前文章 |
| 應用程式權限原則可控制您要提供給組織中 Teams 使用者的應用程式。 您可以使用全域 (全組織) 預設值原則自訂，或者您可以建立一個或多個原則，以符合貴組織的需求。 | [權限原則](https://admin.teams.microsoft.com/policies/app-permission) | [管理應用程式權限原則](teams-app-permission-policies.md) |
| 應用程式設定原則可控制如何使用 Teams 應用程式將應用程式提供給使用者。 使用全域 (全組織) 預設值原則加以自訂或建立自訂原則，並將它們指派給一組使用者。 | [設定原則](https://admin.teams.microsoft.com/policies/app-setup) | [管理應用程式設定原則](teams-app-setup-policies.md) |
| 您可以開發並上傳自訂應用程式作為應用程式套件，並在貴組織的應用程式市集中提供這些應用程式。 | [[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps) 中的全組織應用程式設定 | [管理自訂應用程式原則](teams-custom-app-policies-and-settings.md) |
| 您可以使用貴組織的標誌、自訂背景或色彩來自訂 Teams 應用程式市集。 | [自訂市集](https://admin.teams.microsoft.com/policies/customize-appstore) | [自訂組織的應用程式市集](customize-your-app-store.md) |
| Teams 應用程式使用方式報告會提供哪些應用程式使用中、作用中使用者．及其他應用程式使用狀況資訊的相關資訊。 | [使用情況報告](https://admin.teams.microsoft.com/analytics/reports) | [Teams 應用程式使用報告 ](teams-analytics-and-reports/app-usage-report.md) |
| 使用者可以在主持會議或與其他來賓聊天時新增應用程式。 當他們加入由外部主持的會議或聊天時，他們也可以使用由來賓共用的應用程式。 將會套用主持使用者組織的資料原則，以及該使用者組織共用的任何協力廠商應用程式的資料共用做法。 | [外部存取](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [取決於使用者類型之應用程式行為](non-standard-users.md) |
| 使用來賓存取，您可以提供應用程式和其他 Teams 功能的存取權給組織外部人員，同時維持公司資料的控制權。 | [來賓存取](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Teams 中的來賓存取](guest-access.md) |
| Teams 更新原則是用來管理 Teams 和 Office 預覽版使用者，以便在 Teams 應用程式中查看發行前版本或預覽功能。 | [Teams 更新原則](https://admin.teams.microsoft.com/policies/updatemanagement) | [Teams 公開預覽](public-preview-doc-updates.md) |

下表提供其他入口網站支援的應用程式管理工作。

| 應用程式管理使用案例 | 連結至介面 | 文件 |
|:----|:----|:----|
| 在 Microsoft 365 系統管理中心管理協力廠商應用程式的授權和訂閱 | [Microsoft 365 系統管理中心](https://admin.microsoft.com/#/licenses) | [管理協力廠商應用程式訂閱](/microsoft-365/commerce/manage-saas-apps) |
| 稽核 Microsoft Purview 合規性入口網站上的 Teams 應用程式事件。 | [稽核](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Teams 活動](audit-app-management-activities.md) |
| 可透過三種方法授與應用程式貴組織及其資料的權限：系統管理員同意所有使用者的應用程式、使用者對應用程式授與同意，或是系統管理員整合應用程式並啟用自助存取，或直接將使用者指派給應用程式。 確認應用程式的圖表權限。 確認使用者提供或系統管理員委派的權限。 | [Azure AD 入口網站](https://aad.portal.azure.com/) | [檢閱授與應用程式的權限](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>允許和封鎖應用程式

[管理應用程式] 頁面是您在組織層級允許或封鎖個別應用程式的地方。 此頁面會顯示所有可用的應用程式及其目前的組織層級應用程式狀態。 應用程式清單包括 Microsoft、協力廠商開發人員和貴組織內開發人員提供的應用程式。

若要允許或封鎖應用程式：

1. 登入 Teams 系統管理中心並存取 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**
1. 從應用程式清單中選取應用程式。 您可以依應用程式名稱搜尋。
1. 選取 **[允許]** 或 **[封鎖]** 選項。

當您在 Teams 系統管理中心的 [[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps) 頁面上允許 (或封鎖) 應用程式時，貴組織中的所有使用者都允許 (或封鎖) 特定應用程式。 這個方法與透過權限原則允許 (或封鎖) 應用程式時的應用程式權限原則不同，只會影響獲指派該策略的特定使用者。

使用者只有在允許應用程式透過全租用戶設定並透過權限原則允許使用者時，才能安裝和使用應用程式。

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>允許被開發人員封鎖的應用程式

當開發人員將應用程式發佈至 Teams Store 時，一些應用程式可能需要系統管理員來設定應用程式。 設定完應用程式後，系統管理員向終端使用者提供應用程式。

例如，Contoso Electronics 是為 Microsoft Teams 建立技術支援中心應用程式的應用程式開發人員。 Contoso Electronics 希望其客戶設定應用程式的特定屬性，當使用者與應用程式互動時，應用程式可如預期般運作。 在系統管理員允許或封鎖應用程式之前，其會在 Teams 系統管理中心顯示為 **[已由發行者封鎖]**，而且預設對使用者隱藏。 在遵循發行者的指引設定應用程式之後，您可以將狀態變更為 **[允許]**，讓使用者使用此應用程式。

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Teams 系統管理中心的發行者狀態封鎖的螢幕擷取畫面。":::

如需開發人員在預設情況下如何封鎖應用程式的資訊，請參閱 [隱藏應用程式，直至系統管理員核准](/microsoftteams/platform/concepts/design/enable-app-customization#hide-teams-app-until-admin-approves)。

## <a name="manage-org-wide-app-settings"></a>管理全組織應用程式設定

使用全組織應用程式設定來控制擁有 [F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的使用者是否能獲得量身打造的第一線應用程式體驗、使用者是否可以安裝協力廠商應用程式，以及使用者是否可以上傳或與您組織中的自訂應用程式互動。 全組織應用程式設定會控管所有使用者的行為，並覆寫指派給使用者的任何其他應用程式權限原則。

> [!NOTE]
> 若要瞭解如何在 Microsoft 365 政府版 - 政府社群雲端高 GCCH 和美國國防部 (DOD) Teams 部署中使用全組織應用程式設定，請參閱 [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)。

1. 在 **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)** 頁面上，選取 **[全組織應用程式設定]**。 然後，您可以在窗格中設定所需的設定。

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="[管理應用程式] 頁面上 [全組織應用程式設定] 窗格的螢幕擷取畫面":::

1. 在 **[量身打造的應用程式]**，關閉或開啟 **[顯示量身打造的應用程式]**。 將此設定開啟時，具有 [F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的使用者會獲得量身打造的前端應用程式體驗。 此體驗會在適用於前線員工的 Teams 中釘選最相關的應用程式。 若要深入了解，請參閱 [為您的前線員工量身打造 Teams 應用程式](pin-teams-apps-based-on-license.md)。

    此功能適用於 F 授權。 未來將會支援其他授權類型。
1. 在 [第三方應用程式 **]** 下，關閉或開啟這些設定，以控制對第三方應用程式的存取權：

    * **允許第三方應用程式**：這會控制使用者是否可以使用第三方應用程式。 如果您關閉此設定，您的使用者將無法安裝或使用任何協力廠商應用程式，而這些應用程式的應用程式狀態會在表格中顯示為 **[全組織封鎖]**。

        > [!NOTE]
        > 當 **[允許協力廠商應用程式]** 關閉時，[[外寄 Webhook]](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) 仍會對所有使用者啟用，但您可以透過 [應用程式權限權原則](teams-app-permission-policies.md)允許或封鎖外寄 Webhook 應用程式，在使用者層級控制它們。 請注意，如果您有對 **Microsoft 應用程式** 使用 **[允許特定應用程式並封鎖所有其他應用程式]** 設定的現有 [應用程式權限原則](teams-app-permission-policies.md)，而且您想要為使用者啟用外寄 Webhook，請將外寄 Webhook 應用程式新增至清單中。

        > [!NOTE]
        > Teams 使用者可以在主持會議或與其他組織人員聊天時新增應用程式。 當他們加入由其他組織主持的會議或聊天時，他們也可以使用由其他組織人員共用的應用程式。 將會套用託管使用者組織的資料原則，以及該使用者組織共用的任何協力廠商應用程式的資料共用做法。

    * **預設允許發行到商店的任何新第三方應用程式**：這會控制發佈至 Teams 應用程式商店的新第三方應用程式是否會自動在 Teams 中提供使用。 您只能在允許第三方應用程式時設定此選項。

1. 在 **[自訂應用程式]** 下，關閉或開啟 **[允許與自訂應用程式互動]**。 此設定控制使用者是否可以與自訂應用程式互動。 若要深入了解，請參閱[在 Teams 中管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。
1. 選取 **[儲存]**，讓全組織應用程式設定生效。

## <a name="related-article"></a>相關文章

* [從商務用 Skype 系統管理中心轉換期間管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
* [管理允許應用程式的使用者要求](user-requests-approve-apps.md)。
