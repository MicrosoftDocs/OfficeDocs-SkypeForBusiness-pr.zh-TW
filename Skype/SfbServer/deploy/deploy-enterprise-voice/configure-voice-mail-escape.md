---
title: 在商務用 Skype 中設定語音信箱轉義
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要：瞭解如何使用商務用 Skype Server 管理命令介面，在商務用 Skype Server 中設定語音信箱轉義。
ms.openlocfilehash: 469353dba39b5f4f6b7e4cdd458862d068da97c0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597217"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>在商務用 Skype 中設定語音信箱轉義

**摘要：** 瞭解如何使用商務用 Skype Server 管理命令介面，在商務用 Skype Server 中設定語音信箱轉義。

當使用者設定同時響鈴的行動電話時，如果行動電話關閉、電池計量不足或超出範圍，則通常會將來電者路由傳送至使用者的個人語音信箱。 使用商務用 Skype Server 時，使用者可以選擇要將與業務相關的來電路由傳送至其公司語音信箱系統。 具體而言，您可以設定 timer，如果在所定義的時間範圍內，電信公司的語音信箱接聽來電，商務用 Skype Server 會中斷與載波語音信箱系統的連線 (和使用者的個人語音信箱) ，但使用者在公司系統中的剩餘端點會繼續振鈴。 如此一來，來電者就會自動路由傳送至使用者的公司語音信箱。

使用下列參數，在語音原則層級上使用商務用 Skype Server 管理命令介面 Cmdlet **Set-CsVoicePolicy**，來執行此設定。

### <a name="to-configure-voice-mail-escape"></a>設定語音信箱轉義

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

2. 指定下列要 **Set-CsVoicePolicy** 的參數：

   - **EnableVoicemailEscapeTimer** -啟用或停用轉義計時器。

   - **PSTNVoicemailEscapeTimer** -指定超時值，以毫秒為單位。 預設值為1500毫秒，值的範圍為0毫秒到8000毫秒。

## <a name="example"></a>範例

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>另請參閱

[設定用於授權撥號功能和權限的語音原則和 PSTN 使用方式記錄](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)