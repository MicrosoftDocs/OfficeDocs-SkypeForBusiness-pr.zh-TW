---
title: 適用於 Microsoft Teams 的端對端加密
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 10/23/2021
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ashgupt
description: 了解 Microsoft Teams 中的增強加密功能，使用 Teams 系統管理中心和 Microsoft PowerShell 管理端對端加密。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: bdc626510a180185cae699106c1420880ea55e73
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579695"
---
# <a name="use-end-to-end-encryption-for-one-to-one-microsoft-teams-calls-public-preview"></a>針對一對一 Microsoft Teams 通話使用端對端加密 (公開預覽)

> [!IMPORTANT]
> 為了改善客戶體驗，Teams 服務模型和其加密支援會有所變更。 例如，服務會定期捨棄不再視為安全的加密套件。 任何此類變更的目標都是讓 Teams 保持安全且從設計上值得信賴。 此外，Microsoft 資料中心的所有客戶內容都經過加密。 如需 Microsoft 365 中加密層級的資訊，請參閱 [Microsoft 365 中的加密](/microsoft-365/compliance/encryption)。

端對端加密 (或 E2EE) 是在內容在傳送之前加密，並僅由預定收件者進行解密時才會發生。 使用端對端加密，僅有兩個端點系統參與加密和解密通話資料。 任何其他對象 (包括 Microsoft) 都可存取解密後的交談。

有了這個公開預覽版，我們正要推出適用於未排程一對一通話的 E2EE。 僅有即時媒體流程，也就是影片和語音資料，適用於一對一 Teams 通話會進行端對端加密。 雙方必須開啟此設定，才能啟用端對端加密。 [Microsoft 365 中的加密](/microsoft-365/compliance/encryption) 會保護通話中的聊天、檔案共用、目前狀態及其他內容。

如果您不啟用端對端加密，Teams 仍然會依照產業標準使用加密保護通話或會議的安全。 通話期間交換的資料在傳輸和休息時一定很安全。 如需詳細資訊，請參閱 [適用於 Teams 的媒體加密](teams-security-guide.md#media-encryption)。

在端對端加密通話期間，Teams 會保護下列功能：

- 音訊

- 影片

- 共用螢幕

E2EE 通話期間無法提供下列進一步功能：

- 即時輔助字幕和轉錄

- 來電轉接

- 通話合併

- 通話駐留

- 商討後轉接

- 呼叫小幫手並轉接至其他裝置

- 新增參與者

- 錄製

此外，如果貴組織使用合規性錄製，則無法使用端對端加密。 如需 Teams 如何支援合規性錄製的詳細資訊，請參閱 [通話和會議記錄的 Teams 原則型錄製](teams-recording-policy.md)。

## <a name="configure-end-to-end-encryption-for-microsoft-teams"></a>設定 Microsoft Teams 的端對端加密

完成這些工作，讓使用者可以進行端對端加密通話。

- 建立一或多個定義可以使用端對端加密之人員的原則，為貴組織啟用端對端加密。 在您開始之前，請確定您的公司或學校帳戶已獲指派 Teams 全域系統管理員角色。 如需詳細資訊，請參閱 [使用 Microsoft Teams 系統管理員角色來管理 Teams](using-admin-roles.md)。 當您準備好設定 E2EE 時，可以使用 Teams 系統管理中心或 Microsoft PowerShell。

- 在裝置上的 Teams 設定中切換端對端加密通話。 每個使用者都需要完成此工作，但他們只需要在一部裝置上執行此工作。 Teams 會針對每個使用者在支援的結束點同步此設定。 如需說明，請參閱 [為 Teams 通話使用端對端加密](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)。

### <a name="use-the-teams-admin-center-to-configure-end-to-end-encryption"></a>使用 Teams 系統管理中心設定端對端加密

全域、全組織的預設原則會指定停用端對端加密。 除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。 若要啟用端對端加密，請建立新的加密原則或修改全域預設原則。 若要使用 Teams 系統管理中心啟用端對端加密，請完成這些步驟。

1. 使用已指派 Teams 或全域系統管理員角色的工作或學校帳戶， [Teams 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 請移至 **其他設定** > **增強型加密原則**。

3. 選擇預設原則或選擇 **新增** 以新增新原則，然後命名此新原則。

4. 若要為您的使用者啟用端對端加密，進行 **端對端通話加密**，請選擇 **使用者可以開啟加密**，然後選擇 **儲存**。

   若要停用端對端加密，請選擇 **為所有人關閉加密**。

當您完成設定此原則，請以您管理其他 Teams 原則的方式，將該原則指派給使用者、群組或全體租用戶。 如需在 Teams 中使用原則的資訊，請參閱 [使用原則管理 Teams](manage-teams-with-policies.md)。

### <a name="use-microsoft-powershell-to-configure-end-to-end-encryption"></a>使用 Microsoft PowerShell 來設定端對端加密

您可以使用 Microsoft PowerShell 和 Teams 系統管理中心管理端對端加密原則。 數個端對端加密包含在 Cmdlet Teams PowerShell 模組之中，且紀錄於 [Microsoft Teams cmdlet 參考資料](/powershell/teams/?view=teams-ps&preserve-view=true) 之中。 本文列出您可以使用的 Cmdlet，並提供簡單的範例設定。 這些設定會使用預設的全域原則。 貴組織可能需要更複雜的原則設定。 有關這些 Cmdlet 的完整資訊，可在 Cmdlet 參考資料中找到。

端對端加密 PowerShell Cmdlet：

- [Get-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy) 會傳回貴組織中有關 Teams 的增強加密原則資訊。

- [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) 會指派和取消指派給使用者的現有增強加密原則。 使用 `$NULL` 來取消指派使用者的所有原則。

- [New-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy) 會建立一個新的 Teams 增強加密原則。

- [Remove-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy) 會刪除貴組織的增強加密原則。 您無法刪除全域的預設原則。

- [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) 會更新現有的 Teams 增強加密原則中的值。

您的公司或學校帳戶需要 Teams 或全域系統管理員角色，才能設定端對端加密。

#### <a name="to-enable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>若要使用全域原則為全體租用戶者啟用端對端加密

根據預設，系統會停用端對端加密。 若透過設定預設全域原則，為全體租用戶啟用端對端加密，請執行 [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) Cmdlet，如下所示。

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

其中：

- `Global` 表示您將此組態設定為全域、全組織的預設原則。

- `DisabledUserOverride` 表示 E2EE 預設為在 Teams 中停用，但使用者可以在 Teams 設定中覆寫預設值並開啟 E2EE。

#### <a name="to-disable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>若要使用全域原則為全體租用戶者停用端對端加密

根據預設，系統會停用端對端加密。 如果您已經變更全域原則，您可以透過執行 [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) Cmdlet 將設定回復變更，如下所示。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType Disabled
```

其中：

- `Global` 表示您將此組態設定為全域、全組織的預設原則。

- `Disabled` 表示您針對所有人停用 E2EE，且使用者無法在 Teams 設定中將其開啟。

#### <a name="to-enable-end-to-end-encryption-for-a-single-user"></a>若要為單一使用者啟用端對端加密

若要為使用者啟用端對端加密，請執行 [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) Cmdlet，如下所示。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "username" -PolicyName "policyname"
```

其中：

- *`username`* 是使用者的名稱。

- *`policyname`* 是您想要用於此原則的名稱。 原則名稱不能包含空格，例如 ContosoE2EEUserPolicy。

使用者仍然需要在 Teams 設定中切換端對端加密通話，才能進行端對端加密通話。 如需說明，請參閱 [為 Teams 通話使用端對端加密](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)。

例如：

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName "ContosoE2EEUserPolicy"
```

#### <a name="to-unassign-an-end-to-end-encryption-policy-from-a-single-user"></a>若要從單一使用者取消指派端對端加密原則

使用者可以在同一時間擁有一個，也僅有一個指派給他們的加密原則。 當您取消指派使用者中的原則時，此使用者之後會獲指派一個全域、全組織的預設原則。 您無法取消指派預設原則。 若要取消指派使用者中的端對端加密原則，請執行 [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) Cmdlet，如下所示。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName $NULL
```

## <a name="switch-on-end-to-end-encryption-on-your-device"></a>在裝置上切換端對端加密

如需說明，請參閱 [為 Teams 通話使用端對端加密](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)。

## <a name="related-topics"></a>相關主題

[安全性團隊支援在家工作最常見的 12 項工作](/microsoft-365/security/top-security-tasks-for-remote-work)

[在 Microsoft Teams 中管理會議設定](./meeting-settings-in-teams.md)
