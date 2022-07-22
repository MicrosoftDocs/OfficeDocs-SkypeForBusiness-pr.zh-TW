---
title: 在 Microsoft Teams 系統管理中心管理您的應用程式
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 瞭解如何管理 Teams 應用程式。 瞭解如何允許或封鎖應用程式、檢查組織層級狀態和應用程式屬性、上傳自訂應用程式，以及管理應用程式設定。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 5e1b5f53ba648d1096460572562b91397b74ab3b
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958058"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心管理 Teams 應用程式

您可以在 Teams 系統管理中心入口網站的 **Teams 應用程式** 頁面中管理貴組織的應用程式。 使用 [管理應用程式] 頁面來檢視和管理貴組織應用程式目錄中的所有 Teams 應用程式、滿足應用程式管理的重要使用案例、定義使用原則的應用程式存取權等等。

:::image type="content" source="media/manage-apps.png" alt-text="[管理應用程式] 頁面的螢幕擷取畫面。" lightbox="media/manage-apps.png":::

若要管理應用程式，您可以使用原則來控制使用者的許可權、應用程式安裝，以及上傳您在組織內建立的自訂應用程式。 若要瞭解原則，請參 [閱應用程式原則概觀](app-policies.md)。

若要使用 Teams 系統管理中心，您必須擁有全域管理員或 Teams 系統管理員角色。 如需詳細資料，請參閱 [Teams 系統管理員角色](./using-admin-roles.md) 和 [Microsoft 365 系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

> [!NOTE]
> Microsoft 365 政府社群雲端高 (GCCH) 或美國商務部 (DoD) Teams 部署中無法使用 [管理應用程式] 頁面。

在建立應用程式期間，開發人員會建立並新增應用程式識別碼至資訊清單檔案。 從欄設定啟用欄 `External app ID` 後，您可以在 [管理應用程式] 頁面上檢視此外部應用程式識別碼。 您也可以在自訂應用程式的應用程式詳細資料頁面上檢視。 識別碼僅適用于自訂應用程式。

## <a name="app-management-use-cases-and-the-available-interfaces"></a>應用程式管理使用案例和可用的介面

Teams 系統管理中心提供可完成大部分應用程式管理使用案例的選項。 此外，一些選項也可在相同入口網站的其他入口網站或不同的系統管理中心頁面中使用。

| 應用程式管理使用案例 | 連結至介面 | 文件 |
|:----|:----|:----|
| **在 Teams 系統管理中心** | | |
| 透過允許和封鎖應用程式，控制貴組織中的使用者可使用哪些應用程式。 您也可以上傳及核准自訂應用程式。 在此頁面上管理應用程式之後，您可以使用應用程式許可權和應用程式設定原則來設定貴組織 App 市集中特定使用者可使用的應用程式。 | [在 Teams 系統管理中心管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps) | 目前文章 |
| 應用程式許可權原則可控制您要提供給組織中 Teams 使用者的應用程式。 您可以使用全域 (組織) 預設原則並加以自訂，或者您可以建立一或多個原則來滿足貴組織的需求。 | [許可權原則](https://admin.teams.microsoft.com/policies/app-permission) | [管理應用程式許可權原則](teams-app-permission-policies.md) |
| 應用程式設定原則可控制如何使用 Teams 應用程式將應用程式提供給使用者。 使用全域 (組織的預設) 原則並加以自訂或建立自訂原則，並將它們指派給一組使用者。 | [設定原則](https://admin.teams.microsoft.com/policies/app-setup) | [管理應用程式設定原則](teams-app-setup-policies.md) |
| 您可以開發並上傳自訂應用程式做為應用程式套件，並在貴組織的 App Store 中提供這些應用程式。 | [管理應用程式] 中的全組織 [應用程式設定](https://admin.teams.microsoft.com/policies/manage-apps) | [管理自訂應用程式原則](teams-custom-app-policies-and-settings.md) |
| 您可以使用貴組織的標誌、自訂背景或色彩來自訂 Teams 應用程式存放區。 | [自訂市集](https://admin.teams.microsoft.com/policies/customize-appstore) | [自訂群組織的 App Store](customize-your-app-store.md) |
| Teams 應用程式使用方式報告會提供使用中哪些應用程式、作用中使用者及其他應用程式使用狀況資訊的相關資訊。 | [使用方式報告](https://admin.teams.microsoft.com/analytics/reports) | [Teams 應用程式使用方式報告](teams-analytics-and-reports/app-usage-report.md) |
| 您的使用者可以在主持會議或與來賓聊天時新增應用程式。 當來賓加入外部託管的會議或聊天時，他們也可以使用由來賓共用的應用程式。 系統會套用代管使用者組織的資料原則，以及該使用者組織所共用之任何協力廠商應用程式的資料共用做法。 | [外部存取](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [根據使用者類型而定之應用程式行為](non-standard-users.md) |
| 您可以使用來賓存取權，為組織外部人員提供應用程式及其他 Teams 功能的存取權，同時維持對公司資料的控制權。 | [來賓存取](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Teams 中的來賓存取](guest-access.md) |
| 更新原則是用來管理 Teams 和 Office 預覽版使用者，這些使用者將會在 Teams 應用程式中看到發行前版本或預覽功能。  | [Teams 更新原則](https://admin.teams.microsoft.com/policies/updatemanagement) | [Teams 公開預覽](public-preview-doc-updates.md) |
| **Teams 外部系統管理中心** | | |
| 在 Microsoft 365 系統管理中心 中管理協力廠商應用程式的授權和訂閱 | [Microsoft 365 系統管理中心](https://admin.microsoft.com/#/licenses) | [管理協力廠商應用程式訂閱](/microsoft-365/commerce/manage-saas-apps) |
| 稽核 Microsoft Purview 合規性入口網站 上的 Teams 應用程式事件。 | [審計](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Teams 活動](audit-app-management-activities.md) |
| 應用程式可透過三種方法授與貴組織及其資料的許可權：系統管理員同意所有使用者的應用程式、使用者授與同意應用程式，或是系統管理員整合應用程式並啟用自助存取，或直接將使用者指派給應用程式。 確認應用程式的 Graph 許可權。 確認使用者提供或系統管理員委派的許可權。 | [Azure AD 入口網站](https://aad.portal.azure.com/) | [檢閱授與應用程式的許可權](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>允許和封鎖應用程式

[管理應用程式] 頁面是您在組織層級允許或封鎖個別應用程式的地方。 此頁面會顯示所有可用的應用程式及其目前的組織層級應用程式狀態。 應用程式清單包含 Microsoft、協力廠商開發人員及組織內開發人員所提供的應用程式。

若要允許或封鎖應用程式：

1. 登入 Teams 系統管理中心。
1. 存取 **Teams 應用程式**  >  **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)** 頁面。
1. 從應用程式清單中選取應用程式。 您可以依應用程式名稱搜尋，然後選取它。
1. 選 **取 [允許** ] 或 **[封鎖]** 選項。

當您在 Teams 系統管理中心的 [ [管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps) ] 頁面上允許 (或封鎖) 應用程式時，貴組織中的所有使用者都能 (或封鎖) 。 此方法與應用程式許可權原則不同，上下文中允許 (或透過許可權原則封鎖) 應用程式，只會影響獲指派原則的特定使用者。

使用者只能在允許應用程式透過整個租使用者設定並透過許可權原則允許使用者時，才可以安裝和使用應用程式。

## <a name="manage-user-requests-to-unblock-apps"></a>管理使用者要求以解除封鎖應用程式

您可以檢視要求，讓封鎖的應用程式可供使用。 要求會傳送給 IT 系統管理員，IT 系統管理員可以在 Teams 系統管理中心檢視和管理使用者要求。

  :::image type="content" source="media/user-request.png" alt-text="提出封鎖應用程式核准的要求":::

### <a name="view-a-request"></a>檢視要求

 1. 登入 Teams 系統管理中心，然後選取 [[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)

    :::image type="content" source="media/requested-apps1.png" alt-text="已封鎖應用程式的使用者要求會顯示在 Teams 系統管理中心的標題為[使用者要求] 的欄中。" lightbox="media/requested-apps.png":::

 1. 若要檢視及檢查每個應用程式的要求數目，請在 [ **依使用者** 要求] 欄中排序要求。
 1. 選取您要解除封鎖的應用程式名稱，它會開啟應用程式詳細資料頁面。
 1. 選 **取 [管理要求** ]，並完成快顯對話方塊中顯示的步驟。 核准應用程式的步驟會根據用來封鎖它的方法而有所不同。

    * 如果應用程式使用許可權原則遭到封鎖，請修改 [許可權原則](teams-app-permission-policies.md)以允許應用程式。
    * 如果已封鎖所有使用者的應用程式， [請允許該應用程式](#allow-and-block-apps)。
    * 如果所有使用者都已封鎖所有應用程式，請修改 [整個組織的設定](#manage-org-wide-app-settings)。

 如果系統管理員允許應用程式，則不會通知使用者已處理他們的要求。 使用者必須流覽市集中的應用程式，以檢查應用程式是否已解除封鎖。

### <a name="dismiss-a-user-request"></a>解除使用者要求

 1. 選取您要關閉使用者要求的應用程式名稱。
 1. 選 **取 [管理要求** ]，然後選取 **[關閉對話方塊上的所有要求** ]。
 1. 當要求被關閉時，會將使用者要求重設為零。

  :::image type="content" source="media/reject.png" alt-text="已封鎖的應用程式拒絕。"border="true":::

如果系統管理員解除要求，則不會通知使用者已處理他們的要求。 使用者必須流覽市集中的應用程式，以檢查應用程式是否已解除封鎖。

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>允許被開發人員封鎖的應用程式

當開發人員將應用程式發佈到 Teams App Store 時，可能需要系統管理員來設定或自訂應用程式體驗。 系統管理員會在設定應用程式時為使用者提供體驗。

例如，Contoso 電子版是一種 ISV，可為 Microsoft Teams 建立技術支援中心應用程式。 Contoso Electronics 希望其客戶設定應用程式的特定屬性，讓當使用者與應用程式互動時，應用程式會如預期般運作。 系統管理員允許或封鎖應用程式之前，該應用程式會在 Teams 系統管理中心顯示為 **[被發行者封鎖** ]，而且根據預設，使用者會隱藏該應用程式。 在遵循發行者的指引來設定應用程式之後，您可以將狀態變更為 [ **允許**]，讓使用者使用此應用程式。

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Teams 系統管理中心的發行者狀態封鎖的螢幕擷取畫面。":::

## <a name="manage-org-wide-app-settings"></a>管理整個組織的應用程式設定

使用全組織應用程式設定來控制擁有 [F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) 的使用者是否能獲得量身打造的第一線應用程式體驗、使用者是否可以安裝協力廠商應用程式，以及使用者是否可以上傳或與您組織中的自訂應用程式互動。 全組織應用程式設定會控管所有使用者的行為，並覆寫指派給使用者的任何其他應用程式權限原則。 您可以使用這些原則來控制惡意或有問題的應用程式。

> [!NOTE]
> 若要瞭解如何在 Microsoft 365 政府版 - 政府社群雲端高 GCCH 和美國商務部 (DoD) Teams 部署中使用全組織應用程式設定，請參閱 [管理 Teams 中的應用程式許可權原則](teams-app-permission-policies.md)。

1. 在 [管理應用程式] 頁面上，選取 **[全組織應用程式設定]**。 然後您可以在窗格中設定您要的設定。

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="[管理應用程式] 頁面上 [全組織應用程式設定] 窗格的螢幕擷取畫面":::

1. 在 **[量身打造的應用程式**] 底下，關閉或開啟 **[顯示量身打造的應用程式]**。 開啟此設定時，擁有 [F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) 的使用者會獲得量身打造的一線應用程式體驗。 此體驗會為第一線工作人員釘選 Teams 中最相關的應用程式。 若要深入瞭解，請參閱 [為您的前線員工量身打造 Teams 應用程式](pin-teams-apps-based-on-license.md)。

    此功能適用于 F 授權。 未來將會支援其他授權類型。
1. 在 [第三方應用程式 **]** 下，關閉或開啟這些設定，以控制對第三方應用程式的存取權：

    * **允許第三方應用程式**：這會控制使用者是否可以使用第三方應用程式。 如果您關閉此設定，您的使用者將無法安裝或使用任何協力廠商應用程式，而這些應用程式的應用程式狀態會在表格中顯示為 [ **全封鎖的組織** ]。

        > [!NOTE]
        > 當 **[允許協力廠商應用程式** ] 關閉時，所有使用者仍會啟用 [外寄網路功能](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ，但您可以透過應用程式許可權原則允許或封鎖外寄 Webhook [應用程式](teams-app-permission-policies.md)，在使用者層級控制它們。 請注意，如果您有使用 [**允許特定應用程式並封鎖所有其他應用程式**] 設定的 **Microsoft** 應用程式現有應用程式許可權 [原則](teams-app-permission-policies.md)，而且您想要為使用者啟用外寄 Web 端子，請將外寄 Webhook 應用程式新增至清單中。

        > [!NOTE]
        > Teams 使用者可以在主持會議或與其他組織人員聊天時新增應用程式。 當他們加入由其他組織主持的會議或聊天時，他們也可以使用由其他組織人員共用的應用程式。 將會套用託管使用者組織的資料原則，以及該使用者組織共用的任何協力廠商應用程式的資料共用做法。

    * **預設允許發行到商店的任何新第三方應用程式**：這會控制發佈至 Teams 應用程式商店的新第三方應用程式是否會自動在 Teams 中提供使用。 您只能在允許第三方應用程式時設定此選項。

1. 在 [ **自訂應用程式]** 底下，關閉或開啟 **[允許與自訂應用程式互動]**。 此設定會控制使用者是否可以與自訂應用程式互動。 若要深入了解，請參閱[在 Teams 中管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。
1. 選 **取 [** 儲存為整個組織的應用程式設定] 以生效。

## <a name="related-article"></a>相關文章

* [從系統管理中心轉換期間管理 Teams 商務用 Skype](manage-teams-skypeforbusiness-admin-center.md)
