---
title: 使用 Teams 應用程式提交 API 來提交及核准您的自訂應用程式
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
description: 瞭解如何在 Microsoft Teams 中使用 Teams 應用程式提交 API 來核准您提交的自訂應用程式。
ms.openlocfilehash: 2fb0ab6778a0704b0cb60faef0d0fd739351ee10
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958068"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>使用 Teams 應用程式提交 API 發佈提交的自訂應用程式

本文提供端對端指導方針，說明如何將您的 Teams 應用程式從開發到部署到探索。 您將概略瞭解 Teams 在整個應用程式生命週期中提供的連線體驗，以簡化如何在貴組織的 App 市集中開發、部署及管理自訂應用程式。

我們將涵蓋生命週期的每個步驟，包括開發人員如何使用 Teams 應用程式提交 API 將自訂應用程式直接提交到 Microsoft Teams 系統管理中心供您檢閱及核准、如何設定原則以管理組織中使用者的應用程式，以及使用者如何在 Teams 中探索這些應用程式。

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="從開發到部署的應用程式概觀。":::

此指導方針著重于應用程式的 Teams 層面，適用于系統管理員和 IT 專業人員。 如需開發 Teams 應用程式的相關資訊，請參閱 [Teams 開發人員檔](/microsoftteams/platform)。

> [!NOTE]
> 當您發佈自訂的 Teams 應用程式時，您可以在貴組織的 App Store 中供使用者使用。 發佈自訂應用程式的方式有兩種，使用方式取決於您取得應用程式的方式。 本文著重于如何核准及發佈開發人員透過 Teams 應用程式提交 API 提交的自訂應用程式。 當開發人員以.zip格式傳送應用程式套件給您時，會使用上傳自訂應用程式的其他方法。 若要深入瞭解該方法，請參閱 [上傳應用程式套件以發佈自訂應用程式](/microsoftteams/upload-custom-apps)。 GCC 租使用者無法使用核准的應用程式小工具。

> [!IMPORTANT]
> 此方法目前不適用於 GCC 環境。 在 GCC 中，使用 *上傳自訂應用程式* 的方法。

## <a name="develop"></a>開發

### <a name="create-the-app"></a>建立應用程式

Microsoft Teams 開發人員平臺可讓開發人員輕鬆整合您自己的應用程式與服務，以提升生產力、更快速地做出決策，以及針對現有內容和工作流程建立共同作業。 建置在 Teams 平臺上的應用程式是 Teams 用戶端與您的服務和工作流程之間的橋樑，可將它們直接帶入共同作業平臺的內容。 如需詳細資訊，請移至 [Teams 開發人員檔](/microsoftteams/platform)。

### <a name="submit-the-app"></a>提交應用程式

當應用程式在生產中準備就緒時，開發人員可以使用 Teams 應用程式提交 API 來提交應用程式，該應用程式可從[圖形 API](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)叫用、整合式開發環境 (IDE) ，例如 Visual Studio Code，或 Power Apps 和 Power Virtual Agents 等平臺。 這樣做可讓您在 Teams 系統管理中心的 [ [管理應用程式](/microsoftteams/manage-apps) ] 頁面上使用該應用程式，您可以在這裡檢閱及核准它。

[Microsoft Graph 建置的](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)Teams 應用程式提交 API 可讓貴組織在您選擇的平臺上進行開發，並自動化 Teams 上自訂應用程式的提交核准程式。

以下是此應用程式提交步驟在 Visual Studio Code 中的外觀範例：

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="在 Visual Studio Code 中提交應用程式。":::

請記住，這並不會將應用程式發佈到貴組織的 App Store。 此步驟會將應用程式提交到 Teams 系統管理中心，您可以在此核准該應用程式以發佈到貴組織的 App Store。

如需使用圖形 API提交應用程式的詳細資訊，請參閱[這裡](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)。

## <a name="notify"></a>通知

您可以開啟通知，讓您知道開發人員何時提交新的應用程式以供檢閱和核准。 開發人員提交應用程式更新時，您也會收到通知。 若要在 Teams 系統管理中心啟用應用程式提交通知，請移至 **通知&通知**  >  **[規則](https://admin.teams.microsoft.com/notifications/rules)**  >  **應用程式提交**，並藉由將狀態變更為 [**使用** 中] 來啟用規則。 此設定預設會關閉。 您必須是全域系統管理員或 Teams 系統管理員，才能開啟此設定。

開啟此設定之後，您會在名為 [**應用程式提交**] 的新頻道底下 **，于 [管理員通知] 和 [通知**] 小組中收到通知。 或者，您可以選擇現有的團隊和頻道，以將通知傳送到指定的團隊和頻道。 若要這樣做，請執行下列步驟：

1. 在 **應用程式提交規則中**，選取 [動作] 底下的 **[頻道通知****] 複** 選框。
1. 選擇 [ **選取頻道** ] 按鈕。
1. 搜尋要新增的團隊。
1. 搜尋要新增的頻道。
1. 選取 [ **套用]**。

   :::image type="content" source="media/channel-alert.png" alt-text="自訂頻道通知通知核取方塊。" lightbox="media/channel-alert.png":::

> [!NOTE]
> 選取 **[預設頻道通知**] 核取方塊，以接收應用程式提交通道中 **管理員通知和通知** 小組 **的通知**。

:::image type="content" source="media/default-channel-alert.png" alt-text="[預設頻道通知通知] 核取方塊。" lightbox="media/default-channel-alert.png":::

您也可以在選取 **[Webhook** ] 核取方塊後，指定公用 Webhook URL，來設定對外部 Webhook 的通知。 JSON 通知承載將會傳送至您的 Webhook URL。

:::image type="content" source="media/app-submission-notification.png" alt-text="應用程式提交通知。" lightbox="media/app-submission-notification.png":::

設定應用程式提交規則之後，您可以檢閱指定頻道中的通知卡片以查看應用程式詳細資料，並選取 [ **檢視詳細資料** ] 以在 Teams 系統管理中心開啟應用程式。

## <a name="validate"></a>驗證

Teams 系統管理中心中的 [[管理應用程式](/microsoftteams/manage-apps)] 頁面 (左側導覽畫面，移至 [ **[Teams 應用程式**  >  **] [管理應用程式**](https://admin.teams.microsoft.com/manage-apps)]) ，讓您檢視貴組織的所有 Teams 應用程式。 頁面頂端的 **[待核准** ] 小工具可讓您知道何時已提交自訂應用程式以供核准。

在表格中，新提交的應用程式會自動顯示 [**已提交**] 和 [**封鎖****狀態**] 的 **發佈狀態**。 您可以以遞減順序排序 **[發佈狀態** ] 欄，快速找到應用程式。

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="發佈狀態。" lightbox="media/custom-app-lifecycle-validate-app.png":::

按一下應用程式名稱以移至應用程式詳細資料頁面。 在 [ **關於] 索** 引標籤上，您可以檢視應用程式的相關詳細資料，包括描述、狀態、提交者及應用程式識別碼。

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="已提交應用程式的應用程式詳細資料頁面。" lightbox="media/custom-app-lifecycle-app-details.png":::

如需使用圖形 API檢查 **發佈狀態** 的詳細資訊，請參閱 [這裡](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true)。

## <a name="publish"></a>發佈

當您準備好讓應用程式可供使用者使用時，請發佈應用程式。

1. 登入 Teams 系統管理中心，並移至 **Teams 應用程式**  >  **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。
1. 選取應用程式名稱以移至應用程式詳細資料頁面，然後在 [ **發佈狀態** ] 方塊中選取 [ **發佈]**。

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="應用程式詳細資料頁面上的 [發佈] 按鈕。":::

發佈應用程式之後， **[發佈] 狀態** 會變更為 [ **已發佈** ]， **而 [狀態** ] 會變更為 [ **允許]**。

## <a name="set-up-and-manage"></a>設定及管理

### <a name="control-access-to-the-app"></a>控制應用程式的存取權

根據預設，貴組織中的所有使用者都可以存取貴組織 App 市集中的應用程式。 若要限制及控制誰有權使用應用程式，您可以建立並指派應用程式許可權原則。 若要深入了解，請參閱[管理 Teams 中的應用程式權限原則](teams-app-permission-policies.md)。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>釘選並安裝應用程式，讓使用者探索

根據預設，使用者必須前往貴組織的 App Store 並流覽或搜尋應用程式，才能找到該應用程式。 若要讓使用者輕鬆存取應用程式，您可以將應用程式釘選到 Teams 中的應用程式行。 若要這麼做，請建立應用程式設定原則，並將它指派給使用者。 若要深入了解，請參閱[管理 Teams 中的應用程式設定原則](teams-app-setup-policies.md)。

### <a name="search-the-audit-log-for-teams-app-events"></a>搜尋 Teams 應用程式事件的稽核記錄

您可以搜尋稽核記錄來檢視組織中的 Teams 應用程式活動。 若要深入瞭解如何搜尋稽核記錄，並查看已記錄在稽核記錄中的 Teams 活動清單，請參閱 [搜尋 Teams 中的事件稽核記錄](audit-log-events.md)。

在您可以搜尋稽核記錄檔之前，您必須先在[安全性與合規性中心](https://sip.protection.office.com/)中開啟稽核。 如需深入了解，請參閱[開啟或關閉稽核記錄](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true)。 請記住，只有當您開啟稽核時，才能使用稽核資料。

## <a name="discover-and-adopt"></a>探索並採用

擁有該應用程式許可權的使用者可以在貴組織的應用程式市集中找到它。 移至 [應用程式] 頁面上 **專為 *您的組織名稱* 建立**，以尋找貴組織的自訂應用程式。

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="顯示已發佈應用程式的 [應用程式] 頁面。" lightbox="media/custom-app-lifecycle-discovery.png":::

如果您建立並指派了應用程式設定原則，應用程式會釘選到 Teams 中的應用程式行，以便為獲指派原則的使用者輕鬆存取。

## <a name="update"></a>更新

若要更新應用程式，開發人員應繼續依照開發一節中的步驟 [進行](#develop) 。

當開發人員向已發佈的自訂應用程式提交更新時，您會在 [[管理應用程式](/microsoftteams/manage-apps)] 頁面的 **[擱置核准** 小工具] 中收到通知。 在表格中，應用程式的 **發佈狀態** 會設定為 **已提交更新**。 如果您開啟應用程式提交通知，您也會在 **應用程式提交** 通道下的 **管理員通知和通知** 小組中收到通知。 通知卡片上會有一個連結，可讓您直接前往 Teams 系統管理中心的應用程式。 如需有關如何開啟應用程式提交通知的詳細資訊，請參閱 [通知](#notify)。

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="顯示擱置要求和應用程式狀態的 [管理應用程式] 頁面。" lightbox="media/custom-app-lifecycle-update-submitted.png":::

若要檢閱及發佈應用程式更新：

1. 在 Teams 系統管理中心的左側導覽中，移至 **[Teams 應用程式**  >  **管理應用程式]**。
1. 按一下應用程式名稱以移至應用程式詳細資料頁面，然後選取 **[可用的更新]** 以檢閱更新的詳細資料。

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="應用程式詳細資料頁面。" lightbox="media/custom-app-lifecycle-update-app.png":::

1. 當您準備好時，請選取 **[發佈** ] 以發佈更新。 這樣做會取代現有的應用程式、更新版本號碼，並將 **發佈狀態** 變更為 **[已發佈]**。 已更新的應用程式仍會強制執行所有應用程式許可權原則和應用程式設定原則。

    如果您拒絕更新，繼承應用程式仍會維持發佈狀態。

請記住下列事項：

* 當應用程式獲得核准時，任何一個應用程式都可以提交更新給應用程式。 這表示其他開發人員，包括原本提交應用程式的開發人員，可以提交更新給應用程式。
* 當開發人員提交應用程式且要求擱置中時，只有同一個開發人員可以提交更新給應用程式。 其他開發人員只能在應用程式核准後提交更新。

如需使用圖形 API來更新應用程式的詳細資訊，請參閱[這裡](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true)。

## <a name="related-articles"></a>相關文章

* [上傳應用程式套件以發佈自訂應用程式](upload-custom-apps.md)
* [在 Microsoft Teams 系統管理中心管理您的應用程式](manage-apps.md)
* [在 Teams 中管理自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)
* [在 Teams 中管理應用程式權限原則](teams-app-permission-policies.md)
* [在 Teams 中管理應用程式設定原則](teams-app-setup-policies.md)
* [Teams 監控與警示](alerts/teams-admin-alerts.md)
* [適用于 Teams 應用程式的 Microsoft 圖形 API](alerts/teams-admin-alerts.md)
