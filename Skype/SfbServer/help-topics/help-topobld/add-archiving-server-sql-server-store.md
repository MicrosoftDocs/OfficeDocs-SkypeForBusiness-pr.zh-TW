---
title: 新增封存伺服器 SQL Server 儲存區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 封存伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫來封存，或定義新的 SQL server 資料庫，方法是指定 SQL Server 資料庫所在伺服器的完整功能變數名稱 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL Server 實例 (（可以是) 指定的預設實例或命名實例）。
ms.openlocfilehash: eb25152916c61ff40274705a408fe0a7a618cbcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217434"
---
# <a name="add-archiving-server-sql-server-store"></a>新增封存伺服器 SQL Server 儲存區

封存伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫來封存，或定義新的 SQL server 資料庫，方法是指定 SQL Server 資料庫所在伺服器的完整功能變數名稱 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL Server 實例 (（可以是) 指定的預設實例或命名實例）。

> [!NOTE]
> 如果用來發行拓撲的帳戶有適當的使用者權利和權限，您可以在發行拓撲時建立封存資料庫 (LcsLog)。您也可以之後再建立資料庫，作為安裝程序或其他程序的一部分。

> [!NOTE]
> 若要在以 SQL Server 為基礎的伺服器上安裝及部署資料庫，您必須是要安裝資料庫檔案之 SQL server 的伺服器的 SQL Server 系統管理員群組成員。 如果您不是 SQL Server 系統管理員群組的成員，則必須要求加入至群組，直到部署資料庫檔案為止。 如果您無法成為系統管理員群組的成員，則應該為 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。 如需您完成程序所需之使用者權利和權限的詳細資訊，請參閱部署文件中的＜[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)＞。


