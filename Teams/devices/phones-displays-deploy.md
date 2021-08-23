---
title: 使用 intune Teams Android Teams手機、Microsoft Teams 會議室和手機
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
description: 本文提供螢幕顯示功能Microsoft Teams概觀。
ms.openlocfilehash: e7772de5767b9aefe69e1192051be65ccb632656
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359160"
---
# <a name="deploy-teams-phones-teams-displays-and-microsoft-teams-rooms-on-android-using-intune"></a>使用 intune Teams Android Teams手機、Microsoft Teams 會議室和手機

本文提供如何在 Android 上使用 intune Teams手機、Teams和Microsoft Teams 會議室部署概觀。

## <a name="conditional-access"></a>條件式存取

條件式存取Azure Active Directory (Azure AD) 功能，可協助確保存取您資源Office 365且安全。  如果您將條件式存取原則適用于 Teams 服務，Android 裝置 (包括 Teams 手機、Teams 顯示器，以及 Android) Teams 上的 Microsoft Teams 會議室 必須註冊至 Intune，其設定必須符合您的原則。  如果裝置未註冊到 Intune，或已註冊，但其設定不符合您的政策，條件式 Access 會防止使用者登錄或使用裝置上的 Teams 應用程式。

一般來說，Intune 中定義的合規性政策會指派給使用者群組。  這表示如果您將 Android 合規性原則指派給 user@contoso.com，該原則會平均適用于 Android 智慧型手機，以及任何Teams登錄的 Android user@contoso.com 裝置。

如果您使用條件式 Access，而需要強制執行 Intune 註冊，在貴組織中，您需要設定幾個專案，以順利註冊 Intune：

- **Intune 授權** 使用者必須擁有 intune Teams裝置授權。  只要Teams已登錄具有有效 Intune 授權之使用者帳戶，裝置就會在 Microsoft Intune 中自動註冊為登錄程式。
- **設定 Intune** 您必須為 Android 裝置系統管理員註冊設定正確的 Intune 租使用者。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>設定 Intune 以註冊Teams Android 型裝置

TeamsAndroid 型裝置是由 Intune 透過 Android 裝置系統管理員 (DA) 管理。 在裝置可以註冊到 Intune 之前，有一些基本步驟可以執行。  如果您目前已經使用 Intune 管理裝置，您可能已經完成所有這些工作。  如果沒有，請執行以下工作：

> [!NOTE]
> - 如果租使用者系統管理員想要將一般地區電話註冊到 Intune，他們需要在帳戶新增 Intune 授權，並遵循 Intune 註冊的步驟。
> - 如果用來登錄帳戶的使用者帳戶Teams Intune 沒有授權，必須停用該帳戶的 Intune 合規性策略和註冊限制。



1. 將 Intune MDM (行動裝置管理) 授權。  

   如果您之前從未使用過 Intune，您必須設定 MDM 授權，才能註冊裝置。 詳細資訊，請參閱 [設定行動裝置管理機關](/intune/fundamentals/mdm-authority-set)。  這是建立新 Intune 租使用者時必須執行一次的步驟。
1. 啟用 Android 裝置系統管理員註冊。
  
   Android 型Teams裝置會以 Intune 的裝置系統管理員裝置管理。  根據預設，新建立租使用者會關閉裝置系統管理員註冊。 請參閱 [Android 裝置系統管理員註冊](/intune/enrollment/android-enroll-device-administrator)。
1. 指派授權給使用者。 
 
   註冊Teams Intune 的裝置使用者必須獲得有效的 Intune 授權。 詳細資訊，請參閱 [指派授權給使用者，讓使用者可以在 Intune 中註冊裝置](/intune/fundamentals/licenses-assign)。
1. 指派裝置系統管理員合規性政策。  

   1. 建立 Android 裝置系統管理員合規性政策。

   1. 將其指派給Azure Active Directory組，其中包含將登錄至Teams的使用者。 請參閱 [使用合規性原則來設定使用 Intune 管理之裝置的規則](/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>另請參閱

[Teams 的電話](phones-for-teams.md)

[IP 電話已Microsoft Teams](teams-ip-phones.md)

[Teams顯示](teams-displays.md)

[在 Teams 中管理裝置](device-management.md)

[Teams市場](https://office.com/teamsdevices)
