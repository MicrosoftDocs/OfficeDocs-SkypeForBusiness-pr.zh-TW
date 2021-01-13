---
title: 管理商務用 Skype Server 中的封存
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要：瞭解如何管理商務用 Skype 伺服器的封存。
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817733"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>管理商務用 Skype Server 中的封存

**摘要：** 瞭解如何管理商務用 Skype Server 的封存。
  
當您為組織部署封存時，您會在部署期間指定初始設定。 不過，有時候您可能想要變更如何針對日常管理執行封存支援，或符合貴組織的新需求。 例如，您可能需要為特定網站、特定集區或組織內的特定使用者設定不同的封存支援。 針對駐留在商務用 Skype Server 的使用者，您可以建立及自訂封存設定選項和使用者原則，以執行此動作。 
  
閱讀本主題之前，請確定您已熟悉 [規劃商務用 Skype server](../../plan-your-deployment/archiving/archiving.md) 中的封存資訊，以及如何 [部署商務用 skype server](../../deploy/deploy-archiving/deploy-archiving.md)的封存。
  
> [!NOTE]
> 如果您為部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否為位於 Exchange 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 如需詳細資訊，請參閱 Plan for 封存 [In 商務用 Skype server](../../plan-your-deployment/archiving/archiving.md) 和 [設定與 Exchange storage 的整合（適用于商務用 skype 伺服器](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)）。 
  
## <a name="archiving-configuration-options"></a>封存設定選項

封存設定選項指定是否：
  
- 啟用或停用封存
    
- 封存 IM 工作階段
    
- 封存 web 會議會話
    
- 封存無法使用時封鎖活動
    
- 使用 Exchange 整合
    
- 設定資料的清除和匯出
    
您可以在全域、網站或集區層級設定這些選項。 如需詳細資訊，請參閱 [Manage 封存 options In 商務用 Skype Server](options.md)。
  
## <a name="archiving-policies"></a>封存原則

封存原則決定是否要封存下列專案：
  
- 內部通訊
    
- 外部通訊
    
您可以在全域、網站或使用者層級設定這些原則。 如需詳細資訊，請參閱 [在商務用 Skype Server 中管理封存原則](policies.md)。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>使用控制台或使用 Windows PowerShell 管理封存

您可以使用 [控制台] 或使用 Windows PowerShell 管理封存。 下表摘要說明可協助您管理封存的 Cmdlet。 如需語法的詳細資訊（包括所有可用參數），請參閱 [商務用 Skype Server 管理命令](../management-shell.md)介面。 


|**指令程式**|**描述**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |匯出已儲存在商務用 Skype Server 封存資料庫中的記錄。  <br/> |
|Get-CsArchivingConfiguration  <br/> |傳回組織中封存設定設定的相關資訊。  <br/> |
|Get-CsArchivingPolicy  <br/> |傳回組織內部和外部通訊的封存原則資訊。  <br/> |
|Grant-CsArchivingPolicy  <br/> |指派立即訊息 (IM) 會話封存原則指派給使用者或使用者組。 這些原則可讓您封存內部使用者之間及/或封存內部使用者與外部協力廠商之間所發生的所有 IM 工作階段。  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |手動清除封存資料庫中的記錄。  <br/> |
|New-CsArchivingConfiguration  <br/> |會建立一組新的立即訊息 (IM) 設定，可用來啟用或停用自動儲存 IM 會話，並封鎖任何無法封存的立即訊息。  <br/> |
|New-CsArchivingPolicy  <br/> |建立新的立即訊息 (IM) 會話封存原則。 這些原則可讓您封存內部使用者之間及/或封存內部使用者與外部協力廠商之間所發生的所有 IM 工作階段。  <br/> |
|Remove-CsArchivingConfiguration  <br/> |移除指定的封存設定集合，用來啟用或停用自動儲存立即訊息 (IM) 會話，並選擇性地封鎖無法封存的任何立即訊息。  <br/> |
|Remove-CsArchivingPolicy  <br/> |移除指定的立即訊息 (IM) 封存原則，可判斷商務用 Skype 伺服器是否會自動儲存內部使用者和/或內部使用者與同盟協力廠商之間所有 IM 會話之間所發生的所有 IM 會話。  <br/> |
|Set-CsArchivingConfiguration  <br/> |修改現有的立即訊息 (IM 集合) 封存設定選項。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改現有的立即訊息 (IM) 封存原則。 封存原則讓您能夠封存內部使用者之間所發生的所有 IM 會話和會議。您也可以封存在內部使用者與同盟協力廠商之間進行的會話。  <br/> |
|Set-CsArchivingServer  <br/> |可讓您指定一或多個封存伺服器的新資料庫位置。  <br/> |
   

