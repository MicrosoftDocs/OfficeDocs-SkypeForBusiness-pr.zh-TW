---
title: 安裝與 Microsoft Teams 的 Moodle 整合
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: 瞭解如何在 MICROSOFT Teams 的 LMS (中) 和設定 Moodle 開放來源學習管理系統。
keywords: Teams Moodle App 整合外掛程式
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d547d3c811f499faee5727634068a7807566293
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948709"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>安裝與 Microsoft Teams 的 Moodle 整合

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/)是 LMS (中最受歡迎的) 系統，現在已與 Microsoft Teams 整合！ 此整合可協助授課者和教師圍繞 Moodle 課程共同作業、詢問成績和作業相關問題，以及隨時更新通知 ，就在 Teams 中！

為了協助 IT 系統管理員輕鬆設定此整合，我們已使用下列功能更新開放來源 Moodle 外掛程式：

* 使用 Azure AD 自動註冊 Moodle 伺服器。
* 一鍵將 Moodle 小幫手 Bot 部署到 Azure。
* 針對所有團隊自動提供團隊和自動同步處理團隊註冊，或選取 Moodle 課程。
* 自動將 Moodle 定位停駐點和 Moodle 小幫手 Bot 自動安裝至每個同步的團隊。  (即將推出) 
* 一鍵將 Moodle App 發佈至您的私人 Teams App Store。  (即將推出) 

若要深入瞭解此整合提供的功能，請參閱安裝與 Microsoft Teams 的 [Moodle 整合](/microsoftteams/platform/resources/moodleinstructions)。

## <a name="prerequisites"></a>必要條件

若要安裝和設定此應用程式，您需要：

1. Moodle 系統管理員認證
2. Azure AD 系統管理員認證
3. 您可以在中建立新資源的 Azure 訂閱

## <a name="step-1-install-the-moodle-plugin"></a>步驟 1：安裝 Moodle 外掛程式

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft Teams 中的 Moodle 整合是由開放來源 [Moodle 外掛程式集所提供](https://github.com/Microsoft/o365-moodle)。 若要在您的 Moodle 伺服器中安裝外掛程式：

1. 首先，下載 [Moodle 外掛程式集，](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) 並將其儲存到您的本地電腦。 您必須使用版本 3.5 或更新版本。
    * 安裝local_o365外掛程式也會安裝auth_oidc boost_o365Teams外掛程式。 [](https://moodle.org/plugins/auth_oidc) [](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams)
1. 以系統管理員的登錄您的 Moodle 伺服器，然後從左側流覽 **面板** 選取網站管理。
1. 選取 [ **外掛程式>** 選項卡，然後按一下 [ **安裝外掛程式**> 。
1. 在 [ **從 ZIP 檔案安裝外掛程式** > 區段下，按一下 [ **選擇檔案>** 按鈕。
1. 從左側 **流覽** 選取 [上傳檔案選項，流覽上方下載的檔案，然後按一下 **[上傳此檔案**> 。
1. 再次 **從左側流覽面板** 選取網站管理選項，以返回您的系統管理儀表板。 向下卷起至 **[本地外掛程式** ，然後按一下 **Microsoft Office 365 整合連結** 。 在個別的瀏覽器選項卡中保持此組式頁面開啟，因為您將在整個程式的其餘部分使用。

您可以在 Moodle 檔中找到如何安裝 [Moodle 外掛程式的更多資訊](https://docs.moodle.org/34/en/Installing_plugins)。

**重要注意事項：** 讓 Microsoft 365 或 Office 365 Moodle 外掛程式設定頁面在個別的瀏覽器索引鍵中保持開啟，因為您將在整個過程中回到這組頁面。

*還沒有 Moodle 網站？* 您可能會想要查看 Azure 上的 [Moodle，](https://github.com/azure/moodle) 您可以在 Azure 上快速部署 Moodle 實例，並根據您的需求進行自訂。

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>步驟 2：設定 Microsoft 365 或 Office 365 外掛程式與 Azure Active Directory 之間的連接

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

接下來，您需要將 Moodle 註冊為 Azure Active Directory 中的應用程式。 我們已提供 PowerShell 腳本，可協助您完成此程式。 PowerShell Script 會為 Microsoft 365 或 Office 365 組織提供新的 Azure AD 應用程式，由 Moodle 外掛程式使用。 腳本會針對您的 Microsoft 365 或 Office 365 租使用者設定應用程式、設定所設定應用程式的所有必要的回復 URL 和許可權，並退回 AppID 和 Key。 您可以在 Moodle 外掛程式設定頁面中使用產生的 AppID 和 Key 來設定您的 Moodle 伺服器與 Azure AD。 如果您想要查看 PowerShell 腳本自動化的詳細手動步驟，您可以在外掛程式的完整檔中 [找到這些步驟](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)。

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Microsoft Teams 資訊流程的 Moodle Tab

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Microsoft Teams 資訊流程的 Moodle 定位停駐點圖例" />

1. 從 Microsoft 365 或 Office 365 整合外掛程式頁面，選取設定 **選項卡** 。
1. 按一下 [ **下載 PowerShell 腳本>** 按鈕，並將其儲存到您的本地電腦。
1. 您必須從 ZIP 檔案準備 PowerShell 腳本。 若要這麼做：
    * 下載並解壓縮 `Moodle-AzureAD-Powershell.zip` 檔案。
    * 開啟解壓縮的資料夾。
    * 以滑鼠右鍵按一下 `Moodle-AzureAD-Script.ps1` 檔案，然後選取 [ **屬性**> 。
    * 在屬性 **視窗** 的一般標籤下，勾選底部的 `Unblock` **安全性屬性** 旁的方塊。
    * 按一下 [確定]。
    * 複製解壓縮資料夾的目錄路徑。
1. 接下來，您將以系統管理員的名次執行 PowerShell：
    * 按一下 [開始。
    * 輸入 PowerShell。
    * 以滑鼠右鍵按一下 Windows PowerShell。
    * 按一下 [以系統管理員執行」。
1. 輸入目錄的路徑，以流覽至未解壓縮 `cd ...\...\Moodle-AzureAD-Powershell` `...\...` 的目錄。
1. 執行 PowerShell 腳本：：
    * 輸入 `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` 。
    * 輸入 `.\Moodle-AzureAD-Script.ps1` 。
    * 在快顯視窗中登入您的 Microsoft 365 或 Office 365 系統管理員帳戶。
    * 輸入 Azure AD 應用程式名稱 (Ex。 Moodle/Moodle 外掛程式) 。
    * 輸入您的 Moodle 伺服器的 URL。
    * 複製 **腳本產生的****應用程式** 識別碼和應用程式金鑰，然後儲存它們。
1. 接下來，您需要在 Moodle 外掛程式中新增 Id 和 Key。 返回 Microsoft 365 整合 (管理>外掛程式>管理頁面) 。
1. 在 [**設定」** 選項卡上，新增您先前複製的應用程式 **識別碼** 和應用程式金鑰，然後按一下 [**儲存變更**。
1. 頁面重新建立之後，您應該會看到新的一節選擇 **連接方法**。 按一下標示為 [預設值」 **的核取方塊** ，然後再按一下 **[儲存** 變更。
1. 頁面重新啟用之後，您就會看到另一個新節系統管理 **同意&其他資訊**。
    * 按一下 [**提供系統管理員同意** 連結，輸入您的 Microsoft 365 或 Office 365全域系統管理員認證，然後接受以授予許可權。
    * 按一下 **Azure AD 租使用者欄位** 旁的 [ **偵測>** 按鈕。
    * 按一下 **商務用 OneDrive URL 旁** 的 [ **偵測>** 按鈕。
    * 欄位填入後，再次按一下 [ **儲存變更** > 按鈕。
1. 按一下 [ **更新>** 按鈕以驗證安裝，然後儲存 **變更**。
1. 接下來，您需要在 Moodle 伺服器和 Azure Active Directory 之間同步處理使用者。 視您的環境，您可以在此階段選取不同的選項。 請注意，您在這裡設定的配置會隨著每一個 Moodle cron 執行 (一天執行一次) 讓所有專案保持同步。若要開始使用：
    * 切換到同步 **設定選項卡**
    * 在與 **Azure AD 同步** 處理使用者區段，選取適用于您環境的核取方塊。 一般來說，您至少會選取：
        * 在 Azure AD 中為使用者建立 Moodle 帳戶
        * 在 Azure AD 中更新 Moodle 中使用者的所有帳戶
    * 在使用者 **建立限制** 區段，您可以設定篩選以限制要同步到 Moodle 的 Azure AD 使用者。
    * 使用者 **欄位映射** 區段將允許您自訂 Azure AD 到 Moodle 使用者設定檔欄位的映射。
    * 在 Teams **同步處理** 區段，您可以選擇自動 (群組，) 或所有現有 Moodle 課程的 Teams 群組。
1. 若要驗證 cron 工作 (如果您想要第一次執行，請手動執行) 請按一下 [同步處理使用者與 Azure  **AD>** 區段的 [排定的工作管理頁面> 連結。 這會將您帶至排 **程工作** 頁面。
    * 向下卷起並尋找將使用者與 **Azure AD 工作同步** 處理的工作，然後按一下 **[立即執行**> 。
    * 如果您選擇根據現有的課程建立群組，您也可以在 **Office 365** 工作中執行建立使用者群組。
1. 返回 Microsoft 365 整合 (管理>外掛程式>管理頁面) 並選取 Teams **設定** 頁面。 您需要設定一些安全性設定，才能啟用 Teams App 整合。
    * 若要啟用 OpenID Connect，請按一下 [ **管理** 驗證> 連結，然後按一下 **OpenId Connect** 行上的眼睛圖示 ，如果顯示為灰色。
    * 接下來，您需要啟用框架內嵌。 按一下 **HTTP 安全性** 連結，然後按一下 [允許內嵌 **框架> 旁的核取方塊**。
    * 下一個步驟是啟用 Web 服務，以啟用 Moodle API 功能。 按一下 **[進一步功能** > 連結，然後確認已勾選 [ **啟用 Web 服務> 旁的** 核取方塊。
    * 最後，您需要啟用 Microsoft 365 或 Office 365 的外部服務。 接著 **，按一下 [外部服務** 連結：
        * 在 **Moodle** **Office 365 Webservices** 列上按一下 [編輯。
        * 標記 [已啟用的 **核取方塊，** 然後按一下 [ **儲存變更**
    * 接下來，您需要編輯已驗證的使用者許可權，讓他們建立 Web 服務權杖。 按一下 **[編輯角色'已驗證的使用者'連結** 。 向下卷起並尋找 **建立 Web 服務權杖** 功能，並 **標記允許核取方塊** 。

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>步驟 3：將 Moodle 小幫手 Bot 部署到 Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Microsoft Teams 的免費 Moodle 小幫手 Bot 可協助教師和學生回答在 Moodle 中課程、作業、成績和其他資訊的問題。 Bot 也會在 Teams 中傳送 Moodle 通知給學生和教師。 此 Bot 是由 Microsoft 維護的開放原始碼專案，可在 [GitHub 上使用](https://github.com/microsoft/Moodle-Teams-Bot)。

> [!NOTE]
> 在此區段，您將部署資源至 Azure 訂閱，而所有資源都會使用免費 **層級** 進行配置。 視您 Bot 的使用量，您可能需要縮放這些資源。
> 如果您想要直接使用沒有 Bot 的 Moodle 定位停駐點，請跳至[步驟 4。](#step-4-deploy-your-microsoft-teams-app)

### <a name="moodle-bot-information-flow"></a>Moodle Bot 資訊流程

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Microsoft Teams 資訊流程的 Moodle Bot 圖例" />


若要安裝 Bot，您首先需要在 [Microsoft 身分](https://identity.microsoft.com/Landing)識別平臺上註冊。 這可讓您的 Bot 針對您的 Microsoft 端點進行驗證。 若要註冊您的 Bot：

1. 返回 Microsoft 365 整合 (網站管理>外掛程式>管理頁面) 並選取 Teams **設定** 選項卡。
1. 按一下 **Microsoft 應用程式註冊入口網站** 連結，然後使用 Microsoft Id 登入。
1. 輸入應用程式的名稱，例如 (名稱。 MoodleBot) 並按一下 [ **建立>** 按鈕。
1. 複製 **應用程式識別碼，** 然後將其貼到小組設定頁面上的 **Bot 應用程式識別碼** 欄位。 
1. 按一下 [ **產生新密碼>** 按鈕。 複製產生的密碼，並貼到小組設定頁面上的 **Bot** 應用程式 **密碼** 欄位。
1. 卷起至表單底部，然後按一下 [ **儲存變更**。

現在，您產生了應用程式識別碼和密碼，是時候將 Bot 部署到 Azure 了。 按一下 [部署至 **Azure>** 按鈕，然後填寫表單 ([Bot 應用程式識別碼、Bot 應用程式密碼和 Moodle 機密」 位於[小組設定> 頁面上，而 Azure資訊位於 [設定) > 頁面上。 填寫好表單之後，請按一下核取方塊以同意條款與條件，然後按一下 [購買 (所有 Azure 資源都部署到免費層級) 。

資源部署到 Azure 後，您必須設定具有其訊息端點的 Moodle 外掛程式。 首先，您必須從 Azure 中的 Bot 取得端點。 若要這麼做：

1. 如果您還沒有，請登入 [Azure 入口網站](https://portal.azure.com)。
2. 在左窗格中選取 **資源群組**。
3. 從清單中選取您部署 Bot 時 (或) 建立的資源群組。
4. 從群組中的資源清單中選取 **WebApp** Bot 資源。
5. 從 **概觀區段** 複製訊息 **端點** 。
6. 在 Moodle 中，開啟您 Moodle **外掛程式** 的小組設定頁面。
7. 在 **Bot 端點欄位中** 貼上您剛才複製的 URL，然後將郵件 *一* 詞變更為 *web上。* URL 現在應該看起來像 `https://botname.azurewebsites.net/api/webhook`
8. 按一下 **[儲存變更**
9. 儲存變更之後，請回到 [小組設定> 選項卡，按一下[下載清單檔案> 按鈕，將清單套件儲存到您的電腦 (您將在) 的下一節中使用它。

## <a name="step-4-deploy-your-microsoft-teams-app"></a>步驟 4：部署您的 Microsoft Teams 應用程式

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

現在，您的 Bot 已部署至 Azure，且已配置為與 Moodle 伺服器交談，現在該是部署 Microsoft Teams 應用程式的時候。 若要這麼做，您將在上一個步驟的 Moodle 外掛程式小組設定頁面載入您下載的清單檔案。

安裝應用程式之前，您必須確認已啟用外部 App 和側載應用程式。 若要這麼做，您可以遵循[下列步驟。](./admin-settings.md) 一旦確定已啟用外部應用程式後，您可以遵循下列步驟來部署應用程式。

1. 開啟 Microsoft Teams。
2. 按一下 **流覽** 欄左下角的 [市集」 圖示。
3. 按一下 **選項清單中的 [** 上傳自訂應用程式連結。 *注意：* 如果您是以全域管理員登入，您可以選擇將應用程式上傳到組織的 App Store，否則您只能載入您屬於 (「側載」) 之 Teams 的應用程式。
4. 選取 `manifest.zip` 您先前下載的套件，然後按一下 [ **儲存**。 如果您尚未下載清單套件，可以從 Moodle 中外掛程式設定頁面的小組設定選項卡執行此操作。

現在您已安裝應用程式，您可以將該定位停駐點新到任何您能夠存取的頻道。 若要這麼做，請流覽至頻道，按一下 **+** 符號，然後從清單中選取您的應用程式。 請遵循提示完成將 Moodle 課程定位停駐點新增到頻道。

就是這樣！ 您和您的團隊現在可以直接從 Microsoft Teams 開始處理您的 Moodle 課程。

若要與我們分享任何功能要求或意見，請流覽我們的 [使用者語音頁面](https://microsoftteams.uservoice.com/forums/916759-moodle)。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]