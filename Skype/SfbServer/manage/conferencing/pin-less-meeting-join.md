---
title: 在商務用 Skype Server 中設定 PIN 較少的會議加入
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 摘要：瞭解如何在商務用 Skype Server 中設定 PIN 不足的會議加入選項。
ms.openlocfilehash: 13af671edaa9ab8853e0390d43c62b6576bed4e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861360"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>在商務用 Skype Server 中設定 PIN 較少的會議加入
 
**摘要：** 瞭解如何在商務用 Skype Server 中設定 PIN 不足的會議加入選項。
  
當撥入來電者嘗試加入會議時，會議自動語音應答 (CAA) 服務會將來電者放在不同于會議廳的保留觸筆中 &#x2014; 如果簡報者尚未在來電中，且撥入來電者未進入領導者 PIN 碼。 PIN 不足的會議加入選項允許撥入來電者加入會議，而不輸入引線 PIN 碼，即使他們是呼叫的第一位 PIN。 
  
設定此功能時，請牢記下列事項：
  
- 僅適用于私人會議。
    
- 允許 PSTN 來電者保留私人會議，而不存在已驗證的使用者。
    
- 設定變更後，它會套用至所有現有和新的私人會議。
    
- 可在召集人的網站或全域層級上啟用。
    
- 可以為下列其中一項設定可略過大廳的選項： 
    
  - **組織中與來電者的任何人都可以直接取得**
    
  - **任何人 () 的來電者都不會直接取得任何限制** (這是預設設定。 ) 
    
- 設定以啟用 PIN 碼的加入時，CAA 服務仍然會提示輸入前置字元。 使用者可以加入會議，不論是否輸入 PIN 碼。 不過，保留引線 PIN 碼的功能可讓撥入來電者以主持人身分驗證，並視需要管理會議。
    
## <a name="configure-pin-less-meeting-join"></a>設定 PIN 較少的會議加入

若要為您的使用者啟用 PIN 碼較少的會議加入，請使用 [CsDialInConferencingConfiguration 指令程式](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) 搭配 AllowAnonymousPstnActivation 參數，如下所示：
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

例如，下列命令會為網站 Redmond 啟用 PIN 碼較少的會議加入：
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

基於安全性的考慮，當開啟 PIN 不足的會議加入時，您可能會想要限制匿名使用者撥出的方式是確保 ConferencingPolicy 已設定如下：
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

如需詳細資訊，請參閱 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
