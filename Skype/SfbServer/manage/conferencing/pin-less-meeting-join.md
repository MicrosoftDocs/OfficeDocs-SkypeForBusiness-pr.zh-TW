---
title: 在商務用 Skype Server 中設定 PIN 較少的會議加入
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 摘要：瞭解如何在商務用 Skype Server 中設定 PIN 較少的會議加入選項。
ms.openlocfilehash: 5b8ad452f54785a916ac70acd468458215135934
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991788"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>在商務用 Skype Server 中設定 PIN 較少的會議加入
 
**摘要：** 瞭解如何在商務用 Skype Server 中設定 PIN 較少的會議加入選項。
  
當電話撥入來電者嘗試加入會議時，會議自動語音應答（CAA）服務會將呼叫者放在與大廳不同的觸筆中，&#x2014; 如果簡報者未在通話中，且撥入來電者未進入引線針腳。 PIN 較少的會議加入選項可讓撥入呼叫者加入會議，而不需輸入引線針腳，即使對方是通話中的第一個使用者也一樣。 
  
設定此功能時，請記住下列事項：
  
- 僅適用于私人會議。
    
- 可讓 PSTN 呼叫者在不存在經過驗證的使用者的情況下，繼續私人會議。
    
- 設定變更之後，就會套用至所有現有和新的私人會議。
    
- 您可以在召集人的網站或全域層級啟用。
    
- 您可以針對可以略過大廳的人員設定下列選項之一： 
    
  - **我組織中與來電者直接取得的任何人**
    
  - **呼叫者直接加入的任何人（無限制）** （這是預設設定）。
    
- 如果設定為啟用 PIN 較少的聯結，CAA 服務仍會提示輸入引線針腳。 無論是否輸入 PIN，使用者都可以加入會議。 不過，保留引線釘選功能可讓撥入來電者進行驗證，並視需要管理會議。
    
## <a name="configure-pin-less-meeting-join"></a>設定 PIN 更少的會議加入

若要為使用者啟用 PIN 較少的會議加入，請使用[CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) Cmdlet 及 AllowAnonymousPstnActivation 參數，如下所示：
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

例如，下列命令可為網站雷德蒙器啟用 PIN 較少的會議加入：
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

為安全起見，當您開啟 PIN 較少的會議加入時，您可能會想要限制匿名使用者撥出，方法是確保 ConferencingPolicy 的設定方式如下：
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

如需詳細資訊，請參閱[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

