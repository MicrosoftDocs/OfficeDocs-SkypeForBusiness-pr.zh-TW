---
title: 使用商務用 Skype 2015 設定用戶端體驗
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 摘要：閱讀此主題以瞭解如何設定商務用 Skype 使用者的用戶端體驗。
ms.openlocfilehash: 4ad311917ef868a8eea55fab88e7aad6dd854dfe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772684"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>使用商務用 Skype 2015 設定用戶端體驗
 
**摘要：** 閱讀此主題以瞭解如何設定商務用 Skype 2015 使用者的用戶端經驗。
  
商務用 Skype 2015 提供以 Skype 使用者產品經驗為基礎的新使用者體驗。 除了 Lync 的所有功能之外，商務用 Skype 還會以簡化的控制項及熟悉的圖示來提供新功能。 如需有關新用戶端體驗的詳細資訊，請參閱[探索商務用 Skype](https://go.microsoft.com/fwlink/?LinkId=529022)。
  
商務用 Skype Server 支援新的商務用 Skype 用戶端經驗，以及 Lync 用戶端體驗。 身為管理員，您可以為使用者選擇喜歡的用戶端體驗。 例如，您可能想要部署 Lync 用戶端體驗，直到貴組織中的使用者已完全訓練新的商務用 Skype 體驗。 或者，如果您尚未將所有使用者升級為商務用 Skype Server，您可能會想要讓所有的使用者都有相同的用戶端體驗，直到全部使用者都升級至新伺服器為止。
  
> [!IMPORTANT]
> 如果您的組織同時部署商務用 Skype Server 和 Lync 伺服器，則預設的用戶端經驗會因伺服器版本和使用者介面設定而異。 當使用者第一次啟動商務用 Skype 時，他們會永遠看到商務用 Skype 使用者介面，即使您已選取 Lync 用戶端經驗也是一樣。 幾分鐘後，系統會要求使用者切換至 Lync 模式。 如需詳細資訊，請參閱本主題稍後的 **第一次啟動用戶端行為** 。
  
> [!NOTE]
> Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本或更新版本的選項。 在您嘗試設定用戶端環境以使用 Lync 2013 用戶端之前，請檢查用戶端版本，以確保其不是以數位16開頭;例如： x.x.x。 
  
## <a name="configure-the-client-experience"></a>設定用戶端體驗

您可以使用 **Set-CSClientPolicy** Cmdlet 搭配 EnableSkypeUI 參數，指定您組織中的使用者所看到的用戶端體驗：
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

其中 Microsoft.rtc.management.xds.xdsidentity 指的是全域原則或已命名的網站原則。
  
下列命令會為組織中的所有使用者選取受全域原則影響的商務用 Skype 用戶端體驗 (記住、網站或使用者特定原則會覆寫全域原則) ： 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

下一個命令會為組織中的所有使用者選取受全域原則影響的 Lync 用戶端體驗：
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

下一個命令會為 Redmond 網站內的所有使用者選取商務用 Skype 用戶端體驗：
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

如果您想要為組織內的特定使用者設定用戶端經驗，您可以使用 **New-CsClientPolicy** Cmdlet 來建立新的使用者原則，然後使用 **Grant-CsClientPolicy** Cmdlet 將原則指派給特定使用者。
  
例如，下列命令會建立新的用戶端原則 SalesClientUI，以選取商務用 Skype 用戶端體驗：
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

下一個命令會將原則 SalesClientUI 指派給銷售部門的所有成員：
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>第一次啟動用戶端行為

根據預設，當使用者第一次啟動商務用 Skype 2015 時，他們會永遠看到商務用 Skype 使用者介面--即使您已透過將 EnableSkypeUI 參數的值設定為 $False （如先前所述），您已選取 Lync 用戶端經驗。 幾分鐘後，系統會要求使用者切換至 Lync 模式。
  
當使用者第一次啟動商務用 Skype 用戶端時，如果您想要顯示 Lync 使用者介面，請在用戶端第一次更新後的第一次啟動之前，執行下列步驟：
  
1. 確認的值  `EnableSkypeUI` 已設定為在您使用的原則中 $False，如先前所述。
    
2. 更新使用者電腦上的系統登錄。 您應該在使用者第一次啟動商務用 Skype 用戶端之前執行此作業，您應該只執行一次。 如需如何建立群組原則物件以更新加入網域之電腦上之登錄的詳細資訊，請參閱本主題稍後的章節。
    
    在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 機碼中，建立新的 **二進位** 值。
    
    **值名稱** 必須是 **EnableSkypeUI**，且 **數值資料** 必須設定為 **00 00 00 00**。
    
    索引鍵應該如下所示：
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

當使用者第一次啟動商務用 Skype 用戶端時，即會顯示 Lync 使用者介面。
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制歡迎使用畫面教學課程的顯示

當使用者開啟商務用 Skype 用戶端時，預設行為是顯示歡迎畫面，其中包含 *大多數人員所要求的7個快速秘訣*。 您可以在用戶端電腦上新增下列登錄值，關閉 [歡迎] 畫面，但仍允許使用者存取教學課程：
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 機碼中，建立新的 **DWORD (32-bit) 值**。 **值名稱** 必須是 **IsBasicTutorialSeenByUser**，且 **數值資料** 必須設定為 **1**。
  
索引鍵應該如下所示：
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>關閉用戶端教學課程

如果您不想讓使用者能夠存取教學課程，您可以使用下列登錄值來關閉用戶端教學課程：
  
在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 機碼中，建立新的 **DWORD (32-bit) 值**。 **值名稱** 必須是 **TutorialFeatureEnabled**，且 **數值資料** 必須設定為 **0**。
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

您可以將 **數值資料** 設為 **1**，以重新開啟教學課程。
  
## <a name="default-client-behaviors"></a>預設用戶端行為

如果您的組織同時部署了商務用 Skype Server 和 Lync 伺服器，則用戶端經驗會因伺服器版本和 Skype 使用者介面設定而有所不同。 下表顯示以伺服器版本及 UI 設定為基礎的初始用戶端體驗：
  

|**伺服器版本**|**EnableSkypeUI 設定**|**用戶端經驗**|
|:-----|:-----|:-----|
|商務用 Skype Server |預設  <br/> |商務用 Skype  <br/> |
|商務用 Skype Server  |True  <br/> |商務用 Skype  <br/> |
|商務用 Skype Server  |錯  <br/> |使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true 時，切換至商務用 Skype)   <br/> |
|使用正確修補程式的 lync Server 2010 或 Lync Server 2013 ()   <br/> |預設  <br/> |使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true 時，切換至商務用 Skype)   <br/> |
|使用正確修補程式的 lync Server 2010 或 Lync Server 2013 ()   <br/> |True  <br/> |商務用 Skype  <br/> |
|使用正確修補程式的 lync Server 2010 或 Lync Server 2013 ()   <br/> |錯  <br/> |使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true 時，切換至商務用 Skype)   <br/> |
|不含修補程式的 lync Server 2010 或 Lync Server 2013 ()   <br/> |預設  <br/> |使用者要求切換至 Lync 模式 (使用者無法在稍後切換商務用 Skype)   <br/> |
   
下表顯示管理員變更 Skype UI 體驗的初始設定時，用戶端的體驗：
  

|**伺服器版本**|**EnableSkypeUI 設定**|**用戶端 UI = Lync**|**用戶端 UI = 商務用 Skype**|
|:-----|:-----|:-----|:-----|
|商務用 Skype Server |True  <br/> |使用者要求切換至商務用 Skype  <br/> |商務用 Skype  <br/> |
|商務用 Skype Server |錯  <br/> |Lync 模式  <br/> |使用者要求切換至 Lync 模式  <br/> |
|使用正確修補程式的 lync Server 2010 或 Lync Server 2013 ()   <br/> |True  <br/> |使用者要求切換至商務用 Skype  <br/> |商務用 Skype  <br/> |
|使用正確修補程式的 lync Server 2010 或 Lync Server 2013 ()   <br/> |錯  <br/> |Lync 模式  <br/> |使用者要求切換至 Lync 模式  <br/> |
|不含修補程式的 lync Server 2010 或 Lync Server 2013 ()   <br/> |預設  <br/> |Lync 模式 (無法切換成商務用 Skype)   <br/> |Lync 模式 (無法切換成商務用 Skype)   <br/> |
   
管理商務用 Skype 用戶端設定所需的修補程式版本如下：
  
- Lync Server 2010-2 月2015累積更新 (4.0.7577.710) 的 Lync Server 2010。 如需詳細資訊，請參閱 [Lync Server 2010 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-Lync Server 2013 的2014累計更新 (5.0.8308.857) 。 如需詳細資訊，請參閱 [Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>建立群組原則物件以在加入網域的電腦上修改登錄

當使用者第一次啟動商務用 Skype 2015 用戶端時，要顯示 Lync 用戶端經驗的登錄更新，應只執行一次。 如果您使用群組原則物件 (GPO) 來更新登錄，您必須定義物件來建立新的值，而不是更新值資料。 套用 GPO 時，如果新值不存在，GPO 將會建立它，並將數值資料設定為0。 
  
下列程式說明如何修改登錄，讓使用者第一次啟動商務用 Skype 2015 用戶端時，就會顯示 Lync 用戶端體驗。 您也可以使用此程式來更新登錄，以停用先前所述的歡迎畫面教學課程。
  
### <a name="to-create-the-gpo"></a>建立 GPO

1. 啟動 [ **群組原則管理主控台**]。
    
    如需如何使用「群組原則管理主控台」的詳細資訊，請參閱 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))。
    
2. 在 [ **群組原則物件** ] 節點上按一下滑鼠右鍵，然後在功能表上選取 [ **新增** ]。
    
3. 在 [ **新增 gpo** ] 對話方塊中，輸入 GPO 的名稱，例如 [MakeLyncDefaultUI]，然後按一下 **[確定]**。
    
4. 在您剛才建立的新 GPO 上按一下滑鼠右鍵，然後從功能表中選取 [ **編輯** ]。
    
5. 在 [**群組原則管理編輯器**] 中，展開 [**使用者** 設定]，展開 [**喜好** 設定]，展開 **Windows 設定**]，然後選取 **登錄節點。**
    
6. **在 [登錄**] 節點上按一下滑鼠右鍵，然後選取 [**新增** 登錄  >  **專案**]。
    
7. 在 [ **新增註冊表屬性** ] 對話方塊中，更新下列專案：
    
   |**Field**|**要選取或輸入的值**|
   |:-----|:-----|
   |**動作** <br/> |**Create** <br/> |
   |**蜂巢** <br/> | HKEY_CURRENT_USER <br/> |
   |**機碼路徑** <br/> |Software\Microsoft\ Office \Lync  <br/> |
   |**Value name** <br/> |EnableSkypeUI  <br/> |
   |**Value type** <br/> |REG_BINARY  <br/> |
   |**值資料** <br/> |00000000  <br/> |
   
8. 按一下 **[確定]** 以儲存變更，然後關閉 GPO。
    
接下來，您必須將您建立的 GPO 連結至您要指派原則的使用者群組，例如 OU。
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>若要使用 GPO 指派原則

1. 在 [群組原則管理主控台] 中，以滑鼠右鍵按一下您要指派原則的 OU，然後選取 [ **連結到現有的 GPO**]。
    
2. 在 [ **選取 gpo** ] 對話方塊中，選取您建立的 GPO，然後選取 **[確定**]。
    
3. 在目標使用者的電腦上，開啟命令提示字元，並輸入下列命令：
       
   ```console
   pupdate /target:user
   ```
     郵件「更新原則 ...」會在應用 GPO 時顯示。 完成後，就會顯示「已成功完成使用者原則更新」郵件。
    
4. 在命令提示字元處，輸入下列命令：
    
    **gpresult/r**
    
    您應該會看到 "指派的群組原則物件"，具有您在下方所建立的 GPO 名稱。
    
您也可以檢查登錄，以確認 GPO 是否已成功更新使用者電腦上的登錄。 開啟 [登錄編輯程式]，然後流覽至 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 機碼。 如果 GPO 成功更新登錄，您將會看到名為 EnableSkypeUI 的值，其值為0。
