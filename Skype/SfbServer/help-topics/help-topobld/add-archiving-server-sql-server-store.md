---
title: 新增封存伺服器 SQL Server 儲存區
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 封存伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫，用以封存或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的完整功能變數名稱 (FQDN) ，以及想要用於新 SQL Server 的 SQL Server 實例。 資料庫 (可以是您指定) 的預設實例或命名實例。
ms.openlocfilehash: a0f2b40bcf5d24063c689bbc760a57b14b98ad28
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832197"
---
# <a name="add-archiving-server-sql-server-store"></a>新增封存伺服器 SQL Server 儲存區

封存伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫，用以封存或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的完整功能變數名稱 (FQDN) ，以及想要用於新 SQL Server 的 SQL Server 實例。 資料庫 (可以是您指定) 的預設實例或命名實例。

> [!NOTE]
> 如果用來發行拓撲的帳戶有適當的使用者權利和權限，您可以在發行拓撲時建立封存資料庫 (LcsLog)。您也可以之後再建立資料庫，作為安裝程序或其他程序的一部分。

> [!NOTE]
> 若要在 SQL Server 型伺服器上安裝及部署資料庫以進行封存，您必須是要安裝資料庫檔案之 SQL Server 服務器的 SQL Server 系統管理員群組成員。 如果您不是 SQL Server 系統管理員群組的成員，則必須要求加入至群組，直到部署資料庫檔案為止。 如果您無法成為系統管理員群組的成員，則應該為您的 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。 如需您完成程序所需之使用者權利和權限的詳細資訊，請參閱部署文件中的＜[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)＞。