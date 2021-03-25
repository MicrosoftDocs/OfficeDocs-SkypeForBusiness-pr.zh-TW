---
title: 新增前端 SQL Server 存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Standard Edition server 部署會自動安裝必要的 Microsoft SQL Server Express 資料庫軟體和 SQL Server 資料庫。 因此，所有選項都會預先填入，您無法變更預設設定。
ms.openlocfilehash: e369f58afd015953cf0b58ca9788965a4829fd16
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119732"
---
# <a name="add-front-end-sql-server-store"></a>新增前端 SQL Server 存放區

Standard Edition server 部署會自動安裝必要的 Microsoft SQL Server Express 資料庫軟體和 SQL Server 資料庫。 因此，所有選項都會預先填入，您無法變更預設設定。

Enterprise Edition server 部署的前端集區需要支援後端資料庫的64位版本的 SQL Server 資料庫軟體。 您可以選取先前定義的 SQL Server 資料庫，以用於後端資料庫。或定義新的 SQL Server 資料庫，方法是指定要在其上放置 SQL Server 資料庫之伺服器的 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL SERVER 實例（可以是預設實例），或是您指定)  (的命名實例。 您也可以選擇啟用 SQL Server 儲存區上的鏡像，並指定自動容錯移轉的鏡像見證。

如需 SQL Server 支援的詳細資訊，請參閱支援檔中的 [資料庫軟體和群集支援](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) 。 如需針對後端資料庫設定 SQL Server 的詳細資訊，請參閱部署檔中的 [CONFIGURE Sql server For Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) 。

> [!NOTE]
> 若發行拓朴所用的帳戶具有適當的使用者權限，您可以在發行拓撲時，建立後端資料庫 (即時通訊 (RTC) ) 。 您也可以之後再建立資料庫，包括在安裝程序中。

> [!NOTE]
> 若要在適用于企業版的 SQL server 伺服器上安裝及部署資料庫，您必須是要安裝資料庫檔案之 SQL server 之伺服器的 SQL Server 系統管理員群組成員。 如果您不是 SQL Server 系統管理員群組的成員，則必須要求加入至群組，直到部署資料庫檔案為止。 如果您無法成為系統管理員群組的成員，則應該為 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。 如需完成程式所需之使用者權利和許可權的詳細資訊，請參閱 [SQL Server 的部署許可權](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。