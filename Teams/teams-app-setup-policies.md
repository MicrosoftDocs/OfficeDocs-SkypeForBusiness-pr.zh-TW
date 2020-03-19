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
ms.openlocfilehash: 241a109a6d6a6809f3bcfe363884f6168e67ef12
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858686"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>在 Microsoft 團隊中管理 app 設定原則

> [!NOTE]
> 如果您已啟用整個組織內的應用程式設定，**允許與自訂應用程式互動**，您可能不會在 Microsoft 團隊系統管理中心看到 app 設定原則。 目前正在推出，且即將在您的組織中提供此功能。

以管理員身分，您可以使用應用程式設定原則來執行下列動作：

- 自訂小組，以醒目提示對您的使用者而言最重要的 app。 您可以選擇要釘選的 app，並設定它們出現的順序。 釘選應用程式可讓您展示貴組織中的使用者所需的應用程式，包括由協力廠商或貴組織中的開發人員所建立的 app。
- 控制使用者是否可以將 app 釘選到團隊。
- 代表使用者安裝應用程式 **（在 [預覽] 中）**。 您可以選擇在使用者開始團隊時預設會為使用者安裝哪些 app。 請記住，如果指派給他們的[app 許可權原則](teams-app-permission-policies.md)允許，使用者仍然可以自行安裝應用程式。

應用程式會釘選到應用程式行。 這是團隊桌面用戶端和團隊行動用戶端（iOS 和 Android）底部的列。

|團隊桌面用戶端  |團隊行動用戶端 |
|---------|---------|
|![顯示小組桌面用戶端的螢幕擷取畫面](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![顯示團隊行動用戶端的螢幕擷取畫面](media/app-setup-policies-mobile-app-bar.png)      |

若要查看其預先安裝的應用程式，請在應用程式行中，按一下 [使用者] **。** 團隊桌面及網頁用戶端中的其他應用程式，並在行動用戶端中向上滑動。

您可以在 Microsoft [團隊管理中心] 管理 app 設定原則。 您可以使用全域（組織範圍預設值）原則，或建立自訂原則，並將它們指派給使用者。 除非您建立並指派自訂原則，否則貴組織中的使用者會自動取得全域原則。 您必須是全域管理員或團隊服務系統管理員，才能管理這些原則。

您可以編輯全域原則中的設定，以包含您想要的 app。 如果您想要針對貴組織中不同的使用者群組自訂小組，請建立並指派一或多個自訂原則。 如果指派給使用者的是自訂原則，該原則會套用給使用者。 如果使用者未獲指派自訂原則，則全域原則會套用至使用者。

![顯示 [應用程式設定原則] 頁面的螢幕擷取畫面](media/app-setup-policies.png)

> [!NOTE]
> 如果您有教育版小組，請務必知道作業 app 預設會在全域原則中固定，即使您目前不會看到它列在全域原則中也一樣。 它將是團隊用戶端上固定應用程式清單中的第四個應用程式。

## <a name="create-a-custom-app-setup-policy"></a>建立自訂應用程式設定原則

您可以使用 Microsoft 團隊系統管理中心來建立自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **設定原則**]。
2. 按一下 [**新增**]。
    ![顯示 [新增應用程式設定原則] 頁面的螢幕擷取畫面](media/app-setup-policies-add.png)
3. 輸入原則的名稱和描述。
4. 開啟或關閉 [上**傳自訂應用程式**]，視您是否要讓使用者將自訂應用程式上傳至團隊而定。 如果 [**允許協力廠商應用**程式在[組織內的應用程式設定](manage-apps.md#manage-org-wide-app-settings)中關閉]，您將無法變更此設定。
5. 開啟或關閉 [**允許使用者釘**用]，視您是否要讓使用者將應用程式釘選到自己的應用程式行。
6. 若要為使用者安裝應用程式 **（在預覽中）**，請執行下列動作：

    1. 在 [**已安裝的 app**] 底下，按一下 [**新增 app**]。
    2. 在 [**新增已安裝的應用程式**] 窗格中，搜尋您想要在使用者開始團隊時自動安裝的應用程式。 您也可以依應用程式許可權原則篩選 app。 當您選取 app 清單後，請按一下 [**新增**]。

        ![顯示 [新增已安裝的應用程式] 窗格的螢幕擷取畫面](media/app-setup-policies-add-installed-apps.png)

7. 若要釘選應用程式，請執行下列動作：

    1. 在 [**固定應用程式**] 底下，按一下 [**新增應用程式**]。
    2. 在 [**新增釘選的應用程式**] 窗格中，搜尋您要新增的應用程式，然後按一下 [**新增**]。 您也可以依應用程式許可權原則篩選 app。 當您選擇要釘選的 app 清單時，請按一下 [**新增**]。

         ![顯示 [新增釘選的應用程式] 窗格的螢幕擷取畫面](media/app-setup-policies-add-apps.png)

    3. 依您希望它們出現在團隊中的順序排列應用程式，然後按一下 [**儲存**]。

        ![顯示 [固定的 app] 區段的螢幕擷取畫面](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>編輯應用程式設定原則

您可以使用 Microsoft 團隊系統管理中心來編輯原則，包括全域（組織範圍預設值）原則和您建立的自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **設定原則**]。
2. 按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。
3. 您可以從這裡進行所要的變更。
4. 按一下 [**儲存**]。

## <a name="assign-a-custom-app-setup-policy-to-users"></a>將自訂應用程式設定原則指派給使用者

您可以使用 Microsoft 團隊系統管理中心，將自訂原則指派給個別的使用者或商務用 Skype PowerShell 模組，將自訂原則指派給使用者群組，例如安全群組或通訊群組。

### <a name="assign-a-custom-app-setup-policy-to-users"></a>將自訂應用程式設定原則指派給使用者

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。
2. 按一下使用者名稱左邊的，然後按一下 [**編輯設定**]，選取使用者。
3. 在 [**應用程式設定原則**] 底下，選取您要指派的 App 設定原則，**然後按一下 [** 套用]。

若要一次將原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > **設定原則**]。
2. 按一下原則名稱左方，選取原則。
3. 選取 [**管理使用者**]。
4. 在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。 針對您要新增的每個使用者重複此步驟。
5. 完成新增使用者之後，請選取 [**儲存**]。

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>將自訂應用程式設定原則指派給群組中的使用者

您可能會想要將自訂應用程式設定原則指派給已識別的多個使用者。 例如，您可能會想要將原則指派給安全性群組中的所有使用者。 您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。 如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。

在這個範例中，我們會將名為「人力資源 App 設定」策略的自訂應用程式設定原則指派給 Contoso 製藥人力資源專案群組中的所有使用者。  

> [!NOTE]
> 請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。

取得特定群組的 GroupObjectId。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
取得指定群組的成員。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
將群組中的所有使用者指派給特定的 app 設定原則。 在這個範例中，它是 HR App 設定原則。
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.UserPrincipalName}
``` 
根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。

## <a name="faq"></a>常見問題集

### <a name="working-with-app-setup-policies"></a>使用應用程式設定原則

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Microsoft 團隊系統管理中心包含哪些內建應用程式設定原則？

- **全域（組織範圍預設值）**：除非您指派其他原則，否則此預設原則會套用到貴組織中的所有使用者。 編輯 [全域原則]，將最重要的 app 釘選到您的使用者。
- **FirstLineWorker**：此原則適用于第一線員工工作者。 您可以將它指派給貴組織中的第一線員工工作人員。 請務必注意，您所建立的自訂原則，您必須將原則指派給使用者，才能讓設定生效。 如需詳細資訊，請移至本文的將[自訂應用程式設定原則指派給 [使用者](#assign-a-custom-app-setup-policy-to-users)] 區段。

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>為什麼我無法在 [新增釘選的 app] 窗格中找到應用程式？

並非所有 app 都可透過應用程式設定原則釘選到團隊。 有些應用程式可能不支援此功能。 若要尋找可釘選的 app，請在 [**新增釘**選的 app] 窗格中搜尋應用程式。 具有個人範圍（靜態索引標籤）和 bot 的索引標籤可釘選到團隊桌面用戶端，而這些應用程式可在 [**新增固定的應用程式**] 窗格中取得。

請記住，[團隊] app 商店會列出所有團隊應用程式，而 [**新增固定應用程式**] 窗格只會包含可透過原則釘選至團隊的 app。 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>我是教育版管理員的團隊。關於 [教育版小組] 中的應用程式設定原則，我還需要知道什麼？

在教育版小組中無法使用通話應用程式。 當您建立新的自訂應用程式設定原則時，通話 app 會顯示在應用程式清單中。 不過，應用程式不會釘選到團隊用戶端與教育版小組，也不會在團隊中看到 [通話] 應用程式。

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>您可以將多少固定 app 新增至原則？

您至少必須將兩個 app 釘選到團隊行動用戶端（iOS 和 Android）。 如果原則的 app 少於兩個，行動用戶端不會反映原則設定，而是會繼續使用現有的設定。

您可以新增至原則的固定 app 數目沒有限制。

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>原則變更需要多少時間才能生效？

在您編輯全域原則或指派原則之後，變更才會生效24小時。

### <a name="user-experience"></a>使用者體驗

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>使用者如何在團隊中查看所有釘選的 app？

若要查看針對使用者釘選的所有 app，使用者可能必須執行下列動作，視已安裝的應用程式數量以及其小組用戶端視窗的大小而定。

|團隊桌面用戶端 |團隊行動用戶端 |
|---------|---------|
|在團隊側面的應用程式行中，按一下 **.。。其他應用程式**。| 在團隊底部附近的 [應用程式行] 中，向上滑動。|
|![在團隊桌面用戶端中顯示更多應用程式的螢幕擷取畫面](media/app-setup-policies-desktop-more-apps.png)<br>   |![在團隊行動用戶端中顯示更多應用程式的螢幕擷取畫面](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>關於小組行動體驗，我還需要知道什麼？

團隊行動用戶端（iOS 和 Android）目前不支援使用靜態索引標籤的個人 app。 根據原則中設定的應用程式，釘選到團隊行動用戶端的應用程式可能不會出現在小組行動用戶端中。 在行動用戶端上，個人機器人仍會出現在聊天中。

透過團隊行動用戶端，使用者將會看到核心團隊 app （例如活動、交談和團隊），而且您可以將某些協力廠商應用程式釘選到 Microsoft （例如倒班）。

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>使用者可以變更透過原則釘選的 app 順序嗎？

目前，使用者可以變更小組行動用戶端上的釘選 app 順序，但不能變更小組桌面或 web 用戶端上的應用程式。

### <a name="custom-teams-apps"></a>自訂團隊應用程式

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>我的組織已建立自訂團隊應用程式，並將其發佈至 AppSource 或租使用者目錄，但是當 app 釘選到 [團隊] 中的應用程式行時，應用程式圖示不會顯示為預期。 我要如何修正？

在提交 app 之前，請務必遵循標誌指導方針。 若要深入瞭解，請參閱[賣方儀表板提交的檢查清單](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)。 

 ## <a name="related-topics"></a>相關主題

- [在 Teams 中的應用程式系統管理設定](admin-settings.md)
