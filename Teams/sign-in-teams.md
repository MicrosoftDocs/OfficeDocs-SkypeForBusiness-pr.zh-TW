---
title: 使用新式驗證登入 Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 了解新式驗證如何運作、如何切換帳戶，以及如何疑難排解新式驗證。 包含如何在登入時告訴 Teams 忽略預先填入的使用者名稱 (UPN)。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d6e4e8989bf26e4a907deec550d18f344728129
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868300"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>使用新式驗證登入 Microsoft Teams
==========================

Microsoft 建議組織使用最新版本的 Windows 10，內含有混合式網域加入或 Azure AD 加入設定。 這可確保在 Windows 網頁帳戶管理員中已將使用者的帳戶準備好，進而讓您以單一的方式登入 Teams 和其他 Microsoft 應用程式。 這可提供更好的使用者體驗 (無訊息式登入) 和加強的安全性狀況。

Microsoft Teams 使用新式驗證讓登入體驗更加簡單可靠。 若要瞭解使用者如何登入 Teams，請閱讀[登入 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。

## <a name="how-modern-authentication-works"></a>新式驗證的運作方式

新式驗證是一種程序，可讓 Teams 知道使用者已經在別處輸入其認證 (例如他們的工作電子郵件和密碼)，因此不需要再次輸入就能啟動應用程式。 這項體驗會根據幾項因素而有所不同，例如使用者是在 Windows 或在 Mac 上工作。 它也會根據您的組織是啟用單一要素驗證還是多重要素驗證而有所不同 (多重要素驗證通常牽涉到透過手機，提供唯一的驗證碼、輸入 PIN 或呈現指紋來驗證認證)。 以下是每個新式驗證案例的摘要。

### <a name="windows-users"></a>Windows 使用者

- 如果使用者已透過他們的公司或學校帳戶登入 Windows 或其他 Office 應用程式，當他們啟動 Teams 時，就可以直接進入應用程式。 不需要再輸入認證。

- Microsoft 建議使用 Windows 10 版本 1903 或更新版本，以獲得最佳的單一登入體驗。

- 如果使用者未登入他們的 Microsoft 公司或學校帳戶，當他們啟動 Teams 時，系統會要求他們提供單一要素或多重要素驗證 (SFA 或 MFA)，取決於您的組織決定要採取的程序。

- 如果使用者登入加入網域的電腦，當他們啟動 Teams 時，系統可能會要求他們執行一個進一步的驗證步驟，視您的組織是否選擇要求 MFA 或他們的電腦是否要求 MFA 才能登入而定。 如果使用者的電腦要求 MFA 才能登入，當他們開啟 Teams 時，應用程式會自動啟動。

- 在已加入網域的電腦上，如果無法使用 SSO，Teams 可能會使用使用者主體名稱 (UPN) 預先填入其登入畫面。 您可能不會想要這種情況發生，特別是如果您的組織在內部部署和 Azure Active Directory 中使用不同的 UPN。 如果是這樣，您可以使用下列 Windows 登錄機碼來關閉 UPN 的預先填入：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > 針對以 ".local" 或 ".corp" 結尾的使用者名稱，略過或忽略使用者名稱預先填入的功能依預設會開啟，因此您不需要設定登錄機碼就能關閉此功能。


### <a name="mac-users"></a>Mac 使用者

在 MacOS 上，Teams 會提示使用者輸入其使用者名稱和認證，並根據貴組織的設定，可能會提示多重要素驗證。 使用者輸入認證後，就不需要再次提供這些認證。 從這時起，只要他們在同一部電腦上工作，Teams 就會自動啟動。

## <a name="teams-for-ios-and-android-users"></a>適合 iOS 和 Android 使用者的 Teams

登入後，行動使用者將會看到目前登入或先前已在其裝置上登入的所有 Microsoft 365 帳戶清單。 使用者可以點擊任何帳戶登入。 以行動裝置登入會有下列兩種案例：
    
1. 如果選取的帳戶目前已登入其他 Office 365 或 Microsoft 365 app，系統會將該使用者直接移至 Teams。 使用者不需要再輸入認證。
    
2. 如果使用者未登入其 Microsoft 365 帳戶的其他位置，系統會要求他們提供單一要素或多重要素驗證 (SFA 或 MFA)，視貴組織針對 [行動裝置登入原則] 設定的內容而定。

### <a name="adding-multiple-accounts-to-teams"></a>新增多個帳戶至 Teams

IOS 和 Android 版的 Teams 支援將多個帳戶從單一裝置新增至 Teams。 下列影像顯示如何在 Teams 中新增多個帳戶。
    
:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="在 Teams 中新增多個帳戶":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a>使用企業行動管理來控制哪些帳戶可以登入 Teams

IOS 和 Android 版 Teams 提供 IT 系統管理員將帳戶設定推入 Microsoft 365 帳戶的功能。 這項功能可與任何使用 iOS [受控應用程式設定 ](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) 通道或 Android 的 [Android 企業](https://developer.android.com/work/managed-configurations) 通道的行動裝置管理 (MDM) 提供者相配合。

針對註冊于 Microsoft Intune 的使用者，您可以在 Azure 入口網站中使用 Intune 部署帳戶配置設定。

當 MDM 提供者設定好帳戶設定之後，且使用者註冊其裝置之後，iOS 和 Android 版 Teams 將只會在 Teams 登入頁面上顯示允許的帳戶。 使用者可以點擊此頁面中任何允許的帳戶以登入。

在受管理的裝置的 Azure Intune 入口網站中設定下列設定參數。


|平台 |機碼  |值  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **已啟用**: 唯一允許的帳戶是由 IntuneMAMUPN 機碼所定義的受管用戶帳戶。<br> **已停用** (或與 **啟用**不區分大小寫的任何值): 允許任何帳戶。        |
|iOS     |   **IntuneMAMUPN**      |   允許登入 Teams 的帳戶 UPN。<br> 如果您是 Intune 註冊的裝置，可以使用 {{userprincipalname}} 符號來代表已註冊的使用者帳戶。       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    只有允許帳戶是由此編碼定義的受管用戶帳戶。<br> 一或多個分號 [;]- delmited UPNs。<br> 如果您是 Intune 註冊的裝置，可以使用 {{userprincipalname}} 符號來代表已註冊的使用者帳戶。

當帳戶設定完成之後， Teams 會限制登入的能力，因此只有登入的裝置上允許的帳戶才能取得存取權。

若要為受管理的 iOS/iPadOS 裝置建立應用程式設定原則，請參閱 [新增受管理的 iOS/iPadOS 裝置 app 設定原則](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios)。

若要為受管理的 Android 裝置建立應用程式設定原則，請參閱 [新增受管理的 Android 裝置應用程式設定原則](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android)。


## <a name="switching-accounts-after-completing-modern-authentication"></a>完成新式驗證後切換帳戶

如果使用者正在加入網域的電腦 (例如，如果其租用戶已啟用 Kerberos) 上工作，他們在完成新式驗證之後，就無法切換使用者帳戶。 如果使用者不是在加入網域的電腦上工作，他們就可以切換帳戶。

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>完成新式驗證後登出 Teams

若要登出 Teams，使用者可以按一下應用程式頂端的個人檔案圖片，然後選取 **[登出]**，也可以在其工作列中的應用程式圖示上按一下滑鼠右鍵，然後選取 **[登出]**。登出 Teams 之後，必須再次輸入認證，才能啟動應用程式。

### <a name="signing-out-of-teams-for-ios-and-android"></a>登出 iOS 和 Android 的 Teams

行動使用者可以移至功能表，並選擇 **[更多]** 功能表，然後選擇 **[登出]**，以登出 Teams。一旦登出，使用者則需在下一次啟動該應用程式時，重新輸入認證。

> [!NOTE]
> Android 版 Teams 使用單一登入（SSO）來簡化登入體驗。 使用者除了 Team 以外，還應務必登出 **所有** 的 Microsoft 應用程式，以便完全登出 Android 平臺。

## <a name="urls-and-ip-address-ranges"></a>URL 和 IP 位址範圍

Teams 需要連線到網際網路。 若要瞭解客戶在 Office 365 方案、政府和其他雲端中使用 Teams 能夠連線的端點，請參閱 [Office 365 URL 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。

> [!IMPORTANT]
> Teams 目前需要讓所有使用者存取 (TCP 通訊埠 443) 連線到 Google ssl.gstatic.com 服務 (<https://ssl.gstatic.com)>。即使您沒有使用 Gstatic 亦同。 Teams 很快會移除此要求 (2020 年初)，我們到時候也會更新本文。

## <a name="troubleshooting-modern-authentication"></a>疑難排解新式驗證

每個使用 Teams 的組織都能使用新式驗證，因此如果使用者無法完成程序，您的網域或組織的 Microsoft 公司或學校帳戶可能有問題。

如需詳細資訊，請參閱[為何我無法登入 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)
