---
title: Android 裝置驗證最佳做法
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Android 裝置驗證Teams最佳做法指南。
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ffa30efd7f122b6d95c4545dd2d2517f3669472
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2021
ms.locfileid: "61576163"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>Android 裝置Teams驗證最佳做法

本文提供部署手機和通話裝置驗證Teams一般指南和最佳做法。

>[!NOTE]
>條件式 Access 需要Azure Active Directory (Azure AD) 進階版訂閱。

>[!NOTE]
>Android 行動裝置原則可能不適用於 Android Teams裝置。


## <a name="personal-and-shared-devices"></a>個人及共用裝置

共用Teams裝置 ，例如會議室裝置或一般地區電話，無法對通常適用于個人裝置之註冊和合規性使用相同的需求。 將個人裝置驗證需求適用于共用裝置會造成下列登錄問題：

1.  **由於密碼政策，裝置已退出**

在裝置Teams帳戶具有密碼到期政策。 與使用者不同的是，與共享裝置一起使用的帳戶沒有指定使用者來更新，並還原為密碼到期時的有效狀態。 如果貴組織需要密碼定期到期並重設，這些帳戶會在 Teams 裝置上停止運作，Teams系統管理員重設密碼並重新登錄。

2.  **由於條件式存取策略，裝置無法登錄**

共用裝置無法遵守使用者帳戶Azure AD個人裝置的條件式 Access 政策。 如果共用裝置與使用者帳戶或個人裝置分組，以取得條件式 Access 策略，則登錄將會失敗。

例如，如果需要多重要素驗證才能存取Teams，使用者必須介入才能完成驗證。 共用裝置不支援多重要素驗證。 同樣地，如果帳戶已配置為每 X 天重新驗證一次，則共用裝置無法解決沒有使用者介入的挑戰。

## <a name="best-practices-for-teams-shared-device-deployments"></a>共用裝置部署Teams最佳做法

Microsoft 建議在組織中部署Teams下列設定。

### <a name="password-policy"></a>**密碼政策**

Teams裝置應該使用Exchange[帳戶](/exchange/recipients-in-exchange-online/manage-resource-mailboxes)。 這些帳戶可以從 Active Directory 同步處理，或直接在 Azure AD。 使用者的任何密碼到期原則也會Teams共用裝置上所使用的帳戶。

若要避免密碼過期政策所造成的干擾，請設定共用裝置的密碼到期政策永不過期。

從 Teams 裝置 CY21 [Update #1 (Teams](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones)版本 1449/1.0.94.2021022403 開始適用于 Teams 手機) 和[CY2021 Update #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams Android) 上的 Microsoft Teams 會議室 版本 1449/1.0.96.2021051904，租使用者系統管理員可以遠端登入 Teams 裝置。 請勿與技術人員共用密碼以設定裝置。 系統管理員可以使用遠端登入來發行驗證碼，然後從系統管理中心Teams這些裝置。

詳細資訊，請參閱在 Android 裝置上遠端Teams[和登錄](/MicrosoftTeams/devices/remote-provision-remote-login)。 

### <a name="conditional-access-policies"></a>**條件式 Access 政策**

Azure AD條件式 Access 會設定裝置必須符合的其他需求，才能進行登錄。 針對Teams，請閱閱下列指南，判斷您是否已撰寫適當的政策。 有關條件式存取概觀，請參閱 [什麼是條件式存取](/azure/active-directory/conditional-access/overview)。

### <a name="multi-factor-authentication"></a>多重要素驗證

共用裝置的帳戶會連結至會議室或實體空間，而不是使用者帳戶。 由於共用裝置不支援多重要素驗證，因此將共用裝置排除在任何多重要素驗證政策中。

>[!TIP]
>使用指定 [位置](/azure/active-directory/conditional-access/location-condition) 或 [要求相容的裝置](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) 來保護共用裝置。

### <a name="location-based-access-with-named-locations"></a>具有指定位置的位置式存取

如果共用裝置是設定在定義明確的位置，可以識別為 IP 位址範圍，您可以使用這些裝置的名稱位置設定條件式存取。 [](/azure/active-directory/conditional-access/location-condition) 此條件將允許這些裝置在您的網路記憶體取您的公司資源。

### <a name="require-compliant-device"></a>需要相容的裝置

>[!NOTE]
>裝置合規性需要 Intune 授權。

如果您要將共用裝置註冊到 Intune，您可以將裝置合規性設定為條件式 Access 中的控制項，讓只有相容的裝置可以存取您的公司資源。 Teams，您可以根據裝置合規性為條件式 Access 策略來配置裝置。 詳細資訊，請參閱條件[式存取：需要相容](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)或混合式Azure AD裝置。

若要使用 Intune 為裝置設定合規性設定，請參閱使用合規性原則來設定使用 [Intune 管理之裝置的規則](/intune/protect/device-compliance-get-started)。

>[!NOTE]
> 用於 hotdesking 的共用裝置應排除在合規性政策之外。 合規性政策會防止裝置註冊到 Hot-desk 使用者帳戶。 請改為使用已命名的位置保護這些裝置。
> 若要增加安全性，除了指定位置[](/azure/active-directory/authentication/tutorial-enable-azure-mfa)策略之外，您也可以要求對桌面使用者進行多重要素驗證。

### <a name="sign-in-frequency"></a>登錄頻率

在條件式 Access[](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency)中，您可以設定登錄頻率，要求使用者在指定的時段之後再次登錄以存取資源。 如果會議室帳戶強制執行登錄頻率，則共用裝置會登出，直到系統管理員再次登錄。Microsoft 建議從任何登錄頻率政策中排除共用裝置。

### <a name="filters-for-devices"></a>裝置篩選

[裝置篩選是](/azure/active-directory/conditional-access/concept-condition-filters-for-devices)條件式 Access 中的一項功能，可讓您根據裝置中可用的裝置屬性設定更精細Azure AD。 您也可以在裝置物件上設定擴充屬性 1-15，然後使用這些副檔名屬性，以使用您自己的自訂值。

使用裝置篩選來識別您的公用區域裝置，並啟用兩種關鍵案例的策略：

1.  從適用于個人裝置的政策中排除共用裝置。 例如，要求裝置合規性並非針對用於熱桌面的共用裝置強制執行，而是根據型號對所有其他裝置強制執行。

2.  在不應適用于個人裝置之共用裝置上強制執行特殊原則。 例如，僅根據您針對這些裝置所設定擴充屬性的公用區域裝置，要求將指定位置做為 (例如：「CommonAreaPhone」) 。

>[!NOTE] 
> 某些屬性 ，例如 **模型**、 **製造商** 和 **operatingSystemVersion** 只能在 Intune 管理裝置時設定。 如果您的裝置不是由 Intune 管理，請使用擴充屬性。