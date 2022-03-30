---
title: 支援的條件式 Access 和 Intune 裝置合規性Microsoft Teams 會議室
ms.author: czawideh
author: cazawideh
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 瞭解支援的建議條件式 Access 和 Intune 裝置合規性Microsoft Teams 會議室。
ms.openlocfilehash: ea27f71a7d4f64bc1d9e8c8a3cd3d7b2a52151f3
ms.sourcegitcommit: ecc67b7b9378cc72f85517f30c32680045056fda
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2022
ms.locfileid: "64504193"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>支援的條件式 Access 和 Intune 裝置合規性Microsoft Teams 會議室

本文提供支援的條件式 Access 和 Intune 裝置合規性Microsoft Teams 會議室。 有關最佳做法和範例政策，請參閱條件[式 Access 和 Intune](conditional-access-and-compliance-for-devices.md)合規性最佳做法Microsoft Teams 會議室。

> [!NOTE]
> Teams 會議室必須已經部署在您想要指派條件式 Access 策略的裝置上。 如果您尚未部署Teams 會議室，請參閱為會議室建立資源帳戶，Teams[](with-office-365.md)裝置共用，以及在[Android](../devices/collab-bar-deploy.md) Microsoft Teams 會議室部署資源帳戶。

## <a name="supported-conditional-access-policies"></a>支援的條件式 Access 政策  

下列清單包含適用于 Android 和 Teams 會議室 Windows的受支援條件式 Access 政策。 支援的 Android 原則適用于所有 Android 裝置、手機和麵板。

| 指派 | Windows | Android |
|------------|---------|---------|
| 使用者或工作負載身分 |支援 | 支援 |
|雲端 App 或動作 | 支援 <br><br> Teams 會議室模式時，必須存取下列三個雲端應用程式：Teams、Office 365 Exchange Online、Office 365 SharePoint Online 和 Microsoft Teams | 支援 <br><br> Teams 會議室模式時，必須存取下列三個雲端應用程式：Teams、Office 365 Exchange Online、Office 365 SharePoint Online 和 Microsoft Teams |
|**條件**| --- | --- |
| 使用者風險 | 支援 | 支援 |
| 登錄風險 | 支援 | 支援 |
| 裝置平臺 | 支援 | 支援 |
| 位置 | 支援 | 支援 |
|用戶端應用程式 |不支援| 不支援 |
|篩選裝置 | 支援 | 支援 |
|**授予**| --- | --- |
| 封鎖存取 | 支援 | 支援 |
| 授予存取權 | 支援 | 支援 | 
| 需要多重要素驗證 | 不支援 | 不支援 |
| 要求裝置標示為相容 | 支援 | 支援 |
|需要混合式Azure AD連接裝置 | 不支援 | 不支援 |
|需要核准的用戶端應用程式 | 不支援 | 不支援 |
| 需要應用程式保護政策 | 不支援 |不支援 |
| 需要變更密碼 | 不支援 | 不支援 |

> [!NOTE]
> 商務用 Skype線上已停用且不受支援。 商務用 Skype條件式 Access 政策不支援線上雲端應用程式。

> [!NOTE]
> Microsoft Teams 會議室上的Windows必須符合下列需求，以支援裝置合規性授予控制項：
>
> - Microsoft Teams 會議室 4.8.19.0 或以上應用程式
> - Windows 10 10.0.19042 (版本 20H2) 

## <a name="supported-device-compliance-policies"></a>支援的裝置合規性政策 

Microsoft Teams 會議室 Android Windows Teams 會議室支援不同的裝置合規性政策。

#### <a name="teams-rooms-on-windows"></a>[Teams 會議室上Windows](#tab/mtr-w)

以下是裝置合規性設定清單，以及適用于Teams 會議室。  

|政策 | 可用 性 | 注釋|
|---------|-------------|-------|
| [**裝置健康狀態**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|需要 BitLocker| 支援 | 僅適用于您第一次啟用 BitLocker Teams 會議室。 |
|要求在裝置上啟用安全啟動 |支援 |安全啟動是系統Teams 會議室。 |
|需要程式碼完整性 |支援  | 程式碼完整性已經是Teams 會議室。 |
| [**裝置屬性**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|作業系統版本 (最小值、最大值)  |不支援 | Teams 會議室更新至較新版本的登錄Windows此處設定值可能會防止作業系統更新後成功登錄。|
|適用于行動裝置的作業系統版本 (上限)  | 不支援。 | 不適用 |
| 有效的作業系統建立 | 不支援 | 不適用 |
| [**Configuration Manager 合規性**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| 需要 Configuration Manager 的裝置合規性 | 支援 |  不適用 |
| [**系統安全性**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| 所有密碼政策 | 不支援 | 密碼政策可防止Skype帳戶自動登入。 |
| 需要加密裝置上的資料儲存空間。 | 支援  | 只有在您第一次啟用資料儲存空間加密時，才能Teams 會議室。 |
| 防火牆 | 支援 | 防火牆已經是防火牆Teams 會議室 |
| 信任的平臺模組 (TPM)  | 支援 | 信任的平臺模組 (TPM) 已是該平臺Teams 會議室。 |
| 防毒 | 支援 | 防毒軟體 (Windows Defender) 已是系統Teams 會議室。 |
| 反間諜軟體 | 支援 | 反間諜軟體 (Windows Defender) 已是系統Teams 會議室。 |
| Microsoft Defender 反惡意軟體 | 支援 | Microsoft Defender Antimalware 已經Teams 會議室。 |
| Microsoft Defender 反惡意軟體最低版本 | 不支援。 | Teams 會議室自動更新此元件，因此不需要設定合規性政策。|
| Microsoft Defender 反惡意軟體安全性智慧
最新 | 支援 | 驗證 Microsoft Defender Antimalware 已經是 Microsoft Defender 反惡意軟體Teams 會議室。 |
| 即時保護 | 支援 | 即時保護已是Teams 會議室。 |
| [**Microsoft Defender for 端點**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| 要求裝置位於或位於機器風險分數之下。 | 支援 |  不適用 |

#### <a name="teams-rooms-on-android"></a>[Teams 會議室 Android 上的應用程式](#tab/mtr-a)

以下是裝置合規性設定清單，以及適用于Teams 會議室。  

| 政策 | 可用 性 | 注釋 |
|---------|-------------|-------|
| [**Microsoft Defender for 端點**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| 要求裝置位於或位於機器風險分數之下 | 不支援 |  不適用 |
| [**裝置健康狀態**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| 由裝置系統管理員管理的裝置 | 不支援。 | Teams Android 裝置是使用裝置管理
管理員。 |
| 根根裝置 | 支援 |  不適用 |
| 要求裝置處於或位於裝置威脅等級之下 | 不支援 |  不適用 |
| [**Google Play 保護**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services 已配置 | 不支援 | Android 裝置上未Teams Google play。 |
| 最新安全性提供者 | 不支援 | Android 裝置上未Teams Google play。 |
| 應用程式上的威脅掃描 | 不支援 | Android 裝置上未Teams Google play。 |
| SafetyNet 裝置認證 | 不支援 | Android 裝置上未Teams Google play。|
| [**裝置屬性**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| 作業系統版本 (最小值、最大值)  | 支援 |  不適用 |
[**系統安全性**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| 需要加密裝置上的資料儲存空間。 |支援 |  不適用 |
[**裝置安全性**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| 封鎖來自未知來源的應用程式 | 不支援 | 只有Teams安裝 App 或 OEM 工具 |
| 公司入口網站應用程式執行時間完整性 | 支援 |  不適用|
| 受限制的應用程式 | 不支援 |  不適用 |
| 封鎖裝置上的 USB 調試 | 支援 |  不適用|
[**所有 Android 裝置*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|需要密碼前，不活動分鐘數上限 | 不支援 |  不適用 |
| 需要密碼才能解除鎖定行動裝置 | 不支援 | 不適用 |
| [**Android 10 及更高版本**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 及更早版本或 Samsung Knx**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|必要的密碼類型 |不支援 | 不適用|

---
