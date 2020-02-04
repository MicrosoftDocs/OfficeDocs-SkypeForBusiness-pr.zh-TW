---
title: 新增前端封存存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: 封存需要 Microsoft SQL Server 資料庫軟體支援的64位版本，才能儲存歸檔資料。 您可以選取先前定義的 SQL Server 資料庫來進行封存，或透過指定 sql Server 資料庫所駐留之伺服器的完整功能變數名稱（FQDN），以及 SQL Se 的實例來定義新的 SQL Server 資料庫。您想要用於新的 SQL Server 資料庫的 rver （可以是預設實例，或是您指定的命名實例）。
ms.openlocfilehash: d5ef47dd0df4063ce92b7c4adad955596e776f50
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702938"
---
# <a name="add-front-end-archiving-store"></a>新增前端封存存放區

封存需要 Microsoft SQL Server 資料庫軟體支援的64位版本，才能儲存歸檔資料。 您可以選取先前定義的 SQL Server 資料庫來進行封存，或透過指定 sql Server 資料庫所駐留之伺服器的完整功能變數名稱（FQDN），以及 SQL Se 的實例來定義新的 SQL Server 資料庫。您想要用於新的 SQL Server 資料庫的 rver （可以是預設實例，或是您指定的命名實例）。

> [!NOTE]
> 如果用於發佈拓朴的帳戶具有適當的使用者權利和許可權，您可以在發佈拓撲時建立監視資料庫。 您也可以在稍後建立資料庫，並將它納入安裝程式的一部分。

> [!NOTE]
> 若要在進行監視的 SQL Server server 伺服器上安裝及部署資料庫，您必須是安裝資料庫檔案之 SQL server 系統管理員群組的成員。 如果您不是 SQL Server 系統管理員群組的成員，您必須先將其新增至群組，直到部署資料庫檔案。 如果您無法成為系統管理員群組的成員，您應該使用腳本來提供您的 SQL Server 資料庫系統管理員，以設定及部署資料庫。 如需有關完成程式所需的使用者權利和許可權的詳細資訊，請參閱部署檔中的[SQL Server 部署許可權](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


