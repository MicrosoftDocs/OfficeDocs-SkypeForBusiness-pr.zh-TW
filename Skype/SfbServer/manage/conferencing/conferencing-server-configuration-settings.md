---
title: 在商務用 Skype Server 中管理會議服務器配置設定
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議服務器設定設定。
ms.openlocfilehash: 2175b1bc66425b98ade2a421a3f3cb477856ffb240bd835646164bc85dd668d8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341888"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議服務器配置設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中管理會議服務器配置設定。
  
本主題說明如何管理會議配置設定。 如需如何規劃及部署會議的詳細資訊，請參閱[商務用 Skype Server 中的會議計畫](../../plan-your-deployment/conferencing/conferencing.md)商務用 Skype Server 中的[部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
會議配置設定會決定會議內容和講義的允許大小上限等專案;應用程式共用會議服務的最大頻寬量;儲存量限制和到期期限;支援之用戶端的內部及外部下載的 URLs;指向內部和外部 URLs 的指標，使用者可以在其中取得會議説明和資源;以及用來進行應用程式共用、用戶端音訊、檔案傳輸和媒體流量的埠。 這些設定可讓您自行管理實際的伺服器。 您可以使用商務用 Skype Server 管理命令介面來設定這些設定。
  
當您安裝商務用 Skype Server 時，系統會在全域集合)  (提供單一的會議配置設定集合。 如果您需要為網站或服務建立自訂設定，您可以使用 **New-CsConferencingConfiguration** Cmdlet 來執行。 請注意，新設定只能在網站或服務範圍上套用;您無法建立新的會議設定全域集合，但您可以使用 **Set-CsConferencingConfiguration** Cmdlet 修改全域集合。 此外，任何網站或服務都不能裝載多個設定集合。 如果您嘗試為 Redmond 網站建立新的設定，而 Redmond 網站已裝載會議設定的集合，則此命令會失敗。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面管理會議配置設定

若要使用商務用 Skype Server 管理命令介面來管理會議配置設定，請使用下列 Cmdlet：
  
**會議配置設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |傳回組織的會議設定設定資訊。  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |會建立新的會議配置設定集合。  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |移除指定的會議配置設定集合。  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改現有會議配置設定的集合。  <br/> |
   
下列命令會為 Redmond 網站 (site： Redmond) 建立新的會議配置設定集合。 在此範例中，會包含另一個參數 (組織) 用以將組織屬性值設定為 Litwareinc： 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

請注意，每個網站只能有一個這類集合，所以如果 Redmond 網站已具備會議設定的集合，則此命令會失敗。 
  
下一個範例會定義新的會議設定的集合，這些設定會在最初儲存于記憶體中，然後再套用至 Redmond 網站。 
  
第一個命令會使用 **New-CsConferencingConfiguration** 指令程式，來建立新的記憶體集合，這些設定會儲存在變數 $x 中。 InMemory 參數會指定應該在記憶體中建立集合，而不會立即套用至 Redmond 網站。
  
建立集合之後，第二個命令會將組織關係屬性的值設定為 Litwareinc。 
  
最後，第三個命令會使用 **Set-CsConferencingConfiguration** Cmdlet，以實際將新設定套用至 Redmond 網站：
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

如果您未呼叫 **Set-CsConferencingConfiguration** Cmdlet，新設定永遠不會生效。 相反地，當您結束 Windows PowerShell 會話或刪除變數 $x 時，它們會立即消失。
