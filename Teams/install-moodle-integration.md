---
title: 安裝與 Microsoft Teams 的 Moodle 整合
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: 瞭解如何安裝及設定 Moodle 開放原始碼學習管理系統 (適用于 Microsoft Teams 的 LMS) 應用程式。
keywords: Teams Moodle 應用程式整合外掛程式
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7f0078be9f9077966fbba1a91fd569e1c4e11ec
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789538"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>安裝與 Microsoft Teams 的 Moodle 整合

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/)是全球最熱門的開放原始碼學習管理系統 (LMS) ，現在已與 Microsoft Teams 整合！ 這項整合可協助教師和學生在 Moodle 課程中共同作業、詢問關於其成績和作業的問題，並持續取得通知的更新 ， 直接在 Teams 中！

為了協助 IT 系統管理員輕鬆設定這項整合，我們已使用下列功能更新開放原始碼 Moodle 外掛程式：

* 使用 Azure AD 自動註冊您的 Moodle 伺服器。
* 按一下將 Moodle Assistant Bot 部署到 Azure。
* 自動布建團隊和自動同步處理所有或選取 Moodle 課程的團隊註冊。
* 自動將 [心情] 索引標籤和 [Moodle 小幫手] Bot 安裝到每個同步處理的小組。  (即將推出) 
* 按一下滑鼠將 Moodle 應用程式發佈到您的私人 Teams App Store。  (即將推出) 

若要深入瞭解此整合所提供的功能，請參閱 [安裝與 Microsoft Teams 的 Moodle 整合](/microsoftteams/platform/resources/moodleinstructions)。

## <a name="prerequisites"></a>必要條件

若要安裝並設定此應用程式，您將需要：

1. Moodle 系統管理員認證
2. Azure AD 系統管理員認證
3. Azure 訂閱，您可以在

## <a name="step-1-install-the-moodle-plugin"></a>步驟 1：安裝 Moodle 外掛程式

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft Teams 中的 Moodle 整合是由 開放原始碼[Moodle 外掛程式組所提供](https://github.com/Microsoft/o365-moodle)。 若要在您的 Moodle 伺服器中安裝外掛程式：

1. 首先，下載 [Moodle 外掛程式集](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) 並儲存到您的本機電腦。 您必須使用版本 3.5 或更新版本。
    * 安裝local_o365外掛程式也會安裝 [auth_oidc](https://moodle.org/plugins/auth_oidc) 和 [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) 外掛程式。
1. 以系統管理員身分登入您的 Moodle 伺服器，然後從左側流覽面板選取 [ **網站管理** ]。
1. 選取 **[外掛程式] 索引** 標籤，然後按一下 [ **安裝外掛程式]**。
1. 在 [ **從 ZIP 檔案安裝外掛程式** ] 區段下，按一下 [ **選擇檔案]** 按鈕。
1. 從左側導覽選取 **[上傳檔案** ] 選項，流覽上述下載的檔案，然後按一下 **[上傳此檔案]**。
1. 再次從左側導覽面板選取 [ **網站管理** ] 選項，以返回您的系統管理儀表板。 向下捲動至 [**本機] 外掛程式**，然後按一下 **[Microsoft Office 365整合]** 連結。 將此設定頁面保持在個別的瀏覽器索引標籤中開啟，因為您會在此程式的其餘部分使用此設定頁面。

您可以在 [Moodle 檔](https://docs.moodle.org/34/en/Installing_plugins)中找到有關如何安裝 Moodle 外掛程式的詳細資訊。

**重要注意事項：** 讓您的 Microsoft 365 或 Office 365 Moodle 外掛程式設定頁面在另一個瀏覽器索引標籤中開啟，因為您將在整個程式中返回這組頁面。

*還沒有 Moodle 網站嗎？* 您可能會想要查看 Azure [Repo](https://github.com/azure/moodle) 上的 Moodle，您可以在 Azure 上快速部署 Moodle 實例，並根據您的需求進行自訂。

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>步驟 2：設定 Microsoft 365 或Office 365外掛程式與 Azure Active Directory 之間的連線

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

接下來，您需要將 Moodle 註冊為 Azure Active Directory 中的應用程式。 我們已提供 PowerShell 腳本，協助您完成此程式。 PowerShell 腳本會為您的 Microsoft 365 或Office 365組織提供新的 Azure AD 應用程式，該應用程式將由 Moodle 外掛程式使用。 腳本會為您的 Microsoft 365 或Office 365租使用者布建應用程式、為布建的應用程式設定所有必要的回復 URL 和許可權，並傳回 AppID 和金鑰。 您可以使用 Moodle 外掛程式安裝頁面中產生的 AppID 和金鑰，以 Azure AD 設定您的 Moodle 伺服器。 如果您想要查看 PowerShell 腳本自動化的詳細手動步驟，可以在 [外掛程式的完整檔](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)中找到這些步驟。

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Microsoft Teams 資訊流程的 [情境] 索引標籤

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Microsoft Teams 資訊流程的 [Moodle] 索引標籤圖例" />

1. 從 [Microsoft 365] 或 [Office 365整合] 外掛程式頁面上，選取 [**設定] 索引卷** 標。
1. 按一下 **[下載 PowerShell 腳本]** 按鈕，並將其儲存到本機電腦。
1. 您必須從 ZIP 檔案準備 PowerShell 腳本。 若要這麼做：
    * 下載並解壓縮 `Moodle-AzureAD-Powershell.zip` 檔案。
    * 開啟解壓縮的資料夾。
    * 以滑鼠右鍵按一下檔案， `Moodle-AzureAD-Script.ps1` 然後選取 [ **內容]**。
    * 在屬性視窗的 [一 **般**] 索引標籤底下，核 `Unblock` 取底部 **[安全** 性] 屬性旁邊的方塊。
    * 按一下 [確定]。
    * 複製解壓縮資料夾的目錄路徑。
1. 接下來，您將以系統管理員身分執行 PowerShell：
    * 按一下 [開始]。
    * 輸入 PowerShell。
    * 以滑鼠右鍵按一下 [Windows PowerShell]。
    * 按一下 [以系統管理員身分執行]。
1. 輸入 `cd ...\...\Moodle-AzureAD-Powershell` 目錄路徑的位置 `...\...` ，以流覽至解壓縮的目錄。
1. 執行 PowerShell 腳本，方式如下：
    * 輸入 `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` 。
    * 輸入 `.\Moodle-AzureAD-Script.ps1` 。
    * 在快顯視窗中登入您的 Microsoft 365 或Office 365系統管理員帳戶。
    * 輸入 Azure AD Application (Ex 的名稱。 Moodle/Moodle 外掛程式) 。
    * 輸入您的 Moodle 伺服器 URL。
    * 複製腳本所產生的 **應用程式識別碼** 和 **應用程式金鑰** ，然後儲存它們。
1. 接下來，您需要將識別碼和金鑰新增至 Moodle 外掛程式。 返回 (Microsoft 365 整合) > [網站管理>外掛程式] 的外掛程式管理頁面。
1. 在 [ **設定] 索引卷** 標上新增您先前複製的 **應用程式識別碼** 和 **應用程式金鑰** ，然後按一下 [ **儲存變更]**。
1. 頁面重新整理之後，您現在應該會看到 [ **選擇連線方法**] 的新區段。 按一下標示為 **[預設]** 的核取方塊，然後再按一下 [儲存 **變更]** 。
1. 重新整理頁面之後，您會看到另一個新節 **管理員同意&其他資訊**。
    * 按一下 **[提供管理員同意**] 連結，輸入您的 Microsoft 365 或Office 365全域系統管理員認證，然後 **[接受**] 以授與許可權。
    * 按一下 **Azure AD 租使用者** 欄位旁的 **[偵測]** 按鈕。
    * 按一下 **商務用 OneDrive URL** 旁邊的 **[偵測]** 按鈕。
    * 欄位填入後，再次按一下 [ **儲存變更]** 按鈕。
1. 按一下 **[更新]** 按鈕以驗證安裝，然後 [ **儲存變更]**。
1. 接下來，您需要同步處理 Moodle 伺服器和 Azure Active Directory 之間的使用者。 視您的環境而定，您可能會在此階段選取不同的選項。 請注意，您在這裡設定的設定將會與每個 Moodle cron 執行 (通常一天一次，) 讓所有專案保持同步。若要開始使用：
    * 切換到 [ **同步設定] 索引標籤**
    * 在 [ **同步使用者與 Azure AD]** 區段中，選取適用于您環境的核取方塊。 一般情況下，您至少會選取：
        * 在 Azure AD 中為使用者在 Moodle 中建立帳戶
        * 在 Azure AD 中為使用者更新 Moodle 中的所有帳戶
    * 在 [ **使用者建立限制** ] 區段中，您可以設定篩選以限制將同步處理至 Moodle 的 Azure AD 使用者。
    * [ **使用者欄位對應** ] 區段可讓您自訂 Azure AD 到 Moodle User Profile 欄位對應。
    * 在 **[Teams 同步** 處理] 區段中，您可以選擇自動建立群組 (，也即 Teams) 部分或全部現有 Moodle 課程。
1. 若要驗證 cron 工作 (，如果您想要第一次執行，請手動執行) 按一下 [同步 **處理使用者與 Azure AD] 區** 段中的 [**排程任務管理] 頁面** 連結。 這會將您帶到 [ **排程的工作]** 頁面。
    * 向下捲動並尋找工作 **：使用 Azure AD 工作同步處理使用者** ，然後按一下 [ **立即執行]**。
    * 如果您選擇根據現有課程建立群組，您也可以在Office 365工作中執行建立 **使用者群組**。
1. 返回 (Microsoft 365 整合) >外掛程式>的 [網站管理] 頁面，然後選取 **[Teams 設定]** 頁面。 您必須設定一些安全性設定，才能啟用 Teams 應用程式整合。
    * 若要啟用 OpenID Connect，請按一下 **[管理驗證]** 連結，並在 **OpenId Connect** 線條呈現灰色時按一下眼睛圖示。
    * 接下來，您需要啟用框架內嵌。 按一下 **[HTTP 安全** 性] 連結，然後按一下 [ **允許內嵌框架**] 旁的核取方塊。
    * 下一個步驟是啟用可啟用 Moodle API 功能的 Web 服務。 按一下 [ **進階功能]** 連結，然後確定已核取 [ **啟用 Web 服務** ] 旁的核取方塊。
    * 最後，您需要為 Microsoft 365 或 Office 365 啟用外部服務。 按一下 **[外部服務]** 連結，然後：
        * 按一下 **[Moodle Office 365 Webservices**] 列上的 [**編輯**]。
        * 標示 [ **已啟用**] 旁的核取方塊，然後按一下 [ **儲存變更]**
    * 接下來，您將需要編輯已驗證的使用者許可權，以允許他們建立 Web 服務權杖。 按一下 **[編輯角色為已驗證的使用者]** 連結。 向下捲動並尋找 **建立 Web 服務權杖** 功能，並標記 [ **允許** ] 核取方塊。

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>步驟 3：將 Moodle Assistant Bot 部署到 Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Microsoft Teams 免費的 Moodle Assistant Bot 可協助教師和學生回答有關其課程、作業、成績和 Moodle 中其他資訊的問題。 Bot 也會直接在 Teams 中傳送 Moodle 通知給學生和教師。 此 Bot 是由 Microsoft 維護的開放原始碼專案，[可在 GitHub 上使用](https://github.com/microsoft/Moodle-Teams-Bot)。

> [!NOTE]
> 在此區段中，您將部署資源到您的 Azure 訂閱，所有資源將會使用 **免費** 層級進行設定。 視 Bot 的使用量而定，您可能需要調整這些資源的縮放比例。
> 如果您只想在沒有 Bot 的情況下使用 [Moodle] 索引標籤，請跳至 [步驟 4](#step-4-deploy-your-microsoft-teams-app)。

### <a name="moodle-bot-information-flow"></a>Moodle Bot 資訊流程

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Microsoft Teams 的 Moodle Bot 資訊流程圖例" />


若要安裝 Bot，您必須先在 [Microsoft 身](https://identity.microsoft.com/Landing)分識別平臺註冊。 這可讓您的 Bot 根據您的 Microsoft 端點進行驗證。 若要註冊您的 Bot：

1. 返回 (Microsoft 365 整合> [網站管理] >外掛程式) 的外掛程式管理頁面，然後選取 **[Teams 設定] 索引卷** 標。
1. 按一下 **[Microsoft 應用程式註冊入口網站** ] 連結，並使用您的 Microsoft Id 登入。
1. 輸入應用程式 (Eg 的名稱。 MoodleBot) ，然後按一下 [ **建立]** 按鈕。
1. 複製 **應用程式識別碼**，並貼到 **[團隊設定**] 頁面上的 **[Bot 應用程式標識** 符] 欄位。
1. 按一下 [ **產生新密碼]** 按鈕。 複製產生的密碼，並貼到 **[團隊設定**] 頁面上的 **[Bot 應用程式密碼**] 欄位。
1. 捲動到表單底部，然後按一下 [ **儲存變更]**。

現在您已產生應用程式識別碼和密碼，是時候將您的 Bot 部署到 Azure 了。 按一下 [ **部署到 Azure** ] 按鈕，並填寫表單 (小組 **設定頁面上的** Bot 應用程式識別碼、Bot 應用程式密碼和 Moodle Secret，以及 Azure 資訊位於 [ **設定** ] 頁面) 。 填寫表單後，按一下核取方塊以同意條款及條件，然後按一下 [ **購買** ] 按鈕， (所有 Azure 資源都部署到免費層級) 。

完成資源部署至 Azure 後，您將需要使用其傳訊端點來設定 Moodle 外掛程式。 首先，您需要從 Azure 中的 Bot 取得端點。 若要執行此動作：

1. 如果您尚未登入，請登入[Azure 入口網站](https://portal.azure.com)。
2. 在左窗格中選取 **[資源群組]**。
3. 從清單中選取您剛剛在部署 Bot 時 (或建立) 的資源群組。
4. 從群組中的資源清單中選取 **WebApp Bot** 資源。
5. 從 [**概觀**] 區段複製 **訊息中心端點**。
6. 在 [Moodle] 中，開啟 [Moodle 外掛程式] 的 [ **團隊設定** ] 頁面。
7. 在 **Bot 端點** 欄位中貼上您剛才複製的 URL，並將 *訊息* 一詞變更為 *webhook*。 URL 現在看起來應該像 `https://botname.azurewebsites.net/api/webhook`
8. 按一下 **[儲存變更]**
9. 儲存變更之後，回到 [ **小組設定] 索引** 標籤，按一下 [ **下載資訊清單檔案]** 按鈕，並將資訊清單套件儲存到電腦 (您將在下一節) 使用它。

## <a name="step-4-deploy-your-microsoft-teams-app"></a>步驟 4：部署 Microsoft Teams 應用程式

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

現在您已將 Bot 部署到 Azure，並設定為與您的 Moodle 伺服器通話，是時候部署您的 Microsoft Teams 應用程式了。 若要這麼做，您將載入從上一個步驟的 Moodle 外掛程式小組設定頁面下載的資訊清單檔案。

安裝應用程式之前，您必須先確認已啟用外部應用程式和側載應用程式。 若要這麼做，您可以依照 [下列步驟進行](./admin-settings.md)。 一旦您確定已啟用外部應用程式，您可以遵循下列步驟來部署您的應用程式。

1. 開啟 Microsoft Teams。
2. 按一下導覽列左下角的 [ **市** 集] 圖示。
3. 按一下選項清單中的 **[上傳自訂應用程式** ] 連結。 *注意：* 如果您以全域系統管理員的身分登入，您可以選擇將應用程式上傳到貴組織的 App Store，否則您只能載入屬於 (「側載」) 的 Teams 相關應用程式。
4. 選取您先前下載的 `manifest.zip` 套件，然後按一下 [ **儲存]**。 如果您尚未下載資訊清單套件，您可以從 Moodle 中外掛程式設定頁面的 [ **團隊設定** ] 索引標籤下載。

現在您已安裝應用程式，可以將索引標籤新增至您有權存取的任何頻道。 若要這麼做，請流覽至頻道，按一下 **+** 該符號，然後從清單中選取您的應用程式。 依照提示完成新增您的 Moodle 課程索引標籤至頻道。

就是這樣！ 您和您的小組現在可以直接從 Microsoft Teams 開始使用您的 Moodle 課程。

若要與我們分享任何功能要求或意見反應，請造訪我們的意見 [反應入口網站](https://feedbackportal.microsoft.com)。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]
