---
title: 新增監控伺服器 SQL Server 存放區
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 監控伺服器需要支援的64位版本 SQL Server 資料庫軟體才能儲存監控資料。 您可以選擇要用於監視的先前定義的 SQL Server 資料庫，也可以指定 SQL Server 資料庫所在之伺服器 (FQDN) 的完整功能變數名稱，或定義新的 SQL Server 資料庫，除了您想要用於新 SQL Server 資料庫的 SQL Server 實例之外（也就是您指定 (的命名實例）。
ms.openlocfilehash: a9417132e1b0bc2d6fc39bffaa4dd1abf86c6817
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743829"
---
# <a name="add-monitoring-server-sql-server-store"></a>新增監控伺服器 SQL Server 存放區

監控伺服器需要支援的64位版本 SQL Server 資料庫軟體才能儲存監控資料。 您可以選擇要用於監視的先前定義的 SQL Server 資料庫，也可以指定 SQL Server 資料庫所在之伺服器 (FQDN) 的完整功能變數名稱，或定義新的 SQL Server 資料庫，除了您想要用於新 SQL Server 資料庫的 SQL Server 實例之外（也就是您指定 (的命名實例）。

如需 SQL Server 支援的詳細資訊，請參閱支援檔中的[資料庫軟體和群集支援](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support)。 如需監控資料庫（包括監控資料庫的組合）的詳細資訊，請參閱支援檔中的[支援伺服器位置](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)、規劃檔中的[監控](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)， [SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)以及部署檔中的記錄檔位置。

> [!NOTE]
> 若發行拓撲所用的帳戶具有適當的使用者權限，您可以在發行拓撲時建立監控資料庫。 您也可以之後再建立資料庫，包括在安裝程序中。 > 若要在 SQL Server 型伺服器上安裝及部署資料庫以進行監視，您必須是要安裝資料庫檔案之 SQL Server 服務器的 SQL Server 系統管理員群組成員。 如果您不是 SQL Server sysadmin 群組的成員，則必須要求加入至群組，直到部署資料庫檔案為止。 如果您無法成為系統管理員群組的成員，則應該為您的 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。 如需完成這些程式所需之使用者權限的詳細資訊，請參閱部署檔中[的 SQL Server 部署許可權](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。