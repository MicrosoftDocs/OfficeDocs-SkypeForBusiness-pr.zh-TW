---
title: 設定通用區域電話授權
ms.author: czawideh
author: cazawideh
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
description: '瞭解如何為大廳、接收區域和會議室設定通用區域電話 '
ms.openlocfilehash: f3f3ee2c98e48a41bb12dcaa7fc461c623f49994
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045822"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>部署適用于 Microsoft Teams 的常見區域電話

常見的區域電話通常位於大廳或其他可供多人撥打電話的區域中;例如，接收區、大廳或會議電話。 通用區域電話是以系結至通用區域電話授權的帳戶登入。

本文提供如何將Teams電話部署及設定為共用空間常見區域電話的概觀。 若要獲得更完整的會議室體驗，包括音訊會議，請考慮使用會議室裝置購買專用會議室授權。

## <a name="overview"></a>概觀

通用區域電話授權支援：

|                                           | 通用區域電話                                 |
|-------------------------------------------|---------------------------------------------------|
| **Microsoft Teams**                       | &#x2714;                                          |
| **Teams 電話**&sup1;                   | &#x2714;                                          |
| **音訊會議**                    | &#x2718; &sup2;                                   |
| **Microsoft Intune**                      | &#x2714;                                          |
| **Azure Active Directory Premium方案 1** | &#x2714;                                          |
| **Exchange Online方案 2**                | &#x2714;  &sup3;                                  |
| **全球可用性**                | &#x2714;                                          |
| **通道可用性**                  | EA、EAS、EES、雲端解決方案提供者、Web Direct、GCC、GCC-High、DoD |

&sup1;先前稱為 電話系統。

&sup2;一般區域電話可以透過會議召集人提供的撥入號碼加入音訊會議。  

&sup3;僅限雲端式語音信箱功能。

>[!NOTE]
> 在 商務用 Skype Server 中建立的常見區域電話物件帳戶無法移轉至Microsoft Teams。 請依照本文中的步驟重新建立Teams帳戶，並視需要移轉您的 PTSN 連線能力。

## <a name="step-1---buy-the-licenses"></a>步驟 1 - 購買授權

首先，您需要購買通用區域電話 (CAP) 授權，並確定您有經過認證的手機。 若要搜尋並深入瞭解經過認證的手機，請移至[Microsoft Teams裝置](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。

1. 在Microsoft 365 系統管理中心中，移至 **帳單**  >  **購買服務**。 

2. 如果尚未顯示 [ **依類別檢視** ] 區段，請移至 [ **從 Microsoft 購買**]，然後選 **取 [檢視產品]**。 然後選取 [ **共同作業與通訊]**。  

3. 在產品清單中，尋找 [**通用區域] 電話**，然後選取 [**詳細資料]**。

4. 輸入您需要的授權數目，然後選取 [ **購買]**。

>[!NOTE]
>如果您在環境中使用Intune，並且有需要裝置合規性的條件式存取規則，您必須指派Azure Active Directory Premium方案 1，Intune一般區域電話的裝置帳戶授權。
>
>常見的區域電話可能會受到條件式存取規則及其他身分識別設定的影響，例如多重要素驗證。 若要深入瞭解，請參閱[Teams Android裝置的驗證最佳做法](devices/authentication-best-practices-for-android-devices.md)。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>步驟 2 - 建立新的使用者帳戶並指派授權

### <a name="using-the-microsoft-365-admin-center"></a>使用Microsoft 365 系統管理中心

如果您要一次部署一個以上的常見區域電話，請瞭解如何 [使用 PowerShell](#using-powershell)建立帳戶和指派授權。

如果您要部署一個裝置：

1. 在Microsoft 365 系統管理中心中，移至 **[使用者**  >  **作用中使用者**  >  **新增使用者]**。

2. 輸入名字的使用者名稱，例如「主要」，第二個名稱輸入「接收」。

3. 如果沒有自動產生顯示名稱，請輸入顯示名稱，例如「主要接收」。

4. 輸入使用者名稱，例如「MainReception」或「Mainlobby」。

5. 手動設定常用區域電話的密碼以防止。 若要這麼做，請取消核取 **[自動建立密碼** ]，並要求 **此使用者在第一次登入時變更密碼**。  

    >[!Important]
    > 強烈建議您手動設定常見區域電話的密碼，以防止使用者發生登入問題。

6. 選取裝置的使用位置，並將通用區域電話授權指派給帳戶。 如果需要任何其他授權，例如通話方案，請指派授權。

>[!NOTE]
> 您不需要新增電話系統授權。 它已包含在通用區域電話授權中。
>
>如果您不是使用 Microsoft 電話 System Direct Routing 或 電信業者連線，建議您新增通話方案授權。 如需授權的詳細資訊，請[參閱Microsoft Teams附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="using-powershell"></a>使用 PowerShell

當您想要一次建立並指派多個使用者帳戶的授權時，請使用 PowerShell。 如需詳細資訊，請參閱[使用 PowerShell 建立Microsoft 365使用者帳戶](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)和[使用 PowerShell 指派Microsoft 365授權給使用者帳戶](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)。

## <a name="step-3---set-policies-for-common-area-phones"></a>步驟 3 - 設定通用區域電話的原則

使用原則來控制哪些功能可供常用的區域電話使用者使用。

>[!NOTE]
>指派原則之後，請登出電話並重新登入。 可能需要長達一小時的時間，原則指派才會生效。

### <a name="ip-phone-policies"></a>IP 電話原則

使用已獲指派共同區域電話授權之帳戶登入的電話，將會顯示通用區域使用者體驗。

如果您想要覆寫手機的預設介面，請考慮建立 [IP 電話原則](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps&preserve-view=true)。 例如，如果公用區域使用通用的區域電話，請設定 IP 電話原則以限制搜尋貴組織的全域通訊錄，並封鎖快捷電話。 若要深入瞭解，請參閱[設定Teams Android裝置使用者介面](devices/Teams-Android-devices-user-interface.md)。

### <a name="calling-policies"></a>通話原則

使用通話原則啟用私人通話、使用來電轉接，或在常見區域電話上同時撥打電話。 若要深入瞭解，請參閱[Teams中的通話和來電轉接](teams-calling-policy.md)。

根據預設，一般區域電話不會啟用通話駐留。 您必須建立原則才能啟用它。 若要深入瞭解，請參閱[在 Microsoft Teams 中撥號並擷取公園](call-park-and-retrieve.md)。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>步驟 4 - 取得並指派電話號碼

請參閱 [管理貴組織的電話號碼](manage-phone-numbers-landing-page.md) ，瞭解如何根據 PSTN 連線選項取得及指派電話號碼。

## <a name="step-5---sign-in"></a>步驟 5 - 登入

建立並設定使用者帳戶後，您就可以登入手機。 根據您部署的手機數量而定，您有三個登入選項：

- [本機登入](#local-sign-in)
- [從其他裝置登入](#sign-in-from-another-device)
- [使用 Teams 系統管理中心登入](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>本機登入

若要使用使用者名稱和密碼在本機登入： 

1. 開啟常用區域電話

2. 選 **取 [在此裝置上登入]**

3. 依照裝置上的登入指示進行。 登入之後，手機將會顯示常見的區域電話使用者體驗。

> [!NOTE]
> 如果您使用取消釘選通話應用程式的自訂設定原則，撥號鍵台不會顯示在 [常用區域] 電話。 如需Teams設定原則的詳細資訊，請參閱[管理 Microsoft Teams 中的應用程式設定原則](/microsoftteams/teams-app-setup-policies)。

### <a name="sign-in-from-another-device"></a>從其他裝置登入

您也可以使用代碼從另一部裝置登入通用的區域電話。 當您以這種方式登入時，您會在另一個裝置上輸入使用者名稱和密碼，而不是在手機本身上。

1. 首先，在您常用的區域電話上，尋找登入畫面上顯示的代碼。

2. 在其他裝置上，移至 https://www.microsoft.com/devicelogin 。

3. 輸入驗證碼，然後依照指示完成登入。

### <a name="sign-in-using-the-teams-admin-center"></a>使用 Teams 系統管理中心登入

身為系統管理員，您可以從Teams系統管理中心遠端布建並登入通用的區域電話。 當您一次部署大量手機時，這是最有效率的登入方法。 若要深入瞭解，請參閱[遠端布建和登入Teams Android裝置](devices/remote-provision-remote-login.md)。

## <a name="next-steps"></a>後續步驟

現在您已為組織設定並登入通用的區域電話，您可以在Teams系統管理中心管理這些電話。 請[參閱Microsoft Teams：管理您的裝置](devices/device-management.md)以深入瞭解。

## <a name="related-topics"></a>相關主題

- [遠端更新Microsoft Teams裝置](devices/remote-update.md)
- [管理Microsoft Teams裝置標籤](devices/manage-device-tags.md)
- [Microsoft Teams裝置健康情況監視](alerts/device-health-status.md)
