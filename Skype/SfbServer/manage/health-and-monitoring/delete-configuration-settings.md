---
title: 在商務用 Skype Server 中刪除現有 CDR 設定設定集合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 摘要：瞭解如何在商務用 Skype Server 中移除 CDR 配置設定。
ms.openlocfilehash: ad23743e6361a0931499c373e337bb9869738fa8e00d5d856ad272e96798655b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276818"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除現有 CDR 設定設定集合
 
**摘要：** 瞭解如何在商務用 Skype Server 中移除 CDR 配置設定。
  
詳細通話記錄 (CDR) 讓您能夠追蹤點對點即時訊息工作階段、Voice over Internet Protocol (VoIP) 電話通話，以及會議通話之類的使用狀況。這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。
  
當您安裝商務用 Skype Server 時，會為您建立單一、全域的 CDR 配置設定集合。 系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。 根據設計，在網站範圍設定的設定會優先于在全域範圍設定的設定。 如果您刪除網站範圍的設定，則會使用通用設定在該網站中管理 CDR。
  
請注意，您也可以「刪除」全域設定。 不過，全域設定實際上不會被移除。 相反地，該集合中的所有屬性都會重設為預設值。 例如，預設會在 CDR 設定設定的集合中啟用清除。 假設您修改全域集合以停用清除。 如果您稍後刪除全域設定，所有屬性都會重設為其預設值。 在此情況下，這表示會再次啟用清除。
  
您可以使用商務用 Skype Server 控制台] 或[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) Cmdlet 來移除 CDR 設定設定。
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台移除 CDR 設定設定

1. 在商務用 Skype Server 控制台] 中，按一下 [**監視與** 封存]。 
    
2. 在 [ **詳細通話記錄** ] 索引標籤上，選取要移除之 CDR 設定的集合 (或集合) 。 若要選取多個集合，請按一下第一個集合，按住 Ctrl 鍵，然後按一下 [其他集合]。
    
3. 按一下 [ **編輯**]，然後按一下 [ **刪除**]。
    
4. 在 [商務用 Skype Server 控制台] 對話方塊中，按一下 **[確定]**。
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 CDR 配置設定

您可以使用 Windows PowerShell 和 **Remove-CsCdrConfiguration** Cmdlet 來刪除詳細通話記錄設定設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 商務用 Skype Server 中的程式相同。
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>移除指定的 CDR 配置設定集合

 此命令會移除套用至 Redmond 網站的 CDR 設定設定：
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>移除所有套用至網站範圍的 CDR 設定設定

 此命令會移除所有套用至網站範圍的 CDR 設定設定：
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

如需詳細資訊，請參閱 [Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中手動清除詳細通話記錄與經驗品質資料庫](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)