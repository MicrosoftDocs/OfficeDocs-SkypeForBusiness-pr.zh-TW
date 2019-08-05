---
title: 在商務用 Skype Server 中刪除經驗的設定品質設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '摘要: 瞭解如何在商務用 Skype Server 中刪除 [經驗品質 (QoE)] 設定。'
ms.openlocfilehash: 4b521afd85a97550b27f320b9e49c5439e431681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193752"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除經驗的設定品質設定
 
**摘要:** 瞭解如何在商務用 Skype Server 中刪除體驗品質 (QoE) 設定。
  
經驗品質 (QoE) 度量單位會追蹤您組織中的音訊和視頻通話品質, 包括網路資料包遺失、背景雜色及「抖動」 (資料包延遲的差異) 的數量。 這些度量單位會與其他資料 (例如通話明細記錄) 之外, 儲存在資料庫中, 讓您可以啟用和停用與其他資料錄製無關的 QoE。
  
當您安裝商務用 Skype Server 時, 系統會為您建立單一、全域的 QoE 配置設定集合。 系統管理員也可以選擇建立可套用至個別網站的自訂設定集合。 根據設計, 在網站範圍設定的設定會優先于在全域範圍中設定的設定。 如果您刪除網站範圍的設定, 就會使用全域設定在該網站中管理 QoE。
  
請注意, 您也可以 [刪除] 全域設定。 不過, 全域設定將不會實際移除。 相反地, 該集合中的所有屬性都會重設為預設值。 例如, 在 QoE 配置設定的集合中啟用 [清除]。 假設您修改全域集合, 以便停用清除功能。 如果您稍後刪除全域設定, 所有屬性都將會重設為預設值。 在這種情況下, 這表示清除會再次啟用。
  
您可以使用商務用 Skype Server 的 [控制台] 或 [ [remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) ] Cmdlet 來移除 QoE 設定設定。
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 的 [控制台] 刪除 QoE 配置設定

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊, 請參閱**委派設定許可權**。
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中, 按一下 [**監視及**封存], 然後按一下 [**體驗資料品質**]。
    
4. 在 [**體驗品質資料**] 頁面上, 按一下您要的原則, 按一下 [**編輯**], 然後按一下 [**刪除**]。
    
5. 按一下 [確定]****。
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 QoE 配置設定

您可以使用 Windows PowerShell 和**Remove-CsQoEConfiguration** Cmdlet 來刪除 QoE 設定設定。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中, 程式是一樣的。
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>移除指定的 QoE 配置設定集合

 這個命令會移除套用至雷德蒙網站的 QoE 設定設定:
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 QoE 設定設定

 這個命令會移除所有套用至網站範圍的 QoE 設定:
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>若要移除 QoE 監視功能停用的所有 QoE 設定設定

 這個命令會移除已停用 QoE 監視的所有 QoE 設定設定:
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

如需詳細資訊, 請參閱[移除-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中手動清除通話詳細資料錄製和體驗資料庫品質](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

