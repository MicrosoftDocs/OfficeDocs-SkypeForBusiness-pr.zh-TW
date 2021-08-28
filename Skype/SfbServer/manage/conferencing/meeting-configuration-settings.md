---
title: 在商務用 Skype Server 中管理會議配置設定
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議配置設定。
ms.openlocfilehash: 14e84021e398308fe1b2d3d2187329c30dcb8412
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603922"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議配置設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中管理會議配置設定。
  
本主題說明如何管理會議配置設定。 如需如何規劃及部署會議的詳細資訊，請參閱[商務用 Skype Server 中的會議計畫](../../plan-your-deployment/conferencing/conferencing.md)商務用 Skype Server 中的[部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
會議設定設定會口述使用者可以建立的會議類型，除了控制 (，甚至) 匿名使用者和電話撥入式會議使用者是否可以加入這些會議。 請注意，這些設定只會影響排程的會議;它們不會影響在商務用 Skype 中按一下 [立即開會] 選項所建立的特定會議。
  
會議配置設定定義下列專案：
  
- 是否將以公用交換電話網路 (PSTN) 撥入的使用者帶到大廳
    
- 誰可以成為簡報者
    
- 是否依預設值指派會議類型
    
- 預設是否允許匿名 (未授權) 使用者加入
    
您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面來定義會議的特性。 
  
您可以指定預設) 、網站層級或集區層級所建立之全域層級 (的會議設定。 根據預設，全域設定會定義會議經驗。 如果您建立集區層級設定，這些設定會套用至該集區所主控的所有會議。 如果您未建立集區層級設定，則會套用網站層級設定（如果有的話）。 如果您未定義網站層級設定，全域設定會套用至所有會議。
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台管理會議設定

若要使用商務用 Skype Server 控制台管理會議設定：
  
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面管理會議設定

若要使用商務用 Skype Server 管理命令介面來管理會議，請使用下列 Cmdlet：
  
**會議組態設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |會傳回組織中目前使用之會議設定設定的相關資訊。  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在網站或服務範圍建立新的會議組態設定集合。  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |會刪除現有的會議配置設定集合。  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改組織中目前使用的會議設定設定。  <br/> |
