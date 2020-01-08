---
title: 在商務用 Skype 和 Lync 用戶端使用者介面之間切換
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: '瞭解如何在 Office 365 中使用 PowerShell 在商務用 Skype 和 Lync 用戶端使用者介面之間切換 '
ms.openlocfilehash: 0f24879c136c98db1a856765cb164d376417ad5a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962881"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>在商務用 Skype 和 Lync 用戶端使用者介面之間切換

針對商務用 Skype Online 組織，您可以使用 Office 365 中的遠端 PowerShell，讓您的商務用 Skype 使用者使用商務用 Skype 用戶端或商務用 Skype （Lync）用戶端使用者介面。 預設設定是供使用者使用商務用 Skype 用戶端使用者介面。 如果您喜歡使用 Lync 用戶端體驗，您可以依照本主題稍後的步驟，管理第一次啟動用戶端行為，以顯示 Lync 使用者介面。
  
> [!NOTE]
> Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本的選項。 在您嘗試將用戶端環境設定為使用 Lync 2013 用戶端之前，請先檢查用戶端版本，以確保它不是以數位16開頭;例如： x.x.x。 
  
> [!TIP]
> 如果您想要輕鬆地切換使用者介面，且不想執行手動步驟，請參閱 PowerShell 腳本的[Microsoft 下載中心](https://go.microsoft.com/fwlink/?LinkId=532431)，讓它變得更容易。
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>為使用者切換商務用 Skype 使用者介面

商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只支援在64位電腦上從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如需其他資訊，請參閱針對[商務用 Skype Online 管理設定您的電腦](https://go.microsoft.com/fwlink/?LinkId=534539)。
  
> [!IMPORTANT]
> 切換使用者介面的_全域_原則設定將不會套用到已套用自訂原則的使用者。 若要能夠變更使用者介面，您必須針對已套用自訂原則的每個使用者執行下列動作：
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> _ClientPolicyEnableSkypeUI_原則會取代使用者現有的自訂策略設定。
  
若要讓貴組織中的所有使用者都能使用商務用 Skype 用戶端，請開啟遠端 PowerShell，並輸入以下內容：
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

如果您設定了原則，就會看到：
  
![PowerShell： SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
若要讓貴組織中的所有使用者都能使用商務用 Skype （Lync）用戶端，請開啟遠端 PowerShell，並輸入以下內容： 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

如果您設定了原則，就會看到：
  
![PowerShell： SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
若要允許貴組織中的一位使用者使用商務用 Skype 用戶端，請開啟遠端 PowerShell，並輸入以下內容：
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

如果您設定了原則，就會看到：
  
![商務用 Skype Online-啟用 UI](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
若要允許貴組織中的一位使用者使用商務用 Skype （Lync）用戶端，請開啟遠端 PowerShell，並輸入以下內容：
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

如果您設定了原則，就會看到：
  
![商務用 Skype Online-已停用 UI](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
若要允許貴組織中的多位使用者使用商務用 Skype 用戶端，請開啟遠端 PowerShell，並輸入以下內容：
  

```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

若要允許貴組織中的多位使用者使用商務用 Skype （Lync）用戶端，請開啟遠端 PowerShell，並輸入以下內容：
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

若要允許貴組織中的一組使用者使用商務用 Skype 用戶端，請開啟遠端 PowerShell，並輸入以下內容：
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

若要允許貴組織中的一組使用者使用商務用 Skype （Lync）用戶端，請開啟遠端 PowerShell，並輸入以下內容：
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  使用者的名稱是應該指派原則的使用者帳戶名稱。 使用者的帳戶名稱可以採用下列其中一種格式：使用者的 > SIP 位址> 使用者的使用者主體名稱（UPN）>\\使用者> Active Directory 顯示名稱
  
[使用 Windows PowerShell 管理 Lync Online](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a>商務用 Skype Online 原則設定

下表顯示原則第一次套用至使用者時的使用者體驗：
  
|**管理員原則設定**|**顯示使用者介面**|
|:-----|:-----|
|原則沒有設定。 |使用者將繼續使用商務用 Skype 用戶端使用者介面。|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|使用者將繼續使用商務用 Skype 用戶端使用者介面。|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|使用者會被要求切換到商務用 Skype （Lync）用戶端使用者介面。 他們可以稍後切換。|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|使用者將使用商務用 Skype 用戶端使用者介面。 |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|使用者會被要求切換到商務用 Skype （Lync）用戶端使用者介面。 系統管理員可以在將來變更設定，將其切換到商務用 Skype 用戶端使用者介面。 |
   
下表顯示原則變更時的使用者體驗：
  
|**管理員原則設定**|**商務用 Skype （Lync）使用者介面**|**商務用 Skype 使用者介面**|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|使用者會被要求切換到商務用 Skype 用戶端使用者介面。  <br/> |使用者將繼續使用商務用 Skype 用戶端使用者介面。  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|使用者將繼續使用商務用 Skype （Lync）介面。  <br/> |使用者會被要求切換到商務用 Skype （Lync）用戶端使用者介面。  <br/> |
|原則沒有設定。  <br/> |如果沒有設定原則，使用者就不會看到商務用 Skype （Lync）用戶端使用者介面。 他們將永遠使用商務用 Skype 用戶端使用者介面。  <br/> |使用者將繼續使用商務用 Skype 用戶端使用者介面。  <br/> |
   
下表顯示所有可用的線上自訂原則。 在 EnableSkypeUI 旗標間切換時，系統會建立新的原則，以提供管理員靈活性來保留舊的自訂原則。 請使用上方的 Cmdlet 來向您的使用者授予下列其中一項原則。
  
|**原則名稱**|**EnableSkypeUI**|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |虛假|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |虛假|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |虛假|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |虛假|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |虛假|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|虛假|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |虛假|

   
若要開始使用 Windows PowerShell，請參閱以下主題：
  
- [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>第一次啟動用戶端行為

根據預設，當使用者第一次啟動商務用 Skype 時，他們將永遠會看到商務用 Skype 的使用者介面，即使您已透過將用戶端原則設定為 Lync 用戶端體驗（），（`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`如先前所述），您已選取 lync 用戶端的使用經驗。 幾分鐘之後，系統會要求使用者切換到 Lync 模式。
  
如果您想要在使用者第一次啟動商務用 Skype 用戶端時顯示 Lync 使用者介面，請在用戶端第一次更新之後，按照下列步驟進行：
  
1. 請依照本主題前面所述的步驟進行，並確認用戶端原則已設定為停用商務用 Skype 使用者介面。
    
2. 更新使用者電腦上的系統登錄。 您應該在使用者第一次啟動商務用 Skype 用戶端之前執行此動作，而您只能執行此動作一次。 如需如何建立群組原則物件以更新加入網域的電腦上的登錄的相關資訊，請參閱主題稍後的章節。
    
    在 **[\\HKEY_CURRENT_USER\\軟體 Microsoft\\Office\\Lync]** 金鑰中，建立新的**二進位**值。
    
    **值名稱**必須是**EnableSkypeUI**，而**值資料**必須設定為**00 00 00 00**。
    
    此索引鍵看起來應該像以下這樣：
    
    [HKEY_CURRENT_USER\\軟體\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab" = dword：00000001
    
    "CanShareOneNoteInCollab" = dword：00000001
    
    "CanAppShareInCollab" = dword：00000001
    
    "EnableSkypeUI" = 十六進位：00、00、00、00
    
Lync 使用者介面現在會在使用者第一次啟動商務用 Skype 用戶端時顯示。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制歡迎畫面教學課程的顯示

當使用者開啟商務用 Skype 用戶端時，預設行為是顯示 [歡迎] 畫面，其中包含*大部分人要求的7個快速秘訣*。 您可以在用戶端電腦上新增下列登錄值，以關閉歡迎畫面的顯示，但仍允許使用者存取教學課程：
  
在 **[\\HKEY_CURRENT_USER 軟體\\Microsoft\\Office\\15.0\\Lync]** 金鑰中，建立新的**DWORD （32位）值**。 **值名稱**必須是**IsBasicTutorialSeenByUser**，而**值資料**必須設定為**1**。
  
此索引鍵看起來應該像以下這樣：
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>關閉用戶端教學課程

如果您不想讓使用者存取教學課程，您可以使用下列登錄值來關閉用戶端教學課程：
  
在 **[\\HKEY_CURRENT_USER 軟體\\Microsoft\\Office\\15.0\\Lync]** 金鑰中，建立新的**DWORD （32位）值**。 **值名稱**必須是**TutorialFeatureEnabled**，而**值資料**必須設定為**0**。
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

您可以將**值資料**設定為**1**，將教學課程改回開啟。
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>建立群組原則物件來修改加入網域的電腦上的登錄

在使用者第一次啟動商務用 Skype 用戶端時，若要顯示 Lync 用戶端體驗的登錄更新，則必須只進行一次。 如果您使用群組原則物件（GPO）來更新註冊表，您需要定義物件來建立新的值，而不是更新值資料。 當套用 GPO 時，如果新值不存在，GPO 將會建立它，並將值資料設定為0。
  
下列程式說明如何修改註冊表，以便在使用者第一次啟動商務用 Skype 時顯示 Lync 用戶端體驗。 您也可以使用此程式來更新註冊表，如前文所述，停用歡迎畫面教學課程。
  
 **建立 GPO**
  
1. 啟動**群組原則管理主控台**。
    
    如需如何使用群組原則管理主控台的相關資訊，請參閱[群群組原則管理主控台](https://go.microsoft.com/fwlink/?LinkId=532759)。
    
2. 以滑鼠右鍵按一下 [**群群組原則物件**] 節點，然後在功能表上選取 [**新增**]。
    
3. 在 [**新增 gpo** ] 對話方塊中，輸入 GPO 的名稱，例如 [MakeLyncDefaultUI]，然後按一下 **[確定]**。
    
4. 以滑鼠右鍵按一下您剛建立的新 GPO，然後從功能表中選取 [**編輯**]。
    
5. 在 [**群組原則管理編輯器**] 中，展開 [**使用者**設定]，展開 [**喜好**設定]，展開 [ **Windows 設定**]，然後**選取 [登錄**] 節點。
    
6. 以滑鼠右鍵**按一下 [登錄**] 節點，然後選取 [**新增** > **註冊專案**]。
    
7. 在 [**新增登錄屬性**] 對話方塊中，更新下列專案：
    
|**域**|**要選取或輸入的值**|
|:-----|:-----|
|**動作** <br/> |**建立** <br/> |
|**一兩** <br/> | HKEY_CURRENT_USER <br/> |
|**索引鍵路徑** <br/> |軟體\\Microsoft\\Office\\Lync  <br/> |
|**值名稱** <br/> |EnableSkypeUI  <br/> |
|**數值型別** <br/> |REG_BINARY  <br/> |
|**值資料** <br/> |00000000  <br/> |
   
按一下 **[確定]** 儲存變更，然後關閉該 GPO。
    
接著，您必須將您所建立的 GPO 連結至您要指派原則的使用者群組（例如 OU）。
  
 **使用 GPO 指派原則**
  
1. 在 [群組原則管理主控台] 中，以滑鼠右鍵按一下您要指派原則的 OU，然後選取 [**連結到現有的 GPO**]。
    
2. 在 [**選取 gpo** ] 對話方塊中，選取您所建立的 GPO，然後選取 **[確定]**。
    
3. 在目標使用者的電腦上，開啟命令提示字元，然後輸入下列命令：
    
    **gpupdate/target： user**
    
    訊息「正在更新原則 ...」會在應用 GPO 時顯示。 完成後，就會顯示「使用者原則更新已成功完成」訊息。
    
4. 在命令提示字元中，輸入下列命令：
    
    **gpresult/r**
    
    您應該會看到「指派的群群組原則物件」與您所建立之 GPO 的名稱，如下所示。
    
您也可以檢查登錄，以驗證 GPO 是否已在使用者的電腦上成功更新登錄。 開啟 [登錄編輯程式]，然後流覽至 **[\\HKEY_CURRENT_USER\\\\軟體\\Microsoft Office Lync]** 金鑰。 如果 GPO 成功更新了註冊表，您會看到一個名為 EnableSkypeUI 的值，其值為0。
  
## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)

  
 
