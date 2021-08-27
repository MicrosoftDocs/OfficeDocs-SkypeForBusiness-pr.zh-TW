---
title: 設定公用區域電話
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 瞭解部署步驟以取得正確的固件、如果需要更新、指派授權，以及設定一般地區電話的設定。
ms.openlocfilehash: 14c7a76ed8f0aa319049d4352c1cdc6ce4c4ce98
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607420"
---
# <a name="set-up-common-area-phones"></a>設定公共區域電話

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]
一般區域電話 (CAP) 一般會放置在大廳等區域，或是可供許多人使用的區域。 例如，接收區電話、門電話或會議室電話、CAP 會設定為裝置，而不是使用者，並自動登入網路。 在下列步驟中，我們會協助您設定帳戶電話系統通話方案，以便為貴組織部署這類電話。

## <a name="prerequisites-for-common-area-phones"></a>一般地區電話的先決條件

您要做的第一件事是確認您擁有下列專案：

- 購買公用電話授權和通話方案。
- 搜尋及購買核准的 (，並在這裡[查看) 。](deploying-skype-for-business-online-phones.md)
- 更新您手機上的 (請參閱本主題 [中的](getting-phones-for-skype-for-business-online.md) 支援) 。  您可以執行以下方法檢查手機上的固件：
  - **Polycom VVX 電話**：**前往** 設定  >  **Status**  >  **Platform**  >  **Application**  >  **Main**。
  - **Yealink 手機****：前往主要** 電話畫面上的狀態。
  - **音訊代碼手機****：從開始** 畫面前往功能表  >  **裝置**  >  狀態固件版本。
  - **Lync 電話版本 (LPE**) 手機：從開始畫面系統資訊  >  功能表選項。

    固件更新是由服務商務用 Skype管理。 每個商務用 Skype認證的手機的固件都會上傳到 商務用 Skype 補救伺服器，且裝置更新預設在所有手機上都會啟用。

    根據電話和投票間隔上的非啟用時間，電話會自動下載並安裝最新的認證版本。 您可以使用  [Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) Cmdlet，將 *EnableDeviceUpdate* 參數設定為 來停用裝置更新設定 `false` 。

## <a name="setting-up-a-common-area-phone"></a>設定共同區域電話
您需要遵循下列步驟：

### <a name="step-1---buy-the-licenses"></a>步驟 1 - 購買授權
1. 在系統管理中心，**前往帳單**  >  **購買服務**，然後新增 **其他方案**。

    ![共同區域授權電話螢幕擷取畫面](../../images/cap-license.png)
2. 按一下 [**常用區域電話**  >  **立即** 購買>在 [結帳>按一下[立即 **購買**> 。
3. 按一下以展開 **附加元件訂閱** ，然後按一下以購買通話方案。 選擇國內 **通話方案或****國內及國際通話方案**。

> [!Note]
> 您不需要授權電話系統授權。 它包含在共同區域授權 **電話** 中。

有關授權詳細資訊，請參閱[商務用 Skype Microsoft Teams附加元件授權。](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>步驟 2 - 為手機建立新使用者帳戶並指派授權
1. 在系統管理中心，前往 **使用者**  >  **活動使用者**  >  **新增使用者**。
2. 輸入使用者名稱 **，** 例如名字的「主」，第二個名稱的「接收」。
3. 如果顯示名稱 **無法** 像「主要接收」一樣自動生成，請輸入顯示名稱。
4. 輸入使用者 **名稱，** 例如「MainReception」或「Mainlobby」。
5. 對於一般地區電話，您可能會想要手動設定密碼，或針對所有常見的地區電話設定相同的密碼。 此外，您可能會考慮取消選擇讓此使用者在首次登出 **時變更其密碼**。
6. 如果您仍然在那裡，請指派授權給此使用者。 在同一頁上，按一下 以展開 **[產品授權>**。 開啟下列功能：
   - 共同區域電話
   - 然後，您需要選擇國內通話方案或國內及 **國際通話方案**。

     指派授權看起來像：

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > 您只要知道，商務用 Skype 2 方案已包含在 **共同** 區域電話授權中。

若要瞭解詳細資料，請參閱 [新增使用者](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>步驟 3 - 將電話號碼指派給共同電話使用者帳戶

![一個圖示，商務用 Skype標誌使用系統管理中心指派電話號碼給使用者商務用 Skype ](../../images/sfb-logo-30x30.png) **圖示**

1. 在系統管理中心>**系統管理中心**  >  **商務用 Skype。**
2. 在系統 **管理商務用 Skype**  >   **語音電話**  >  **號碼**。
3. 從電話號碼清單中選取一個數位，然後按一下 [ **指派**。
4. 在指派 **頁面上**，**在語音使用者** 方塊中，輸入用於電話的使用者名稱，然後在選取語音使用者下拉式 **清單中選擇使用者。**
5. 當您在那裡時，您需要新增緊急位址。 搜尋後，請在選取緊急位址下尋找，以挑選適合您的位址。
6. 按一下 **[儲存** ，您的使用者應該看起來像這樣：

    ![使用者電話號碼的螢幕擷取畫面](../../images/cap-user-number.png)

   > [!Note]
   > 使用者只有在已申請授權 **電話系統顯示。** 如果您只是這麼做，有時候使用者需要一點時間，才顯示在清單中。

有關更多內容，請參閱 [取得使用者的電話號碼](/microsoftteams/getting-phone-numbers-for-your-users)。

如果您想知道，您也可以將您擁有的電話號碼帶至另一個電信公司，然後「移轉」，或將電話號碼移Microsoft 365或Office 365。** 請參閱[將電話號碼轉接到 Teams。](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)

### <a name="step-4---setting-up-your-phone"></a>步驟 4 - 設定您的手機

**在手機上設定模式**

您擁有的電話或電話必須開啟共同區域 **電話模式**。 您可能會想要檢查該核取方塊，確定它們確實可以。

**以下是如何設定 Polycom VVX 手機的範例**

- 按照下列電話，為 Polycom VVX 啟用共同區域模式：
    1. 在瀏覽器中，連接到 Web 介面，以便啟用 CAP 模式。
    2. 接著，請前往設定 **，商務用 Skype** 設定選項中，選取 **共同區域電話。** 
    3. 按一下 **[是** 」 以儲存您的設定。

- 現在已啟用 CAP 模式，請用手機的顯示器設定電話。 顯示器應該會顯示 **已啟用 CaAP。** 然後執行下列操作：

    1. 按一下 **[設定。**
    2. 選取 **進位**。
    3. 輸入密碼。
    4. 在 **系統管理設定** 中，選取 **共同區域電話 設定。**
    5. 啟用 **CAP** 和 **CAP 系統管理模式**。
    6. 按一下 **[儲存 Config>**。

- 現在您的手機已準備就緒，因此您可以在主畫面上登錄。

    1. 選取功能選項 **設定**  >  **以**  >  **商務用 Skype。**
    2. 選取 **使用者認證**，然後選取 **CAP** (網頁) 以產生程式碼。
    3. 請前往 [資源調配入口網站](https://aka.ms/skypecap)，然後以系統管理員的登錄 **。**
    4. 輸入顯示名稱 (例如，主接收) 。

       > [!Note]
       > 如果 **只勾選了搜尋一般地區** 電話，請清除核取方塊，然後再次搜尋。

    5. 在配對程式碼視窗中，輸入手機上顯示的代碼，然後按一下 [ **備入**。

        遵循最後一個步驟，電話應該會自動登入。


> [!NOTE]
> CAP 設定網站指出，它會將 CAP 帳戶的密碼重設為隨機密碼。 請注意，CAP 所參照的帳戶是 AAD Azure Active Directory (AAD) 帳戶。 如果您只在 AAD 中建立帳戶，則程式非常簡單。 如果您將內部部署 Active Directory 同步到 AAD，而且使用協力廠商 IDP 或 ADFS，則 CAP 置備將會失敗。 在這種情況下，您只需要使用 Microsoft 365 或 Office 365/Azure Active Directory 帳戶 (，例如擁有 **onmicrosoft.com** 網域) 的帳戶，才能使用 CAP 資源配置。


### <a name="related-topics"></a>相關主題

- 在部署線上電話時，深入瞭解[商務用 Skype電話](deploying-skype-for-business-online-phones.md)。
- [取得商務用 Skype Online 的電話](getting-phones-for-skype-for-business-online.md)
