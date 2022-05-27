---
title: 使用 Intune 在 Android 上部署Teams手機、Teams顯示器、Teams面板和Microsoft Teams 會議室
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
description: 本文提供Microsoft Teams Android裝置支援的概觀和功能。
ms.openlocfilehash: 17f5e537b44d3aacd967ff5e8ffaa84df9da3f9b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674855"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>使用 Intune 在 Android 上部署Teams手機、Teams顯示器、Teams面板和Microsoft Teams 會議室

本文提供如何使用 Intune 在 Android 上部署Teams手機、Teams顯示器、Teams面板和Microsoft Teams 會議室的概觀。

## <a name="conditional-access"></a>條件式存取

條件式存取是 Azure AD) Azure Active Directory (功能，可協助您確保存取Office 365資源的裝置受到妥善管理且安全。  如果您將條件式存取原則套用至Teams服務，Android裝置 (包括Teams手機、Teams顯示器、Teams面板，以及必須註冊存取Teams Android) 上的Microsoft Teams 會議室Intune及其設定必須符合您的原則。  如果裝置未註冊Intune，或是已註冊但其設定不符合您的原則，條件式存取會防止使用者登入或使用裝置上的 Teams 應用程式。

一般說來，Intune內定義的合規性原則會指派給使用者群組。  這表示，如果您將Android合規性原則指派給 user@contoso.com，該原則將同樣套用至Android智慧型手機，以及任何 user@contoso.com 登入的Android型Teams裝置。

如果您在貴組織中使用需要強制執行Intune註冊的條件式存取，您必須設定幾個專案，才能成功註冊Intune：

- **Intune授權** 登入Teams裝置的使用者必須獲得Intune授權。  只要Teams裝置已登入具有有效Intune授權的使用者帳戶，該裝置就會在登入程式中自動註冊Microsoft Intune。
- **設定Intune** 您必須為Android裝置系統管理員註冊設定正確設定Intune租使用者。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>設定Intune以註冊Teams Android型裝置

Teams Android型裝置是由Intune透過Android裝置系統管理員 (DA) 管理來管理。 在可以註冊裝置Intune之前，有一些基本步驟可以執行。  如果您目前已經在使用Intune管理裝置，您可能已經完成所有這些工作。  如果沒有，請執行下列步驟：

> [!NOTE]
> - 如果租使用者系統管理員想要註冊通用的區域電話Intune，他們必須將Intune授權新增至帳戶，並遵循Intune註冊的步驟。
> - 如果用來登入Teams裝置的使用者帳戶未獲得Intune授權，則帳戶必須停用Intune合規性原則和註冊限制。



1. 將行動裝置管理 (Intune) 授權單位設定 MDM。  

   如果您從未使用過 Intune，您必須先設定 MDM 授權單位，才能註冊裝置。 如需詳細資訊，請參閱 [設定行動裝置管理機構單位](/intune/fundamentals/mdm-authority-set)。  這是建立新的Intune租使用者時必須完成的一次性步驟。
1. 啟用Android裝置系統管理員註冊。
  
   Android型Teams裝置會以裝置系統管理員裝置的Intune方式管理。  新建立的租使用者預設會關閉裝置系統管理員註冊。 請[參閱Android裝置系統管理員註冊](/intune/enrollment/android-enroll-device-administrator)。
1. 指派授權給使用者。 
 
   註冊Intune Teams裝置的使用者必須獲派有效的Intune授權。 如需詳細資訊，請參閱[指派授權給使用者，讓他們可以在Intune中註冊裝置](/intune/fundamentals/licenses-assign)。
1. 指派裝置系統管理員合規性原則。  

   1. 建立Android裝置系統管理員合規性原則。

   1. 將它指派給包含要登入Teams裝置之使用者的Azure Active Directory組。 請參閱[使用合規性原則為您使用Intune管理的裝置設定規則](/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>另請參閱

[Teams 的電話](phones-for-teams.md)

[通過 Microsoft Teams 認證的 IP Phone](teams-ip-phones.md)

[Teams顯示器](teams-displays.md)

[在 Teams 中管理裝置](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
