---
title: 在商務用 Skype Server 中啟用或停用電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '摘要: 瞭解如何使用 [控制台] 或 [管理命令介面] 來啟用或停用商務用 Skype Server 中的電話撥入式會議。'
ms.openlocfilehash: 6723c3501b226d11977ad176a804210540f1a2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192578"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用或停用電話撥入式會議
 
**摘要:** 瞭解如何使用 [控制台] 或 [管理命令介面] 來啟用或停用商務用 Skype Server 中的電話撥入式會議。
  
您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面來啟用電話撥入式會議。
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 的 [控制台] 來啟用或停用電話撥入式會議

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [**會議原則**]。
    
4. 在會議原則清單中, 選取您要啟用電話撥入式會議的原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。 
    
5. 若要允許使用者透過撥入方式加入會議, 請核取 [**啟用 PSTN 電話撥入式會議**] 核取方塊。 根據預設, 使用者可以使用公開交換電話網絡 (PSTN) 撥入會議。
    
6. 按一下 [認可]****。 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來啟用或停用電話撥入式會議

若要啟用或停用電話撥入式會議, 請使用**CsConferencingPolicy** Cmdlet 及 EnableDialInConferencing 參數, 如下所示:
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

如需詳細資訊, 請參閱[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

