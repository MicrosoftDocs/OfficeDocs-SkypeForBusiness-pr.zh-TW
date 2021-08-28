---
title: 在商務用 Skype Server 中查看 CDR 設定資訊
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 摘要：瞭解如何在商務用 Skype Server 中使用 (CDR) 上的詳細通話記錄。
ms.openlocfilehash: 8bd8ef54510a7353d39735b587d1e1a2a1373fe3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586905"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看 CDR 設定資訊
 
**摘要：** 瞭解如何在商務用 Skype Server 中使用 (CDR) 的詳細通話記錄。
  
詳細通話記錄 (CDR) 讓您能夠追蹤點對點即時訊息工作階段、Voice over Internet Protocol (VoIP) 電話通話，以及會議通話之類的使用狀況。這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。
  
當您安裝商務用 Skype Server 時，會為您建立單一、全域的 CDR 配置設定集合。 系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。 您可以使用商務用 Skype Server 控制台] 或[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) Cmdlet 來查看組織中所使用的 CDR 設定設定。
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台來查看 CDR 設定資訊

1. 在商務用 Skype Server 控制台中，按一下 [**監視與** 封存]。
    
2. 您所有 CDR 組態設定的清單將在 **[詳細通話記錄]** 索引標籤中顯示；在每一個設定集合中，您將會看到 **[名稱]** 集合；無論是否啟用 CDR (**CDR** 屬性)；無論是否啟用清除 (**CDR purging** 屬性)。若要檢視有關集合的詳細資訊，請在該集合按兩下滑鼠，或選取合適的集合，按一下 **[編輯]**，然後按一下 **[顯示詳細資訊]**。請記住，您一次只能檢視單一 CDR 組態設定集合的詳細資訊。
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 CDR 設定資訊

您可以使用 Windows PowerShell 和 Get-CsCdrConfiguration Cmdlet 來查看 CDR 設定設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 商務用 Skype Server 中的程式相同。
  
### <a name="to-view-cdr-configuration-information"></a>檢視 CDR 組態資訊

- 若要查看所有 CDR 設定設定的資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 enter：
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    如此將傳回類似如下的資訊：
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

如需詳細資訊，請參閱 [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。
