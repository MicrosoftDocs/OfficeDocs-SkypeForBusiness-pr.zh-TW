---
title: 管理語音信箱原則
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
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
ms.openlocfilehash: 3f4c64194fc9e2b24c59dc7bc06ed972e801a6a8
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370826"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>在貴組織中設定語音信箱原則

> [!WARNING]
> 對於商務用 Skype客戶來說，透過Microsoft Teams通話原則停用語音信箱可能也會停用商務用 Skype使用者的語音信箱服務。

您可以使用語音信箱原則來控制與雲端語音信箱相關的不同功能。

## <a name="voicemail-organization-defaults-for-all-users"></a>所有使用者的語音信箱組織預設值
- 已啟用語音信箱轉譯。
- 已啟用語音信箱轉譯。
- 語音信箱轉譯不雅遮罩已停用。
- 錄製持續時間上限設為五分鐘。
- 編輯通話接聽規則已啟用。
- 主要和次要系統提示語言設定為 Null，並使用使用者的語音信箱語言設定。

您可以使用全域 (組織的預設) 自動建立的原則，或建立及指派自訂原則。

## <a name="create-a-custom-voicemail-policy"></a>建立自訂語音信箱原則

請依照下列步驟建立自訂語音信箱原則。

1. 在 Microsoft Teams系統管理中心的左側導覽畫面中，移至 **VoiceVoicemail** ****  >  原則。
2. 選取 [新增 **]**。
3. 開啟或關閉您要在語音信箱原則中使用的功能。
4. 選取 [儲存 **]**。

## <a name="edit-a-voicemail-policy"></a>編輯語音信箱原則

請依照下列步驟編輯現有的語音信箱原則。

1. 在 Microsoft Teams系統管理中心的左側導覽畫面中，選取 **[****VoiceVoicemail**  >  原則]。
2. 按一下您要修改的原則旁邊，然後選取 [ **編輯]**。
3. 進行您要的變更，然後按一下 [ **儲存]**。

> [!IMPORTANT]
> 您無法編輯或移除預先設定的原則實例，稱為 TranscriptionDisabled 和 TranscriptionProfanityMaskingEnabled。


## <a name="assign-a-custom-voicemail-policy-to-users"></a>指派自訂語音信箱原則給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="voicemail-policy-settings"></a>語音信箱原則設定
  
### <a name="enable-transcription"></a>啟用轉譯

此設定會控制雲端語音信箱服務是否會產生錄製之語音信箱的文字轉寄，並將它包含在語音信箱訊息中。 轉譯會根據錄製的語音信箱中偵測到的語言來完成。

### <a name="transcription-translation"></a>轉譯轉譯

此設定會控制雲端語音信箱服務是否會翻譯錄製之語音信箱的轉譯。 系統會嘗試將翻譯轉譯成語音信箱接收器的慣用語言。

### <a name="transcription-profanity-masking"></a>轉譯不雅的遮罩

此設定會控制雲端語音信箱服務是否會遮罩語音信箱轉譯中的不雅用語。

### <a name="maximum-recording-duration"></a>錄製持續時間上限

錄製長度上限可控制語音信箱的錄製時間上限。 預設值為 5 分鐘。

### <a name="call-answering-rules"></a>通話接聽規則

此設定會控制是否允許使用者在 Microsoft Teams 中設定語音信箱來電接聽規則。

### <a name="dual-language-system-prompts"></a>雙語言系統提示

根據預設，語音信箱系統提示會以使用者在設定語音信箱時所選取的語言呈現給來電者。 如果商務需要以兩種語言顯示語音信箱系統提示，則可以設定主要和次要語言，而且可能不一樣。

### <a name="share-data-for-service-improvements"></a>共用資料以改善服務

指定是否要與服務共用語音信箱和轉譯資料，以進行訓練並提高準確度。 如果設為 False，無論使用者選擇何種，語音信箱資料都不會共用。


> [!IMPORTANT]
> Microsoft 365和Office 365中的語音信箱服務會快取語音信箱原則，每隔 6 小時更新一次快取。 因此，您所做的原則變更最多可能需要 6 小時才能套用。

## <a name="related-articles"></a>相關文章

[New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

[Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)
