---
title: 在商務用 Skype 用戶端中設定智慧連絡人清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要：瞭解如何在商務用 Skype 用戶端中開啟 [智慧連絡人清單] 功能。
ms.openlocfilehash: 9db4e6616aa4c11be3ad2f9ee1cd92a0587b4e51
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768866"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>在商務用 Skype 用戶端中設定智慧連絡人清單

**摘要：** 瞭解如何在商務用 Skype 用戶端中開啟 [智慧連絡人清單] 功能。

[智慧連絡人清單] 功能可讓您的使用者自動填入連絡人清單。 在您第一次使用商務用 Skype 時，您的使用者會自動看到其小組中的主管及其他人。 預設會針對 Office 365 使用者開啟這項功能，但您必須透過設定用戶端原則設定，為您的內部部署使用者明確啟用此功能。

設定此功能時，請記住下列事項：

- 使用者（最多13個）會自動新增到 [智慧連絡人] 清單中，順序如下：

  1. R

  2. 依字母順序定向

  3. 對等依字母順序排列

- 使用者第一次登入時，就會建立一個名為「我的群組」的新群組。 群組會根據 [管理員] 欄位中填入的使用者別名，自動填入使用者的 AD 群組關係中的人員。 請注意，在最初填入群組之後，變更 AD 群組成員資格不會導致更新到我的群組。 如果使用者刪除連絡人或群組，則不會重新建立連絡人與群組。 

- 如果已開啟 [自動標記]，清單中的連絡人將會標記為 [目前狀態變更]。 自動標記功能預設為開啟狀態，但您可以選擇將它關閉。 

- 群組中的所有新使用者都會收到已新增至 [連絡人] 清單的資訊。 使用者可以手動將新成員新增到他們的群組，或其他他們選擇的群組。

- 此功能僅適用于第一次登入的使用者。 如果使用者先前已從任何裝置登入，包括（例如，任何行動裝置或 Mac），則該使用者沒有啟用該功能。

## <a name="configure-smart-contacts-list"></a>設定智慧連絡人清單

若要為使用者啟用 [智慧連絡人清單] 功能，您必須執行下列步驟： 

- 建立新的 CsClientPolicy 專案，然後將它新增到全域用戶端原則。 

- 請確定 [通訊錄搜尋] 只設定為 [網頁搜尋]。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>建立原則專案以啟用智慧連絡人清單

若要建立原則專案以啟用智慧連絡人清單功能，請使用[CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) Cmdlet 與 EnableClientAutoPopulateWithTeam 選項，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

接著，使用[CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) Cmdlet，將變更寫入全域原則，如下所示：

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

您也可以選擇建立原則來關閉自動標記，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

您也必須將對應原則的 AddressBookAvailability 參數設定為 WebSearchOnly。 如需詳細資訊，請參閱[設定 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 

### <a name="troubleshoot"></a>疑難排解

如果智慧連絡人清單無法正常運作，請檢查下列專案：

- 驗證設定。 

- 確認已填入廣告組織資訊。

- 收集新使用者的商務用 Skype 用戶端記錄，以進行進一步分析。

- 確認商務用 Skype 用戶端 UI 不會顯示無法連接至通訊錄的訊息。 若要確認通訊錄連通性，請在商務用 Skype 用戶端搜尋列中執行搜尋。

- 當使用者第一次登入商務用 Skype 時，AD DS 複製問題可能會導致連絡人無法解析。


