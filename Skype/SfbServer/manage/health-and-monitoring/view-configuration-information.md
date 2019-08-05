---
title: 在商務用 Skype Server 中查看 CDR 配置資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '摘要: 瞭解如何在商務用 Skype Server 中使用通話詳細資料錄製 (CDR)。'
ms.openlocfilehash: e0aed0c26672b83cb223ba763eb6224025d68118
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188623"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看 CDR 配置資訊
 
**摘要:** 瞭解如何在商務用 Skype Server 中使用通話詳細資料錄製 (CDR)。
  
通話詳細資料錄製 (CDR) 可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定 (VoIP) 電話撥打電話及會議呼叫等專案的使用方式。 此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。
  
當您安裝商務用 Skype Server 時, 系統會為您建立單一、全域的 CDR 配置設定。 系統管理員也可以選擇建立可套用至個別網站的自訂設定集合。 您可以使用商務用 Skype Server [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) Cmdlet 來查看貴組織中使用的 CDR 設定設定。
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 來查看 CDR 配置資訊

1. 在商務用 Skype Server 的 [控制台] 中, 按一下 [**監視及**封存]。
    
2. [**通話詳細資料記錄**] 索引標籤中會顯示所有 CDR 設定設定的清單;針對每個設定集合, 您會看到集合**名稱**;是否已啟用 CDR ( **cdr**屬性);以及是否已啟用清除 ( **CDR 清除**屬性)。 若要查看集合的詳細資訊, 請按兩下該集合, 或選取適當的集合, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。 請注意, 您一次只能針對單一的 CDR 配置設定集合查看詳細資訊。
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 CDR 配置資訊

您可以使用 Windows PowerShell 和 CsCdrConfiguration Cmdlet 來查看 CDR 配置設定。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中, 程式是一樣的。
  
### <a name="to-view-cdr-configuration-information"></a>若要查看 CDR 配置資訊

- 若要查看所有 CDR 配置設定的相關資訊, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER:
    
  ```
  Get-CsCdrConfiguration
  ```

    這會傳回如下所示的資訊:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

如需詳細資訊, 請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。
  

