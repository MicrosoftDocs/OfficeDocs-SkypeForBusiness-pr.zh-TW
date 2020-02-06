---
title: 新增前端 SQL Server 存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: 標準版伺服器部署會自動安裝所需的 Microsoft SQL Server Express 資料庫軟體與 SQL Server 資料庫。 因此，所有選項都會預先填入，而且您無法變更預設設定。
ms.openlocfilehash: 58b0af996e418a3db5852571cec6fa82380dde76
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798510"
---
# <a name="add-front-end-sql-server-store"></a>新增前端 SQL Server 存放區

標準版伺服器部署會自動安裝所需的 Microsoft SQL Server Express 資料庫軟體與 SQL Server 資料庫。 因此，所有選項都會預先填入，而且您無法變更預設設定。

企業版 server 部署的前端池需要後端資料庫的 SQL Server 資料庫軟體支援的64位版本。 您可以選取先前定義的 SQL Server 資料庫，以用於後端資料庫，或指定新的 SQL Server 資料庫，方法是指定要存放 SQL Server 資料庫之伺服器的完整功能變數名稱（FQDN），以及 SQL S 的實例您想要用於新的 SQL Server 資料庫的 erver （可以是預設實例，或是您指定的命名實例）。 您也可以選擇在 SQL Server 網上商店啟用鏡像，並指定自動容錯移轉的鏡像見證。

如需有關 SQL Server 支援的詳細資訊，請參閱支援檔中的[資料庫軟體和群集支援](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。 如需有關為後端資料庫設定 SQL Server 的詳細資訊，請參閱部署檔中的[[設定 Sql server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) ]。

> [!NOTE]
> 如果用於發佈拓朴的帳戶具有適當的使用者權利和許可權，您可以在發佈拓撲時建立後端資料庫（即時通訊（RTC））。 您也可以日後建立資料庫，包括安裝程式的一部分。

> [!NOTE]
> 若要在部署企業版的 SQL Server 服務器上安裝及部署資料庫，您必須是您安裝資料庫檔案之 SQL server 系統管理員群組的成員。 如果您不是 SQL Server 系統管理員群組的成員，您必須要求將資料庫檔案部署之後，才能將其新增至群組中。 如果您無法成為系統管理員群組的成員，您應該使用腳本來提供您的 SQL Server 資料庫系統管理員，以設定及部署資料庫。 如需有關完成程式所需的使用者權利和許可權的詳細資訊，請參閱[SQL Server 的部署許可權](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


