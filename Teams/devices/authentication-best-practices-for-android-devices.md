---
title: Microsoft Teams 共用 Android 裝置管理的驗證最佳做法。
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 在 Teams 中共用 Android 裝置管理的最佳做法。 這項功能包括條件式存取、密碼原則、多重要素驗證建議等等。
ms.collection:
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0f658a70235440563d7cb3910830c56923b60f3e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270098"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Android 裝置上 Teams 共用裝置管理的驗證最佳做法

與 Teams 搭配使用的裝置目標需要不同的裝置管理原則。 例如，單一銷售人員所使用的個人商務平板電腦，與許多客戶服務人員共用的通話電話有不同的需求。

安全性系統管理員和營運團隊必須針對組織中可用的裝置進行規劃。 他們必須實作最適合每個用途 *的安全* 性措施。 本文提供的建議可讓您更輕鬆地做出其中一些決策。

>[!NOTE]
>條件式存取需要 Azure Active Directory (Azure AD) Premium 訂閱。

>[!NOTE]
>Android 行動裝置的原則可能不適用於 Teams Android 裝置。

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>個人與共享 Android 裝置的驗證建議不同

共用的 Teams 裝置無法對個人裝置上使用的註冊和合規性使用相同的要求。 將個人裝置驗證需求套用至共用裝置會導致登入問題。

1.  **裝置已登出，因為密碼原則。**

在 Teams 裝置上使用的帳戶有密碼過期原則。 與共享裝置搭配使用的帳戶不會有特定使用者在密碼過期時更新並還原到正常運作狀態。 如果貴組織要求密碼必須過期並偶爾重設，這些帳戶將會在 Teams 裝置上停止運作，直到 Teams 系統管理員重設密碼並重新登入為止。

**挑戰**：存取時。 來自裝置的 Teams，人員的帳戶有密碼過期原則。 密碼即將過期時，只要變更密碼即可。 但是在 *共用裝置* 上使用的帳戶 (資源帳戶) 可能無法連線到可以視需要變更密碼的單一人員。 這表示密碼可能會過期並讓員工不知如何繼續工作。

當貴組織要求重設密碼或強制執行密碼到期時，請確定已準備好讓 Teams 系統管理員重設密碼，讓這些共用帳戶可以重新登入。

2.  **裝置無法登入，因為條件式存取原則。**

**挑戰**：共用裝置無法遵守使用者帳戶或個人裝置的 Azure AD 條件式存取原則。 如果共用裝置是依條件式存取原則與使用者帳戶或個人裝置分組，則登入將會 *失敗*。

例如，如果存取 Teams 需要多重要素驗證，使用者必須輸入驗證碼才能完成驗證。 共用裝置通常沒有單一使用者可以設定及完成多重要素驗證。 此外，如果帳戶必須每隔 X 天重新撰寫一次，共用裝置就無法在沒有使用者介入的情況下解決此挑戰。

共用裝置不支援多重要素驗證。 使用方法如下所述。

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>使用 Teams 部署共用 Android 裝置的最佳做法

在貴組織中部署 Teams 裝置時，Microsoft 建議您使用下列設定。

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**使用資源帳戶並取消密碼到期**

Teams 共用裝置應使用 [Exchange 資源信箱](/exchange/recipients-in-exchange-online/manage-resource-mailboxes)。 建立這些信箱會自動產生帳戶。 這些帳戶可以從 Active Directory 同步處理至 Azure AD，或直接在 Azure AD 中建立。 使用者的任何密碼到期原則也會套用至 Teams 共用裝置上使用的帳戶，因此，若要避免密碼過期原則造成的干擾，請將共用裝置的密碼到期原則設為永不過期。

從 Teams 裝置 CY21[更新開始 #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (適用于 Android) 的 Teams 手機版 Teams 版本 1449/1.0.94.2021022403) 和[CY2021 更新 #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams 版本 1449/1.0.96.202105190 Microsoft Teams 會議室4， 租使用者系統管理員可以遠端登入 Teams 裝置。 租使用者系統管理員應使用遠端登入來發行驗證碼，而不是與技術人員共用密碼來設定裝置。 您可以從 Teams 系統管理中心登入這些裝置。

如需詳細資訊，請參閱 [Teams Android 裝置的遠端布建和登入](/MicrosoftTeams/devices/remote-provision-remote-login)。 

### <a name="review-these-conditional-access-policies"></a>**檢閱這些條件式存取原則**

Azure AD 條件式存取會設定裝置在登入時必須符合的其他需求。 針對 Teams 裝置，請檢閱下列指導方針，以判斷您是否已撰寫允許共用裝置使用者執行其工作的原則。

> [!TIP]
> 如需條件式存取的概觀，請參閱 [什麼是條件式存取](/azure/active-directory/conditional-access/overview)？

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>不要在共用裝置上使用多重要素驗證

共用裝置的帳戶會連結至會議室或實體空間，而不是使用者帳戶。 因為共用裝置不支援多重要素驗證，因此將共用裝置排除在任何多重要素驗證原則之外。

>[!TIP]
>使用 [具名位置](/azure/active-directory/conditional-access/location-condition) 或 [需要符合規範的裝置](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) 來保護共用裝置。

### <a name="you-can-use-location-based-access-with-named-locations"></a>您可以將位置型存取與具名位置搭配使用

如果共用裝置是在定義清楚的位置布建，可以使用 IP 位址範圍識別，您可以使用這些裝置的 [具名位置](/azure/active-directory/conditional-access/location-condition) 來設定條件式存取。 此條件可讓這些裝置僅在您的網路記憶體取您的公司資源。

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>何時不需符合規範的共用裝置

>[!NOTE]
>裝置合規性需要Intune授權。

如果您要將共用裝置註冊到 Intune，您可以將裝置合規性設定為條件式存取中的控制項，以便只有相容的裝置可以存取您的公司資源。 Teams 裝置可以根據裝置合規性來設定條件式存取原則。 如需詳細資訊，請參閱 [條件式存取：需要符合規範或混合式 Azure AD 加入的裝置](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。

若要使用Intune設定裝置的合規性設定，請參閱[使用合規性原則為您使用Intune管理的裝置設定規則](/intune/protect/device-compliance-get-started)。

>[!NOTE]
> 應將用於 *熱桌的* 共用裝置排除在合規性原則之外。 合規性原則可防止裝置註冊至熱門桌面使用者帳戶。 **請改用具名位置來保護這些裝置**。
> 若要提高安全性，除了具名的位置原則之外，您還可以為 *熱門桌面使用者/使用者帳戶*[要求多重要素驗證](/azure/active-directory/authentication/tutorial-enable-azure-mfa)。

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>排除共用裝置的登入頻率條件

在條件式存取中，您可以 [設定登入頻率](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) ，要求使用者在指定的時段後再次登入以存取資源。 如果對聊天室帳戶強制執行登入頻率，共用裝置將會登出，直到系統管理員再次登入為止。Microsoft 建議您將共用裝置排除在任何登入頻率原則之外。

### <a name="using-filters-for-devices"></a>使用裝置的篩選

[裝置篩選](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) 是條件式存取中的一項功能，可讓您根據 Azure AD 中提供的裝置屬性，為裝置設定更細化的原則。 您也可以在裝置物件上設定 1-15 副檔名屬性，然後使用這些值，藉此使用您自己的自訂值。

使用裝置的篩選來識別您的常見區域裝置，並在兩個關鍵案例中啟用原則：

1.  從適用于個人裝置的原則中排除共用裝置。 例如，對於用於熱門桌面的共用裝置 *，不會強制要求* 裝置合規性，但會根據型號對所有其他裝置 *強制執行* 。

2.  在 *不應* 套用至個人裝置的共用裝置上強制執行特殊原則。 例如，根據您為這些裝置設定的擴充功能屬性要求命名位置為原則， (例如：「CommonAreaPhone」) 。

>[!NOTE] 
> 只有當裝置由 Intune 管理時，才能設定 **型號**、**製造商** 和 **操作SystemVersion** 等某些屬性。 如果您的裝置不受Intune管理，請使用擴充功能屬性。
