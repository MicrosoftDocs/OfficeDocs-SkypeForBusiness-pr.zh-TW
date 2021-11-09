---
title: 在商務用 Skype Server 中建立會議目錄
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
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 摘要：瞭解如何在商務用 Skype Server 中建立會議目錄。
ms.openlocfilehash: 4ec5ba95de6c9b5518f1a060d0fc76d9186a1403
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828796"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>在商務用 Skype Server 中建立會議目錄
 
**摘要：** 瞭解如何在商務用 Skype Server 中建立會議目錄。
  
會議目錄會維護參與者在使用商務用 Skype 時加入會議時使用的字母數位會議識別碼之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議識別碼。 
  
## <a name="create-a-conference-directory"></a>建立會議目錄

建立多個會議目錄可確保會議 IDs 持續縮短，直到建立大量會議為止。 
  
在組織中，每位使用者的會議數目為典型，我們建議您針對集區中的每個999使用者建立一個會議目錄。 使用這種指導方針，會議 IDs 一般會變小。 不過，一旦集區 (的會議目錄數目) 超過9，會議識別碼長度就會成長以支援其他會議。
  
會議識別碼的格式如下： 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

若要建立會議目錄，請使用 **New-CsConferenceDirectory** Cmdlet。 例如，下列命令會建立「集區 atl-cs-001.litwareinc.com」42所主控的會議目錄，該目錄會主控于集區：
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

如需詳細資訊，請參閱 [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。
