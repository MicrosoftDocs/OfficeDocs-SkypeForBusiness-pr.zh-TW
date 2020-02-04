---
title: 新增監控伺服器 SQL Server 存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 監視伺服器需要支援的64位版本的 SQL Server 資料庫軟體，才能儲存監視資料。 您可以選取先前定義的 SQL Server 資料庫來進行監視，或指定新的 SQL Server 資料庫，方法是指定 sql Server 資料庫將駐留之伺服器的完整功能變數名稱（FQDN），以及 SQL 的實例您想要用於新的 SQL Server 資料庫的伺服器（可以是預設實例，或是您指定的命名實例）。
ms.openlocfilehash: 8c74462e0623c34fbbbf4c3f67d1a0adf0f3c922
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698178"
---
# <a name="add-monitoring-server-sql-server-store"></a>新增監控伺服器 SQL Server 存放區

監視伺服器需要支援的64位版本的 SQL Server 資料庫軟體，才能儲存監視資料。 您可以選取先前定義的 SQL Server 資料庫來進行監視，或指定新的 SQL Server 資料庫，方法是指定 sql Server 資料庫將駐留之伺服器的完整功能變數名稱（FQDN），以及 SQL 的實例您想要用於新的 SQL Server 資料庫的伺服器（可以是預設實例，或是您指定的命名實例）。

如需有關 SQL Server 支援的詳細資訊，請參閱支援檔中的[資料庫軟體和群集支援](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。 如需監控資料庫的詳細資料，包括監視資料庫的 collocation，請參閱支援檔中的[支援伺服器位置](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)，在規劃檔與[SQL Server 資料](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)中[規劃監視](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)，以及在部署檔中放置記錄檔案。

> [!NOTE]
> 如果用於發佈拓朴的帳戶具有適當的使用者權利和許可權，您可以在發佈拓撲時建立監視資料庫。 您也可以日後建立資料庫，包括安裝程式的一部分。 > 若要在進行監視的 SQL Server server 伺服器上安裝和部署資料庫，您必須是安裝資料庫檔案之 SQL server 系統管理員群組的成員。 如果您不是 SQL Server 系統管理員群組的成員，您必須要求將資料庫檔案部署之後，才能將其新增至群組中。 如果您無法成為系統管理員群組的成員，您應該使用腳本來提供您的 SQL Server 資料庫系統管理員，以設定及部署資料庫。 如需完成這些程式所需的使用者權利和許可權的詳細資料，請參閱部署檔中的[SQL Server 部署許可權](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


