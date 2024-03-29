---
title: 商務用 Skype Server 2015 中的 Persistent Chat Server 的硬體和軟體需求
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要：閱讀此主題以瞭解商務用 Skype Server 2015 中的 Persistent Chat Server 的硬體和軟體需求。
---

# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 Persistent Chat Server 的硬體和軟體需求
 
**總結：** 閱讀此主題以瞭解商務用 Skype Server 2015 中的 Persistent Chat Server 的硬體和軟體需求。
  
Persistent Chat Server 可以隨商務用 Skype Server 2015 Enterprise Edition 或 Standard Edition 一起安裝。 需求取決於您已安裝的商務用 Skype Server 2015 版本，以及您的業務效能需求。 Enterprise Edition 最多可支援80000並行使用者。Standard Edition 最多可支援20000並行使用者。 Persistent Chat 是由前端元件及後端 SQL 資料庫元件所組成。
  
在您部署 Persistent Chat Server 之前，您必須確定符合下列硬體及軟體需求：
  
- 符合支援商務用 Skype Server 2015、Persistent Chat Server、資料庫伺服器及檔案伺服器等基本需求的硬體。 如需詳細資訊，請參閱[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- 支援的作業系統和資料庫軟體。
    
    如需支援的作業系統和資料庫軟體的詳細資訊，以及 Windows 的更新需求，請參閱[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- 商務用 Skype Server 2015 前端伺服器。 前端伺服器是會話初始通訊協定 (SIP) 路由的基礎，它使得執行持續聊天伺服器的電腦與可能的持久聊天功能之間進行通訊。 
    
- 訊息佇列軟體。 由 Persistent Chat Server 和 Persistent Chat 規章服務（若已部署）使用。
    
下列各節說明 Persistent Chat Server 和儲存 Persistent Chat 資料之資料庫的特定需求。

> [!NOTE] 
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 
  
## <a name="front-end-server-requirements"></a>前端伺服器需求

前端伺服器需求取決於您是否要使用商務用 Skype Server 2015 Enterprise Edition 或 Standard Edition 部署 Persistent Chat Server。
  
- 若要使用商務用 Skype Server 2015 Enterprise Edition 部署 persistent chat server，您可以在 Enterprise Edition 集區中的一或多台獨立電腦上部署 persistent chat server 前端伺服器。 您無法在商務用 Skype Server 2015 前端伺服器上組合持久聊天前端伺服器。 
    
    單一 Persistent Chat Server 前端伺服器可支援20000作用中的使用者。 您可以有最多4個作用中前端的持久聊天伺服器集區，以支援所有80000並行使用者。 
    
- 若要使用商務用 Skype Server 2015 Standard Edition 部署 persistent chat Server，您可以組合與前端伺服器的持久聊天。 這種單一伺服器部署最多可支援20000使用者。 
    
## <a name="persistent-chat-server-database-requirements"></a>Persistent Chat Server 資料庫需求

Persistent chat Server 需要 SQL Server 資料庫軟體，以儲存聊天室記錄與內容、設定資料、使用者布建資料，以及其他相關的中繼資料。 另外，它會使用 Persistent 聊天室規範資料庫來儲存規範資料。 您可以在相同的 SQL Server 上和後端資料庫一樣，在相同的上組合持久的聊天室資料庫，甚至是相同的 SQL 實例。 
  
- 若要使用商務用 Skype Server 2015 Enterprise Edition 安裝 Persistent chat Server，以確保最佳效能，建議您安裝 Persistent chat file store。
    
- 若要使用商務用 Skype Server 2015 Standard edition 來安裝 persistent chat server，您可以在本機 SQL Server Express 實例上部署 persistent chat Store 後端伺服器。
    
- Persistent Chat database (mgc) ，且規範資料庫 (mgccomp) 可以位於相同的 SQL Server 實例或不同的 SQL 伺服器上。
    
若要準備資料庫伺服器平臺，請確定每一部電腦都符合硬體需求，然後安裝必要軟體。 Persistent Chat 資料庫伺服器的伺服器平臺需要與商務用 Skype Server 2015 後端資料庫伺服器相同的硬體。 如需詳細資訊，請參閱[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
  
在資料庫伺服器上，確定已安裝下列其中一個軟體應用程式：

- 使用最新的 service pack Microsoft SQL Server 2017。

- Microsoft SQL Server 2016 搭配 Service Pack 1，必須使用商務用 Skype Server 累積更新7或更新版本執行。 建議使用最新的 service pack 執行 SQL Server 2016。 如需如何安裝 Microsoft SQL Server 2016 的詳細資訊，請參閱[install SQL Server 2016](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。

- Microsoft SQL Server 2014，您必須使用商務用 Skype Server 累積更新6或更新版本執行。 建議使用最新的 service pack 執行 SQL Server 2014。 如需如何安裝 Microsoft SQL Server 2014 的詳細資訊，請參閱[install SQL Server 2014](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。

- Microsoft SQL Server 2012 (64-bit edition) ，建議使用最新的 service pack 來執行。 如需如何安裝 Microsoft SQL Server 2012 的詳細資訊，請參閱[install SQL Server 2012](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110))。

## <a name="persistent-chat-server-certificate-requirements"></a>Persistent Chat Server 憑證需求

如需取得憑證、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱[Deploy 商務用 Skype Server 2015](../../deploy/deploy.md)。 
  
## <a name="for-more-information"></a>相關資訊

如需硬體和軟體需求的詳細資訊，請參閱下列主題：
  
- [商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
