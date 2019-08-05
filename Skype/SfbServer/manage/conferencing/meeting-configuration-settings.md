---
title: 在商務用 Skype Server 中管理會議設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: '摘要: 瞭解如何在商務用 Skype Server 中管理會議設定設定。'
ms.openlocfilehash: d9ed049fe4873428729149e1ea624bf715bb81ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189649"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議設定設定
 
**摘要:** 瞭解如何在商務用 Skype Server 中管理會議設定設定。
  
本主題說明如何管理會議設定。 如需如何規劃及部署會議的詳細資訊, 請參閱[在商務用 Skype server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md), 以及[在商務用 Skype 伺服器中部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
[會議設定] 設定決定使用者可以建立的會議類型, 除了控制匿名使用者和電話撥入式會議使用者是否可以加入這些會議。 請注意, 這些設定只會影響排程的會議;它們不會影響在商務用 Skype 中按一下 [立即開會] 選項所建立的即席會議。
  
會議設定設定會定義下列專案:
  
- 從公用交換電話網絡 (PSTN) 撥入的使用者是否會移至大廳
    
- 誰可以是簡報者
    
- 預設是否指派會議類型
    
- 預設是否承認匿名 (未經授權) 使用者
    
您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面來定義會議的特性。 
  
您可以指定全域層級的會議設定 (預設為建立)、網站層級或文件庫層級。 根據預設, 全域設定會定義會議體驗。 如果您建立了 [pool] 層級設定, 這些設定就會套用至該池子主持的所有會議。 如果您沒有建立池層級設定, 就會套用網站層級設定 (如果存在的話)。 如果您沒有定義網站層級設定, 全域設定就會套用至所有會議。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 管理會議設定

若要使用商務用 Skype Server [控制台] 管理會議設定, 請執行下列動作:
  
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [**會議配置**]。
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 管理會議設定

若要使用商務用 Skype Server Management Shell 管理會議, 請使用下列 Cmdlet:
  
**會議配置設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |傳回目前在貴組織中使用之會議配置設定的相關資訊。  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在網站或服務範圍建立新的會議配置設定集合。  <br/> |
|[移除-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |刪除現有的會議配置設定集合。  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改組織中目前使用的會議設定設定。  <br/> |
   

