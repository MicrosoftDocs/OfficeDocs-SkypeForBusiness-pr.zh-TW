---
title: 在商務用 Skype Server 中建立體驗配置設定品質
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 摘要：瞭解商務用 Skype Server 中的體驗品質（QoE）設定。
ms.openlocfilehash: 5366937f1faa01e6533b51677122713ee9e839fa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818033"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中建立體驗配置設定品質
 
**摘要：** 瞭解商務用 Skype Server 中的體驗品質（QoE）設定。
  
經驗品質（QoE）度量單位會追蹤您組織中的音訊和視頻通話品質，包括網路資料包遺失、背景雜色及「抖動」（資料包延遲的差異）的數量。 這些度量單位會與其他資料（例如通話明細記錄）之外，儲存在資料庫中，讓您可以啟用和停用與其他資料錄製無關的 QoE。
  
當您安裝商務用 Skype Server 時，系統會為您建立單一、全域的 QoE 配置設定集合。 系統管理員也可以選擇在網站範圍中建立自訂設定。 只要使用這些網站範圍的設定，就會優先于全域設定。 例如，如果您為雷德蒙的網站建立網站範圍的設定，則這些設定（而不是 [全域設定]）將會用於管理雷德蒙的 QoE。
  
您可以使用商務用 Skype Server 的 [控制台] 或[新的-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Cmdlet 來建立 QoE 設定設定。 如果您使用商務用 Skype Server 的 [控制台] 來建立新設定，您可以使用下列選項：
  
|**UI 設定**|**PowerShell 參數**|**說明**|
|:-----|:-----|:-----|
|名稱  <br/> |Identity  <br/> |要建立之設定的唯一識別碼。 QoE 設定只能在網站範圍建立。  <br/> |
|啟用監視 QoE 資料  <br/> |EnableQoE  <br/> |指定是否要收集 QoE 記錄並將它儲存到監視資料庫。  <br/> |
|啟用清除 QoE 資料  <br/> |EnablePurging  <br/> |指定是否要在 [保留 QoE 資料] 中定義的持續時間 **（天數）** 屬性已過久之後，才清除記錄。 <br/> |
|保留 QoE 資料以取得最長持續時間（天）  <br/> |KeepQoEDataForDays  <br/> |從資料庫清除 QoE 資料前要儲存的天數。 如果停用清除功能，就會忽略這個值。  <br/> |
   
> [!NOTE]
> CsQoEConfiguration Cmdlet 包含無法在商務用 Skype Server [控制台] 中使用的其他選項。 如需詳細資訊，請參閱[新的 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)說明主題。
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立 QoE 設定設定

1. 以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱**委派設定許可權**。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。
    
4. 在 [**體驗品質資料**] 頁面上，按一下 [**新增**]。
    
5. 在 [**選取網站**] 中，按一下要套用原則的網站，然後按一下 **[確定]**。
    
6. 在 [**新的體驗品質] 設定**中，請執行下列動作：
    
   - 選取 [**啟用 QoE 資料監視**] 來開啟監視。
    
   - 選取 [**啟用清除 QoE 資料**] 以開啟 [清除]。
    
   - 在 **[保留 QoE 的最大持續時間（天）**] 中，選取 QoE 記錄應保留的最大天數。
    
7. 按一下 [認可]****。
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立 QoE 配置設定

您可以使用 Windows PowerShell 和 CsQoEConfiguration Cmdlet 來建立 QoE 配置設定。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>若要建立新的 QoE 配置設定集合

 這個命令會建立套用至雷德蒙網站之 QoE 設定設定的新集合：
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>若要在停用 QoE 監視的情況下，建立新的 QoE 配置設定集合

 因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。 若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 例如，若要建立經驗品質設定的集合，請根據預設，允許停用 QoE 錄製使用如下所示的命令：
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>建立新的 QoE 配置設定集合時，指定多個屬性值

 您可以加入多個參數，以使用多個屬性值。 例如，這個命令會將新設定設為保留30天的 QoE 資料，並在 3:00 AM 清除舊資料：
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

如需詳細資訊，請參閱[新版-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Cmdlet 的說明主題。
  

