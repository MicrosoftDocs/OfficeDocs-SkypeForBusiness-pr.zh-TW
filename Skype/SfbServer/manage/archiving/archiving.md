---
title: 在商務用 Skype Server 中管理存檔
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 摘要：瞭解如何管理商務用 Skype Server 的封存。
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818995"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>在商務用 Skype Server 中管理存檔

**摘要：** 瞭解如何管理商務用 Skype Server 的封存。
  
當您為貴組織部署存檔時，您會在部署期間指定初始配置。 不過，有時候您可能會想要變更針對日常管理實施封存支援的方式，或符合貴組織的新需求。 例如，您可能需要針對特定網站、特定池或貴組織內的特定使用者設定不同的存檔支援。 針對駐留在商務用 Skype Server 的使用者，您可以建立及自訂封存配置選項和使用者原則來執行此動作。 
  
在您閱讀本主題之前，請務必熟悉[在商務用 Skype server 中進行](../../plan-your-deployment/archiving/archiving.md)封存所需的資訊，並[針對商務用 skype server 部署歸檔](../../deploy/deploy-archiving/deploy-archiving.md)。
  
> [!NOTE]
> 如果您針對您的部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否針對駐留在 Exchange 的使用者啟用封存，並將其信箱放在就地保留中。 如需詳細資訊，請參閱[在商務用 Skype server 中進行](../../plan-your-deployment/archiving/archiving.md)封存的規劃，以及[設定與商務用 Skype server 的 Exchange 儲存體整合](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="archiving-configuration-options"></a>封存配置選項

封存配置選項指定是否：
  
- 啟用或停用封存功能
    
- 封存 IM 工作階段
    
- 封存網路會議會話
    
- 存檔無法使用時封鎖活動
    
- 使用 Exchange 整合
    
- 設定清除及匯出資料
    
這些選項可以在 [全域]、[網站] 或 [池] 層級設定。 如需詳細資訊，請參閱[在商務用 Skype Server 中管理封存選項](options.md)。
  
## <a name="archiving-policies"></a>歸檔原則

存檔原則決定是否要封存下列專案：
  
- 內部通訊
    
- 外部通訊
    
這些原則可以在全域、網站或使用者層級設定。 如需詳細資訊，請參閱[在商務用 Skype Server 中管理存檔原則](policies.md)。
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>使用 [控制台] 或使用 Windows PowerShell 來管理存檔

您可以使用 [控制台] 或使用 Windows PowerShell 來管理存檔。 下表摘要列出可協助您管理存檔的 Cmdlet。 如需語法的詳細資料（包括所有可用的參數），請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。 


|**Cmdlet**|**說明**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |匯出已儲存在商務用 Skype Server 封存資料庫中的記錄。  <br/> |
|CsArchivingConfiguration  <br/> |傳回貴組織中的存檔設定設定的相關資訊。  <br/> |
|Get-CsArchivingPolicy  <br/> |傳回貴組織的內部和外部通訊原則的相關資訊。  <br/> |
|授與 CsArchivingPolicy  <br/> |將立即訊息（IM）會話存檔原則指派給使用者或使用者組。 這些原則可讓您封存在內部使用者之間進行的所有 IM 會話，以及/或封存在內部使用者與外部合作夥伴之間發生的所有 IM 會話。  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |手動清除封存資料庫中的記錄。  <br/> |
|新-CsArchivingConfiguration  <br/> |建立一組新的立即訊息（IM）設定，這可以用來啟用或停用自動儲存 IM 會話，並封鎖任何無法封存的立即訊息。  <br/> |
|New-CsArchivingPolicy  <br/> |建立新的立即訊息（IM）會話存檔原則。 這些原則可讓您封存在內部使用者之間進行的所有 IM 會話，以及/或封存在內部使用者與外部合作夥伴之間發生的所有 IM 會話。  <br/> |
|移除-CsArchivingConfiguration  <br/> |移除指定的存檔設定集合，這些設定是用來啟用或停用立即訊息（IM）會話，以及選擇性地封鎖任何無法封存的立即訊息。  <br/> |
|Remove-CsArchivingPolicy  <br/> |移除指定的立即訊息（IM）封存原則，決定商務用 Skype 伺服器是否會自動儲存所有內部使用者之間發生的 IM 會話，以及/或內部使用者與同盟合作夥伴之間的所有 IM 會話。  <br/> |
|Set-CsArchivingConfiguration  <br/> |修改現有的立即訊息（IM）封存配置選項組合。  <br/> |
|Set-CsArchivingPolicy  <br/> |修改現有的立即訊息（IM）封存原則。 存檔原則可讓您將在內部使用者之間發生的所有 IM 會議與會議封存在一起。您也可以封存在內部使用者和聯盟夥伴之間發生的會話。  <br/> |
|Set-CsArchivingServer  <br/> |可讓您為一或多個存檔伺服器指定新的資料庫位置。  <br/> |
   

