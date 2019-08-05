---
title: 常設聊天室伺服器的硬體與軟體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '摘要: 請閱讀本主題, 瞭解商務用 Skype Server 2015 中持續聊天伺服器的硬體和軟體需求。'
ms.openlocfilehash: e700b76c8af29a0c877c1dc594244a299b8a3904
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194042"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a>常設聊天室伺服器的硬體與軟體需求
 
**摘要:** 若要瞭解商務用 Skype Server 2015 中持續聊天伺服器的硬體和軟體需求, 請閱讀本主題。
  
永久聊天伺服器可以與商務用 Skype Server 2015 (企業版或標準版) 一起安裝。 需求取決於您所安裝的商務用 Skype Server 2015 版本, 以及貴企業的效能需求。 企業版最多可支援80000個併發使用者;標準版版本最多可支援20000個併發使用者。 持續聊天是由前端元件以及後端 SQL 資料庫元件所組成。
  
在您部署持久聊天伺服器之前, 您必須確保符合下列硬體和軟體需求:
  
- 符合最低需求以支援商務用 Skype Server 2015、持續聊天伺服器、資料庫伺服器和檔案伺服器的硬體。 如需詳細資訊, 請參閱[商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- 支援的作業系統和資料庫軟體。
    
    如需支援的作業系統和資料庫軟體以及 Windows 更新需求的詳細資訊, 請參閱[商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- 商務用 Skype Server 2015 前端伺服器。 前端伺服器是會話初始通訊協定 (SIP) 路由的基礎, 可讓執行持續聊天伺服器的電腦與持久的聊天功能都能正常運作。 
    
- 訊息佇列軟體。 持續聊天伺服器和持續聊天相容性服務 (如果已部署) 使用。
    
下列各節說明持續性聊天伺服器和儲存持續聊天資料之資料庫的特定需求。

> [!NOTE] 
> 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。 
  
## <a name="front-end-server-requirements"></a>前端伺服器需求

前端伺服器需求取決於您是否要使用商務用 Skype Server 2015 (企業版或標準版) 部署持久聊天伺服器。
  
- 如果您要使用商務用 Skype Server 2015 (企業版) 部署持久聊天伺服器, 您可以在企業版池中的一或多台獨立電腦上部署持久聊天伺服器前端伺服器。 您無法在商務用 Skype Server 2015 前端伺服器上 collocate 持續聊天前端伺服器。 
    
    單一持續式聊天伺服器前端伺服器可以支援20000作用中的使用者。 您可以使用最多4個作用中端的持久聊天伺服器池, 從而支援總共80000個併發使用者。 
    
- 如果您要部署與商務用 Skype Server 2015 標準版的持久聊天伺服器, 您可以 collocate 與前端伺服器的持續聊天。 這個單伺服器部署最多可支援20000個使用者。 
    
## <a name="persistent-chat-server-database-requirements"></a>持續聊天伺服器資料庫需求

持續聊天伺服器需要 SQL Server 資料庫軟體來儲存聊天室記錄及內容、設定資料、使用者預配資料, 以及其他相關的中繼資料。 您也可以使用持續性聊天規範資料庫來儲存合規性資料。 持久聊天資料庫可以在相同的 SQL Server 上 collocated, 或甚至與後端資料庫一樣是相同的 SQL 實例。 
  
- 如果您要在商務用 Skype Server 2015 企業版中安裝持久聊天伺服器, 以確保最佳效能, 建議您安裝永久聊天檔案存放區。
    
- 如果您要在商務用 Skype Server 2015 標準版中安裝持久聊天伺服器, 您可以在本機 SQL Server Express 實例上部署永久聊天存放後端伺服器。
    
- 持久聊天資料庫 (mgc) 和規範資料庫 (mgccomp) 可位於相同的 SQL Server 實例或不同的 SQL 伺服器上。
    
若要準備資料庫伺服器平臺, 請確定每個電腦都符合硬體需求, 然後再安裝必備軟體。 持續聊天資料庫伺服器的伺服器平臺需要與商務用 Skype Server 2015 後端資料庫伺服器相同的硬體。 如需詳細資訊, 請參閱[商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
  
在資料庫伺服器上, 請確定已安裝下列其中一個軟體應用程式:

- Microsoft SQL Server 2017 (含最新 service pack)。

- Microsoft SQL Server 2016 Service Pack 1, 而且您必須在商務用 Skype Server 累積更新7或更新版本上執行。 我們建議您使用最新的 service pack 執行 SQL Server 2016。 如需有關如何安裝 Microsoft SQL Server 2016 的詳細資訊, 請參閱[安裝 SQL server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。

- Microsoft SQL Server 2014, 且您必須在商務用 Skype Server 累積更新6或更新版本上執行。 我們建議您使用最新的 service pack 執行 SQL Server 2014。 如需有關如何安裝 Microsoft SQL Server 2014 的詳細資訊, 請參閱[安裝 SQL server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。

- Microsoft SQL Server 2012 (64 位版本), 我們建議使用最新的 service pack 執行。 如需有關如何安裝 Microsoft SQL Server 2012 的詳細資訊, 請參閱[安裝 SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)。

## <a name="persistent-chat-server-certificate-requirements"></a>持續聊天伺服器憑證需求

如需取得證書、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊, 請參閱[部署商務用 Skype Server 2015](../../deploy/deploy.md)。 
  
## <a name="for-more-information"></a>如需詳細資訊

如需硬體和軟體需求的詳細資訊, 請參閱下列主題:
  
- [商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

