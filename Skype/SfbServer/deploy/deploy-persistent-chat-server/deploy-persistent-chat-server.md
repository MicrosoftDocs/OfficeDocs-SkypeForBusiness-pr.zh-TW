---
title: 在商務用 Skype Server 2015 中部署 Persistent Chat Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 摘要：閱讀此主題以瞭解如何部署商務用 Skype Server 2015 Persistent Chat Server。
ms.openlocfilehash: 60dbabc84e278f6add3b7de408787f4969a164a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830473"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中部署 Persistent Chat Server
 
**摘要：** 閱讀此主題以瞭解如何部署商務用 Skype Server 2015 Persistent Chat Server。
  
若要部署 Persistent Chat Server，您可以： 
  
- 使用拓撲產生器來定義或匯入，然後發佈您要部署的拓撲和元件
    
- 準備部署持久聊天伺服器元件的環境
    
- 為您的部署安裝及設定 Persistent Chat Server 元件
    
在您部署 Persistent Chat Server 之前，您應該 [在商務用 Skype server 2015 中閱讀 Persistent Chat server 的計畫](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 規劃主題說明硬體和軟體需求、可能的拓撲和組合案例。 
  
> [!NOTE] 
> 商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。 小組中提供相同的功能。 如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。 

## <a name="deployment-checklist"></a>部署檢查清單

您可以在部署初始拓撲（包括至少一個商務用 Skype Server 前端集區或一個 Skype for business Standard Edition Server）之後，部署 Persistent Chat Server。 部署檢查清單描述部署 Persistent Chat Server 所需的基本步驟，並提供詳細資訊的連結。
  
**Persistent Chat Server 部署程式**

|**工作**|**步驟**|**必要的角色和群組成員資格**|**相關主題**|
|:-----|:-----|:-----|:-----|
|**安裝必備硬體和軟體** <br/> | 在符合系統需求的硬體上，安裝下列各項： <br/>  在 Persistent Chat Server 前端伺服器上： <br/>  符合系統需求的作業系統 <br/>  執行商務用 Skype Server 之電腦的軟體必要條件 <br/>  在將裝載 Persistent Chat Server 資料庫的伺服器上： <br/>  支援的 SQL Server 版本 <br/>  如果需要 Persistent Chat Server 規範： <br/>  主控持久聊天伺服器規範資料庫的伺服器上的 SQL Server <br/> |屬於本機 Administrators 群組成員的任何使用者。  <br/> |[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [商務用 Skype 2015 Server 中的 Persistent Chat Server 的硬體和軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**建立適當的內部拓撲以支援 Persistent Chat Server (及（選用）持續性聊天規範)** <br/> | 執行拓撲產生器，將 Persistent Chat Server 集區新增至您的拓撲： <br/>  將 Persistent Chat Server 元件新增至拓撲 <br/>  為 Persistent Chat Server store (和備份 SQL Server 建立 SQL Server 資料庫，以進行嚴重損壞修復)  <br/>  定義新的商務用 Skype 檔案存放區，或將現有商務用 Skype 檔案存放區用於 Persistent Chat Server 檔案 <br/>  關聯商務用 Skype 伺服器集區，可將要求路由傳送至此 Persistent Chat Server 集區 <br/>  如果需要持久聊天規範： <br/>  新增 Persistent 聊天室規範存放區 <br/>  按一下 [Persistent Chat Server 集區定義] 核取方塊以啟用相容性 <br/>  發行拓撲。 <br/>  如果您在 Standard Edition 上安裝 Persistent Chat Server，則 Persistent Chat Server 集區的完整功能變數名稱 (FQDN) 必須符合 Standard Edition server，而且 SQL Server 資料庫會在 Standard Edition server 上的 SQL Server Express 實例上組合 <br/> |若要定義拓撲，則為本機使用者群組成員的帳戶。  <br/> 若要發行拓撲，則為 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，而且使用者在 Persistent Chat Server 檔案的商務用 Skype 檔案存放區中也應具有「完全控制」許可權 (讀取/寫入/修改)  (，讓拓撲產生器可以設定必要的 Dacl) 。  <br/> |[在商務用 Skype Server 2015 中建立及發行新的拓撲](../../deploy/install/create-and-publish-new-topology.md) <br/> [將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲](add-persistent-chat-server.md) <br/> |
|**部署常設聊天室伺服器** <br/> | 在所有執行 Persistent Chat Server 的電腦上執行商務用 Skype 伺服器設定。 Persistent Chat Server 安裝程式已整合至商務用 Skype Server 部署嚮導，提供下列指示： <br/>  部署本機管理存放區 <br/>  安裝 Persistent Chat service <br/>  要求並指派憑證 <br/>  執行並啟動服務 <br/> |屬於本機 Administrators 群組成員的任何使用者。  <br/> |[在商務用 Skype Server 2015 中部署 Persistent Chat Server](deploy-persistent-chat-server.md) <br/> |
|**建立常設聊天室系統管理員** <br/> |將使用者新增至 CsPersistentChatAdministrator 安全性群組。  <br/> |任何屬於網域管理員成員的使用者。  <br/> |[在商務用 Skype Server 2015 中建立持續性聊天系統管理員](create-a-persistent-chat-administrator.md) <br/> |
|**設定 Persistent Chat Server** <br/> | 設定使用者： <br/>  使用者必須啟用該原則，才能存取 Persistent Chat Server。 根據預設，會為所有使用者關閉原則，並且可以在全域/網站/集區/使用者範圍上定義。 <br/>  進行設定 <br/> |使用者必須是 CsPersistentChatAdministrator 的成員。 若要變更原則，使用者至少必須在 CsUserAdministrator 中。  <br/> |[在商務用 Skype Server 2015 中管理 Persistent Chat Server](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

