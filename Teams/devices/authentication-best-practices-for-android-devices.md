---
title: Android 裝置共用Microsoft Teams的驗證最佳做法。
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 在 Teams 中共用 android 裝置管理Teams。 此功能具有條件式存取、密碼原則、多重要素驗證建議等功能。
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
ms.openlocfilehash: 070c662c09d8b8159dbce850501026f67dabb203
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279231"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Android 裝置上Teams裝置管理的驗證最佳做法

與裝置一起使用的裝置Teams需要不同的裝置管理原則。 例如，單一銷售人員使用的個人商務平板電腦與許多客戶服務人員共用的通話電話有不同的需求。

安全性系統管理員和操作小組必須規劃組織中可以使用的裝置。 他們必須執行 *最適合* 每個用途的安全措施。 本文的建議可簡化其中一些決策。

>[!NOTE]
>條件式 Access 需要Azure Active Directory (Azure AD) 進階版訂閱。

>[!NOTE]
>Android 行動裝置原則可能不適用於 Android Teams裝置。

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>個人與共享 Android 裝置的不同驗證建議

共用Teams裝置無法對個人裝置使用的註冊和合規性使用相同的需求。 將個人裝置驗證需求適用于共用裝置會造成登錄問題。

1.  **裝置會因為密碼政策而退出。**

在裝置Teams帳戶具有密碼到期政策。 與共享裝置一起使用的帳戶沒有特定使用者可以更新，並且會在密碼到期時還原到工作狀態。 如果貴組織需要密碼過期並偶爾重設，這些帳戶Teams裝置上停止使用，直到 Teams 系統管理員重設密碼並重新登錄為止。

**挑戰**：存取時。 Teams裝置，則某人的帳戶具有密碼到期政策。 當密碼即將到期時，他們只要變更密碼。 但是，在 *共用裝置 (* 資源帳戶) 帳戶可能不會與可以變更密碼的同一個人進行連接。 這表示密碼可能會過期，讓員工留在現場，而不知道如何繼續工作。

當貴組織需要重設密碼或強制執行密碼到期時，請確定Teams系統管理員準備好重設密碼，讓這些共用帳戶可以重新登錄。

2.  **由於條件式存取策略，裝置無法登錄。**

**挑戰**：共用裝置無法遵守使用者帳戶Azure AD個人裝置的條件式存取政策。 如果共用裝置與使用者帳戶或個人裝置分組，以取得條件式 Access 策略，則登錄 *將會失敗*。

例如，如果需要多重要素驗證才能存取Teams，使用者需要輸入程式碼才能完成該驗證。 共用裝置通常沒有一個使用者可以設定及完成多重要素驗證。 此外，如果帳戶必須每隔 X 天重新驗證一次，則共用裝置若沒有使用者的介入，就無法解決這項挑戰。

共用裝置不支援多重要素驗證。 以下是要改為使用的方法。

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>使用手機部署共用 android 裝置Teams

Microsoft 建議在組織中部署Teams下列設定。

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**使用資源帳戶並縮減其密碼到期時間**

Teams裝置應該使用Exchange[信箱](/exchange/recipients-in-exchange-online/manage-resource-mailboxes)。 建立這些信箱會自動產生帳戶。 這些帳戶可以同步處理至 Active Directory Azure AD，或直接在 Azure AD 中Azure AD。 使用者的任何密碼到期原則也會套用至 Teams 共用裝置上所使用的帳戶，因此為了避免密碼過期原則所造成的干擾，請設定共用裝置的密碼到期原則永不過期。

從 Teams 裝置 CY21 [Update #1 (Teams](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones)版本 1449/1.0.94.2021022403 開始適用于 Teams 手機) 和[CY2021 更新 #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams Android) 上的 Microsoft Teams 會議室 版本 1449/1.0.96.2021051904，租使用者系統管理員可以遠端登入 Teams 裝置。 租使用者系統管理員應該使用遠端登入來發出驗證碼，而不是與技術人員共用密碼來設定裝置。 您可以在系統管理中心針對這些裝置Teams。

詳細資訊請參閱在 Android 裝置上遠端Teams[和登錄](/MicrosoftTeams/devices/remote-provision-remote-login)。 

### <a name="review-these-conditional-access-policies"></a>**查看這些條件式 Access 政策**

Azure AD條件式 Access 會設定裝置必須符合的其他需求，才能進行登錄。 針對Teams，請閱閱以下指南，判斷您是否撰寫了允許共用裝置使用者執行其工作的政策。

> [!TIP]
> 有關條件式存取概觀，請參閱 [什麼是條件式存取](/azure/active-directory/conditional-access/overview)？

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>請勿對共用裝置使用多重要素驗證

共用裝置的帳戶會連結至會議室或實體空間，而非使用者帳戶。 由於共用裝置不支援多重要素驗證，因此將共用裝置排除在任何多重要素驗證政策中。

>[!TIP]
>使用指定 [位置](/azure/active-directory/conditional-access/location-condition) 或 [要求相容的裝置](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) 來保護共用裝置。

### <a name="you-can-use-location-based-access-with-named-locations"></a>您可以將位置式存取與命名位置一起使用

如果共用裝置是設定在定義明確的位置，可以識別為 IP 位址範圍，您可以使用這些裝置的名稱位置設定條件式存取。[ ](/azure/active-directory/conditional-access/location-condition) 此條件將允許這些裝置在您的網路記憶體取您的公司資源。

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>何時不需要相容的共用裝置

>[!NOTE]
>裝置合規性需要 Intune 授權。

如果您要將共用裝置註冊到 Intune，您可以將裝置合規性設定為條件式 Access 中的控制項，讓只有相容的裝置可以存取您的公司資源。 Teams根據裝置合規性，針對條件式 Access 策略來為裝置進行配置。 詳細資訊，請參閱條件[式存取：需要相容](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)或混合式Azure AD裝置。

若要使用 Intune 為裝置設定合規性設定，請參閱使用合規性原則來設定使用 [Intune 管理之裝置的規則](/intune/protect/device-compliance-get-started)。

>[!NOTE]
> 用於熱桌面的共用裝置應排除在合規性政策之外。 合規性政策會防止裝置註冊到 Hot desk 使用者帳戶。 **請改為使用已命名的位置保護這些裝置**。
> 若要增加安全性，除了指定的位置 [](/azure/active-directory/authentication/tutorial-enable-azure-mfa)策略之外，您也可以要求對桌面使用者 */* 使用者帳戶進行多重要素驗證。

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>從登錄頻率條件排除共用裝置

在條件式 Access 中，[](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency)您可以設定登錄頻率，要求使用者在指定的時段之後再次登錄以存取資源。 如果會議室帳戶強制執行登錄頻率，則共用裝置會登出，直到系統管理員再次登錄。Microsoft 建議從任何登錄頻率政策中排除共用裝置。

### <a name="using-filters-for-devices"></a>使用裝置篩選

[裝置篩選是](/azure/active-directory/conditional-access/concept-condition-filters-for-devices)條件式 Access 中的一項功能，可讓您根據裝置中可用的裝置屬性設定更精細Azure AD。 您也可以在裝置物件上設定擴充屬性 1-15，然後使用這些副檔名屬性，以使用您自己的自訂值。

使用裝置篩選來識別您的公用區域裝置，並啟用兩種關鍵案例的策略：

1.  從適用于個人裝置的政策中排除共用裝置。 例如，要求裝置合規性並非針對用於熱桌面的共用裝置強制執行，而是根據型號對所有其他裝置強制執行。

2.  在不應適用于個人裝置之共用 *裝置上強制執行* 特殊原則。 例如，僅根據您針對這些裝置所設定擴充屬性的公用區域裝置，要求將指定位置做為 (例如：「CommonAreaPhone」) 。

>[!NOTE] 
> 只有在 Intune 管理裝置時，才能設定某些屬性 ，例如模型、製造商和 **OperatingSystemVersion**。 如果您的裝置不是由 Intune 管理，請使用擴充屬性。
