---
title: 在商務用 Skype Server 中管理存檔選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '摘要: 瞭解如何設定商務用 Skype Server 的存檔選項。'
ms.openlocfilehash: c7353c305125e8e35523c573150471821f53301e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188221"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>在商務用 Skype Server 中管理存檔選項

**摘要:** 瞭解如何設定商務用 Skype Server 的存檔選項。
  
您最初是在部署期間設定封存, 但是您可以在部署之後變更、新增及刪除設定。 [封存選項] 可決定是否要: 
  
- 啟用或停用封存功能
    
- 封存 IM 工作階段
    
- 封存網路會議會話
    
- 存檔無法使用時封鎖活動
    
- 使用 Exchange 整合
    
- 設定清除及匯出資料
    
您可以在下列層面指定配置選項:
  
- 部署商務用 Skype Server 時預設建立的全域層級設定
    
- 選擇性網站層級設定, 指定如何針對特定網站執行歸檔
    
- 指定如何針對特定的資料庫池實施歸檔的選用池層級設定
    
您可以刪除網站配置或池設定, 但無法刪除全域設定。 如果您刪除全域設定, 系統會自動將其重設為預設值。 如需如何實施封存配置以及歸檔設定的階層的詳細資料, 請參閱[在商務用 Skype 伺服器中規劃](../../plan-your-deployment/archiving/archiving.md)封存。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>使用 [控制台] 設定存檔選項

您可以使用 [控制台] 來設定封存選項, 如下所示:
  
1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中, 按一下 [封存**配置**]。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>使用 Windows PowerShell 設定封存選項

您也可以使用下表所列的 Windows PowerShell Cmdlet 來設定封存選項。 如需語法的詳細資料 (包括所有可用的參數), 請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。
  

|**Cmdlet**|**說明**|
|:-----|:-----|
|CsArchivingConfiguration  <br/> |傳回貴組織中的存檔設定設定的相關資訊。  <br/> |
|新-CsArchivingConfiguration  <br/> |建立一組新的立即訊息 (IM) 設定, 這可以用來啟用或停用自動儲存 IM 會話, 並封鎖任何無法封存的立即訊息。  <br/> |
|移除-CsArchivingConfiguration  <br/> |移除指定的存檔設定集合, 這些設定是用來啟用或停用立即訊息 (IM) 會話, 以及選擇性地封鎖任何無法封存的立即訊息。  <br/> |
|Set-CsArchivingConfiguration  <br/> |修改現有的立即訊息 (IM) 封存配置選項組合。  <br/> |
