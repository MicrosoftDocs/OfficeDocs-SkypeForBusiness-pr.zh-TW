---
title: 新增封存伺服器 SQL Server 存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 封存伺服器需要支援的64位版本的 SQL Server 資料庫軟體，才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫來進行封存或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫將駐留之伺服器的完整功能變數名稱（FQDN），以及 SQL Server 實例（您想要用於新的 SQL Server 資料庫（可以是您指定的預設實例或命名實例）。
ms.openlocfilehash: d4fcb526abf0eb1ef961f5790b574a9f30a80b87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821285"
---
# <a name="add-archiving-server-sql-server-store"></a>新增封存伺服器 SQL Server 存放區

封存伺服器需要支援的64位版本的 SQL Server 資料庫軟體，才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫來進行封存或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫將駐留之伺服器的完整功能變數名稱（FQDN），以及 SQL Server 實例（您想要用於新的 SQL Server 資料庫（可以是您指定的預設實例或命名實例）。

> [!NOTE]
> 如果用於發佈拓朴的帳戶具有適當的使用者權利和許可權，您可以在發佈拓撲時建立封存資料庫（LcsLog）。 您也可以日後建立資料庫，做為安裝程式的一部分，或其他方式。

> [!NOTE]
> 若要在要存檔的 SQL Server server 伺服器上安裝及部署資料庫，您必須是安裝資料庫檔案之 SQL server 系統管理員群組的成員。 如果您不是 SQL Server 系統管理員群組的成員，您必須要求將資料庫檔案部署之後，才能將其新增至群組中。 如果您無法成為系統管理員群組的成員，您應該使用腳本來提供您的 SQL Server 資料庫系統管理員，以設定及部署資料庫。 如需有關完成程式所需的使用者權利和許可權的詳細資訊，請參閱部署檔中的[SQL Server 部署許可權](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


