---
title: Microsoft Teams 會議室的條件式存取和合規性最佳做法
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 瞭解建議的條件式存取和Intune裝置合規性原則和Microsoft Teams 會議室的最佳做法。
ms.openlocfilehash: e16513a840dadf7a5cabe961a0fbbd9135da9b89
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606542"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Microsoft Teams 會議室的條件式存取和Intune合規性

本文針對在共用空間中使用的Microsoft Teams 會議室，提供條件式存取和Intune裝置合規性原則的需求和最佳做法。

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

## <a name="requirements"></a>需求

Teams 會議室必須已經部署在您要指派條件式存取原則的裝置上。 如果您尚未部署Teams 會議室，請參閱[建立會議室和共用 Teams 裝置的資源帳戶](with-office-365.md)和[在 Android 上部署Microsoft Teams 會議室](../devices/collab-bar-deploy.md)以取得詳細資訊。

需要 Azure Active Directory P1 服務方案才能使用條件式存取。 它已包含在Microsoft Teams 會議室授權中。

## <a name="teams-rooms-conditional-access-best-practices"></a>Teams 會議室條件式存取最佳做法

條件式存取原則可以保護位於共用空間且由多人使用的裝置上的登入程式。 如需 Azure Active Directory (Azure AD) 之條件式存取的概觀，請參閱 [Azure Active Directory 中什麼是條件式存取？](/azure/active-directory/conditional-access/overview)。

使用條件式存取來保護Teams 會議室時，請考慮下列最佳做法：

-   若要簡化部署和管理，請將所有與Teams 會議室關聯的 Microsoft 365 會議室資源帳戶包含在一個使用者群組中。

-   針對所有Teams 會議室資源帳戶設定命名標準。 例如，帳戶名稱「mtr-room1@contoso.com」和「mtr-room2@contoso.com」都是以前置詞「mtr-」開頭。
    當帳戶名稱標準化時，您可以使用 Azure AD 中的動態群組，一次自動將條件式存取原則套用到所有這些帳戶。 如需有關動態群組的詳細資訊，請參閱 [動態填入群組成員資格](/azure/active-directory/enterprise-users/groups-dynamic-membership) 規則。

如需Teams 會議室支援的條件式存取指派清單，請參閱[支援的條件式存取原則](supported-ca-and-compliance-policies.md#supported-conditional-access-policies)。

## <a name="example-conditional-access-policy"></a>條件式存取原則範例

在下列範例中，條件式存取原則的運作方式如下：

1.  帳戶登入必須是特定使用者群組的成員，在此範例中為「共用裝置」群組。

2.  帳戶登入時，必須只嘗試存取 Exchange Online、Microsoft Teams 或 SharePoint Online。 登入任何其他用戶端應用程式的嘗試將會遭到拒絕。

3.  資源帳戶必須登入 Windows 裝置平臺。

4.  資源帳戶也必須從已知、信任的位置登入。

如果成功符合這些條件，且使用者輸入正確的使用者名稱和密碼，資源帳戶就會登入 Teams。

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Teams 會議室Microsoft Intune合規性的條件式存取

合規性需求是已定義的規則，裝置必須符合該規則才能標示為符合規範，例如最低作業系統版本。 裝置必須符合規範，才能用來登入資源帳戶。

如需Teams 會議室支援的Intune合規性原則清單，請參閱[支援的裝置合規性原則](supported-ca-and-compliance-policies.md#supported-device-compliance-policies)。

如需有關使用 Teams Android 裝置設定Intune的詳細資訊，請參閱設定[Intune以註冊 Teams Android 裝置](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices)。

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>僅 (Windows) 範例：具有Intune裝置合規性的條件式存取

在此範例中，適用于 Windows 上的 Teams 會議室

1. 要求在 Windows 上的 Teams 會議室 上執行防火牆。

2. 要求 Microsoft Defender 在 Teams 會議室 上執行。

3. 如果 Teams 會議室不符合這些需求，就不會標示為符合規範，而且裝置也不會登入。

此合規性原則適用于所有使用者，而不只是 Teams 資源帳戶。
