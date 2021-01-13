---
title: 部署團隊使用 Intune 顯示手機和團隊
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
description: 本文提供 Microsoft 團隊顯示所支援的功能和功能的概覽。
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825413"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>部署團隊使用 Intune 顯示手機和團隊

本文將簡要說明如何使用 Intune 部署團隊手機和團隊。

## <a name="conditional-access"></a>條件式存取

條件式存取是 Azure Active Directory (的 Azure AD) 功能，可協助您確保能正確管理存取 Office 365 資源的裝置，且安全。  如果您將條件式存取原則套用至團隊服務，Android 裝置 (包括 [團隊電話] 和 [團隊]，會顯示需要將其登錄至 Intune 且其設定必須符合您原則的) 。  如果裝置未登錄至 Intune，或已註冊，但其設定不符合您的原則，條件式存取將會防止使用者登入或使用裝置上的 [小組] 應用程式。

通常，在 Intune 中定義的規範原則會指派給使用者群組。  這表示如果您指派 Android 規範原則至 user@contoso.com，該原則會同等地套用到他們的 Android 智慧型手機，以及 user@contoso.com 登入的任何 Android 版的小組裝置。

如果您使用條件式存取（需要強制進行 Intune 註冊），在您的組織中，您需要設定幾個專案，才能允許成功進行 Intune 登記：

- **Intune 授權** 登入小組裝置的使用者必須具備 Intune 的授權。  只要團隊裝置登入擁有有效 Intune 授權的使用者帳戶，裝置就會自動在登入程式中登入 Microsoft Intune。
- **設定 Intune** 您必須為 Android 裝置系統管理員註冊設定正確設定的 Intune 租使用者。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>將 Intune 設定為以 Android 版為基礎的裝置註冊團隊

在 Intune 中，以 Android 裝置管理員身分管理的團隊是由 android 裝置管理員 (DA) 管理。 在能將裝置登記到 Intune 之前，請先執行幾個基本步驟。  如果您目前已使用 Intune 管理裝置，您可能已經完成所有這些專案。  如果沒有，以下是要執行的動作：

1. 將 Intune MDM (行動裝置管理) 頒發機構設定。  如果您之前從未使用過 Intune，您必須先設定 MDM 頒發機構，才能註冊裝置。 如需詳細資訊，請參閱 [設定行動裝置管理機構](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)。  此為一次性步驟，必須在建立新的 Intune 租使用者完成。
2. 啟用 Android 裝置管理員註冊。 Android 版的團隊裝置是使用 Intune 作為裝置系統管理員裝置進行管理。  新建立的租使用者預設會關閉 [裝置管理員註冊]。  如需詳細資訊，請參閱 [Android 裝置系統管理員註冊](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。
3. 指派授權給使用者。 必須為團隊裝置使用者註冊到 Intune 的使用者指派有效的 Intune 授權。 如需詳細資訊，請參閱 [指派授權給使用者，讓他們可以在 Intune 中註冊裝置](https://docs.microsoft.com/intune/fundamentals/licenses-assign)。
4. 指派裝置管理員合規性原則。  建立 Android 裝置管理員合規性原則，並將它指派給 Azure Active Directory 群組，該群組包含要登入小組裝置的使用者。 如需詳細資訊，請參閱 [使用合規性策略來設定您使用 Intune 管理的裝置規則](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>另請參閱

[Teams 的電話](phones-for-teams.md)

[Microsoft 團隊的 IP 手機認證](teams-ip-phones.md)

[團隊顯示](teams-displays.md)

[在 Teams 中管理裝置](device-management.md)

[團隊 Marketplace](https://office.com/teamsdevices)
