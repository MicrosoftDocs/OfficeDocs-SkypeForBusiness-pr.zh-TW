---
title: 在商務用 Skype Server 中建立會議目錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 摘要：瞭解如何在商務用 Skype Server 中建立會議目錄。
ms.openlocfilehash: 0ed141b743d436ca2082b8a4f5010011a0256479
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991848"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>在商務用 Skype Server 中建立會議目錄
 
**摘要：** 瞭解如何在商務用 Skype Server 中建立會議目錄。
  
在使用商務用 Skype 時，會議目錄會在參與者用來加入會議的字母數位會議 ID 之間保留對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議 ID。 
  
## <a name="create-a-conference-directory"></a>建立會議目錄

建立多個會議目錄可確保會議 Id 保持不變，直到建立大量的會議為止。 
  
在每位使用者有典型會議數的組織中，我們建議您為池中的每個999使用者建立一個會議目錄。 使用這種準則，會議 Id 通常可以保持很小的狀態。 不過，一旦會議目錄數量（跨多個池）超過9個，會議 ID 長度就會增長以支援其他會議。
  
會議 ID 的格式如下所示： 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

若要建立會議目錄，請使用**CsConferenceDirectory** Cmdlet。 例如，下列命令會建立一個在 pool atl-cs-001.litwareinc.com 上託管的身分識別42的會議目錄：
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

如需詳細資訊，請參閱[新 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。
  

