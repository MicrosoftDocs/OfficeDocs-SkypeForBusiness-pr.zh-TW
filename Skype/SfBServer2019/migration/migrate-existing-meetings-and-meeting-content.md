---
title: 移轉現有的會議與會議內容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 當使用者帳戶移至商務用 Skype Server 2019 伺服器時，下列資訊就會與該使用者帳戶一起移動：
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813471"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>移轉現有的會議與會議內容

當使用者帳戶移至商務用 Skype Server 2019 伺服器時，下列資訊會與該使用者帳戶一起移動：
  
- **已由使用者排程的會議**。 這包括移動會議目錄及會議資料。
    
- **使用者的個人身分識別號碼（PIN）**。 使用者目前的 PIN 會持續起作用，直到過期為止，或使用者要求新的 PIN。
    
下列使用者帳戶資訊不會移至新的伺服器。
  
- **會議內容**。 若要移動在會議期間共用的內容（例如 PowerPoint、白板、附件或投票資料），請使用 **-MoveConferenceData**參數做為**move-csuser** Cmdlet 的一部分。 
    

