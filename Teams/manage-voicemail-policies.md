---
title: 管理語音信箱原則
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 管理使用者的語音信箱原則。
ms.openlocfilehash: 7af4fa89dd495679a3ec755dd2e902012ad1ef77
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240512"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>管理使用者雲端語音信箱原則

> [!WARNING]
> 對於商務用 Skype客戶來說，透過 Microsoft Teams 通話原則停用語音信箱可能也會停用商務用 Skype使用者的語音信箱服務。

語音信箱原則可讓您設定並指派現有或新的語音信箱原則給使用者群組，以取得通話接聽規則、語音信箱轉錄、轉譯不雅偽裝、轉譯轉譯和系統提示語言等功能。

在指定原則之前，您應該先閱讀[設定雲端語音信箱](set-up-phone-system-voicemail.md)。 如需管理個別使用者設定的相關資訊，請參閱 [管理語音信箱設定](manage-voicemail-settings.md)。

若要管理語音信箱原則，您可以使用 Teams 系統管理中心或New-CsOnlineVoicemailPolicy PowerShell Cmdlet。 

使用者的預設原則為：

- 已啟用語音信箱轉譯。
- 已啟用語音信箱轉譯。
- 語音信箱轉譯不雅遮罩已停用。
- 錄製持續時間上限設為五分鐘。
- 編輯通話接聽規則已啟用。
- 主要和次要系統提示語言設定為 Null，並使用使用者的語音信箱語言設定。

您可以使用全域 (組織的預設) 自動建立的原則，或建立及指派自訂原則。

> [!IMPORTANT]
> Microsoft 365 中的語音信箱服務會快取語音信箱原則，並每隔 6 小時更新一次快取。 因此，您所做的原則變更最多可能需要 6 小時才能套用。

## <a name="use-teams-admin-center"></a>使用 Teams 系統管理中心

### <a name="create-a-custom-voicemail-policy"></a>建立自訂語音信箱原則

請依照下列步驟建立自訂語音信箱原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **語音**  >  **信箱原則**。

2. 選取 [新增 **]**。

3. 開啟或關閉您要在語音信箱原則中使用的功能。

4. 選取 [儲存 **]**。

### <a name="edit-a-voicemail-policy"></a>編輯語音信箱原則

請依照下列步驟編輯現有的語音信箱原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，選取 **[語音**  >  **信箱原則]**。

2. 按一下您要修改的原則旁邊，然後選取 [ **編輯]**。

3. 進行您要的變更，然後按一下 [ **儲存]**。

> [!IMPORTANT]
> 您無法編輯或移除預先設定的原則實例，稱為 TranscriptionDisabled 和 TranscriptionProfanityMaskingEnabled。


### <a name="assign-a-custom-voicemail-policy-to-users"></a>指派自訂語音信箱原則給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>使用 PowerShell

您也可以使用 PowerShell 來設定及指派現有或新的語音信箱原則。 若要使用 PowerShell 管理原則，請使用下列 Cmdlet：

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>語音信箱原則設定
  
- **啟用轉譯**： 此設定會控制雲端語音信箱服務是否會產生已錄製語音信箱的文字轉寄，並將它包含在語音信箱訊息中。 轉譯會根據錄製的語音信箱中偵測到的語言來完成。

- **轉譯**： 此設定會控制雲端語音信箱服務是否會翻譯錄製之語音信箱的轉譯。 系統會嘗試將翻譯轉譯成語音信箱接收器的慣用語言。

- **轉譯不雅遮罩**- 此設定會控制雲端語音信箱服務是否會遮罩語音信箱轉譯中的不雅用語。

- **錄製持續時間上限** - 錄製長度上限會控制語音信箱錄製的時間上限。 預設值為 5 分鐘。

- **通話接聽規則** - 此設定會控制是否允許使用者在 Microsoft Teams 中設定語音信箱通話接聽規則。

- **雙語言系統提示** - 根據預設，語音信箱系統提示會以使用者在設定語音信箱時所選取的語言呈現給來電者。 如果商務需要以兩種語言顯示語音信箱系統提示，則可以設定主要和次要語言，而且可能不一樣。

### <a name="share-data-for-service-improvements"></a>共用資料以改善服務

指定是否要與服務共用語音信箱和轉譯資料，以進行訓練並提高準確度。 如果設為 False，無論使用者選擇何種，語音信箱資料都不會共用。


## <a name="related-articles"></a>相關文章


