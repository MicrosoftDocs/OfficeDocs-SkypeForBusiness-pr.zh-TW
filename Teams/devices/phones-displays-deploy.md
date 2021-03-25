---
title: 使用 Intune 部署 Teams 電話和 Teams
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 本文提供 Microsoft Teams 顯示所支援之概觀和功能。
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120775"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>使用 Intune 部署 Teams 電話和 Teams

本文提供如何使用 Intune 部署 Teams 電話和 Teams 顯示概觀。

## <a name="conditional-access"></a>條件式存取

條件式 Access 是 Azure Active Directory (Azure AD) 功能，可協助確保存取 Office 365 資源的裝置已妥善管理且安全。  如果您將條件式存取原則適用于 Teams 服務，Android 裝置 (包括 Teams 手機和 Teams) 會顯示存取 Teams 必須註冊至 Intune，其設定必須符合您的原則。  如果裝置未註冊到 Intune，或已註冊，但其設定不符合您的政策，條件式 Access 會防止使用者登錄或使用裝置上的 Teams 應用程式。

一般來說，Intune 中定義的合規性政策會指派給使用者群組。  這表示如果您指派 Android 合規性原則給 user@contoso.com，該原則會一併適用于 Android 智慧型手機，以及任何已 user@contoso.com Android 型的 Teams 裝置。

如果您使用條件式 Access，而需要強制執行 Intune 註冊，在貴組織中，您需要設定幾個專案，以順利註冊 Intune：

- **Intune 授權** 使用者必須擁有 Intune 授權，以登錄 Teams 裝置。  只要 Teams 裝置已登錄具有有效 Intune 授權之使用者帳戶，該裝置就會在 Microsoft Intune 中自動註冊，做為登錄程式之一部分。
- **設定 Intune** 您必須為 Android 裝置系統管理員註冊設定正確的 Intune 租使用者。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>設定 Intune 以註冊 Teams Android 型裝置

Android 版 Teams 裝置在 Intune 中透過 Android 裝置系統管理員和 DA (管理) 管理。 在裝置可以註冊到 Intune 之前，有幾個基本步驟可以執行。  如果您目前已經使用 Intune 管理裝置，您可能已經完成所有上述工作。  如果沒有，請執行以下工作：

1. 將 Intune MDM (行動裝置管理) 授權。  如果您之前從未使用過 Intune，您必須設定 MDM 授權，才能註冊裝置。 詳細資訊，請參閱 [設定行動裝置管理機關](/intune/fundamentals/mdm-authority-set)。  這是建立新 Intune 租使用者時必須執行一次的步驟。
2. 啟用 Android 裝置系統管理員註冊。 Android 型 Teams 裝置是使用 Intune 以裝置系統管理員裝置管理。  針對新建立租使用者，裝置系統管理員註冊預設為關閉。  詳細資訊，請參閱 [Android 裝置系統管理員註冊](/intune/enrollment/android-enroll-device-administrator)。
3. 指派授權給使用者。 註冊至 Intune 的 Teams 裝置使用者必須獲得有效的 Intune 授權。 詳細資訊，請參閱 [指派授權給使用者，讓使用者可以在 Intune 中註冊裝置](/intune/fundamentals/licenses-assign)。
4. 指派裝置系統管理員合規性政策。  建立 Android 裝置系統管理員合規性政策，並將其指派給包含要登錄 Teams 裝置之使用者的 Azure Active Directory 群組。 詳細資訊，請參閱使用 [合規性原則來設定使用 Intune 管理之裝置的規則](/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>另請參閱

[Teams 的電話](phones-for-teams.md)

[Microsoft Teams 的 IP 電話認證](teams-ip-phones.md)

[Teams 顯示](teams-displays.md)

[在 Teams 中管理裝置](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)