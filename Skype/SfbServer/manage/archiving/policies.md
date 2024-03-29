---
title: 管理商務用 Skype Server 中的封存原則
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 摘要：瞭解如何管理商務用 Skype Server 的封存的使用者原則。
ms.openlocfilehash: c4d5278ece9c812254c67d2d783b5a9f9175330c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397797"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>管理商務用 Skype Server 中的封存原則

**總結：** 瞭解如何管理商務用 Skype Server 的封存的使用者原則。
  
您在部署封存時，最初會設定封存原則，但您可以在部署後變更、新增和刪除設定。 封存原則決定是否要封存： 
  
- 內部通訊
    
- 外部通訊
    
您可以在全域、網站或使用者層級設定封存原則。
  
> [!NOTE]
> 如果您已對部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否為位於 Exchange 的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 如需詳細資訊，請參閱[Plan for 封存 in 商務用 Skype Server](../../plan-your-deployment/archiving/archiving.md)和[設定與 Exchange 儲存體搭配商務用 Skype Server 的整合](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>使用控制台管理封存原則

您可以使用 [控制台] 來管理封存原則，如下所示：
  
1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左導覽列中，按一下 [封存 **原則**]
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>使用 Windows PowerShell 管理封存原則

您也可以使用下表所列的 Windows PowerShell Cmdlet 來設定封存原則。 如需語法的詳細資料（包括所有可用參數），請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。
  

|**指令程式**|**描述**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |傳回組織的立即訊息 (IM) 會話封存原則的資訊。  <br/> |
|Grant-CsArchivingPolicy  <br/> |指派立即訊息 (IM) 會話封存原則指派給使用者或使用者組。 這些原則可讓您封存內部使用者之間及/或封存內部使用者與外部協力廠商之間所發生的所有 IM 工作階段。  <br/> |
|New-CsArchivingPolicy  <br/> |建立新的立即訊息 (IM) 會話封存原則。 這些原則可讓您封存內部使用者之間及/或封存內部使用者與外部協力廠商之間所發生的所有 IM 工作階段。  <br/> |
|Remove-CsArchivingPolicy  <br/> |會移除指定的立即訊息 (IM) 封存原則，此原則會決定商務用 Skype Server 是否會自動儲存內部使用者和/或內部使用者與同盟協力廠商之間所有 im 會話之間所發生的所有 im 會話。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改現有的立即訊息 (IM) 封存原則。 封存原則讓您能夠封存內部使用者之間所發生的所有 IM 會話和會議。您也可以封存在內部使用者與同盟協力廠商之間進行的會話。  <br/> |
   

