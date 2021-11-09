---
title: 在商務用 Skype Server 中查看會議配置設定
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 摘要：瞭解如何在商務用 Skype Server 中查看會議配置設定。
ms.openlocfilehash: 4d55d4213b0eb7cbd89045960d87c05340520cbc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837625"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中查看會議配置設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中查看會議配置設定。
  
您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面來查看會議配置設定。
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台來查看會議設定設定
<a name="BKMK_ViewJoinSettings"> </a>

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。
    
4. 在 [ **會議** 設定] 頁面上，按一下您要查看的會議設定。
    
5. 在 [ **編輯檔案篩選**] 中，選取 [ **顯示詳細資料** ] 核取方塊。
    
    **編輯會議設定- \<policy\>** 開啟顯示選取原則的設定。
    
    如需設定設定的詳細資訊，請參閱[在商務用 Skype Server 中建立會議配置設定](create-settings.md)。
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來查看會議設定設定
<a name="BKMK_ViewJoinSettings"> </a>

若要查看所有會議設定設定的相關資訊，請使用 **Get-CsMeetingConfiguration** Cmdlet：
  
```
Get-CsMeetingConfiguration
```

此命令會傳回類似下列的資訊：
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

如需詳細資訊，包括完整的參數清單，請參閱 [Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)。
