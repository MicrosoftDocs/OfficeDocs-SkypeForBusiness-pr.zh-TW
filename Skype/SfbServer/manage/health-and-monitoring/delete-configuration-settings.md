---
title: 在商務用 Skype Server 中刪除現有的 CDR 配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: '摘要: 瞭解如何在商務用 Skype Server 中移除 CDR 配置設定。'
ms.openlocfilehash: 91ee9676b3087c5b125c6cfe935f706bbfb22812
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193753"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除現有的 CDR 配置設定集合
 
**摘要:** 瞭解如何在商務用 Skype Server 中移除 CDR 配置設定。
  
通話詳細資料錄製 (CDR) 可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定 (VoIP) 電話撥打電話及會議呼叫等專案的使用方式。 此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。
  
當您安裝商務用 Skype Server 時, 系統會為您建立單一、全域的 CDR 配置設定。 系統管理員也可以選擇建立可套用至個別網站的自訂設定集合。 根據設計, 在網站範圍設定的設定會優先于在全域範圍中設定的設定。 如果您刪除網站範圍的設定, 則會使用全域設定在該網站中管理 CDR。
  
請注意, 您也可以 [刪除] 全域設定。 不過, 全域設定將不會實際移除。 相反地, 該集合中的所有屬性都會重設為預設值。 例如, 在 CDR 配置設定的集合中啟用 [清除]。 假設您修改全域集合, 以便停用清除功能。 如果您稍後刪除全域設定, 所有屬性都將會重設為預設值。 在這種情況下, 這表示清除會再次啟用。
  
您可以使用商務用 Skype Server 的 [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) Cmdlet 來移除 CDR 配置設定。
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>在商務用 Skype Server [控制台] 中移除 CDR 配置設定

1. 在商務用 Skype Server 的 [控制台] 中, 按一下 [**監視及**封存]。 
    
2. 在 [**通話詳細資料記錄**] 索引標籤上, 選取要移除的 CDR 設定的集合 (或 [收藏])。 若要選取多個收藏, 請按一下第一個收藏, 按住 Ctrl 鍵, 然後按一下 [其他集合]。
    
3. 按一下 [**編輯**], 然後按一下 [**刪除**]。
    
4. 在商務用 Skype Server [控制台] 對話方塊中, 按一下 **[確定]**。
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 CDR 配置設定

您可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來刪除通話詳細資料錄製設定設定。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中, 程式是一樣的。
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>移除指定的 CDR 配置設定集合

 這個命令會移除套用至雷德蒙網站的 CDR 設定設定:
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>移除套用至網站範圍的所有 CDR 設定設定

 這個命令會移除所有適用于網站範圍的 CDR 設定設定:
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>若要移除停用通話詳細資料錄製的所有 CDR 設定設定

 這個命令會移除已停用通話詳細資料錄製的所有 CDR 設定設定:
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

如需詳細資訊, 請參閱[Remove CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中手動清除通話詳細資料錄製和體驗資料庫品質](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

