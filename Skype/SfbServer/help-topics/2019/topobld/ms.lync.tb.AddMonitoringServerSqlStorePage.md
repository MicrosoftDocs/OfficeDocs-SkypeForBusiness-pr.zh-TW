---
title: 新增監控伺服器 SQL Server 存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: 監控伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存監控資料。 您可以選取先前定義的 SQL Server 資料庫，以用於監控，或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的 (FQDN) ，也就是您想要用於新 SQL Server 資料庫的 SQL Server 實例 (（可以是預設實例），或是您指定) 的命名實例。
ms.openlocfilehash: 34d5353d78a781fb1462cc908e37e12a0e7d0c5b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100109"
---
# <a name="add-monitoring-server-sql-server-store"></a>新增監控伺服器 SQL Server 存放區

監控伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存監控資料。 您可以選取先前定義的 SQL Server 資料庫，以用於監控，或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的 (FQDN) ，也就是您想要用於新 SQL Server 資料庫的 SQL Server 實例 (（可以是預設實例），或是您指定) 的命名實例。

如需 SQL Server 支援的詳細資訊，請參閱支援檔中的 [資料庫軟體和群集支援](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) 。 如需監控資料庫（包括監控資料庫的組合）的詳細資訊，請參閱支援檔中的[支援伺服器位置](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)、規劃檔和[SQL Server 資料](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)中的[監控](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)，以及部署檔中的記錄檔位置。

> [!NOTE]
> 若發行拓撲所用的帳戶具有適當的使用者權限，您可以在發行拓撲時建立監控資料庫。 您也可以之後再建立資料庫，包括在安裝程序中。 > 若要在 SQL Server 型伺服器上安裝及部署資料庫以進行監視，您必須是要安裝資料庫檔案之 SQL Server 之伺服器的 SQL Server 系統管理員群組成員。 如果您不是 SQL Server 系統管理員群組的成員，則必須要求加入至群組，直到部署資料庫檔案為止。 如果您無法成為系統管理員群組的成員，則應該為 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。 如需完成這些程式所需之使用者權利和許可權的詳細資訊，請參閱部署檔中的 [SQL Server 部署許可權](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) 。