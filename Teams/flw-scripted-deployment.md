---
title: 為一線員工大規模佈建 Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: 使用指令碼為一線員工部署或佈建 Microsoft Teams 的指導方針。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: a650b116f3a558594a2177fc4d53f713cf5d90e1488205573d370c5dd7124c40
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347159"
---
# <a name="how-to-provision-teams-at-scale-for-frontline-workers"></a>如何為一線員工大規模佈建 Teams

您是否需要讓大量使用者快速加入 Microsoft Teams，並為他們設定簡化的使用體驗？ 逐步完成下列指示，您就可以快速佈建身分識別、設定小組，並指派所有相關原則來控制使用者的使用者體驗。

在本逐步解說中，您將了解如何：

- 建立大量使用者。
- 建立大量小組，並設定適當的頻道。
- 大規模指派授權。
- 建立適當的 Teams 訊息原則、應用程式設定原則和應用程式權限原則。
- 對大量使用者套用這些原則。
- 將大量使用者指派到指定的小組。

> [!NOTE]
> 如果您已檢閱此資訊，但仍覺得需要協助或有一些問題，則可以 [**按一下這裡**](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMDv-1voW9MqL7zkQ11DzBUREZaU1E0WEk5T0NYS0NDSkFMSDROUUdYMC4u)，以聯繫 White Glove Support。

## <a name="prerequisites"></a>必要條件

從[此位置](https://aka.ms/flwteamsscale)下載資產。

> [!IMPORTANT]
> 上述連結中的指令碼是 Microsoft 所提供的原始指令碼，您必須根據個別需求加以修改。

## <a name="technical-requirements"></a>技術需求

- 您的租用戶必須具備涵蓋 Microsoft Teams 的適當授權數量。 如果您還沒有這些授權，請參閱 [Teams 探索](teams-exploratory.md)，以取得免費的試用訂閱。
- 執行這些步驟的使用者必須已獲指派下列角色：全域系統管理員、使用者系統管理員及 Teams 服務系統管理員 (在 Azure AD 中)。
- 使用者必須有權在其本機電腦上安裝和設定軟體。

## <a name="step-by-step-process-overview"></a>逐步程序概觀

1. **設定您的環境**
    1. 從包含 PowerShell 指令碼範例和文件的 GitHub 存放庫下載
    1. 設定本機環境
    1. 設定認證
    1. 設定 PowerShell 模組和環境變數
1. **建立及設定小組**
    1. 建立團隊
    1. 建立團隊的步驟
    1. 為團隊建立頻道
1. **建立 Teams 原則**
    1. 建立 Teams 訊息原則
    1. 建立 Teams 應用程式設定原則
    1. 建立 Teams 應用程式權限原則
1. **使用者和安全性群組**
    1. 建立使用者和安全性群組
    1. 透過群組型授權將授權指派給使用者
1. **指派使用者和原則**
    1. 將使用者指派給小組
    1. 將 Teams 原則指派給使用者
    1. 選用：轉換群組成員資格類型
1. **測試與驗證**
    1. 以測試使用者的身分登入 Teams
    1. 檢查錯誤
    1. 錯誤處理
1. **深入閱讀**

## <a name="set-up-your-environment"></a>設定您的環境

下列步驟可讓您設定您的環境：

### <a name="download-from-the-github-repository-containing-sample-powershell-scripts-and-documentation"></a>從包含 PowerShell 指令碼範例和文件的 GitHub 存放庫下載

在您繼續進行之前，您必須先在[此位置](https://aka.ms/flwteamsscale)下載指令碼。

### <a name="configure-the-local-environment"></a>設定本機環境

設定本機環境變數，會允許使用相對路徑執行此處參考的指令碼。 rootPath 是您複製此存放庫的根目錄，且 tenantName 的格式為 **yourTenant.onmicrosoft.com** (不應包含 https)。

1. 開啟 PowerShell 工作階段，並瀏覽至複製的 Git 存放庫內的 scripts 資料夾。
1. 執行此指令碼 .\SetConfig.ps1 -tenantName [您的租用戶名稱] -rootPath "Git 存放庫根目錄的完整路徑"。

例如：.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"

### <a name="set-up-credentials"></a>設定認證

> [!IMPORTANT]
> 在這些指令碼中管理認證的方式，可能不適合您的使用，但易於變更，以符合您的需求。 請務必遵循公司用於保護服務帳戶和管理身分識別的標準和做法。

該指令碼會使用以 XML 檔案格式儲存在 $ENV:LOCALAPPDATA\keys 中的認證，也就是 AppData\Local 資料夾。 需要呼叫模組 **BulkAddFunctions.psm1** 中的 **Set-Creds** Helper 函數，以設定用來執行這些指令碼的認證。 此方式可讓您不再需要對所有服務端點進行驗證，同時在本機存放區中維護認證。 從每個指令碼內，系統會使用 Helper 函數 **Get-Creds** 來讀取適當認證，且這些認證會用來與各種服務連線。

呼叫 **Set-Creds** 時，系統會提示您提供要寫入 $ENV:LOCALAPPDATA\keys 的 XML 檔案名稱。 不同的服務可能有不同的認證。 例如，您可能會有用於 MicrosoftTeams、AzureAD 和 MSonline 的不同認證，在這種情況下，您可以執行 **Set-Creds** 一次以上，將每個認證檔案以對其本身有意義的名稱儲存。

範例：Set-Creds msol-cred.xml Set-Creds azuread-cred.xml Set-Creds teams-cred.xml

執行指令碼 **SetCreds.ps1** 以儲存您的認證。 系統會提示您「正在執行作業 "Export-Clixml"...」，請輸入 'Y' 來核准。

> [!NOTE]
> 用於認證的帳戶不可要求多重要素驗證 (MFA)。

下列範例說明各種指令碼如何使用已儲存的認證來進行驗證：

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = Get-Creds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

### <a name="configure-powershell-modules-and-environmental-variables"></a>設定 PowerShell 模組和環境變數

您必須安裝並連線到數個 PowerShell 模組，包括 Azure AD、MSAL、MSCloudUtils 和 MicrosoftTeams。

1. 在存放庫的 scripts 資料夾中，尋找 **ConfigurePowerShellModules.ps1**。
1. 從 PowerShell 中執行 **ConfigurePowerShellModules.ps1** 指令碼。

## <a name="create-and-set-up-teams"></a>建立及設定小組

為了與您的一線員工溝通與共同作業，您必須先建立一系列的小組，並為這些小組新增標準頻道，我們將在下一節中說明。

### <a name="create-teams"></a>建立團隊

小組是組織內人員、內容和工具的集合。 對於大部分以一線員工為中心的組織而言，最佳做法是以實體位置為中心來定位小組。 例如，為下列每一項建立一個小組：

- 商店
- 配送中心
- 製造廠
- 醫院
- 雜貨店

*最佳做法討論*：設計小組時，請務必記住 [Teams 限制和規格](limits-specifications-teams.md)。 對於較小的組織，可使用整個組織作為小組來簡化溝通工作，並讓實體位置結構變得更完整。 對其他組織來說，結構良好的實體位置小組命名慣例，有助於公司透過交叉發佈輕鬆地同時與多個小組通訊。 例如，若要以所有「美國」地區的團隊為目標，您可以搜尋名稱中有「美國」的所有 Teams，並對其進行交叉發佈。 您可以在[這裡](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)找到有關交叉發佈的詳細資訊。

#### <a name="steps-to-create-teams"></a>建立團隊的步驟

1. 在存放庫的 data 資料夾中，尋找 **TeamsInformation.csv** 檔案。
1. 使用您組織的特定資訊來更新 **TeamsInformation.csv** 檔案中的資訊。 請記住上述的最佳做法。
1. 尋找 **CreateTeams.ps1** 指令碼。
1. 從 PowerShell 中執行 **CreateTeams.ps1** 指令碼。

### <a name="create-channels-for-teams"></a>為團隊建立頻道

頻道是小組內的專用區段，可保存依特定主題、專案、分項等等而統整的交談。 每個小組都會自動取得「一般」頻道，但是您可以根據企業需求，在該處自訂您的結構。 例如，您的額外頻道結構可能包括：

- **製造** - 安全、產線 1、產線 2、公司通訊、訓練
- **雜貨** - 麵包、農產品、肉類、公司通訊、訓練
- **醫療保健** - 護士、醫生、加護病房 1、加護病房 2
- **飯店觀光** - 櫃台、維護、房務、停車和行李服務、公司通訊、訓練
- **零售** - 商店前方、商店後方、公司通訊、訓練

> [!NOTE]
> 頻道不應視為安全性界限。 這是您組織工人以進行共同作業的方式。

*最佳做法討論*：設計頻道結構時，請務必讓一切簡單，特別是當您想要讓許多使用者上手時。 避免針對每個狀況、角色或主題建立頻道，以將訓練的需求降至最低。 一開始最多挑選 3-5 個頻道。 您可以在需求增加時輕鬆地建立其他頻道。 事實上，您現在就可以獨自使用一般通道了！

#### <a name="steps-to-create-channels-for-teams"></a>建立小組頻道的步驟

1. 在存放庫的 scripts 資料夾中，尋找 **TeamsChannels.csv** 檔案。
1. 使用您組織的特定資訊來更新 **TeamsChannels.csv** 檔案。 請記住上述的最佳做法。
1. 在存放庫的 scripts 資料夾中，尋找 **CreateTeamsChannels.ps1**。
1. 從 PowerShell，執行 **CreateTeamsChannels.ps1** 指令碼。

## <a name="create-teams-policies"></a>建立 Teams 原則

如果您是系統管理員，您可以使用 Microsoft Teams 中的小組原則來控制您組織中使用者可看見和可執行的項目。 例如，您可以控制要將哪些應用程式釘選到桌面或網頁瀏覽器的左側滑軌，或行動裝置的底部工具列，以簡化加入大量使用者時的使用者體驗。 其中有些原則可使用 PowerShell 建立，但其他原則必須在 Teams 系統管理中心內手動建立。

*最佳做法討論*：針對下列每個原則，我們將選擇實際建立兩個原則：一個用於一線員工，一個用於一線管理者。 您可以根據自己的喜好，選擇建立任意數量的原則。 對大部分客戶而言，兩個是較佳的起點 (即使您一開始對每個群組都進行相同的設定)。 隨著您對 Teams 愈來愈熟悉，您可以選擇進一步區別他們的經驗，若已建立此兩個原則，則可讓此動作變得更簡單。

### <a name="create-teams-messaging-policies"></a>建立 Teams 訊息原則

管理原則是用來控制 Microsoft Teams 中使用者可用的聊天及頻道訊息功能。

*最佳做法討論*：雖然您可以使用自動建立的預設全域原則，但我們選擇使用下列步驟建立自訂原則，以便為一線管理者和一線員工提供更隱密、簡單且與眾不同的使用體驗。

#### <a name="steps-to-create-teams-messaging-policies"></a>建立 Teams 訊息原則的步驟

1. 在存放庫的 scripts 資料夾中，尋找 **TeamsMessagingPolicies.csv** 檔案。
1. 使用您組織的特定資訊更新 **TeamsMessagingPolicies.csv** 檔案。 您可以在[這裡](./messaging-policies-in-teams.md#messaging-policy-settings)找到一些不同選項的詳細資訊。
1. 在存放庫的 scripts 資料夾中，尋找 **CreateTeamsMessagePolicies.ps1**。
1. 從 PowerShell，執行 **CreateTeamsMessagePolicies.ps1** 指令碼。

### <a name="create-teams-app-setup-policies"></a>建立 Teams 應用程式設定原則

如果您是系統管理員，您可以使用應用程式設定原則來執行下列動作：

- 自訂 Teams 以強調對使用者而言最重要的應用程式。 您可以選擇要釘選的應用程式，並設定其顯示順序。 釘選應用程式可讓您展示組織中使用者所需的應用程式，包括由第三方或您組織開發人員所建立的應用程式。
- 控制使用者是否可以將應用程式釘選到 Teams。

應用程式會釘選到應用程式列。這是位於 Teams 桌面用戶端側邊和 Teams 行動用戶端 (iOS 和 Android) 底部的列。

|Teams 桌面用戶端  |         |Teams 行動用戶端  |
|---------|---------|---------|
|![將應用程式釘選到應用程式列的 Teams 桌面用戶端螢幕擷取畫面。](media/flw-teams-desktop-client.png)         |         |![將應用程式釘選到底部列的 Teams 行動用戶端螢幕擷取畫面。](media/flw-teams-mobile-client.png) |

*最佳做法討論*：您可以在 Microsoft Teams 系統管理中心管理應用程式設定原則。 這些原則無法使用 PowerShell 建立。 您可以使用全域 (預設為全組織) 原則或建立自訂原則，並指派給使用者。 除非您建立並指派自訂原則，否則您組織中的使用者將會自動獲派全域原則。 根據我們的目的，我們要為一線員工和一線管理者建立兩個新的原則，為他們提供更簡單且更精簡的體驗，以便輕鬆地同時加入大量使用者。 您可以選擇根據業務需求來自訂體驗。

#### <a name="create-the-frontline-manager-app-setup-policy"></a>建立一線管理者的應用程式設定原則

您可以根據業務需求來自訂下列設定。 我們已根據最佳做法選擇了一些建議選項，讓您可更輕鬆地加入大量新使用者。 如需詳細資訊，請按一下[這裡](teams-app-setup-policies.md)。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至  **[Teams 應用程式]** > **[設定原則]**。
2. 按一下  **[新增]**。  
3. 輸入原則的名稱和描述。 例如，一線管理者的應用程式設定原則。
    :::image type="content" source="media/flw-flm-app-setup-policy.png" alt-text="一線管理者應用程式設定原則範例名稱和描述的螢幕擷取畫面":::

4. 關閉 **[上傳自訂應用程式]**。
5. 關閉 **[允許使用者釘選]**。
    :::image type="content" source="media/flw-allow-user-pinning.png" alt-text="允許使用者釘選設定的螢幕擷取畫面":::

6. 如果尚未列出，請新增 **Shifts** 應用程式。 如需有關 Shifts 的詳細資訊，請按一下[這裡](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。
    :::image type="content" source="media/flw-add-pinned-apps.png" alt-text="新增釘選應用程式畫面，並顯示 Shifts 應用程式的 [新增] 按鈕的螢幕擷取畫面":::

7. 移除 [通話] 功能 (如果有的話)。移除此功能不會為使用者停用此功能，但會防止其顯示在應用程式列上，藉此簡化使用者體驗。
8. 按照下列順序排列應用程式，以指定應用程式在 Teams 應用程式列中的順序，然後按一下  **[儲存]**。

    - 活動
    - 聊天
    - Teams
    - 行事曆
    - 班次

    :::image type="content" source="media/flw-manager-pinned-apps.png" alt-text="依序列出的一線管理者應用程式的螢幕擷取畫面":::

#### <a name="create-the-frontline-worker-app-setup-policy"></a>建立一線員工的應用程式設定原則

您可以根據業務需求來自訂下列設定。 我們已根據最佳做法選擇了一些建議選項，讓您可更輕鬆地加入大量新使用者。 如需詳細資訊，請按一下[這裡](teams-app-setup-policies.md)。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至  **[Teams 應用程式]** > **[設定原則]**。
2. 按一下  **[新增]**。
3. 輸入原則的名稱和描述。 例如，一線員工的應用程式設定原則。
    :::image type="content" source="media/flw-flw-app-setup-policy.png" alt-text="一線員工應用程式設定原則範例名稱和描述的螢幕擷取畫面":::

4. 關閉 **[上傳自訂應用程式]**。
5. 關閉 **[允許使用者釘選]**。
    :::image type="content" source="media/flw-allow-user-pinning.png" alt-text="允許使用者釘選設定的螢幕擷取畫面":::

6. 如果尚未列出，請新增 **Shifts** 應用程式。 如需有關 Shifts 的詳細資訊，請按一下[這裡](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。

    :::image type="content" source="media/flw-add-pinned-apps.png" alt-text="新增釘選應用程式畫面，並顯示 Shifts 應用程式的 [新增] 按鈕的螢幕擷取畫面":::

7. 注移除 [會議] 和 [通話] (如果有的話)。移除這些功能不會為使用者停用這些功能，但會防止其顯示在應用程式列上，藉此簡化使用者體驗。
8. 按照下列順序排列應用程式，以指定應用程式在 Teams 應用程式列中的順序，然後按一下  **[儲存]**。
    - 活動
    - 聊天
    - Teams
    - 班次

    :::image type="content" source="media/flw-worker-pinned-apps.png" alt-text="依序列出的一線員工應用程式的螢幕擷取畫面":::

### <a name="create-teams-app-permission-policies"></a>建立 Teams 應用程式權限原則

身為系統管理員，您可以使用應用程式權限原則來控制組織中 Microsoft Teams 使用者可使用的應用程式。 您可以允許或封鎖所有應用程式，或是由 Microsoft、第三方和您組織發行的特定應用程式。 當您封鎖應用程式時，擁有原則的使用者將無法從 Teams 應用程式商店安裝該應用程式。 您必須是全域系統管理員或 Teams 服務系統管理員，才能管理這些原則。

*最佳做法討論*：您可以在 Microsoft Teams 系統管理中心管理應用程式設定原則。 這些原則無法使用 PowerShell 建立。 您可以使用全域 (預設為全組織) 原則或建立自訂原則，並指派給使用者。 除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。 根據我們的目的，我們要為一線員工和一線管理者建立兩個新的原則，為他們提供安全且更精簡的體驗，以便輕鬆地同時加入大量使用者。 當然，您可以選擇根據您的業務需求來自訂體驗。

#### <a name="create-the-frontline-manager-app-permission-policy"></a>建立一線管理者的應用程式權限原則

您可以根據業務需求來自訂下列設定。 以下是根據最佳做法提供的建議選項，可讓您更輕鬆地加入大量新使用者。 如需詳細資訊，請按一下[這裡](teams-app-permission-policies.md)。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至  **[Teams 應用程式]** > **[權限原則]**。
2. 按一下  **[新增]**。

    :::image type="content" source="media/flw-add-app-permission-policy.png" alt-text="新增應用程式權限原則頁面的螢幕擷取畫面":::

3. 輸入原則的名稱和描述。 例如，一線管理者的應用程式權限原則。
4. 在  **[Microsoft 應用程式]** 底下，選取 **[允許所有應用程式]**。
5. 在  **[第三方應用程式]** 底下，選取 **[允許所有應用程式]**。
6. 在 **[自訂應用程式]** 底下，選取 **[允許所有應用程式]**。
7. 按一下  **[儲存]**。

#### <a name="create-the-frontline-worker-app-permission-policy"></a>建立一線員工的應用程式權限原則

您可以根據業務需求來自訂下列設定。 以下是根據最佳做法提供的建議選項，可讓您更輕鬆地加入大量新使用者。 如需詳細資訊，請按一下[這裡](teams-app-permission-policies.md)。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至  **[Teams 應用程式]** > **[權限原則]**。
2. 按一下  **[新增]**。

    :::image type="content" source="media/flw-add-app-permission-policy.png" alt-text="新增應用程式權限原則頁面的螢幕擷取畫面":::

3. 輸入原則的名稱和描述。 例如，一線員工的應用程式權限原則。
4. 在  **[Microsoft 應用程式]** 底下，選取 **[允許所有應用程式]**。
5. 在  **[第三方應用程式]** 底下，選取 **[封鎖所有應用程式]**。
6. 在 **[自訂應用程式]** 底下，選取 **[允許所有應用程式]**。
7. 按一下  **[儲存]**。

## <a name="users-and-security-groups"></a>使用者和安全性群組

### <a name="create-users-and-security-groups"></a>建立使用者和安全性群組

若要在 Teams 中與大量使用者合作，您必須先在 Azure AD 中建立使用者。 佈建大量使用者的方法有很多種，但我們會著重說明以下內容：

- 如果這些使用者已存在於下列其中一個 HR 系統中，請使用下列連結來設定使用者佈建：
  - SAP 成功因素 - [教學課程：將 SAP SuccessFactors 設定為 Active Directory 使用者佈建](/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial)。
  - Workday - [教學課程：設定 Workday 以自動佈建使用者](/azure/active-directory/saas-apps/workday-inbound-tutorial)。
- 如果其他系統中有您的使用者資訊，請繼續執行下列步驟。

若要以更有效率的方式管理大量使用者，您必須為一線員工和一線管理者建立兩個安全性群組，並按照下列步驟，將這些使用者直接佈建到安全性群組中：

1. 在存放庫的 scripts 資料夾中，尋找 **Users.csv** 檔案。
1. 使用您組織的特定資訊來更新 **Users.csv** 檔案。
    1. 根據預設，我們提供的指令碼會建立一個使用者和暫時性密碼，第一次登入時必須變更此密碼。 如果您不想要使用預設密碼，請編輯 **CreateUsers.ps1** 指令碼，以符合您的需求。
    1. 請務必更新 SecurityGroup 欄位，以反映先前建立的適當名稱。
1. 在存放庫的 scripts 資料夾中，尋找 **SecurityGroups.csv** 檔案。
1. 使用您組織的特定安全性群組資訊更新 **SecurityGroups.csv** 檔案。
    1. 請務必更新 **[MessagePolicy]**、**[AppPermissionPolicy]** 和 **[AppSetupPolicy]** 欄位，以對應您之前建立的適當原則。
    1. 請務必更新 **[LicensePlan]** 欄位，以反映您要如何將授權提供給每位使用者。 如需產品名稱與服務方案識別碼的詳細資訊，請參閱[此處](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)的文件。
1. 從 PowerShell，執行資產中的 **CreateUsers.ps1** 指令碼。

### <a name="assign-licensing-to-users-via-group-based-licensing"></a>透過群組型授權將授權指派給使用者

Microsoft 付費雲端服務 (例如 Microsoft 365、Office 365、Enterprise Mobility + Security、Dynamics 365 及其他類似產品) 都需要授權。 這些授權會指派給需要存取這些服務的每位使用者。 若要管理授權，系統管理員可使用其中一個管理入口網站 (Office 或 Azure) 和 PowerShell Cmdlet。 Azure Active Directory (Azure AD) 是支援所有 Microsoft 雲端服務身分識別管理的基礎結構。 Azure AD 會儲存使用者授權指派狀態的相關資訊。

為了大規模啟用授權，Azure AD 目前已包含群組型授權，而且基於這個原因，我們已在本文前面建立了安全性群組。 您可以將一個或多個產品授權指派給群組。 Azure AD 可確保授權會指派給群組的所有成員。 任何加入群組的新成員都會獲派適當的授權。 如果成員離開該群組，授權也會移除。 此授權管理免除透過 PowerShell 自動化授權管理的必要，並根據每個使用者來反映組織和部門結構中的變更。

## <a name="assign-users-and-policies"></a>指派使用者和原則

### <a name="assign-users-to-teams"></a>將使用者指派給小組

既然您已經建立使用者並建立小組，您現在可以將所有使用者放在適當的小組中。

1. 在存放庫的 data 資料夾中，尋找 **Users.csv** 檔案，並確認您在此檔案中有與 Teams 的準確對應。
1. 透過 PowerShell，執行存放庫的 scripts 資料夾中的指令碼 **AssignUserstoTeams.ps1**。

### <a name="assign-teams-policies-to-users"></a>指派 Teams 原則給使用者

現在您已建立使用者和用來修改小組體驗的原則，接著您可以將這些原則指派給正確的使用者。

1. 在存放庫的 data 資料夾中，尋找 **SecurityGroups.csv** 檔案，並確認您有與群組準確對應的原則。
1. 透過 PowerShell，執行存放庫的 scripts 資料夾中的指令碼 **AssignPoliciestoUsers.ps1**。

### <a name="optional-convert-group-membership-type"></a>選用：轉換群組成員資格類型

> [!NOTE]
> 此步驟適合擁有 Azure AD P1 或更新版本的使用者。

取得 Azure AD P1 或更新版本授權時，您可以選擇使用動態群組成員資格，而非使用指派的成員資格。 建立 Teams 的指令碼也建立了成員資格類型為「已指派」的 Office 群組，這表示其成員必須明確地新增。

使用動態成員資格，其編寫的規則可用來判斷是否有人為團隊的成員。

> [!NOTE]
> 執行此指令碼時，系統會移除群組的目前成員資格 (其擁有者除外)，並且會在成員資格同步作業執行時加入新的成員。

1. 在存放庫的 data 資料夾中，尋找 **migrateGroups.csv** 檔案。
1. 將 CSV 檔案 **migrateGroups.csv** 更新為將進行移轉的群組，並加上用於動態成員資格的規則。
1. 在存放庫的 scripts 資料夾中，尋找 **ConvertGroupMembershipType.ps1** 檔案。
1. 從 PowerShell，執行指令碼 **ConvertGroupMembershipType.ps1**

## <a name="test-and-validate"></a>測試與驗證

### <a name="sign-in-to-teams-with-a-test-user"></a>以測試使用者的身分登入 Teams

既然您已經完成所有的步驟，您現在可以驗證您所完成的工作。

1. 建立的使用者所擁有的初始密碼位於 CreateUsers.ps1 中，而且必須在第一次登入時變更。
1. 確認 Teams 的外觀與風格是否與您所預期的相同。 如果不是，請檢閱 **[建立 Teams 原則]** 和 **[將 Teams 原則指派給使用者]** 區段。
1. 驗證使用者是否屬於正確的小組。 如果不是，請檢閱 **[建立及設定使用者]** 和 **[將使用者指派給小組]** 區段。

> [!NOTE]
> 如果一線員工佈建是透過您的身分識別和存取管理小組管理，您將必須遵循其用於提供員工認證的程序。

### <a name="check-for-errors"></a>檢查錯誤

當您執行較舊的指令碼時，系統會將錯誤或例外狀況寫入到位於存放庫複本 logs 資料夾中的 .csv 檔案。 您可以使用此檔案來調查可能發生的任何問題。

例如，如果您嘗試建立已存在於租用戶的小組，就可能會發生例外狀況。

1. 尋找 **[記錄]** 資料夾，然後檢視其中包含的任何 .csv 檔案。 如果沒有例外狀況，表示您可能無法在此找到例外狀況檔案。

### <a name="error-handling"></a>錯誤處理

這些範例指令碼中已實作最基本的錯誤處理。 有 try/catch 區塊，而如果觸發，我們會將錯誤儲存到 catch 區塊中的某個變數。 必須根據您的喜好執行其他錯誤處理。

## <a name="further-reading"></a>深入閱讀

- [新增小組頻道 (PowerShell)](/powershell/module/teams/new-teamchannel?view=teams-ps)
- [新增 Teams 訊息原則 (PowerShell)](/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)
- [在 Microsoft Teams 中將原則指派給使用者](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module)
- [使用 Office 365 PowerShell 指派授權和使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
