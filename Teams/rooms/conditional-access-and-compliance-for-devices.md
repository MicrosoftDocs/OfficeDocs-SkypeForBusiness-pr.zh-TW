---
title: 條件式 Access 和合規性最佳做法Microsoft Teams 會議室
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 瞭解建議的條件式 Access 和 Intune 裝置合規性政策，以及適用于Microsoft Teams 會議室。
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689090"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>條件式 Access 和 Intune 合規性Microsoft Teams 會議室

本文提供共用空間中使用的條件式 Access 和 Intune 裝置合規性Microsoft Teams 會議室需求與最佳做法。

## <a name="requirements"></a>需求

Teams 會議室必須已經部署在您想要指派條件式 Access 策略的裝置上。 如果您尚未部署Teams 會議室，請參閱為會議室建立資源帳戶，Teams[](with-office-365.md)裝置共用，以及在[Android](../devices/collab-bar-deploy.md) Microsoft Teams 會議室部署資源帳戶。

使用條件式Azure Active Directory需要 P1 服務方案。 它包含在授權Microsoft Teams 會議室中。

## <a name="teams-rooms-conditional-access-best-practices"></a>Teams 會議室條件式 Access 最佳做法

條件式 Access 策略可保護共用空間中且由多人使用的裝置上的登錄程式。 有關中條件式存取的Azure Active Directory (Azure AD) 概觀，請參閱其中什麼是條件[式Azure Active Directory？](/azure/active-directory/conditional-access/overview)。

使用條件式 Access 保護Teams 會議室，請考慮下列最佳做法：

-   若要簡化部署和管理，請Microsoft 365一個使用者群組中Teams 會議室所有會議室資源帳戶。

-   針對所有資源帳戶Teams 會議室命名標準。 例如，帳戶名稱"mtr-room1@contoso.com"和"mtr-room2@contoso.com"都是以首碼 "0.5"開頭。
    當帳戶名稱標準化時，您可以使用 Azure AD 動態群組，一次自動將條件式 Access 原則套用至所有這些帳戶。 請參閱 [動態填入群組成員資格的規則](/azure/active-directory/enterprise-users/groups-dynamic-membership) ，以瞭解有關動態群組的資訊。

請參閱支援的條件式 Access [Teams 會議室清單。](supported-ca-and-compliance-policies.md#supported-conditional-access-policies)

## <a name="example-conditional-access-policy"></a>條件式 Access 策略範例

在下列範例中，條件式 Access 策略運作方式如下：

1.  帳戶登錄必須是特定使用者群組的成員，在此範例中為「共用裝置」群組。

2.  帳戶的登錄必須只嘗試存取 Exchange Online、Microsoft Teams或 SharePoint Online。 嘗試登錄任何其他用戶端應用程式將會遭到拒絕。

3.  資源帳戶必須在裝置平臺上Windows。

4.  資源帳戶也必須從已知、信任的位置進行登錄。

如果成功符合這些條件，且使用者輸入正確的使用者名稱和密碼，則資源帳戶會Teams。

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>條件式 Access Microsoft Intune合規性Teams 會議室

合規性需求是裝置必須符合的已定義規則，以標示為符合規範，例如最低作業系統版本。 必須先將裝置視為相容，才能用來登錄資源帳戶。

有關支援的 Intune 合規性政策清單Teams 會議室，請參閱[支援的裝置合規性政策](supported-ca-and-compliance-policies.md#supported-device-compliance-policies)。

有關使用 Android 裝置設定 Intune Teams，請參閱設定[Intune 以註冊 Android Teams裝置](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices)。

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>僅 (Windows範例) ：Intune 裝置合規性的條件式 Access

在此範例中，Teams 會議室Windows

1. 要求防火牆在 Teams 會議室 上Windows。

2. 要求 Microsoft Defender 在 Teams 會議室。

3. 如果Teams聊天室不符合上述任一需求，就不會標示為相容，且裝置無法登錄。

此合規性原則適用于所有使用者，而不只是Teams帳戶。
