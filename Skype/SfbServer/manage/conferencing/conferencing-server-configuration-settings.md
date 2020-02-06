---
title: 在商務用 Skype Server 中管理會議服務器配置設定
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議服務器配置設定。
ms.openlocfilehash: c43734a2d79bf07023486eb163fff7bbef56e73f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818634"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議服務器配置設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中管理會議服務器配置設定。
  
本主題說明如何管理會議配置設定。 如需如何規劃及部署會議的詳細資訊，請參閱[在商務用 Skype server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md)，以及[在商務用 Skype 伺服器中部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
會議設定設定會決定會議內容和講義的允許大小上限等專案，應用程式共用會議服務的頻寬最大使用量;儲存空間限制與到期期;受支援之用戶端內部和外部下載的 Url;使用者可取得會議說明和資源之內部和外部 Url 的指標;以及用於應用程式共用、用戶端音訊、檔案傳輸及媒體流量的埠。 這些設定可讓您管理實際的伺服器本身。 您可以使用商務用 Skype Server Management Shell 來設定這些設定。
  
當您安裝商務用 Skype Server 時，系統會為您提供單一的會議配置設定集合（全域集合）。 如果您需要建立網站或服務的自訂設定，您可以使用**CsConferencingConfiguration** Cmdlet 來執行此動作。 請注意，新設定只能在網站或服務範圍內套用;您無法建立新的會議設定全域集合，但您可以使用**CsConferencingConfiguration** Cmdlet 來修改全域集合。 此外，任何網站或服務都不能裝載一個以上的設定集合。 如果您嘗試為雷德蒙的網站建立新的設定，而雷德蒙的網站已經託管會議設定的集合，則您的命令將會失敗。
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 管理會議配置設定

若要使用商務用 Skype Server Management Shell 管理會議配置設定，請使用下列 Cmdlet：
  
**會議配置設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |傳回貴組織會議配置設定的相關資訊。  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |建立新的會議配置設定集合。  <br/> |
|[移除-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |移除指定的會議配置設定集合。  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改現有的會議配置設定集合。  <br/> |
   
下列命令會針對雷德蒙網站（網站：雷蒙德）建立新的會議配置設定集合。 在這個範例中，包含一個額外的參數（組織），用來將組織屬性的值設定為 Litwareinc： 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

請注意，每個網站只能有一個此類集合，所以如果雷德蒙者網站已有會議設定的集合，此命令就會失敗。 
  
下一個範例定義了新的會議配置設定集合，這些設定會先儲存在記憶體中，然後再套用到雷德蒙網站。 
  
第一個命令使用**CsConferencingConfiguration** Cmdlet 來建立一個新的記憶體內集合，這些設定會儲存在變數 $x 中。 InMemory 參數指定應該在記憶體中建立集合，而不會立即套用到雷德蒙的網站。
  
建立集合之後，第二個命令會將 [組織] 屬性的值設定為 [Litwareinc]。 
  
最後，第三個命令使用**CsConferencingConfiguration** Cmdlet，以實際將新設定套用至雷德蒙網站：
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

如果您沒有呼叫**CsConferencingConfiguration** Cmdlet，新設定就不會生效。 相反地，當您結束 Windows PowerShell 會話或刪除變數 $x，它們就會消失。
  

