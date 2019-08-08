---
title: 使用商務用 Skype 2015 設定用戶端體驗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '摘要: 請閱讀本主題, 以瞭解如何設定商務用 Skype 使用者的用戶端體驗。'
ms.openlocfilehash: ea1d38693291ebfa7d7cc4f8893b0aa6ec1c0d83
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234450"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>使用商務用 Skype 2015 設定用戶端體驗
 
**摘要:** 若要瞭解如何設定商務用 Skype 2015 使用者的用戶端體驗, 請閱讀本主題。
  
商務用 skype 2015 提供以 Skype 消費者產品體驗為基礎的新使用者體驗。 除了 Lync 的所有功能之外, 商務用 Skype 也會以簡化的控制項和熟悉的圖示來提供新功能。 如需新用戶端體驗的詳細資訊, 請參閱[探索商務用 Skype](https://go.microsoft.com/fwlink/?LinkId=529022)。
  
商務用 skype 伺服器支援新的商務用 Skype 用戶端體驗, 以及 Lync 用戶端體驗。 作為系統管理員, 您可以為使用者選擇首選的用戶端體驗。 例如, 您可能會想要部署 Lync 用戶端體驗, 直到貴組織中的使用者在新的商務用 Skype 體驗中受到全面訓練為止。 或者, 如果您尚未將所有使用者升級到商務用 Skype Server, 您可能會希望所有使用者都能使用相同的用戶端體驗, 直到全部都升級到新的伺服器為止。
  
> [!IMPORTANT]
> 如果貴組織已部署商務用 Skype Server 和 Lync Server, 則預設的用戶端體驗會依伺服器版本和 UI 設定而有所不同。 當使用者第一次啟動商務用 Skype 時, 他們將永遠會看到商務用 Skype 使用者介面, 即使您已選取 Lync 用戶端體驗也一樣。 幾分鐘之後, 系統會要求使用者切換到 Lync 模式。 如需詳細資訊, 請參閱本主題稍後的**第一次啟動用戶端行為**。
  
> [!NOTE]
> Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本或更新版本的選項。 在您嘗試將用戶端環境設定為使用 Lync 2013 用戶端之前, 請先檢查用戶端版本, 以確保它不是以數位16開頭;例如: x.x.x。 
  
## <a name="configure-the-client-experience"></a>設定用戶端體驗

您可以透過使用**CSClientPolicy** Cmdlet 與 EnableSkypeUI 參數, 來指定貴組織中的使用者所能看到的用戶端體驗:
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

其中 XdsIdentity 指的是全域原則或命名網站原則。
  
下列命令會針對貴組織中受全域原則影響的所有使用者, 選取商務用 Skype 用戶端體驗 (請記住, 網站或使用者專用原則會覆寫全域原則): 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

[下一步] 命令會針對貴組織中的所有使用者選取由全域原則影響的 Lync 用戶端體驗:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

[下一步] 命令會針對雷德蒙網站中的所有使用者選取商務用 Skype 用戶端體驗:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

如果您想要針對貴組織內的特定使用者設定用戶端體驗, 您可以使用 CsClientPolicy Cmdlet 建立新**的**使用者策略, 然後使用**授與 CsClientPolicy**將原則指派給特定使用者。Cmdlet.
  
例如, 下列命令會建立新的用戶端原則 SalesClientUI, 以選取商務用 Skype 用戶端體驗:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

下一個命令會將原則 (SalesClientUI) 指派給銷售部門的所有成員:
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>第一次啟動用戶端行為

根據預設, 當使用者第一次啟動商務用 Skype 2015 時, 他們將永遠會看到商務用 Skype 的使用者介面, 即使您已選取 Lync 用戶端體驗, 只要將 EnableSkypeUI 參數的值設定為 $False (如下所述)。先前. 幾分鐘之後, 系統會要求使用者切換到 Lync 模式。
  
如果您想要在使用者第一次啟動商務用 Skype 用戶端時顯示 Lync 使用者介面, 請在用戶端第一次更新之後, 按照下列步驟進行:
  
1. 確認您使用的原則`EnableSkypeUI`中的值設定為 $False, 如先前所述。
    
2. 更新使用者電腦上的系統登錄。 您應該在使用者第一次啟動商務用 Skype 用戶端之前執行此動作, 而您只能執行此動作一次。 如需如何建立群組原則物件以更新加入網域的電腦上的登錄的相關資訊, 請參閱主題稍後的章節。
    
    在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 索引鍵中, 建立新的**二進位**值。
    
    **值名稱**必須是**EnableSkypeUI**, 而**值資料**必須設定為**00 00 00 00**。
    
    此索引鍵看起來應該像以下這樣:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

Lync 使用者介面現在會在使用者第一次啟動商務用 Skype 用戶端時顯示。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制歡迎畫面教學課程的顯示

當使用者開啟商務用 Skype 用戶端時, 預設行為是顯示 [歡迎] 畫面, 其中包含*大部分人要求的7個快速秘訣*。 您可以在用戶端電腦上新增下列登錄值, 以關閉歡迎畫面的顯示, 但仍允許使用者存取教學課程:
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 索引鍵中, 建立新的**DWORD (32 位) 值**。 **值名稱**必須是**IsBasicTutorialSeenByUser**, 而**值資料**必須設定為**1**。
  
此索引鍵看起來應該像以下這樣:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>關閉用戶端教學課程

如果您不想讓使用者存取教學課程, 您可以使用下列登錄值來關閉用戶端教學課程:
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 索引鍵中, 建立新的**DWORD (32 位) 值**。 **值名稱**必須是**TutorialFeatureEnabled**, 而**值資料**必須設定為**0**。
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

您可以將**值資料**設定為**1**, 將教學課程改回開啟。
  
## <a name="default-client-behaviors"></a>預設用戶端行為

如果貴組織已部署商務用 Skype Server 和 Lync Server, 則用戶端體驗會隨著伺服器版本和 Skype UI 設定而有所不同。 下表顯示以伺服器版本和 UI 設定為基礎的初始用戶端體驗:
  

|**伺服器版本**|**EnableSkypeUI 設定**|**用戶端體驗**|
|:-----|:-----|:-----|
|商務用 Skype 伺服器 |設置  <br/> |商務用 Skype  <br/> |
|商務用 Skype 伺服器  |滿足  <br/> |商務用 Skype  <br/> |
|商務用 Skype 伺服器  |虛假  <br/> |使用者要求切換至 Lync 模式 (如果您將 UI 設定變更為 $true, 使用者就可以在稍後切換到商務用 Skype)  <br/> |
|Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)  <br/> |設置  <br/> |使用者要求切換至 Lync 模式 (如果您將 UI 設定變更為 $true, 使用者就可以在稍後切換到商務用 Skype)  <br/> |
|Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)  <br/> |滿足  <br/> |商務用 Skype  <br/> |
|Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)  <br/> |虛假  <br/> |使用者要求切換至 Lync 模式 (如果您將 UI 設定變更為 $true, 使用者就可以在稍後切換到商務用 Skype)  <br/> |
|Lync Server 2010 或 Lync Server 2013 (不含補丁程式)  <br/> |設置  <br/> |使用者要求切換至 Lync 模式 (使用者稍後無法切換到商務用 Skype)  <br/> |
   
下表顯示管理員變更 Skype UI 體驗的初始設定時的用戶端體驗:
  

|**伺服器版本**|**EnableSkypeUI 設定**|**用戶端 UI = Lync**|**用戶端 UI = 商務用 Skype**|
|:-----|:-----|:-----|:-----|
|商務用 Skype 伺服器 |滿足  <br/> |使用者要求切換到商務用 Skype  <br/> |商務用 Skype  <br/> |
|商務用 Skype 伺服器 |虛假  <br/> |Lync 模式  <br/> |使用者要求切換至 Lync 模式  <br/> |
|Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)  <br/> |滿足  <br/> |使用者要求切換到商務用 Skype  <br/> |商務用 Skype  <br/> |
|Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)  <br/> |虛假  <br/> |Lync 模式  <br/> |使用者要求切換至 Lync 模式  <br/> |
|Lync Server 2010 或 Lync Server 2013 (不含補丁程式)  <br/> |設置  <br/> |Lync 模式 (無法切換到商務用 Skype)  <br/> |Lync 模式 (無法切換到商務用 Skype)  <br/> |
   
管理商務用 Skype 用戶端設定所需的修補程式版本如下:
  
- Lync Server 2010-Lync Server 2010 的2015年2月累計更新 (4.0.7577.710)。 如需詳細資訊, 請參閱[Lync Server 2010 更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-Lync Server 2013 的2014年12月累計更新 (5.0.8308.857)。 如需詳細資訊, 請參閱[Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>建立群組原則物件來修改加入網域的電腦上的登錄

[登錄更新] 會在使用者第一次啟動商務用 Skype 2015 用戶端時, 顯示 Lync 用戶端體驗一次。 如果您使用群組原則物件 (GPO) 來更新註冊表, 您需要定義物件來建立新的值, 而不是更新值資料。 當套用 GPO 時, 如果新值不存在, GPO 將會建立它, 並將值資料設定為0。 
  
下列程式說明如何修改註冊表, 以便在使用者第一次啟動商務用 Skype 2015 用戶端時顯示 Lync 用戶端體驗。 您也可以使用此程式來更新註冊表, 如前文所述, 停用歡迎畫面教學課程。
  
### <a name="to-create-the-gpo"></a>建立 GPO

1. 啟動**群組原則管理主控台**。
    
    如需如何使用群組原則管理主控台的相關資訊, 請參閱[群群組原則管理主控台](https://go.microsoft.com/fwlink/?LinkId=532759)。
    
2. 以滑鼠右鍵按一下 [**群群組原則物件**] 節點, 然後在功能表上選取 [**新增**]。
    
3. 在 [**新增 gpo** ] 對話方塊中, 輸入 GPO 的名稱, 例如 [MakeLyncDefaultUI], 然後按一下 **[確定]**。
    
4. 以滑鼠右鍵按一下您剛建立的新 GPO, 然後從功能表中選取 [**編輯**]。
    
5. 在 [**群組原則管理編輯器**] 中, 展開 [**使用者**設定], 展開 [**喜好**設定], 展開**** [ **Windows 設定**], 然後選取 [登錄] 節點。
    
6. 以滑鼠右鍵按一下 [ **** 登錄] 節點, 然後選取 [**新增** > **註冊專案**]。
    
7. 在 [**新增登錄屬性**] 對話方塊中, 更新下列專案:
    
   |**域**|**要選取或輸入的值**|
   |:-----|:-----|
   |**執行** <br/> |**建立** <br/> |
   |**一兩** <br/> | HKEY_CURRENT_USER <br/> |
   |**索引鍵路徑** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**值名稱** <br/> |EnableSkypeUI  <br/> |
   |**數值型別** <br/> |REG_BINARY  <br/> |
   |**值資料** <br/> |00000000  <br/> |
   
8. 按一下 **[確定]** 儲存變更, 然後關閉該 GPO。
    
接著, 您必須將您所建立的 GPO 連結至您要指派原則的使用者群組 (例如 OU)。
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>使用 GPO 指派原則

1. 在 [群組原則管理主控台] 中, 以滑鼠右鍵按一下您要指派原則的 OU, 然後選取 [**連結到現有的 GPO**]。
    
2. 在 [**選取 gpo** ] 對話方塊中, 選取您所建立的 GPO, 然後選取 **[確定]**。
    
3. 在目標使用者的電腦上, 開啟命令提示字元, 然後輸入下列命令:
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. 在命令提示字元中, 輸入下列命令:
    
    **gpresult/r**
    
    您應該會看到「指派的群群組原則物件」與您所建立之 GPO 的名稱, 如下所示。
    
您也可以檢查登錄, 以驗證 GPO 是否已在使用者的電腦上成功更新登錄。 開啟 [登錄編輯程式], 然後流覽至 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 索引鍵。 如果 GPO 成功更新了註冊表, 您會看到一個名為 EnableSkypeUI 的值, 其值為0。
  

