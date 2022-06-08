---
title: 在 Microsoft Teams 系統管理中心管理您的應用程式
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 瞭解如何在 Microsoft Teams 系統管理中心的 [管理應用程式] 頁面上管理您的 Teams 應用程式。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: c28dfafb4ef895f4eb6b958ba2ef7cca63b825b9
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947202"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心管理 Teams 應用程式

您可以在系統管理中心的 **Teams 應用程式** 中管理貴組織的應用程式。 使用 [ [管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps) 頁面來檢視和管理貴組織應用程式目錄中的所有 Teams 應用程式。 [管理應用程式] 頁面可讓您檢視租使用者目錄中所有可用的應用程式，為您提供決定要允許或封鎖整個組織之應用程式所需的資訊。 您可以查看應用程式的組織層級狀態和屬性、在組織層級封鎖或允許應用程式、將新的自訂應用程式上傳至您的租使用者目錄，以及管理整個組織的應用程式設定。

![[管理應用程式] 頁面的螢幕擷取畫面。](media/manage-apps.png)

若要使用 Teams 系統管理中心，您必須是全域系統管理員或 Teams 服務系統管理員。如需詳細資料，請參閱 [Teams 系統管理員角色](./using-admin-roles.md)。

若要管理應用程式，您可以使用原則來控制使用者的許可權、應用程式安裝，以及上傳您在組織內建立的自訂應用程式。 若要瞭解原則，請參 [閱應用程式原則概觀](app-policies.md)。

> [!NOTE]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

> [!NOTE]
> Microsoft 365 政府社群雲端高 (GCCH) 或美國商務部 (DoD) Teams 部署中無法使用 [管理應用程式] 頁面。

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>將自訂應用程式發佈到貴組織的 App 市集

使用 [管理應用程式] 頁面發佈專為貴組織打造的應用程式。 發佈自訂應用程式之後，您組織應用程式市集中的使用者就可以使用該應用程式。 有兩種方式可以將自訂應用程式發佈到貴組織的 App Store。 您使用的方式取決於取得應用程式的方式。

* [核准自訂應用程式](#approve-a-custom-app)：如果開發人員使用 Teams 應用程式提交 API 直接將應用程式提交到 [管理應用程式] 頁面，請使用此方法。 然後，您可以直接從應用程式詳細資料頁面檢閱及發佈 (或拒絕) 應用程式。
* [上傳應用程式套件](#upload-an-app-package)：如果開發人員以.zip格式傳送應用程式套件給您，請使用此方法。 您可以上傳應用程式套件來發佈應用程式。

### <a name="approve-a-custom-app"></a>核准自訂應用程式

[管理應用程式] 頁面上的 **[待核准** ] 小工具會在開發人員使用 Teams 應用程式提交 API 提交應用程式時通知您。 新提交的應用程式會列出 [**已提交**] 的 **發佈狀態** 和 [封鎖 **的狀態****]**。 移至應用程式詳細資料頁面以查看應用程式的詳細資訊，然後若要發佈，請將 **發佈狀態** 設為 **[發佈]**。

當開發人員提交自訂應用程式的更新時，您也會收到通知。 然後您可以檢閱及發佈 (或拒絕) 應用程式詳細資料頁面上的更新。 已更新的應用程式仍會強制執行所有應用程式許可權原則和應用程式設定原則。

若要深入瞭解，請參閱 [發佈透過 Teams 應用程式提交 API 提交的自訂應用程式](submit-approve-custom-apps.md)。

### <a name="upload-an-app-package"></a>上傳應用程式套件

開發人員使用 [Teams App Studio 建立 Teams 應用程式](/microsoftteams/platform/get-started/get-started-app-studio)套件，然後以.zip格式傳送給您。 當您有應用程式套件時，可以將它上傳到貴組織的 App Store。

若要上傳新的自訂應用程式，請選取 **[上傳** ] 以上傳應用程式套件。 應用程式上傳後不會醒目提示，因此您需要在 [管理應用程式] 頁面上搜尋應用程式清單才能找到它。

若要在應用程式上傳後更新，請在 [管理應用程式] 頁面上的應用程式清單中，選取應用程式名稱，然後選取 [ **更新]**。 這樣做會取代現有的應用程式，而所有應用程式許可權原則和應用程式設定原則仍會針對更新的應用程式強制執行。

若要深入瞭解，請參閱 [上傳應用程式套件以發佈自訂應用程式](upload-custom-apps.md)。

## <a name="allow-and-block-apps"></a>允許和封鎖應用程式

[管理應用程式] 頁面是您在組織層級允許或封鎖個別應用程式的地方。 它會顯示每個可用的應用程式及其目前的組織層級應用程式狀態。

若要允許或封鎖應用程式：

1. 移至 Teams 系統管理中心，>管理應用程式> Teams 應用程式。
1. 從應用程式清單中選取應用程式。
1. 選 **取 [允許** ] 或 **[封鎖]**。

當您在 [管理應用程式] 頁面上封鎖或允許應用程式時，該應用程式會遭到封鎖或允許給貴組織中的所有使用者。  當您在 Teams 應用程式許可權原則中封鎖或允許應用程式時，系統會封鎖或允許指派該原則的使用者使用。 若要讓使用者能夠安裝任何應用程式並與之互動，您必須在 [管理應用程式] 頁面上，以及指派給使用者的應用程式許可權原則中，允許組織層級的應用程式。

 > [!NOTE]
 > 若要卸載應用程式，請以滑鼠右鍵按一下應用程式，然後按一下 [ **卸載** ] 或使用左側的 [ **其他應用程式** ] 功能表。

## <a name="manage-user-requests-to-unblock-apps"></a>管理使用者要求以解除封鎖應用程式

您可以檢視要求，讓封鎖的應用程式可供使用。 要求會傳送給 IT 系統管理員，IT 系統管理員可以在 Teams 系統管理中心檢視和管理使用者要求。

  :::image type="content" source="media/user-request.png" alt-text="提出封鎖應用程式核准的要求":::

### <a name="view-a-request"></a>檢視要求

 1. 登入 Teams 系統管理中心，然後選取 [[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)

    :::image type="content" source="media/requested-apps1.png" alt-text="使用者要求" lightbox="media/requested-apps.png" border="true":::

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

如果系統管理員解除要求，就不會通知使用者他們的要求已處理。 使用者必須流覽市集中的應用程式，以檢查應用程式是否已解除封鎖。

## <a name="apps-blocked-by-publishers"></a>發行者封鎖的應用程式

當 ISV 將應用程式發佈到全域 App Store 時，可能需要系統管理員來設定或自訂應用程式體驗。 系統管理員可以在應用程式完全設定完成時，讓使用者使用。

例如，Contoso 電子版是一種 ISV，可為 Microsoft Teams 建立技術支援中心應用程式。 Contoso Electronics 希望其客戶設定應用程式的特定屬性，讓當使用者與應用程式互動時，應用程式會如預期般運作。 系統管理員允許或封鎖應用程式之前，系統會在 Teams 系統管理中心顯示為 **[被發行者封鎖** ]，而且根據預設，使用者會隱藏該應用程式。 在遵循發行者的指引來設定應用程式之後，您可以將狀態變更為 [ **允許**]，或將狀態變更為 [ **封鎖**] 來封鎖使用者，使其無法使用應用程式。

![在 Teams 系統管理中心被發行者狀態封鎖的螢幕擷取畫面。](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>將應用程式新增至小組

您可以使用 [ **新增至團隊** ] 按鈕來安裝應用程式至團隊。 請記住，這僅適用于可在小組範圍中安裝的應用程式。 [ **新增至小組** ] 按鈕不適用於只能在個人範圍中安裝的應用程式。

![[新增至團隊] 按鈕的螢幕擷取畫面。](media/manage-apps-add-app-team.png)

1. 搜尋您想要的應用程式，然後按一下應用程式名稱的左邊來選取應用程式。
1. 選取 **[新增至團隊]**。
1. 在 [ **新增至團隊** ] 窗格中，搜尋您要新增應用程式的團隊，選取該團隊，然後選取 [ **套用]**。

## <a name="customize-an-app"></a>自訂應用程式

您現在可以根據組織需求自訂應用程式，以包含特定的外觀與風格。 請參閱 [在 Teams 中自訂應用程式](customize-apps.md)。

## <a name="purchase-services-for-third-party-apps"></a>協力廠商應用程式的購買服務

您可以直接從 [管理應用程式] 頁面搜尋及購買貴組織中使用者協力廠商應用程式所提供的服務授權。 資料表中的 **[授權]** 欄會指出應用程式是否提供付費的 SaaS 訂閱。 選 **取 [立即購買** ] 以檢視方案和價格資訊，並為您的使用者購買授權。 若要深入瞭解，請參閱 [在 Microsoft Teams 系統管理中心為 Teams 協力廠商應用程式購買服務](purchase-third-party-apps.md)。

## <a name="grant-admin-consent-to-apps"></a>將系統管理員同意授與應用程式

您可以代表貴組織中的所有使用者，檢閱並要求許可權的應用程式並授與同意。 如此一來，使用者就不必在啟動應用程式時，檢閱並接受應用程式要求的許可權。 [ **許可權]** 欄會指出應用程式是否有需要同意的許可權。 您會看到在 Azure AD 中註冊的每個應用程式的 [檢 **視詳細資料** ] 連結，該應用程式具有需要同意的許可權。 若要深入瞭解，請參 [閱在 Microsoft Teams 系統管理中心檢視應用程式許可權並授與系統管理員同意](app-permissions-admin-center.md)。

## <a name="view-resource-specific-consent-permissions"></a>檢視資源特定的同意許可權

資源特定同意 (RSC) 許可權可讓團隊擁有者同意應用程式存取及修改團隊的資料。 RSC 許可權是精細的 Teams 特定許可權，可定義應用程式可在特定團隊中執行的動作。 您可以在應用程式詳細資料頁面的 [ **權** 限] 索引標籤上檢視 RSC 許可權。 若要深入瞭解，請參 [閱在 Microsoft Teams 系統管理中心檢視應用程式許可權並授與系統管理員同意](app-permissions-admin-center.md)。

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
