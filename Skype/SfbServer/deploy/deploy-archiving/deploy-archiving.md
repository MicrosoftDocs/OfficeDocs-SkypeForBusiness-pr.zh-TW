---
title: 部署商務用 Skype Server 的存檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: '摘要: 請閱讀本主題, 以瞭解如何部署商務用 Skype Server 的封存。'
ms.openlocfilehash: 8611f83b6e3504d860cf37a7ad2c24c20b446671
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234513"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>部署商務用 Skype Server 的存檔
 
**摘要:** 若要瞭解如何為商務用 Skype Server 部署封存, 請閱讀本主題。
  
在商務用 Skype Server 部署中, 存檔會自動安裝在每個前端伺服器上, 但您仍需執行初始設定和設定步驟, 才能使用。 開始之前, 請確定您已經熟悉在[商務用 Skype Server 中進行](../../plan-your-deployment/archiving/archiving.md)封存所需的概念。
  
## <a name="deployment-checklist"></a>部署檢查清單

設定存檔的方式取決於您選擇的儲存空間選項: 
  
- 如果您針對部署中的所有使用者使用 Microsoft Exchange 整合, 就不需要針對使用者設定商務用 Skype Server 封存原則。 相反地, 您可以設定 Exchange 就地保留原則, 以支援駐留在 Exchange 的使用者的封存, 且其信箱會放入就地保留。 如需有關設定這些原則的詳細資訊, 請參閱 Exchange 產品檔。
    
- 如果您不是針對您部署中的所有使用者使用 Microsoft Exchange 整合, 您必須在拓撲中新增商務用 Skype 伺服器封存資料庫 (SQL Server 資料庫), 發佈更新的拓撲, 然後設定封存原則, 並使用者的設定。 您可以在部署初始拓撲或部署至少一個前端池或標準版伺服器之後, 部署存檔資料庫。 本檔說明如何將存檔資料庫新增至現有的部署。
    
如果您在一個前端池或標準版伺服器上啟用封存, 您應該針對部署中的所有其他前端池和標準版伺服器啟用該功能。 這是因為需要封存其通訊的使用者可以受邀加入群組 IM 交談或託管于不同的池中的會議。 如果在託管或會議所在的池中未啟用 [封存], 則可能不會封存整個會話。 在這些情況下, 擁有封存的使用者的 Im 仍可歸檔, 但不適用於會議內容檔案, 以及會議加入或離開活動。
  
> [!IMPORTANT]
> 如果您組織中的存檔是符合合規性的理由, 請務必在適當的層級部署封存、設定原則及其他選項, 然後針對所有適當的使用者開啟封存, 然後再針對您的 Skype 啟用這些使用者商務伺服器。 
  
下表概要說明在現有拓撲中部署存檔所需的步驟。
  
|**分**|**步驟**|**角色和群組成員資格**|**文件**|
|:-----|:-----|:-----|:-----|
|**安裝必備的硬體和軟體** <br/> |若要使用 Microsoft Exchange 整合 (在部分或所有使用者中使用 Exchange 來封存儲存空間), 您需要現有的 Exchange 部署。  <br/> 若要使用個別的存檔資料庫 (使用 SQL Server 資料庫) 來儲存部分或所有使用者的儲存空間, 請在伺服器上將儲存封存資料的 SQL Server。  <br/> 封存是在企業版池和標準版伺服器的前端伺服器上執行。 除了安裝這些伺服器所需的其他硬體或軟體需求之外, 它還沒有其他硬體或軟體需求。  <br/> |屬於本機管理員群組成員的網域使用者。  <br/> |[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [規劃整合商務用 Skype Server 2015 與 Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[商務用 Skype Server 2019 的系統需求](../../../SfBServer2019/plan/system-requirements.md) |
|**建立適當的內部拓朴, 以支援封存 (僅適用于您部署中的所有使用者都不使用 Microsoft Exchange 整合)** <br/> |執行拓撲建立器, 將商務用 Skype Server 封存資料庫 (SQL Server 資料庫) 新增到拓撲結構, 然後發佈拓撲。  <br/> |若要定義拓撲以納入封存資料庫, 該帳戶是 [本機使用者] 群組的成員。  <br/> 若要發佈拓朴, 該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員, 且在檔案共用上具有完全控制許可權 (讀取/寫入/修改), 以用於商務用 Skype Server 檔存放區 (如此一來, 該拓撲建造者可以設定所需的 Dacl)。  <br/> |[在商務用 Skype Server 中新增封存資料庫至現有的部署](add-archiving-databases.md) <br/> |
|**設定伺服器對伺服器驗證 (僅在使用 Microsoft Exchange 整合時)** <br/> |將伺服器設定為在商務用 Skype Server 與 Exchange 之間啟用驗證。 我們建議您在啟用封存前, 執行**測試 CsExchangeStorageConnectivity testuser_sipUri-資料夾 Dumpster** , 以驗證 Exchange 封存儲存連接。 <br/> |具有適當許可權的帳戶, 可在伺服器上管理證書。  <br/> |管理伺服器對伺服器驗證  <br/> |
|**設定封存選項與原則** <br/> |設定封存, 包括是否使用 Microsoft Exchange 整合、全域原則及任何網站和使用者原則 (不使用 Microsoft Exchange 整合進行所有資料儲存), 以及特定的歸檔選項 (例如, 重要模式與資料)匯出和清除。  <br/> 如果您使用的是 Microsoft Exchange 整合, 請視需要設定 Exchange 就地保留原則。  <br/> |RTCUniversalServerAdmins 群組 (僅限 Windows PowerShell) 或將使用者指派給 CSArchivingAdministrator 或 CSAdministrator 角色。  <br/> |[設定商務用 Skype Server 的存檔選項](configure-archiving-options.md) <br/> Exchange 產品檔 (如果您使用的是 Microsoft Exchange 整合)。  <br/> |
   

