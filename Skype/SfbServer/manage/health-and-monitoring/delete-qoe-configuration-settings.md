---
title: 在商務用 Skype Server 中刪除經驗品質設定設定
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 摘要：瞭解如何刪除商務用 Skype Server 的經驗品質 (QoE) 設定。
---

# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除經驗品質設定設定
 
**總結：** 瞭解如何刪除商務用 Skype Server 的經驗品質 (QoE) 設定。
  
「經驗品質 (QoE)」計量在追蹤組織中進行之音訊和視訊通話的品質，包括遺失的網路封包數量、背景雜訊和「抖動」(封包延遲差異) 等項目的數量。這些計量會儲存在與其他資料 (例如詳細通話記錄) 不同的資料庫中，讓您可獨立於其他資料記錄來啟用和停用 QoE。
  
當您安裝商務用 Skype Server 時，會為您建立單一、全域 QoE 設定的集合。 系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。 根據設計，在網站範圍設定的設定會優先于在全域範圍設定的設定。 如果您刪除網站範圍的設定，則會使用通用設定在該網站中管理 QoE。
  
請注意，您也可以「刪除」全域設定。 不過，全域設定實際上不會被移除。 相反地，該集合中的所有屬性都會重設為預設值。 例如，預設會在 QoE 設定設定的集合中啟用清除。 假設您修改全域集合以停用清除。 如果您稍後刪除全域設定，所有屬性都會重設為其預設值。 在此情況下，這表示會再次啟用清除。
  
您可以使用商務用 Skype Server 控制台或使用[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)指令程式移除 QoE 設定設定。
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台刪除 QoE 配置設定

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。  
    
3. 在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。
    
4. 在 [ **經驗品質資料** ] 頁面上，按一下您要的原則，按一下 [ **編輯**]，然後按一下 [ **刪除**]。
    
5. 按一下 [確定]。
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 QoE 設定設定

您可以使用 Windows PowerShell 和 **Remove-CsQoEConfiguration** Cmdlet 刪除 QoE 的設定設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 商務用 Skype Server 中的程式相同。
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>移除指定的 QoE 配置設定集合

 此命令會移除套用至 Redmond 網站的 QoE 設定：
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 QoE 設定設定

 此命令會移除所有套用至網站範圍的 QoE 設定設定：
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>移除所有停用 QoE 監控的 QoE 設定設定

 這個命令會移除所有已停用 QoE 監控的 QoE 設定設定：
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

如需詳細資訊，請參閱 [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中手動清除詳細通話記錄與經驗品質資料庫](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)