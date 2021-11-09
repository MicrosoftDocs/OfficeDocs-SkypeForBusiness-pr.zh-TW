---
title: 部署商務用 Skype Server 的封存
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50fa535c-7347-4e33-80a3-296748ef6666
description: 摘要：閱讀此主題以瞭解如何部署商務用 Skype Server 的封存。
ms.openlocfilehash: bdf0e6fe170371d1596fd556450fca14d6433239
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837415"
---
# <a name="deploy-archiving-for-skype-for-business-server"></a>部署商務用 Skype Server 的封存
 
**摘要：** 閱讀此主題以瞭解如何部署商務用 Skype Server 的封存。
  
封存會自動安裝在商務用 Skype Server 部署的每一部前端伺服器上，但您仍然必須先執行初始設定及設定步驟，才能使用它。 在您開始之前，請確定您已熟悉在[商務用 Skype Server 中](../../plan-your-deployment/archiving/archiving.md)封存的計畫概念。
  
## <a name="deployment-checklist"></a>部署檢查清單

如何設定封存取決於您選擇的儲存體選項： 
  
- 如果您使用 Microsoft Exchange 整合部署中的所有使用者，您就不需要為使用者設定商務用 Skype Server 的封存原則。 相反地，您可以設定 Exchange In-Place 保留原則，以支援位於 Exchange 上之使用者的封存，且其信箱置於 In-Place 保留狀態。 如需設定這些原則的詳細資訊，請參閱 Exchange 產品檔。
    
- 如果您未使用 Microsoft Exchange 整合部署中的所有使用者，您必須在拓撲中新增商務用 Skype Server 封存資料庫 (SQL Server) 資料庫，發佈更新的拓撲，然後為使用者設定封存原則及設定。 您可以在部署初始拓撲時，或在部署至少一個前端集區或 Standard Edition 伺服器之後，部署封存資料庫。 本檔說明如何將封存資料庫新增至現有的部署中，以進行部署。
    
如果您在一個前端集區或 Standard Edition 伺服器上啟用封存，則應該針對部署中的所有其他前端集區和 Standard Edition 伺服器啟用封存。 這是因為，需要將通訊封存的使用者可受邀至由其他集區所主控的群組 IM 交談或會議。 如果封存未在主控交談或會議的所在集區啟用，可能無法封存完整的工作階段。 在此情況下，包含已啟用封存之使用者的 IM 仍可進行封存，但不包含會議內容檔案以及會議加入或離開事件。
  
> [!IMPORTANT]
> 如果您的組織中的封存非常重要，請務必在適當的層級部署封存、設定原則及其他選項，然後為所有適當的使用者啟用封存，然後才為商務用 Skype Server 啟用使用者。 
  
下表提供在現有拓撲中部署封存之所需步驟的概觀。
  
|**階段**|**步驟**|**角色和群組成員資格**|**文件**|
|:-----|:-----|:-----|:-----|
|**安裝必備硬體和軟體** <br/> |若要使用 Microsoft Exchange 整合 (使用 Exchange 封存存放區中的部分或所有使用者) ，您需要有現有的 Exchange 部署。  <br/> 若要使用不同的封存資料庫 (使用 SQL Server 資料庫) 封存儲存區，以供部分或所有使用者使用，請 SQL Server 在將儲存封存資料的伺服器上執行。  <br/> 封存會在 Enterprise 集區和 Standard Edition 伺服器的前端伺服器上執行。 安裝這些伺服器除必條件外，沒有額外的硬體或軟體需求。  <br/> |身為本機系統管理員群組成員的網域使用者。  <br/> |[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/>  [規劃整合商務用 Skype 和 Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) <br/>[商務用 Skype Server 2019 的系統需求](../../../SfBServer2019/plan/system-requirements.md) |
|**只有在您部署中的所有使用者都不使用 Microsoft Exchange 整合時，才建立適當的內部拓撲以支援封存 ()** <br/> |執行拓撲產生器，以新增商務用 Skype Server 封存資料庫 (SQL Server 資料庫) 拓撲，然後發行拓撲。  <br/> |若要定義要納入封存資料庫的拓撲，其帳戶為本機使用者群組的成員。  <br/> 若要發行拓撲，您必須是 domain admins 群組成員和 RTCUniversalServerAdmins 群組成員的帳戶，且具有商務用 Skype Server 檔案存放區之檔案共用上的「讀取/寫入/修改」) 的「完全控制」許可權 (可供拓撲產生器設定所需的 dacl (。  <br/> |[將封存資料庫新增至商務用 Skype Server 中的現有部署](add-archiving-databases.md) <br/> |
|**僅在使用 Microsoft Exchange) 整合時，才設定伺服器對伺服器驗證 (** <br/> |設定伺服器以啟用商務用 Skype Server 和 Exchange 之間的驗證。 建議您在啟用封存之前，執行 **CsExchangeStorageConnectivity testuser_sipUri-Folder 暫放** 以驗證 Exchange 封存儲存連線。 <br/> |具有適當權限可在伺服器上管理憑證的帳戶。  <br/> |管理伺服器對伺服器驗證  <br/> |
|**設定封存選項和原則** <br/> |設定封存，包括是否使用 microsoft Exchange 整合、全域原則及任何網站與使用者原則 (不使用 microsoft Exchange 整合) 所有資料儲存及特定封存選項（例如重要模式和資料匯出及清除）。  <br/> 如果使用 Microsoft Exchange 整合，請適當設定 Exchange In-Place 保留原則。  <br/> |RTCUniversalServerAdmins 群組 (僅限 Windows PowerShell) 或將使用者指派為 CSArchivingAdministrator 或 CSAdministrator 角色。  <br/> |[設定商務用 Skype Server 的封存選項](configure-archiving-options.md) <br/> Exchange 產品檔 (使用 Microsoft Exchange 整合) 。  <br/> |
   

