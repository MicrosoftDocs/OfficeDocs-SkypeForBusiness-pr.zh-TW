---
title: 設定通用區域電話授權
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
- admindeeplinkMAC
- admindeeplinkTEAMS
description: 瞭解如何為大廳、接收區域和會議室設定通用區域電話。
ms.openlocfilehash: 2a282526a0592c46c053e9c0319112a9238a6051
ms.sourcegitcommit: 92a0df6fc3aa62cec1bf72a40690fb8e16226965
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2022
ms.locfileid: "68836747"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>為 Microsoft Teams 設定通用的區域電話

常見的區域電話通常會放在大廳或其他區域，供許多人撥打電話：接收區、大廳或會議電話。 通用區域電話是以系結至 **通用區域電話** 授權的帳戶登入。

本文將概略說明如何將 Teams 手機裝置部署及設定為共用空間的常見區域電話。 若要獲得更完整的會議室體驗，包括音訊會議，請考慮改為使用Teams 會議室裝置購買專用 **Teams 會議室** 授權。 如需Teams 會議室的詳細資訊，請參[閱Microsoft Teams 會議室](rooms/index.md)。

## <a name="overview"></a>概觀

**通用區域電話** 授權支援：

|                                           | 通用區域電話                                 |
|-------------------------------------------|---------------------------------------------------|
| **Microsoft Teams**                       | &#x2714;                                          |
| **Teams Phone**  &sup1;                   | &#x2714;                                          |
| **音訊會議**                    | &#x2718; &sup2;                                   |
| **Microsoft Intune**                      | &#x2714;                                          |
| **Azure Active Directory Premium方案 1** | &#x2714;                                          |
| **Exchange Online方案 2**                | &#x2714;  &sup3;                                  |
| **全球可用性**                | &#x2714;                                          |
| **通道可用性**                  | EA、EAS、EES、雲端解決方案提供者、Web Direct、GCC、GCC-High、DoD |

&sup1;先前稱為 *電話系統*。
&sup2;常見的區域電話可以透過會議召集人提供的撥入號碼加入音訊會議。
&sup3;僅限雲端式語音信箱功能。

> [!NOTE]
> 在 商務用 Skype Server 中建立的常見區域電話物件帳戶無法移轉至 Microsoft Teams。 請依照本文中的步驟重新建立 Teams 帳戶，並視需要移轉您的公用交換電話網路 (PSTN) 連線。

## <a name="step-1---buy-the-licenses"></a>步驟 1 - 購買授權

首先，您需要購買 **通用區域電話** (CAP) 授權，並確定您有經過認證的手機。 若要搜尋並深入瞭解已認證的手機，請移至 [Microsoft Teams 裝置](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。

1. 在 [Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)中，移至 **帳單**  >  **購買服務**。

2. 如果尚未顯示 [ **依類別檢視** ] 區段，請移至 [ **從 Microsoft 購買**]，然後選 **取 [檢視產品]**。 然後選取 [ **共同作業與通訊]**。  

3. 在產品清單中，尋找 **[通用區域電話]**，然後選取 [ **詳細資料]**。

4. 輸入您需要的授權數目，然後選取 [ **購買]**。

> [!NOTE]
> 如果您在環境中使用Intune，並且有需要裝置合規性的條件式存取規則，您必須指派 **Azure Active Directory Premium方案 1****，Intune一** 般區域電話的裝置帳戶授權。
>
> 常見的區域電話可能會受到條件式存取規則及其他身分識別設定的影響，例如多重要素驗證。 若要深入瞭解，請參閱 [Teams Android 裝置的驗證最佳做法](devices/authentication-best-practices-for-android-devices.md) 。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>步驟 2 - 建立新的使用者帳戶並指派授權

### <a name="using-the-microsoft-365-admin-center"></a>使用Microsoft 365 系統管理中心

如果您要一次部署一個以上的常見區域電話，請瞭解如何 [使用 PowerShell](#using-powershell)建立帳戶和指派授權。

如果您要部署一個裝置：

1. 在 [Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)中，移至 **[使用者**  >  **作用中使用者**  >  **新增使用者]**。

2. 輸入使用者名稱，例如 `Main` 名字和第 `Reception` 二個名稱。

3. 如果顯示名稱不會自動產生，請輸入顯示 `Main Reception` 名稱。

4. 輸入使用者名稱，例如 `MainReception` 或 `Mainlobby` 。

5. 手動設定常見區域電話的密碼。 若要設定密碼，請取消核取 **[自動建立密碼** ]，並要求 **此使用者在第一次登入時變更密碼**。  

    > [!IMPORTANT]
    > 強烈建議您手動設定常見區域電話的密碼，以免使用者發生登入問題。

6. 選取裝置的使用位置，並將 **通用區域電話** 授權指派給帳戶。 如果需要任何其他授權，例如通話方案，請指派授權。

> [!NOTE]
> 您不需要使用電話系統功能新增授權。 它已包含在 **通用區域電話** 授權中。
>
> 如果您不是使用 Microsoft Phone System 搭配直接路由或運算子連線，建議您新增 **通話方案** 授權。 如需授權的詳細資訊，請參閱 [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="using-powershell"></a>使用 PowerShell

當您想要一次建立並指派多個使用者帳戶的授權時，請使用 PowerShell。 如需詳細資訊，請參閱 [使用 PowerShell 建立 Microsoft 365 使用者帳戶](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) 和 [使用 PowerShell 指派 Microsoft 365 授權給使用者帳戶](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

## <a name="step-3---set-policies-for-common-area-phones"></a>步驟 3 - 設定通用區域電話的原則

使用原則來控制哪些功能可供常用的區域電話使用者使用。

### <a name="ip-phone-policies"></a>IP 電話原則

Teams IP Phone 原則只有在帳戶登入手機時授權使用 [通用區域電話] 授權以外的專案時，才能修改。  如果授權使用 Microsoft 365 E3 或 E5 訂閱，或是 Office 365 企業版 E1、E3 或 E5 訂閱，您可以修改 IP Phone 原則。  如果您在常用區域電話帳戶上使用會議室授權，則只能讓您使用 `MeetingRoomSignIn` 模式。 `MeetingRoomSignIn` 模式無法在大多數常見的區域電話上使用。 如需手機介面支援覆寫功能的詳細資訊，請參閱 [設定 Microsoft Teams Android 裝置使用者介面](/microsoftteams/devices/teams-android-devices-user-interface#override-automatic-user-interface-detection)。 

使用 Teams IP Phone 原則，設定 [SignInMode 參數](/powershell/module/skype/new-csteamsipphonepolicy#parameters) 以 `CommonAreaPhoneSignIn` 在 Teams 手機裝置上啟用常見區域電話體驗。

若要設定其他參數，請考慮建立 [IP 電話原則](/powershell/module/skype/new-csteamsipphonepolicy)。 例如，如果公用區域使用通用的區域電話，請設定 IP 電話原則以限制搜尋貴組織的全域通訊錄，並封鎖快捷電話。 若要深入瞭解，請參閱 [設定 Teams Android 裝置使用者介面](/microsoftteams/devices/Teams-Android-devices-user-interface)。

### <a name="calling-policies"></a>通話原則

使用通話原則啟用私人通話、使用來電轉接，或在常見區域電話上同時撥打電話。 若要深入瞭解，請參閱 [Teams 中的通話和來電轉接](teams-calling-policy.md)。

根據預設，一般區域電話不會啟用通話駐留。 您必須建立原則才能啟用它。 若要深入瞭解，請參閱 [在 Microsoft Teams 中通話和擷取公園](call-park-and-retrieve.md)。

> [!NOTE]
> 指派原則之後，請登出電話並重新登入。 可能需要長達一小時的時間，原則指派才會生效。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>步驟 4 - 取得並指派電話號碼

請參閱 [管理貴組織的電話號碼](manage-phone-numbers-landing-page.md) ，瞭解如何根據 PSTN 連線選項取得及指派電話號碼。

## <a name="step-5---sign-in"></a>步驟 5 - 登入

建立並設定使用者帳戶後，您就可以登入手機。 根據您部署的手機數量而定，您有三個登入選項：

- [本機登入](#local-sign-in)。
- [從其他裝置登入](#sign-in-from-another-device)。
- [使用 Teams 系統管理中心登](#sign-in-using-the-teams-admin-center)入。

### <a name="local-sign-in"></a>本機登入

若要使用使用者名稱和密碼在本機登入：

1. 開啟常用區域電話。
2. 選 **取 [在此裝置上登入]**。
3. 依照裝置上的登入指示進行。 登入之後，手機將會顯示常見的區域電話使用者體驗。

> [!NOTE]
> 如果您使用取消釘選通話應用程式的自訂設定原則，撥號鍵台不會出現在常見的區域電話上。 如需 Teams 設定原則的詳細資訊，請參閱 [管理 Microsoft Teams 中的應用程式設定原則](teams-app-setup-policies.md)。

### <a name="sign-in-from-another-device"></a>從其他裝置登入

您也可以使用代碼從另一部裝置登入通用的區域電話。 當您以這種方式登入時，您會在另一個裝置上輸入使用者名稱和密碼，而不是在手機本身上。

1. 在您常用的區域電話上，尋找登入畫面上顯示的代碼。
2. 在其他裝置上，移至 [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin) 。
3. 輸入驗證碼，然後依照指示完成登入。

### <a name="sign-in-using-the-teams-admin-center"></a>使用 Teams 系統管理中心登入

身為系統管理員，您可以從 Teams 系統管理 [中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)遠端布建並登入常見區域電話。 當您一次部署大量手機時，這個方法是最有效率的登入方法。 若要深入瞭解，請參閱 [遠端布建和登入 Teams Android 裝置](devices/remote-provision-remote-login.md) 。

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>步驟 6 - 在常見區域電話上設定進階通話 (選用) 

根據預設，基本通話體驗會位於通用區域電話的主畫面，但您可以開啟進階通話體驗。

下列進階通話功能適用于具有 **通用區域電話** 授權的支援 Teams 手機裝置型號，以及最新 Teams 更新 (最低版本：1449/1.0.94.2022061702) ：

- [撥號到公園並擷取](call-park-and-retrieve.md)。
- [透過Exchange Online方案 2 的雲端式語音信箱](set-up-phone-system-voicemail.md)。
  - 若要停用雲端式語音信箱，請參閱 [使用 PowerShell 的語音信箱使用者設定](/powershell/module/skype/set-csonlinevoicemailusersettings)。
- [通話佇列](create-a-phone-system-call-queue.md)。
- [自動語音應答](create-a-phone-system-auto-attendant.md)。
- [群組通話接聽](call-sharing-and-group-call-pickup.md)。
- [轉寄規則](teams-calling-policy.md)。

若要在支援的 Teams 手機裝置型號上使用這些進階通話功能，您可以在 [Teams 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)或已登入 [通用區域電話] 帳戶的 Teams 手機裝置上開啟 [**進階通話**] 切換開關。

開啟進階通話功能需要您購買可支援所有必要功能的硬體型號。

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>在 Teams 系統管理中心開啟 [進階通話]

1. 使用 Microsoft 365 系統管理員帳戶登入 [Teams 系統管理中心](https://admin.teams.microsoft.com/dashboard) 。
1. 從左側功能表流覽至 **Teams 裝置**  >  **手機**>，然後選取 [**設定設定檔] 索引** 標籤。
1. 從清單中，選取指派給常用區域電話的組態設定檔。
1. 在 [ **通話設定]** 區段底下，尋找 [ **進階通話** ] 切換開關。
1. 開啟切換開關。
1. 在頁面底部，選取 [儲存 **]** 按鈕。

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>從 Teams 手機裝置開啟進階通話

1. 登入您的 Teams 手機裝置後，流覽至 [**設定**  >  **裝置設定**  >  **]管理員僅**  >  **通話]**。
1. 尋找 [ **進階通話** ] 切換開關並將其開啟。

## <a name="next-steps"></a>後續步驟

現在您已為組織設定並登入通用的區域電話，您可以在 Teams 系統管理中心進行管理。 請參閱 [Microsoft Teams：管理您的裝置](devices/device-management.md) 以深入瞭解。

## <a name="related-articles"></a>相關文章

- [遠端更新 Microsoft Teams 裝置](devices/remote-update.md)。
- [管理 Microsoft Teams 裝置標籤](devices/manage-device-tags.md)。
- [Microsoft Teams 裝置健康情況監視](alerts/device-health-status.md)。
