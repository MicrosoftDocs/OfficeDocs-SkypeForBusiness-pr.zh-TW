---
title: 在商務用 Skype Server 中管理存檔原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要：瞭解如何管理適用于商務用 Skype Server 的存檔的使用者原則。
ms.openlocfilehash: f2dca47dd7fd3095b2865ff72516b6be84144352
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818885"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中管理存檔原則

**摘要：** 瞭解如何管理適用于商務用 Skype Server 的存檔的使用者原則。
  
您最初是在部署封存時設定封存原則，但是您可以在部署之後變更、新增及刪除設定。 存檔原則決定是否要封存： 
  
- 內部通訊
    
- 外部通訊
    
您可以在全域、網站或使用者層級設定歸檔原則。
  
> [!NOTE]
> 如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否針對駐留在 Exchange 的使用者啟用封存，並將其信箱放在就地保留中。 如需詳細資訊，請參閱[在商務用 Skype server 中進行](../../plan-your-deployment/archiving/archiving.md)封存的規劃，以及[設定與商務用 Skype server 的 Exchange 儲存體整合](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>使用 [控制台] 管理歸檔原則

您可以使用 [控制台] 管理存檔原則，如下所示：
  
1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [封存**原則**]
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>使用 Windows PowerShell 管理存檔原則

您也可以使用下表所列的 Windows PowerShell Cmdlet 來設定歸檔原則。 如需語法的詳細資料（包括所有可用的參數），請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。
  

|**Cmdlet**|**說明**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |傳回貴組織的立即訊息（IM）會話存檔原則的相關資訊。  <br/> |
|授與 CsArchivingPolicy  <br/> |將立即訊息（IM）會話存檔原則指派給使用者或使用者組。 這些原則可讓您封存在內部使用者之間進行的所有 IM 會話，以及/或封存在內部使用者與外部合作夥伴之間發生的所有 IM 會話。  <br/> |
|New-CsArchivingPolicy  <br/> |建立新的立即訊息（IM）會話存檔原則。 這些原則可讓您封存在內部使用者之間進行的所有 IM 會話，以及/或封存在內部使用者與外部合作夥伴之間發生的所有 IM 會話。  <br/> |
|Remove-CsArchivingPolicy  <br/> |移除指定的立即訊息（IM）封存原則，決定商務用 Skype 伺服器是否會自動儲存所有內部使用者之間發生的 IM 會話，以及/或內部使用者與同盟合作夥伴之間的所有 IM 會話。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改現有的立即訊息（IM）封存原則。 存檔原則可讓您將在內部使用者之間發生的所有 IM 會議與會議封存在一起。您也可以封存在內部使用者和聯盟夥伴之間發生的會話。  <br/> |
   

