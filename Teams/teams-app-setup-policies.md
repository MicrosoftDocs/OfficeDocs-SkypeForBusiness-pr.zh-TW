---
title: 在 Microsoft 團隊中管理 app 設定原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中針對貴組織的使用者使用及管理 app 設定原則。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: d3928bd15ab5b023c025024f2dbf05c404adeee6
ms.sourcegitcommit: fae47764336b47c65e9e24b9abd6fe23ad9fc1a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341099"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>在 Microsoft 團隊中管理 app 設定原則

> [!NOTE]
> 如果您已啟用整個組織內的應用程式設定， **允許與自訂應用程式互動**，您可能不會在 Microsoft 團隊系統管理中心看到 app 設定原則。 目前正在推出，且即將在您的組織中提供此功能。

做為管理員，您可以使用應用程式設定原則來執行下列工作：

- 自訂 Teams 以強調對使用者而言最重要的應用程式。 您可以選擇要釘選的 app，並設定它們出現的順序。 釘選應用程式可讓您展示貴組織中的使用者所需的 app，包括由協力廠商或貴組織中的開發人員所建立的應用程式。
- 控制使用者是否可以將應用程式釘選到 Teams。
- ** (在預覽) 中**代表使用者安裝應用程式。 您可以選擇在使用者開始團隊時預設會為使用者安裝哪些 app。 請記住，如果指派給他們的 [app 許可權原則](teams-app-permission-policies.md) 允許，使用者仍然可以自行安裝應用程式。

應用程式會釘選到應用程式行，這是位於團隊桌面用戶端的列，而在團隊行動用戶端 (iOS 和 Android) 。

|團隊桌面用戶端  |團隊行動用戶端 |
|---------|---------|
|![團隊桌面用戶端](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![團隊行動用戶端](media/mobile-app-ui.png)      |

若要查看其預先安裝的應用程式，請在應用程式行中，使用者選取 **.。。** 團隊桌面及網頁用戶端中的其他應用程式，並在行動用戶端中向上滑動。

您可以在 Microsoft [團隊管理中心] 管理 app 設定原則。 使用全域 (組織範圍的預設) 原則，或建立並指派自訂原則。  除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。 您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。

您編輯全域原則中的設定，以包含您想要的 app。 若要針對貴組織中不同群組的使用者自訂小組，請建立並指派一或多個自訂原則。

![[應用程式設定原則] 頁面](media/app-setup-policies.png)

> [!NOTE]
> 如果您有教育版小組，請務必知道作業 app 預設會在全域原則中固定，即使您目前不會看到它列在全域原則中也一樣。 它將是團隊用戶端上固定應用程式清單中的第四個應用程式。

## <a name="create-a-custom-app-setup-policy"></a>建立自訂應用程式設定原則

您可以使用 Microsoft 團隊系統管理中心來建立自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **設定原則**]。
2. 選取 [ **新增**]。
    ![[新增應用程式設定原則] 頁面](media/app-setup-policies-add.png)
3. 輸入原則的名稱和描述。
4. 開啟或關閉 [上 **傳自訂應用程式**]，視您是否要讓使用者將自訂應用程式上傳至團隊而定。 如果 [ **允許協力廠商應用** 程式在 [組織內的應用程式設定](manage-apps.md#manage-org-wide-app-settings)中關閉]，您就無法變更此設定。
5. 開啟或關閉 [ **允許使用者釘**用]，視您是否要讓使用者將應用程式釘選到自己的應用程式行。
6. 若要為使用者安裝應用程式 ** (在預覽) 中 **，請執行下列工作：

    1. 在 [ **已安裝的 app**] 底下，選取 [ **新增 app**]。
    2. 在 [ **新增已安裝的應用程式** ] 窗格中，搜尋您想要在使用者開始團隊時自動安裝的應用程式。 您也可以依應用程式許可權原則篩選 app。 當您選取 app 清單後，請選取 [ **新增**]。

        ![[新增已安裝的應用程式] 窗格](media/app-setup-policies-add-installed-apps.png)

7. 若要釘選應用程式，請執行下列動作：

    1. 在 [ **固定應用程式**] 底下，選取 [ **新增應用程式**]。
    2. 在 [ **新增釘選的應用程式** ] 窗格中，搜尋您要新增的應用程式，然後選取 [ **新增**]。 您也可以依應用程式許可權原則篩選 app。 當您選擇要釘選的 app 清單時，請選取 [ **新增**]。

         ![[新增釘選的 app] 窗格](media/app-setup-policies-add-apps.png)

    3. 依您希望它們出現在團隊中的順序排列 app，然後選取 [ **儲存**]。

        ![[釘選的 app] 區段](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>編輯應用程式設定原則

您可以使用 Microsoft 團隊系統管理中心來編輯原則，包括全域 (組織內的預設) 原則，以及您建立的自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **設定原則**]。
2. 按一下原則名稱左邊的，然後選取 [ **編輯**]，選取原則。
3. 您可以從這裡進行所要的變更。
4. 選取 [ **儲存**]。

## <a name="assign-a-custom-app-setup-policy-to-users"></a>將自訂應用程式設定原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a>常見問題集

### <a name="working-with-app-setup-policies"></a>使用應用程式設定原則

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft 團隊系統管理中心包含哪些內建應用程式設定原則

- **全域 (組織範圍的預設) **：此預設原則適用于貴組織中的所有使用者，除非您指派其他原則。 編輯 [全域原則]，將最重要的 app 釘選到您的使用者。
- **FirstLineWorker**：此原則適用于第一線員工工作者。 您可以將它指派給貴組織中的第一線員工工作人員。 請務必注意，您所建立的自訂原則，您必須將原則指派給使用者，才能讓設定生效。 如需詳細資訊，請移至本文的將 [自訂應用程式設定原則指派給 [使用者](#assign-a-custom-app-setup-policy-to-users) ] 區段。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>為什麼我無法在 [新增釘選的 app] 窗格中找到應用程式

並非所有 app 都可透過應用程式設定原則釘選到團隊。 有些應用程式可能不支援此功能。 若要尋找可釘選的 app，請在 [ **新增釘** 選的 app] 窗格中搜尋應用程式。 具有個人作用中的索引標籤 (靜態] 索引標籤可釘選到 [ **新增釘選的應用程式** ] 窗格中，) 和 bot 都可以固定在小組桌面用戶端。

請記住，[團隊] app store 會列出所有團隊應用程式。 [ **新增釘** 選的 app] 窗格只會包含可透過原則釘選至團隊的 app。

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>我是教育版管理員的團隊。在教育版團隊中，關於 app 設定原則，我需要知道什麼？

在教育版小組中無法使用通話應用程式。 當您建立新的自訂應用程式設定原則時，通話 app 會顯示在應用程式清單中。 不過，應用程式不會釘選到團隊用戶端與教育版小組，也不會在團隊中看到 [通話] 應用程式。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>可將多少固定 app 新增至原則

必須將兩個 app 全部釘選至團隊行動用戶端 (iOS 和 Android) 。 如果原則的 app 少於兩個，行動用戶端不會反映原則設定，而是會繼續使用現有的設定。

您可以新增至原則的固定 app 數目沒有限制。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>原則變更要花多久時間才能生效

在您編輯或指派原則之後，可能需要幾個小時的時間，變更才會生效。

### <a name="user-experience"></a>使用者體驗

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>使用者如何在團隊中查看所有釘選的 app

若要查看針對使用者釘選的所有 app，使用者可能必須執行下列動作，視已安裝的應用程式數量以及其小組用戶端視窗的大小而定。

|團隊桌面用戶端 |團隊行動用戶端 |
|---------|---------|
|在團隊側面的應用程式行中，選取 **.。。其他應用程式**。| 在團隊底部附近的 [應用程式行] 中，向上滑動。|
|![團隊桌面用戶端中的其他應用程式](media/app-setup-policies-desktop-more-apps.png)<br>   |![團隊行動用戶端中的其他應用程式](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>我需要知道的關於小組行動體驗的相關資訊

 (iOS 和 Android) 的小組行動用戶端目前不支援使用靜態索引標籤的個人 app。 根據原則中設定的應用程式，釘選到團隊行動用戶端的應用程式可能不會出現在小組行動用戶端中。 在行動用戶端上，個人機器人仍會出現在聊天中。

透過團隊行動用戶端，使用者將會看到核心團隊 app （例如活動、交談和團隊），而且您可以將某些協力廠商應用程式釘選到 Microsoft （例如倒班）。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>使用者可以變更透過原則釘選的 app 順序

如果開啟 [ **允許使用者釘** 選] 選項，使用者就可以變更其在團隊桌面和行動用戶端上的固定 app 順序。 使用者無法在團隊 web 用戶端變更其固定應用程式的順序。

#### <a name="does-user-pinning-take-precedence"></a>使用者釘選優先

如果指派給使用者的 app 設定原則已變更為 [封鎖使用者 app 釘選]，小組會移除任何釘選到應用程式行的應用程式。 如果隨後將原則變更為 [允許使用者 app 釘選]，使用者就必須重新固定其先前釘駐留的 app。

### <a name="custom-teams-apps"></a>自訂團隊應用程式

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>我的組織已建立自訂團隊應用程式，並將其發佈至 AppSource 或租使用者目錄，但是當 app 釘選到 [團隊] 中的應用程式行時，應用程式圖示不會顯示為預期。 如何修正此問題

在提交 app 之前，請務必遵循標誌指導方針。 若要深入瞭解，請參閱 [賣方儀表板提交的檢查清單](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。

## <a name="related-topics"></a>相關主題

[在 Teams 中的應用程式系統管理設定](admin-settings.md)

[指派策略給小組中的使用者](assign-policies.md)
