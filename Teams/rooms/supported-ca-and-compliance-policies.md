---
title: 支援Microsoft Teams 會議室的條件式存取和Intune裝置合規性原則
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
description: 瞭解Microsoft Teams 會議室支援與建議的條件式存取和Intune裝置合規性原則。
ms.openlocfilehash: befe8faae5db204f5e15e307cadcc24f6867a487
ms.sourcegitcommit: 5fe5516f6118ce3fa0449ab194a6fe87bf48c664
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2022
ms.locfileid: "64732291"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>支援Microsoft Teams 會議室的條件式存取和Intune裝置合規性原則

本文針對Microsoft Teams 會議室提供支援的條件式存取和Intune裝置合規性原則。 如需最佳做法和範例原則，請參閱[條件式存取和Intune Microsoft Teams 會議室合規性最佳做法](conditional-access-and-compliance-for-devices.md)。

> [!NOTE]
> Teams 會議室必須已經部署在您要指派條件式存取原則的裝置上。 如果您尚未部署Teams 會議室，請參閱[建立會議室和共用Teams裝置的資源帳戶](with-office-365.md)和在[Android 上部署Microsoft Teams 會議室](../devices/collab-bar-deploy.md)以取得詳細資訊。

## <a name="supported-conditional-access-policies"></a>支援的條件式存取原則  

下列清單包含Windows和 Android 上Teams 會議室支援的條件式存取原則。 支援的 Android 原則適用于所有位於共用空間的 Android 裝置，包括常見的區域電話和麵板。

| 指派 | Windows | Android |
|------------|---------|---------|
| 使用者或工作負載身分識別 |支援 | 支援 |
|雲端應用程式或動作 | 支援 <br><br> Teams 會議室只能在Teams模式下存取下列三個雲端應用程式：Office 365 Exchange Online、Office 365 SharePoint Online 和 Microsoft Teams | 支援 <br><br> Teams 會議室只能在Teams模式下存取下列三個雲端應用程式：Office 365 Exchange Online、Office 365 SharePoint Online 和 Microsoft Teams |
|**條件**| --- | --- |
| 使用者風險 | 支援 | 支援 |
| 登入風險 | 支援 | 支援 |
| 裝置平臺 | 支援 | 支援 |
| 位置 | 支援 | 支援 |
|用戶端應用程式 |不支援| 不支援 |
|裝置篩選 | 支援 | 支援 |
|**授予**| --- | --- |
| 封鎖存取 | 支援 | 支援 |
| 授與存取權 | 支援 | 支援 | 
| 需要多重要素驗證 | 不支援 | 不支援 |
| 要求將裝置標示為符合規範 | 支援 | 支援 |
|需要已加入裝置Azure AD混合式裝置 | 不支援 | 不支援 |
|需要核准的用戶端應用程式 | 不支援 | 不支援 |
| 需要應用程式保護原則 | 不支援 |不支援 |
| 需要變更密碼 | 不支援 | 不支援 |

> [!NOTE]
> 商務用 Skype Online 已停用，不受支援。 商務用 Skype根據條件式存取原則，不支援線上雲端應用程式。

> [!NOTE]
> Microsoft Teams 會議室上的Windows必須符合下列需求，才能支援裝置合規性授與控制：
>
> - Microsoft Teams 會議室應用程式 4.8.19.0 或更新版本
> - Windows 10版本 20H2 及更新版本 (10.0.19042) 

## <a name="supported-device-compliance-policies"></a>支援的裝置合規性原則 

在 Android 上Windows和Teams 會議室上的Microsoft Teams 會議室支援不同的裝置合規性原則。

#### <a name="teams-rooms-on-windows"></a>[在 Windows 上Teams 會議室](#tab/mtr-w)

以下是裝置合規性設定及建議資料表，以供搭配Teams 會議室使用。  

|政策 | 可用 性 | 注釋|
|---------|-------------|-------|
| [**裝置健康情況**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|需要 BitLocker| 支援 | 只有在您第一次啟用 Teams 會議室 上的 BitLocker 時才使用。 |
|需要在裝置上啟用安全開機 |支援 |安全開機是Teams 會議室的需求。 |
|要求程式碼完整性 |支援  | 程式碼完整性已是Teams 會議室的需求。 |
| [**裝置內容**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|作業系統版本 (最低、最大)  |不支援 | Teams 會議室自動更新至較新版本的 Windows，而在此設定值可能會造成作業系統更新後無法成功登入。|
|行動裝置適用的作業系統版本 (最低、最大)  | 不支援。 | 不適用 |
| 有效的作業系統組建 | 不支援 | 不適用 |
| [**Configuration Manager合規性]**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| 要求Configuration Manager裝置合規性 | 支援 |  不適用 |
| [**系統安全性**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| 所有密碼原則 | 不支援 | 密碼原則可以防止本機Skype帳戶自動登入。 |
| 需要加密裝置上的資料儲存空間。 | 支援  | 只有在您第一次啟用 Teams 會議室 上的資料儲存加密時才使用。 |
| 防火牆 | 支援 | 防火牆已是Teams 會議室的需求 |
| 信賴平臺模組 (TPM)  | 支援 | 信賴平臺模組 (TPM) 已經是Teams 會議室的需求。 |
| 防毒 | 支援 | 防毒 (Windows Defender) 已是Teams 會議室的需求。 |
| 反間諜功能 | 支援 | 反間諜功能 (Windows Defender) 已經是Teams 會議室的需求。 |
| Microsoft Defender 反惡意程式碼 | 支援 | Microsoft Defender 反惡意程式碼已是Teams 會議室的需求。 |
| Microsoft Defender 反惡意程式碼最小版本 | 不支援。 | Teams 會議室自動更新此元件，因此不需要設定合規性原則。|
| Microsoft Defender 反惡意程式碼安全情報
最新 | 支援 | 驗證 Microsoft Defender 反惡意程式碼已是Teams 會議室的需求。 |
| 即時保護 | 支援 | 即時保護已是Teams 會議室的需求。 |
| [**適用於端點的 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| 要求裝置處於或低於電腦風險分數。 | 支援 |  不適用 |

#### <a name="teams-rooms-on-android"></a>[在 Android 上Teams 會議室](#tab/mtr-a)

以下是裝置合規性設定及建議資料表，以供搭配Teams 會議室使用。  

| 政策 | 可用 性 | 注釋 |
|---------|-------------|-------|
| [**適用於端點的 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| 要求裝置處於或低於電腦風險分數 | 不支援 |  不適用 |
| [**裝置健康情況**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| 由裝置系統管理員管理的裝置 | 必要 | Teams Android 裝置管理需要啟用裝置系統管理員。 |
| 根據裝置 | 支援 |  不適用 |
| 要求裝置處於或低於裝置威脅等級 | 不支援 |  不適用 |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play 服務已設定 | 不支援 | Google play 未安裝在 Teams Android 裝置上。 |
| 最新的安全性提供者 | 不支援 | Google play 未安裝在 Teams Android 裝置上。 |
| 應用程式上的威脅掃描 | 不支援 | Google play 未安裝在 Teams Android 裝置上。 |
| SafetyNet 裝置證明 | 不支援 | Google play 未安裝在 Teams Android 裝置上。|
| [**裝置內容**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| 作業系統版本 (最低、最大)  | 支援 |  不適用 |
[**系統安全性**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| 需要加密裝置上的資料儲存空間。 |支援 |  不適用 |
[**裝置安全性**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| 封鎖來自不明來源的應用程式 | 不支援 | 僅Teams系統管理員安裝應用程式或 OEM 工具 |
| 公司入口網站應用程式執行時間完整性 | 支援 |  不適用|
| 受限制的應用程式 | 不支援 |  不適用 |
| 在裝置上封鎖 USB 偵錯 | 支援 |  不適用|
[**所有 Android 裝置*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|需要密碼之前最多閒置幾分鐘 | 不支援 |  不適用 |
| 需要密碼才能解除鎖定行動裝置 | 不支援 | 不適用 |
| [**Android 10 及更新版本**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 及更舊版本或 Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|必要密碼類型 |不支援 | 不適用|

---