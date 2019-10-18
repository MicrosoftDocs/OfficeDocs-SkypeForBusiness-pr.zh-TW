---
title: 安裝與 Microsoft 團隊的 Moodle 整合
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: 瞭解如何安裝和設定 Microsoft 團隊的 Moodle 整合應用程式
keywords: 團隊 Moodle 應用程式整合外掛程式
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c6e2d8cfb4e3932d4559a5c5c7b618189da7e57
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572055"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>安裝 Moodle 整合與 Microsoft 團隊

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/)是世界上最流行和開放來源學習管理系統（LMS）現已與 Microsoft 團隊整合！ 此整合可協助教師和教師在 Moodle 課程上共同作業、在團隊內提出有關其成績與作業的問題，並隨時掌握更新通知。

為了協助 IT 管理員輕鬆地設定此整合，我們已更新我們的開放來源 Office 365 Moodle 外掛程式，並提供下列功能：

* 使用 Azure AD 自動註冊您的 Moodle 伺服器。
* 按一下即可將 Moodle Assistant bot 部署到 Azure。
* 自動為團隊自動進行調配，或選取 Moodle 課程的自動同步處理小組註冊。
* 自動將 [Moodle] 索引標籤和 Moodle 助理 bot 安裝至每個同步處理的小組。 （即將推出）
* 按一下即可將 Moodle 應用程式發佈到您的私人小組 App 存放區。 （即將推出）

若要深入瞭解此整合提供的功能，請移至[這裡](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle)。

## <a name="prerequisites"></a>先決條件

若要安裝和設定此應用程式，您需要：

1. Moodle 管理員認證
2. Azure AD 管理員認證
3. Azure 訂閱您可以在中建立新資源

## <a name="step-1-install-the-office-365-moodle-plugin"></a>步驟1：安裝 Office 365 Moodle 外掛程式

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft 團隊中的 Moodle 整合是由開放來源[Office 365 Moodle 外掛程式集](https://github.com/Microsoft/o365-moodle)所支援。 若要在您的 Moodle 伺服器中安裝外掛程式：

1. 首先，請下載[Office 365 外掛程式集](https://moodle.org/plugins/pluginversions.php?plugin=local_o365)，然後將它儲存到您的本機電腦。 您必須使用版本3.5 或更新版本。
    * 安裝 local_o365 外掛程式也會安裝[auth_oidc](https://moodle.org/plugins/auth_oidc)和[boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams)外掛程式。
1. 以系統管理員身分登入您的 Moodle 伺服器，然後從左側導覽面板中選取 [**網站管理**]。
1. 選取 [**外掛程式**] 索引標籤，然後按一下 [**安裝外掛程式**]。
1. 在 [**從 ZIP 檔案安裝外掛程式**] 區段底下，按一下 [**選擇**檔案] 按鈕。
1. 從左側導覽中選取 [**上傳**檔案] 選項，流覽到上述您下載的檔案，然後按一下 [**上傳此**檔案]。
1. 再次從左側導覽面板中選取 [**網站管理**] 選項，即可返回您的系統管理儀表板。 向下滾動至 [**本機外掛程式**]，然後按一下 [ **Microsoft Office 365 整合**] 連結。 保持這個設定頁面在其他瀏覽器索引標籤中開啟，因為您將在整個程式的其餘部分中使用它。

您可以在[Moodle 檔](https://docs.moodle.org/34/en/Installing_plugins)中找到有關如何安裝 Moodle 外掛程式的詳細資訊。

**重要注意事項：** 讓 Office 365 Moodle 外掛程式設定頁面在其他瀏覽器索引標籤中開啟，因為您會在整個程式中返回這組頁面。

*還沒有 Moodle 網站嗎？* 您可能會想要查看 Azure 存放庫上的 Moodle，讓您可以快速地[在 azure 上](https://github.com/azure/moodle)部署 Moodle 實例，並根據您的需求加以自訂。

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>步驟2：設定 Office 365 外掛程式與 Azure Active Directory 之間的連線

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

接下來，您將需要在您的 Azure Active Directory 中將 Moodle 註冊為應用程式。 我們提供 PowerShell 腳本以協助您完成此程式。 PowerShell 腳本會為您的 Office 365 租使用者提供新的 Azure AD 應用程式，而 Office 365 Moodle 外掛程式會使用此應用程式。 此腳本將為您的 O365 租使用者提供應用程式，為已設定的應用程式設定所有必要的回復 Url 和許可權，並傳回 AppID 與 Key。 您可以在 O365 Moodle 外掛程式設定頁面中使用產生的 AppID 和 Key，以使用 Azure AD 設定您的 Moodle 伺服器。 如果您想要查看 PowerShell 腳本自動化的詳細手動步驟，您可以在外掛程式的完整[檔](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)中找到這些步驟。

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Microsoft 團隊資訊流程的 [Moodle] 索引標籤

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Microsoft 團隊資訊流程的 [Moodle] 索引標籤圖例" />

1. 從 [Microsoft Office 365 整合外掛程式] 頁面 slect [**設定**] 索引標籤。
1. 按一下 [**下載 PowerShell 腳本**] 按鈕，並將它儲存到您的本機電腦。
1. 您必須從 ZIP 檔案準備 PowerShell 腳本。 若要執行此動作：
    * 下載並解壓縮`Moodle-AzureAD-Powershell.zip`檔案。
    * 開啟 [提取的資料夾]。
    * 在檔案上`Moodle-AzureAD-Script.ps1`按一下滑鼠右鍵，然後選取 [**屬性**]。
    * 在 [屬性] 視窗的 **[一般**] 索引卷`Unblock`標底下，選取底部 [**安全性**] 屬性旁的方塊。
    * 按一下 [確定]****。
    * 複製解壓縮資料夾的目錄路徑。
1. 接下來，您將以系統管理員身分執行 PowerShell：
    * 按一下 [開始]。
    * 輸入 PowerShell。
    * 以滑鼠右鍵按一下 [Windows PowerShell]。
    * 按一下 [以系統管理員身分執行]。
1. 輸入`cd ...\...\Moodle-AzureAD-Powershell`目錄路徑，以流覽至解壓縮`...\...`後的目錄。
1. 執行 PowerShell 腳本的方式如下：
    * Enter `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`。
    * Enter `.\Moodle-AzureAD-Script.ps1`。
    * 在快顯視窗中登入您的 O365 系統管理員帳戶。
    * 輸入 Azure AD 應用程式的名稱（例如 Moodle/Moodle 外掛程式）。
    * 輸入您 Moodle 伺服器的 URL。
    * 複製腳本產生的**應用程式識別碼**和**應用程式金鑰**並儲存。
1. 接下來，您需要將識別碼和金鑰新增至 Office 365 Moodle 外掛程式。 回到 [外掛程式管理] 頁面（網站管理 > 外掛程式 > Microsoft Office 365 整合）。
1. 在 [**設定**] 索引標籤上，新增您先前複製的**應用程式識別碼**和**應用程式金鑰**，然後按一下 [**儲存變更**]。
1. 在頁面重新整理之後，您現在應該會看到一個新區段，**選擇 [連接方法**]。 按一下標示為 [**預設**] 的核取方塊，然後再次按一下 [**儲存變更**]。
1. 在頁面重新整理之後，您會看到另一個新的「管理員同意」一節， **& 其他資訊**。
    * 按一下 [**提供管理員同意**] 連結，輸入您的 Office3 365 全域系統管理員認證，然後**接受**以授與許可權。
    * 按一下 [ **AZURE AD 租**使用者] 欄位旁**的 [偵測] 按鈕。**
    * 在商務用**ONEDRIVE URL**旁邊，按一下 [偵測 **] 按鈕。**
    * 填寫完欄位之後，再按一下 [**儲存變更**] 按鈕。
1. 按一下 [**更新**] 按鈕以驗證安裝，然後再按 [**儲存變更**]。
1. 接下來，您將需要在 Moodle 伺服器與 Azure Active Directory 之間同步處理使用者。 視您的環境而定，您可能會在此階段選取不同的選項。 請注意，您在這裡設定的設定將會與每個 Moodle cron 執行（通常是一天一次）一起執行，以保持所有同步處理。若要開始使用：
    * 切換到 [**同步處理設定]** 索引標籤
    * 在 [**與 AZURE AD 同步處理使用者**] 區段中，選取適用于您的環境的核取方塊。 您通常會選取至少：
        * 在 Moodle 中為 Azure AD 中的使用者建立帳戶
        * 針對 Azure AD 中的使用者更新 Moodle 中的所有帳戶
    * 在 [**使用者建立限制**] 區段中，您可以設定篩選來限制將同步處理到 Moodle 的 Azure AD 使用者。
    * [**使用者欄位對應**] 區段可讓您自訂 Azure AD 以 Moodle 使用者設定檔欄位對應。
    * 在 [**團隊同步**處理] 區段中，您可以選擇在現有的 Moodle 課程中自動建立群組（亦即小組）。
1. 若要驗證 cron 作業（並在您想要在第一次執行時手動執行），請按一下 [**同步處理使用者與 AZURE AD** ] 區段中的 [**排程任務管理] 頁面**連結。 這會將您帶到 [**排程的任務**] 頁面。
    * 向下滾動並找出 [**與 AZURE AD 作業同步處理使用者**]，然後按一下 [**立即執行**]。
    * 如果您選擇根據現有課程建立群組，您也可以在**Office 365 工作中執行 [建立使用者] 群組**。
1. 回到外掛程式管理頁面（網站管理 > 外掛程式 > Microsoft Office 365 整合），然後選取 [**團隊設定**] 頁面。 您必須設定一些安全性設定，才能啟用團隊 app 整合。
    * 若要啟用 OpenID Connect，請按一下 [**管理驗證**] 連結，然後在**OpenID 連接**線上按一下 [眼睛] 圖示（如果它是灰色的）。
    * 接下來，您將需要啟用框架內嵌。 按一下 [ **HTTP 安全性**] 連結，然後按一下 [**允許框架嵌入**] 旁的核取方塊。
    * 下一步是啟用可啟用 Moodle API 功能的 web 服務。 按一下 [**高級功能**] 連結，然後確認已核取 [**啟用 web 服務**] 旁的核取方塊。
    * 最後，您必須啟用 Office 365 的外部服務。 按一下 [**外部服務**] 連結，然後：
        * 按一下 [ **Moodle Office 365 Webservices** ] 列上的 [**編輯**]。
        * 標示為 [**啟用**] 旁的核取方塊，然後按一下 [**儲存變更**]。
    * 接下來，您將需要編輯已驗證的使用者許可權，才能允許他們建立 web 服務權杖。 按一下**編輯角色的 [已驗證使用者**] 連結。 向下滾動並找出 [**建立 web 服務標記**] 功能並標示 [**允許**] 核取方塊。

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>步驟3：將 Moodle Assistant Bot 部署到 Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Microsoft 團隊的免費 Moodle 小幫手 Bot 可協助教師與學生在 Moodle 中回答其課程、作業、成績及其他資訊的相關問題。 Bot 也會在小組中傳送 Moodle 通知給學生和教師。 此 bot 是由 Microsoft 所維護，且[可在 GitHub 上](https://github.com/microsoft/Moodle-Teams-Bot)取得的開放來源專案。

> [!NOTE]
> 在此區段中，您會將資源部署至 Azure 訂閱，所有資源都將使用**免費**的層級進行設定。 視您的 bot 使用方式而定，您可能需要縮放這些資源。
> 如果您只想使用 [Moodle] 索引標籤而不使用 bot，請跳至[步驟 4](#step-4-deploy-your-microsoft-teams-app)。

### <a name="moodle-bot-information-flow"></a>Moodle bot 資訊流程

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Microsoft 團隊資訊流程的 Moodle bot 圖例" />


若要安裝 bot，您必須先在[Microsoft 身分識別平臺](https://identity.microsoft.com/Landing)上註冊。 這可讓您的 Bot 針對您的 Microsoft 端點進行驗證。 若要註冊您的 bot：

1. 回到外掛程式管理頁面（網站管理 > 外掛程式 > Microsoft Office 365 整合），然後選取 [**團隊設定**] 索引標籤。
1. 按一下 [ **Microsoft 應用程式註冊入口網站**] 連結，然後使用您的 Microsoft Id 登入。
1. 輸入您 app 的名稱（例如 MoodleBot），然後按一下 [**建立**] 按鈕。
1. 複製**應用程式識別碼**，並將它貼到 [**團隊設定**] 頁面上的 [ **Bot 應用程式識別碼**] 欄位。
1. 按一下 [**產生新密碼**] 按鈕。 複製產生的密碼，並將它貼到 [**小組設定**] 頁面上的 [ **Bot 應用程式密碼**] 欄位。
1. 滾動至表單底部，然後按一下 [**儲存變更**]。

現在您已經產生您的應用程式識別碼和密碼，就可以開始將您的機器人部署到 Azure 了。 按一下 [**部署到 Azure** ] 按鈕，然後使用必要的資訊（Bot 應用程式識別碼、Bot 應用程式密碼及 Moodle 密碼）填寫表單，並**在 [** **設定**] 頁面上輸入 Azure 資訊。. 填寫完表單後，請按一下核取方塊以接受條款與條件，然後按一下 [**購買**] 按鈕（所有 Azure 資源都會部署至免費層）。

完成資源部署至 Azure 之後，您必須使用它的訊息端點來設定 Office 365 Moodle 外掛程式。 首先，您必須從 Azure 中的 Bot 取得端點。 若要執行此動作：

1. 如果您還沒有，請登入[Azure 入口網站](https://portal.azure.com)。
2. 在左窗格中，選取 [**資源群組**]。
3. 從清單中選取您剛剛使用（或建立）的資源群組（在部署 Bot 時）。
4. 從群組資源清單中選取 [ **WebApp Bot** ] 資源。
5. 從 **[概覽**] 區段複製**訊息端點**。
6. 在 Moodle 中，開啟 Office 365 Moodle 外掛程式的 [**團隊設定**] 頁面。
7. 在**Bot [端點**] 欄位中，貼上您剛剛複製的 URL，並將 [*訊息*] 變更為 [ *webhook*]。 URL 現在看起來像這樣`https://botname.azurewebsites.net/api/webhook`
8. 按一下 [**儲存變更**]
9. 儲存變更之後，請回到 [**團隊設定**] 索引標籤上，按一下 [**下載資訊清單**檔案] 按鈕，並將資訊清單套件儲存至您的電腦（您將在下一節中使用它）。

## <a name="step-4-deploy-your-microsoft-teams-app"></a>步驟4：部署您的 Microsoft 團隊應用程式

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

現在您已將 Bot 部署至 Azure，並將其設定為與您的 Moodle 伺服器進行交談，那就是部署 Microsoft 團隊 app 的時候了。 若要這樣做，您將會載入您從上一個步驟的 [Office 365 Moodle 外掛程式小組設定] 頁面下載的資訊清單檔案。

您必須先確認已啟用應用程式的外部 app 和側載，才能安裝應用程式。 若要這樣做，您可以依照下列[步驟](https://docs.microsoft.com/en-us/MicrosoftTeams/admin-settings)進行。 確認已啟用外部應用程式後，您可以遵循下列步驟來部署您的應用程式。

1. 開啟 Microsoft 團隊。
2. 按一下導覽列左下角的 [**商店**] 圖示。
3. 從選項清單中按一下 [**上傳自訂應用程式**] 連結。 *注意：* 如果您是以全域管理員身分登入，您可以選擇將應用程式上傳到貴組織的 app store，否則您將只能針對您所屬的團隊載入應用程式（"側載"）。
4. 選取您`manifest.zip`先前下載的套件，然後按一下 [**儲存**]。 如果您尚未下載資訊清單套件，您可以從 Moodle 中的 [外掛程式設定] 頁面的 [**團隊設定**] 索引標籤執行此操作。

現在您已安裝應用程式，您可以將索引標籤新增至您有權存取的任何頻道。 若要執行此動作，請流覽至頻道**+** ，按一下符號，然後從清單中選取您的 app。 依照提示完成將您的 [Moodle 課程] 索引標籤新增至頻道。

就是這樣！ 您和您的小組現在可以直接從 Microsoft 團隊開始使用您的 Moodle 課程。

若要與我們共用任何功能要求或意見反應，請造訪我們的[使用者語音頁面](https://microsoftteams.uservoice.com/forums/916759-moodle)。