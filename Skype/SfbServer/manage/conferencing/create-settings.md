---
title: 在商務用 Skype Server 中建立會議配置設定
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 摘要：瞭解如何在商務用 Skype Server 中建立會議配置設定。
ms.openlocfilehash: 03a9194a5b4015d9434641e7946b66c57ff4df77
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747149"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中建立會議配置設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中建立會議配置設定。
  
您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面來建立會議設定設定。
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立會議配置設定

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。
    
4. 在 [ **會議** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：
    
    - 若要建立網站層級原則，請按一下 [ **網站** 設定]。 在 [ **選取網站** ] 搜尋欄位中，輸入您要定義會議加入設定之網站的全部或部分名稱。 在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。
    
    - 若要建立集區層級原則，請按一下 [ **集** 區設定]。 在 [ **選取服務** ] 搜尋欄位中，輸入您要定義會議加入設定之集區服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的集區，然後按一下 **[確定]**。
    
5. 若要透過會議廳從公用交換電話網路 (PSTN) 傳送從公用交換電話網路撥號的參與者，請清除 [ **PSTN 來電者旁路會議廳** ] 核取方塊。 根據預設，從 PSTN 撥入的參與者會直接進入會議。
    
6. 若要設定在會議中誰可以是簡報者，請在 [ **指定為簡報者**] 中，執行下列其中一項動作：
    
   - 若不允許召集人以外的任何人員成為簡報者，請按一下 [ **無**]。
    
   - 若只要允許屬於組織成員的參與者成為簡報者，請按一下 [ **公司**]。 這是預設設定。
    
   - 若要允許任何參與者成為簡報者，請按一下 [ **所有人**]。
    
7. 若要讓召集人在排程會議時選取會議類型，請清除 [ **依預設指派會議類型** ] 核取方塊。 依預設，會自動指派會議類型。
    
8. 若要防止匿名 (未驗證的使用者自動獲准) 使用者，請清除 [ **預設會承認匿名使用者** ] 核取方塊。 根據預設，匿名使用者會自動獲准參加會議。
    
9. 若要自訂傳送給參與者的會議邀請，請執行下列動作。 請注意，URLs 和自訂頁腳文字的最大長度為1KB。 除了 [說明 **URL**] 之外，如果您沒有指定自訂專案的值，這些自訂專案不會包含在會議中。 如果不包含自訂的 help url，則會在邀請中顯示商務用 Skype 的預設說明 url。 
    
   - 若要自訂出現在會議邀請中的標誌，請在 [ **標誌 URL**] 中輸入標誌的位置。 此徽標必須是大小為 188 x 30 圖元的 GIF 或 JPG 影像。 
    
   - 若要自訂出現在會議邀請中的解說文字，請在 [說明 **URL**] 中輸入説明文字的位置。
    
   - 若要自訂出現在會議邀請中的法律文字，請在 [ **合法文字 URL**] 中輸入法律文字的位置。
    
   - 若要自訂出現在會議邀請中的頁腳文字，請在 [ **自訂頁腳文字**] 中輸入文字。
    
10. 按一下 **[認可]**。
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面建立會議配置設定

若要建立會議配置設定，請使用 **New-CsMeetingConfiguration** Cmdlet。
  
下列命令會為 Redmond 網站建立一組新的會議配置設定：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

由於上述命令中未指定任何 (必要 Identity 參數) 以外的參數，因此新的會議設定會使用其所有屬性的預設值。
  
若要建立使用不同屬性質的設定，只需要加入適當的參數和參數值即可。 例如，若要建立會議設定的集合，根據預設，承認所有人都可以加入會議，以供簡報者使用類似如下的命令：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

您可以透過包含多個參數來設定多個屬性值。 例如，下列命令會 admits 每個人參加會議的簡報者，也會強制 PSTN 使用者在大廳等候，直到他們正式獲准參加會議為止：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

如需詳細資訊，包括完整的參數清單，請參閱 [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)。
