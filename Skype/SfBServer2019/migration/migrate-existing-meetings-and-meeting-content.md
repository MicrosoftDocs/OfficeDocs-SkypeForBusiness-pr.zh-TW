---
title: 移轉現有的會議與會議內容
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 當使用者帳戶移至商務用 Skype Server 2019 伺服器時，下列資訊會隨該使用者帳戶一起移動：
ms.openlocfilehash: e28cbce30608672d27578cfaa5ab92dbe1ed3c4cd6b234da7389b1f9a6978350
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312291"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>移轉現有的會議與會議內容

當使用者帳戶移至商務用 Skype Server 2019 伺服器時，下列資訊會隨該使用者帳戶一起移動：
  
- **使用者已排定的會議**。包含移動會議目錄及會議資料。
    
- **使用者的個人身分識別號碼 (PIN)**。 使用者目前的 PIN 碼會持續運作，直到到期或使用者要求新的 PIN 碼。
    
下列使用者帳戶資訊不會移到新的伺服器。
  
- **會議內容**。 為了移動在會議期間共用的內容，例如 PowerPoint、白板、附件或投票資料，請使用 **-MoveConferenceData** 參數做為 **Move-CsUser** Cmdlet 的一部分。 
    

