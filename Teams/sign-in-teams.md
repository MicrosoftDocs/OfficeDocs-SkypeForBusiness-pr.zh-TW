---
title: 登入 Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: 了解新式驗證如何運作、如何切換帳戶，以及如何疑難排解新式驗證。包含如何在登入時告訴 Teams 忽略預先填入的使用者名稱 (UPN)。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9171ffa0b2750d053afa76c5dc788b24cf8ec2d4
ms.sourcegitcommit: cb50f1fde4913c5a61e521c77fb554b883beb451
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376016"
---
<a name="sign-in-to-microsoft-teams"></a>登入 Microsoft Teams
==========================

## <a name="windows-users"></a>Windows 使用者

Microsoft 建議組織使用最新版本的 Windows 10，內含有混合式網域加入或 Azure AD 加入設定。使用最近的版本能確保在 Windows 網頁帳戶管理員中已將使用者的帳戶準備好，進而讓您以單一的方式登入 Teams 和其他 Microsoft 應用程式。單一登入可提供更好的使用者體驗 (無訊息式登入) 和加強的安全性狀況。

Microsoft Teams 使用新式驗證讓登入體驗更加簡單可靠。若要瞭解使用者如何登入 Teams，請閱讀[登入 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。

### <a name="how-modern-authentication-works"></a>新式驗證的運作方式

新式驗證是一種程序，可讓 Teams 知道使用者已經在別處輸入其認證 (例如，他們的工作電子郵件和密碼)，因此不需要再次輸入就能啟動應用程式。這項體驗會根據幾項因素而有所不同，例如使用者是在 Windows 或在 Mac 上工作。它也會根據您的組織啟用單要素驗證或多重要素驗證而有所不同。多重要素驗證通常涉及透過手機驗證認證、提供唯一的代碼、輸入 PIN，或顯示指紋。

使用 Teams 的每一個組織都能使用新式驗證。 如果使用者無法完成此程序，則表示貴組織的 Azure AD 設定可能有基礎問題。 如需詳細資訊，請參閱[為何我無法登入 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

- 如果使用者已透過他們的公司或學校帳戶登入 Windows 或其他 Office 應用程式，當他們啟動 Teams 時，就可以直接進入應用程式。 不需要再輸入認證。

- Microsoft 建議使用 Windows 10 版本 1903 或更新版本，以獲得最佳的單一登入體驗。

- 如果使用者未登入他們的 Microsoft 公司或學校帳戶，當他們啟動 Teams 時，系統會要求他們提供單一要素或多重要素驗證 (SFA 或 MFA)。 此程序取決於貴組織決定登入程式所需的方式。

- 如果使用者登入加入網域的電腦，當他們啟動 Teams 時，系統可能會要求他們執行一個進一步的驗證步驟，視您的組織是否選擇要求 MFA 或他們的電腦是否要求 MFA 才能登入而定。 如果使用者的電腦要求 MFA 才能登入，當他們開啟 Teams 時，應用程式會自動啟動。

- 在已加入網域的電腦上，如果無法使用 SSO，Teams 可能會使用使用者主體名稱 (UPN) 預先填入其登入畫面。 您可能不會想要這種情況發生，特別是如果您的組織在內部部署和 Azure Active Directory 中使用不同的 UPN。 如果是這樣，您可以使用下列 Windows 登錄機碼來關閉 UPN 的預先填入：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > 針對以「.local」或「.corp」結尾的使用者名稱，略過或忽略使用者名稱預先填入的功能預設為開啟，因此您不需要設定登錄機碼就能關閉預先填入。

### <a name="signing-out-of-teams-after-completing-modern-authentication"></a>完成新式驗證後登出 Teams

若要登出 Teams，使用者可以選取應用程式頂端的個人檔案圖片，然後選取 **[登出]**，也可以在其工作列中的應用程式圖示上按一下滑鼠右鍵，然後選取 **[登出]**。登出 Teams 之後，必須再次輸入認證，才能啟動應用程式。

### <a name="signing-in-to-another-account-on-a-domain-joined-computer"></a>在加入網域的電腦上登入另一個帳戶

在加入網域的電腦上的使用者可能無法使用在同一 Active Directory 網域中的另一個帳戶登入 Teams。

## <a name="macos-users"></a>MacOS 使用者

在 MacOS 上，Teams 會提示使用者輸入其使用者名稱和認證，並根據貴組織的設定，可能會提示多重要素驗證。 使用者輸入認證後，就不需要再次提供這些認證。 從這時起，只要他們在同一部電腦上工作，Teams 就會自動啟動。

## <a name="teams-on-ios-and-android-users"></a>iOS 和 Android 版 Teams 使用者

登入後，行動使用者將會看到目前登入或先前已在其裝置上登入的所有 Microsoft 365 帳戶清單。 使用者可以點選任何帳戶以登入。 以行動裝置登入會有下列兩種案例：

1. 如果選取的帳戶目前已登入其他 Office 365 或 Microsoft 365 app，系統會將該使用者直接移至 Teams。 使用者不需要輸入認證。

2. 如果使用者未登入其 Microsoft 365 帳戶的其他位置，系統會要求他們提供單一要素或多重要素驗證 (SFA 或 MFA)，視貴組織針對 [行動裝置登入原則] 設定的內容而定。

> [!NOTE]
> 若要讓使用者體驗本節所述的 [登入體驗]，他們的裝置必須是能夠執行 iOS 版2.0.13 （組建2020061704）或更新版本，或為 Android 版的 Teams 版本 1416/1.0.0.2020061702 或更新版本。

## <a name="using-teams-with-multiple-accounts"></a>使用多個 Teams 帳戶

iOS 和 Android 版 Teams 支援多個公司、學校和多個個人帳戶並行使用。 Teams 桌面應用程式會在 2020 年 12 月支援並行使用一個公司/學校和一個個人帳戶，稍後即將推出支援多個公司/學校帳戶。

下列圖片顯示使用者如何在 Teams 行動裝置應用程式中新增多個帳戶。

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="在 Teams 中新增多個帳戶":::

## <a name="restrict-sign-in-to-teams"></a>限制登入 Teams

組織可能會想要限制在受管理的裝置上使用公司核准應用程式的方式，例如，限制學生或員工從其他組織存取資料，或將公司核准的應用程式用作個人使用的情況。 可以透過設定 Teams 應用程式可識別的裝置原則來強制執行這些限制。   

### <a name="how-to-restrict-sign-in-on-mobile-devices"></a>如何在行動裝置上限制登入

iOS 和 Android 版 Teams 提供 IT 系統管理員將帳戶設定推入 Microsoft 365 帳戶的能力。 這項功能可與任何使用 iOS [受控應用程式設定](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) 通道或 Android 的 [Android 企業](https://developer.android.com/work/managed-configurations) 通道的行動裝置管理 (MDM) 提供者相配合。

對於已註冊 Microsoft Intune 的使用者，可以在 Azure 入口網站中使用 Intune 部署帳戶組態設定。

當 MDM 提供者設定好帳戶組態設定且使用者註冊其裝置之後，iOS 和 Android 版 Teams 在 Teams 登入頁面上將只會顯示允許的帳戶。 使用者可以點選此頁面中任何允許的帳戶以登入。

在受管理的裝置的 Azure Intune 入口網站中設定下列設定參數。

|平台 |機碼  |值  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **已啟用**: 唯一允許的帳戶是由 IntuneMAMUPN 機碼所定義的受管用戶帳戶。<br> **已停用** (或與 **啟用** 不區分大小寫的任何值): 允許任何帳戶。        |
|iOS     |   **IntuneMAMUPN**      |   允許登入 Teams 的帳戶 UPN。<br> 如果您是 Intune 註冊的裝置，可以使用 {{userprincipalname}} 符號來代表已註冊的使用者帳戶。       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    唯一允許的帳戶是由此機碼所定義的受管使用者帳戶。<br> 以一或多個分號 ;]- 分隔 UPN。<br> 如果您是 Intune 註冊的裝置，可以使用 {{userprincipalname}} 符號來代表已註冊的使用者帳戶。

當帳戶設定完成之後， Teams 會限制登入的能力，因此只有登入的裝置上允許的帳戶才能取得存取權。

若要為受管理的 iOS/iPadOS 裝置建立應用程式設定原則，請參閱 [為受控 iOS/iPadOS 裝置新增應用程式設定原則](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios)。

若要為受管理的 Android 裝置建立應用程式設定原則，請參閱[新增受管理的 Android 裝置應用程式設定原則](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android)。

### <a name="how-to-restrict-sign-in-on-desktop-devices"></a>如何限制在桌面裝置上登入
Windows 和 MacOS 上的 Teams 應用程式可支援限制登入組織的裝置原則。 這些原則可以透過一般的裝置管理解決方案 (例如 MDM (行動裝置管理) 或 GPO (群組原則物件)) 進行設定。 

當您在裝置上設定此原則時，使用者只能使用位於 Azure AD 租用戶 (包含於原則中定義的「租用戶允許清單」) 中的帳戶登入。 原則會套用至所有的登入，包括第一個和其他的帳戶。 如果您的組織包括多個 Azure AD 租用戶，您可以在允許清單中包含多個租用戶識別碼。 新增另一個帳戶的連結可能會持續顯示在 Teams 應用程式中，但無法操作。

> [!NOTE]
>1. 原則只會限制登入。它不會限制使用者在其他 Azure AD 租用戶中受邀為來賓，或切換到其他租用戶。
>2. 原則需要 Windows 版 Teams 版本 1.3.00.30866 或更新版本，以及 MacOS 版 Teams 版本 1.3.00.30882 (於 2020 年 11 月中發行)。

**Windows 原則** [下載中心](https://www.microsoft.com/download/details.aspx?id=49030)提供了系統管理範本檔案 (ADMX/ADML)。 此外，您可以在 Windows 登錄中手動設定金鑰：

- 值名稱：RestrictTeamsSignInToAccountsFromTenantList
- 值類型：字串
- 值資料：租用戶識別碼或逗號分隔的租用戶識別碼清單
- 路徑：請使用下列其中之一

 Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams

範例： SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 或 SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 1,Tenant ID 2,Tenant ID 3

**MacOS 原則** 針對 MacOS 的受管理裝置，請使用 .plist 來部署登入限制。 設定檔是一個 .plist 檔案，由金鑰 (表示喜好設定的名稱) 所識別的項目所組成，後接一個值 (取決於喜好設定的性質)。 值可以為簡單 (例如數值) 或複雜 (例如喜好設定的巢狀清單)。

- 網域：com.microsoft.teams
- 金鑰：RestrictTeamsSignInToAccountsFromTenantList
- 資料類型：字串
- 註解：輸入以逗號分隔的 Azure AD 租用戶識別碼清單


## <a name="sign-out-on-mobile-devices"></a>在行動裝置上登出

行動使用者可以移至功能表，選取 **[更多]** 功能表，然後選取 **[登出]**，以登出 Teams。一旦登出，使用者則需在下一次啟動該應用程式時，重新輸入認證。

> [!NOTE]
> Android 版 Teams 使用單一登入（SSO）來簡化登入體驗。 使用者除了 Team 以外，還應務必登出 **所有** 的 Microsoft 應用程式，以便完全登出 Android 平臺。

### <a name="global-sign-in-and-sign-out"></a>全域登入和登出

Teams Android 應用程式現在支援全域登入和登出，為第一線員工提供輕鬆便利的登入和登出體驗。 員工可以從共用裝置集區中挑選一部裝置，並執行單一登入，以在其班次期間將之作為自己的裝置。 在班次結束時，他們應該能夠執行登出，以便在裝置上全域登出。 這會自裝置移除其個人與公司資訊，他們便能將裝置歸還回裝置集區。 若要取得這項功能，裝置必須處於共用模式。 若要瞭解如何設定共用裝置，請參閱 [如何在 Android 上使用共用裝置模式](https://docs.microsoft.com/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode)。

登入體驗看起來類似我們的標準 Teams 登入體驗，而登出則看來像以下兩個圖片：

![顯示登出的行動電話](media/global-SignOut.png)  

## <a name="urls-and-ip-address-ranges"></a>URL 和 IP 位址範圍

Teams 需要連線到網際網路。 若要瞭解客戶在 Office 365 方案、政府和其他雲端中使用 Teams 能夠連線的端點，請參閱 [Office 365 URL 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。

> [!IMPORTANT]
> Teams 目前需要讓所有使用者存取 (TCP 通訊埠 443) 連線到 Google ssl.gstatic.com 服務 (<https://ssl.gstatic.com)>。即使您沒有使用 Gstatic 亦同。 Teams 很快會移除此要求 (2020 年初)，我們到時候也會更新本文。

## <a name="related-topics"></a>相關主題

[Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
