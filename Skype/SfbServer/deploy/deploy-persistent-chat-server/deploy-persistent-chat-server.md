---
title: 在商務用 Skype Server 2015 中部署常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: '摘要: 請閱讀本主題, 以瞭解如何部署商務用 Skype Server 2015 永久聊天伺服器。'
ms.openlocfilehash: 2d3c9ca11447a5be212a053d8c5cb002ada4c522
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240826"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中部署常設聊天室伺服器
 
**摘要:** 請閱讀本主題, 瞭解如何部署商務用 Skype Server 2015 持續聊天伺服器。
  
若要部署持久聊天伺服器, 您可以: 
  
- 使用拓撲建立器來定義或匯入, 並隨後發佈您要部署的拓撲和元件
    
- 準備部署持久聊天伺服器元件的環境
    
- 針對您的部署安裝及設定持續聊天伺服器元件
    
在您部署持久聊天伺服器之前, 您應該閱讀[商務用 Skype server 2015 中持續聊天伺服器的規劃](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 規劃主題描述硬體和軟體需求、可能的拓撲及 collocation 案例。 
  
> [!NOTE] 
> 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。 

## <a name="deployment-checklist"></a>部署檢查清單

您可以在部署初始拓撲 (包括至少一個商務用 Skype Server 前端池或一個商務用 Skype 標準版伺服器) 之後, 部署持續式聊天伺服器。 部署檢查清單說明部署持久聊天伺服器所需的基本步驟, 並提供更多詳細資料的連結。
  
**持續聊天伺服器部署程式**

|**工作**|**步驟**|**必要角色和群組成員資格**|**相關主題**|
|:-----|:-----|:-----|:-----|
|**安裝必備的硬體和軟體** <br/> | 在符合系統需求的硬體上, 安裝下列各項: <br/>  在永久聊天伺服器前端伺服器上: <br/>  符合系統需求的作業系統 <br/>  執行商務用 Skype Server 之電腦的軟體先決條件 <br/>  在將主控持久聊天伺服器資料庫的伺服器上: <br/>  支援的 SQL Server 版本 <br/>  如果需要持續聊天伺服器合規性: <br/>  伺服器上將主控持久聊天伺服器合規性資料庫的 SQL Server <br/> |屬於本機管理員群組成員的任何使用者。  <br/> |[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [常設聊天室伺服器的硬體與軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**建立適當的內部拓朴, 以支援持續聊天伺服器 (以及可隨意進行的聊天合規性)** <br/> | 執行拓撲建立器, 以新增持久聊天伺服器池至您的拓撲: <br/>  新增持久聊天伺服器元件至拓撲 <br/>  建立持久聊天伺服器存放區的 SQL Server 資料庫 (以及災害復原的備份 SQL Server) <br/>  定義新的商務用 Skype 檔案存放區, 或使用現有的商務用 Skype 檔案存放區做為持續聊天伺服器檔案 <br/>  建立可將要求路由至此持續聊天伺服器池的商務用 Skype 伺服器池 <br/>  如果需要持續聊天合規性: <br/>  新增持久聊天合規性存放區 <br/>  按一下 [持續聊天伺服器池定義] 核取方塊以啟用合規性 <br/>  發佈拓撲。 <br/>  如果您在標準版上安裝持續式聊天伺服器, 則持久性聊天伺服器池的完整功能變數名稱 (FQDN) 必須符合標準版伺服器, 且 SQL Server 資料庫在標準版的 SQL Server Express 實例上是 collocated 的。Edition 伺服器 <br/> |若要定義拓撲, 該帳戶是 [本機使用者] 群組的成員。  <br/> 若要發佈拓朴, 該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員, 而且使用者在商務用 Skype 檔案存放區上也應該有完整的控制許可權 (讀取/寫入/修改), 以取得持續聊天伺服器檔案 (因此拓撲建立器可以設定所需的 Dacl)。  <br/> |[在商務用 Skype Server 2015 中建立和發佈新的拓撲](../../deploy/install/create-and-publish-new-topology.md) <br/> [在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器](add-persistent-chat-server.md) <br/> |
|**部署常設聊天室伺服器** <br/> | 在執行永久聊天伺服器的所有電腦上執行商務用 Skype 伺服器設定。 持續聊天伺服器設定會整合到商務用 Skype Server 部署嚮導中, 提供下列指示: <br/>  部署本機管理存放區 <br/>  安裝永久性聊天服務 <br/>  要求並指派憑證 <br/>  執行並啟動服務 <br/> |屬於本機管理員群組成員的任何使用者。  <br/> |[在商務用 Skype Server 2015 中部署常設聊天室伺服器](deploy-persistent-chat-server.md) <br/> |
|**建立常設聊天室管理員** <br/> |將使用者新增至 CsPersistentChatAdministrator 安全性群組。  <br/> |屬於網域管理員成員的任何使用者。  <br/> |[建立常設聊天室管理員](create-a-persistent-chat-administrator.md) <br/> |
|**設定常設聊天室伺服器** <br/> | 設定使用者: <br/>  使用者必須由原則啟用, 才能存取持久聊天伺服器。 根據預設, 對於所有使用者而言, 原則都是關閉的, 而且可以在全域/網站/池/使用者範圍中定義。 <br/>  設定設定 <br/> |使用者必須是 CsPersistentChatAdministrator 的成員。 若要變更原則, 使用者至少必須在 CsUserAdministrator 中。  <br/> |[管理商務用 Skype Server 2015 中的常設聊天室](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

