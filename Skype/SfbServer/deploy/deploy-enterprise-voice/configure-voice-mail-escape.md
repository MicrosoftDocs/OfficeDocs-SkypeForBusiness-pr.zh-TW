---
title: 在商務用 Skype 中設定語音信箱轉義
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要：瞭解如何使用商務用 Skype Server Management 命令介面，在商務用 Skype Server 中設定語音信箱轉義。
ms.openlocfilehash: e372b43a0a580cd1a7b95fc3db8130a65c8398ca
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768006"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>在商務用 Skype 中設定語音信箱轉義

**摘要：** 瞭解如何使用商務用 Skype Server 管理命令介面，在商務用 Skype Server 中設定語音信箱轉義。

當使用者設定同時撥打至行動電話時，如果行動電話關閉、不使用電池電源或超出範圍，通常會將呼叫者路由到使用者的個人語音信箱。 在商務用 Skype Server 中，使用者可以選擇要將商務相關通話路由至其公司語音信箱系統。 具體來說，您可以設定計時器，如果在所定義的時間範圍內，由承運人的語音信箱應答通話，商務用 Skype Server 將會與載波的語音信箱系統（與使用者的個人語音信箱）斷開連線，而使用者的公司系統中的剩餘端點會繼續撥打。 如此一來，來電者就會自動路由到使用者的公司語音信箱。

此設定是使用商務用 Skype Server Management Shell Cmdlet （ **CsVoicePolicy**）在語音原則層級執行，並使用下列參數。

### <a name="to-configure-voice-mail-escape"></a>若要設定語音信箱轉義

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

2. 指定下列參數來**設定-CsVoicePolicy**：

   - **EnableVoicemailEscapeTimer** -啟用或停用轉義計時器。

   - **PSTNVoicemailEscapeTimer** -指定超時值（以毫秒為單位）。 預設值為1500毫秒，值的範圍可以是0毫秒到8000毫秒。

## <a name="example"></a>範例

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>另請參閱

[設定語音原則和 PSTN 使用記錄，以授權通話功能和許可權](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

