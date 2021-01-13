---
title: 管理商務用 Skype Server 中的封存選項
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 摘要：瞭解如何設定商務用 Skype Server 的封存選項。
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817533"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>管理商務用 Skype Server 中的封存選項

**摘要：** 瞭解如何設定商務用 Skype Server 的封存選項。
  
您最初在部署時設定封存，但是您可以在部署後變更、新增和刪除設定。 封存選項會決定是否要： 
  
- 啟用或停用封存
    
- 封存 IM 工作階段
    
- 封存 web 會議會話
    
- 封存無法使用時封鎖活動
    
- 使用 Exchange 整合
    
- 設定資料的清除和匯出
    
您可以在下列層級指定設定選項：
  
- 當您部署商務用 Skype Server 時，預設會建立全域層級設定
    
- 選用的網站層級設定，指定如何為特定網站實施封存
    
- 選用集區層級設定，指定如何為特定集區實施封存
    
您可以刪除網站設定或集區設定，但無法刪除全域設定。 如果您刪除全域設定，它會自動重設為預設值。 如需如何執行封存設定與封存設定階層的詳細資訊，請參閱 [在商務用 Skype Server 中規劃](../../plan-your-deployment/archiving/archiving.md)封存。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>使用控制台設定封存選項

您可以使用 [控制台] 設定封存選項，如下所示：
  
1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 
    
3. 在左導覽列中 **，按一下 [** 封存設定]。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>使用 Windows PowerShell 設定封存選項

您也可以使用下表所列的 Windows PowerShell Cmdlet 來設定封存選項。 如需語法的詳細資訊（包括所有可用參數），請參閱 [商務用 Skype Server 管理命令](../management-shell.md)介面。
  

|**指令程式**|**描述**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |傳回組織中封存設定設定的相關資訊。  <br/> |
|New-CsArchivingConfiguration  <br/> |會建立一組新的立即訊息 (IM) 設定，可用來啟用或停用自動儲存 IM 會話，並封鎖任何無法封存的立即訊息。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |移除指定的封存設定集合，用來啟用或停用自動儲存立即訊息 (IM) 會話，並選擇性地封鎖無法封存的任何立即訊息。  <br/> |
|Set-CsArchivingConfiguration  <br/> |修改現有的立即訊息 (IM 集合) 封存設定選項。  <br/> |
