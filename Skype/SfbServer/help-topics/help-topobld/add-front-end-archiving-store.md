---
title: 新增前端封存存放區
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 封存需要支援的64位版本的 Microsoft SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫，以用於封存，或透過指定 SQL Server 資料庫所在之伺服器的 FQDN)  (FQDN 來定義新的 SQL Server 資料庫，以及您想要用於新的 SQL Server 實例。SQL Server 資料庫 (可以是預設實例，或是您指定) 的命名實例。
ms.openlocfilehash: 177b2c386ea63bed6b58d4b332ab8f552bb82c1e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399157"
---
# <a name="add-front-end-archiving-store"></a>新增前端封存存放區

封存需要支援的64位版本的 Microsoft SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫，以用於封存，或透過指定 SQL Server 資料庫所在之伺服器的 FQDN)  (FQDN 來定義新的 SQL Server 資料庫，以及您想要用於新的 SQL Server 實例。SQL Server 資料庫 (可以是預設實例，或是您指定) 的命名實例。

> [!NOTE]
> 若發行拓撲所用的帳戶具有適當的使用者權限，您可以在發行拓撲時建立監控資料庫。 您也可以稍後再建立資料庫（包括安裝程式的一部分）。

> [!NOTE]
> 若要在 SQL Server 的伺服器上安裝及部署資料庫以進行監視，您必須是要安裝資料庫檔案之 SQL Server 服務器的 SQL Server 系統管理員群組成員。 如果您不是 SQL Server sysadmin 群組的成員，則必須先要求您新增至群組，直到部署資料庫檔案為止。 如果您無法成為系統管理員群組的成員，則應該為您的 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。 如需您完成程序所需之使用者權利和權限的詳細資訊，請參閱部署文件中的＜[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)＞。