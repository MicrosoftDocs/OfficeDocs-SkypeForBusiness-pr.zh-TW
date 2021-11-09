---
title: 新增前端 SQL Server 存放區
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Standard Edition server 部署會自動安裝必要的 Microsoft SQL Server Express 資料庫軟體和 SQL Server 資料庫。 因此，所有選項都會預先填入，您無法變更預設設定。
ms.openlocfilehash: eaa6b6f313632fe3b0acfc5d89a0117978cced42
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835711"
---
# <a name="add-front-end-sql-server-store"></a>新增前端 SQL Server 存放區

Standard Edition server 部署會自動安裝必要的 Microsoft SQL Server Express 資料庫軟體和 SQL Server 資料庫。 因此，所有選項都會預先填入，您無法變更預設設定。

Enterprise Edition 伺服器部署的前端集區需要後端資料庫的支援64位版本 SQL Server 資料庫軟體。 您可以選取先前定義的 SQL Server 資料庫，以用於後端資料庫。或者，您可以指定 SQL Server 資料庫所在之伺服器的完整功能變數名稱 (FQDN) ，也可以定義新的 SQL Server 資料庫，而您想要用於新 SQL Server 資料庫的 SQL Server 實例（可以是預設實例，或是指定的命名實例） (。 您也可以選擇啟用 SQL Server 儲存區上的鏡像，並指定自動容錯移轉的鏡像見證。

如需 SQL Server 支援的詳細資訊，請參閱支援檔中的[資料庫軟體和群集支援](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support)。 如需設定後端資料庫 SQL Server 的詳細資訊，請參閱部署檔中的[Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server) 。

> [!NOTE]
> 若發行拓朴所用的帳戶具有適當的使用者權限，您可以在發行拓撲時，建立後端資料庫 (即時通訊 (RTC) ) 。 您也可以之後再建立資料庫，包括在安裝程序中。

> [!NOTE]
> 若要在 Enterprise Edition 部署的 SQL Server 服務器上安裝及部署資料庫，您必須是要安裝資料庫檔案之 SQL Server 服務器的 SQL Server 系統管理員群組成員。 如果您不是 SQL Server 系統管理員群組的成員，則必須要求加入至群組，直到部署資料庫檔案為止。 如果您無法成為系統管理員群組的成員，則應該為您的 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。 如需完成程式所需之使用者權利和許可權的詳細資訊，請參閱[SQL Server 的部署許可權](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。