---
title: 在商務用 Skype Server 中建立會議配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 摘要：瞭解如何在商務用 Skype Server 中建立會議配置設定。
ms.openlocfilehash: cd3d207816f352a33fb3fd228e7249d9e5d836b3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818604"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中建立會議配置設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中建立會議配置設定。
  
您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面來建立會議設定設定。
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立會議配置設定

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議配置**]。
    
4. 在 [**會議**設定] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：
    
    - 若要建立網站層級原則，按一下 [**網站**設定]。 在 [**選取網站**搜尋] 欄位中，輸入您要定義會議加入設定的網站名稱全部或部分名稱。 在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。
    
    - 若要建立池層級原則，請按一下 [**池**設定]。 在 [**選取服務**搜尋] 欄位中，輸入您要定義會議加入設定的全部或部分的 [池服務] 名稱。 在產生的服務清單中，按一下您想要的 [池]，然後按一下 **[確定]**。
    
5. 若要傳送透過大廳從公用交換電話網絡（PSTN）撥入的參與者，請清除**PSTN 呼叫者略過大廳**核取方塊。 根據預設，從 PSTN 撥入的參與者會直接進入會議。
    
6. 若要設定在會議中可成為簡報者的人員，請在 [**指定為簡報者**] 中，執行下列其中一項操作：
    
   - 若要不允許召集人以外的任何人成為簡報者，請按一下 [**無**]。
    
   - 若要只允許作為您組織成員的參與者成為簡報者，請按一下 [**公司**]。 這是預設設定。
    
   - 若要讓任何參與者成為簡報者，請按一下 [**所有人**]。
    
7. 若要讓召集人在排程會議時選取會議類型，請清除 [**預設為指派的會議類型**] 核取方塊。 根據預設，會自動指派會議類型。
    
8. 若要防止匿名（未經授權）使用者自動獲准，請清除 [**預設承認匿名使用者**] 核取方塊。 根據預設，匿名使用者會自動獲准參加會議。
    
9. 若要自訂傳送給參與者的會議邀請，請執行下列動作。 請注意，Url 和自訂頁尾文字的最大長度為1KB。 除了說明**URL**之外，如果您沒有指定自訂專案的值，就不會包含在會議中。 如果您不包含自訂的說明 URL，則會在邀請中顯示商務用 Skype 的預設說明 URL。 
    
   - 若要自訂會議邀請中出現的標誌，請在 [**標誌 URL**] 中輸入標誌的位置。 標誌必須是一個大小為 188 x 30 圖元的 GIF 或 JPG 影像。 
    
   - 若要自訂會議邀請中出現的解說文字，請在 [說明] **URL**中輸入解說文字的位置。
    
   - 若要自訂會議邀請中出現的法律文字，請在 [**合法文字 URL**] 中輸入法律文字的位置。
    
   - 若要自訂會議邀請中顯示的頁尾文字，請在 [**自訂頁尾文字**] 中輸入文字。
    
10. 按一下 [認可]****。
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 建立會議設定設定

若要建立會議設定，請使用**CsMeetingConfiguration** Cmdlet。
  
下列命令會針對雷德蒙的網站建立一組新的會議配置設定：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

因為在上述命令中沒有指定任何參數（除了是強制身分識別參數），所以新的會議設定會針對其所有屬性使用預設值。
  
若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 例如，若要建立會議設定的集合，根據預設，承認所有人都可以以演講者身分參與會議，請使用如下所示的命令：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

您可以透過包含多個參數來設定多個屬性值。 例如，下列命令會允許所有人作為簡報者加入會議，同時也會強制 PSTN 使用者在大廳等候，直到正式獲准取得會議為止：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

如需詳細資訊（包括完整的參數清單），請參閱[新 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)。
  

