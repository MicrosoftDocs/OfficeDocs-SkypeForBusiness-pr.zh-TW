---
title: 設定商務用 Skype 用戶端中的智慧連絡人清單
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要：瞭解如何在商務用 Skype 用戶端中開啟智慧連絡人清單功能。
ms.openlocfilehash: f70ffcd6893c361262c0f0f8e712d7dd0db247e7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775853"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>設定商務用 Skype 用戶端中的智慧連絡人清單

**摘要：** 瞭解如何在商務用 Skype 用戶端中開啟智慧連絡人清單功能。

[智慧連絡人清單] 功能可讓您的使用者自動填入連絡人清單。 在您第一次使用商務用 Skype 時，您的使用者將會自動查看其主管和其小組中的其他人員。 預設會為 Microsoft 365 和 Office 365 使用者開啟此功能，但您必須透過設定用戶端原則設定，明確為內部部署使用者啟用此功能。

設定此功能時，請牢記下列事項：

- 使用者最多13個會依下列順序自動新增至 [智慧連絡人] 清單：

  1. 管理員

  2. 依字母順序指示

  3. 對等字母順序

- 當使用者第一次登入時，就會建立新的群組，名稱為 My Group。 根據在 [管理員] 欄位中填入的使用者別名，群組會自動填入使用者的 AD 群組關聯中的人員。 請注意，對 AD 群組成員資格的變更不會對最初填入的群組進行更新。 若使用者刪除連絡人或群組，就不會重新建立連絡人或群組。 

- 如果開啟自動標記，清單中的連絡人將會標示為「顯示狀態變更」。 自動標記預設為開啟狀態，但您可以選擇將它關閉。 

- 群組中的所有新使用者都會收到已新增至 [連絡人] 清單中的通知。 使用者可以手動將新成員新增至其「我的群組」或其選擇的其他群組。

- 此功能僅適用于第一次登入的使用者。 如果使用者先前已從任何裝置登入，例如，任何行動裝置或 Mac--沒有為該使用者啟用該功能。

## <a name="configure-smart-contacts-list"></a>設定智慧連絡人清單

若要為您的使用者啟用 [智慧連絡人清單] 功能，您必須執行下列步驟： 

- 建立新的 CsClientPolicy 專案，並將其新增至全域用戶端原則。 

- 請確定 [通訊錄] 搜尋只針對 Web 搜尋設定。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>建立原則專案以啟用智慧連絡人清單

若要建立原則專案以啟用智慧連絡人清單功能，請將 [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) Cmdlet 與 EnableClientAutoPopulateWithTeam 選項搭配使用，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

接下來，使用 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) Cmdlet，將變更寫入全域原則，如下所示：

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

您可以選擇性地建立原則來關閉自動標記，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

您也必須將對應原則的 AddressBookAvailability 參數設定為 WebSearchOnly。 如需詳細資訊，請參閱 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 

### <a name="troubleshoot"></a>疑難排解

如果智慧連絡人清單未如預期運作，請檢查下列各項：

- 驗證設定。 

- 確認已填入 AD 組織資訊。

- 收集新使用者的商務用 Skype 用戶端記錄，以便進一步分析。

- 確認商務用 Skype 用戶端 UI 不會顯示無法連接到通訊錄的訊息。 若要確認通訊錄連通性，請在商務用 Skype 用戶端搜尋列中執行使用者搜尋。

- 當使用者第一次登入商務用 Skype 時，AD DS 複寫問題可能會造成連絡人無法解析。