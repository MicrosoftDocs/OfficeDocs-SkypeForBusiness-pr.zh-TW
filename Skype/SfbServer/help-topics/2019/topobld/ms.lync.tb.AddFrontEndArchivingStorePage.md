---
title: 新增前端封存存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: 封存需要支援的64位版本的 Microsoft SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫，以用於封存。或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL SERVER 實例（可以是預設實例），或指定 () 所指定實例的名稱。
ms.openlocfilehash: a0a9528b141730da91d233774a6c676956c9b19b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833523"
---
# <a name="add-front-end-archiving-store"></a>新增前端封存存放區

封存需要支援的64位版本的 Microsoft SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫，以用於封存。或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL SERVER 實例（可以是預設實例），或指定 () 所指定實例的名稱。

> [!NOTE]
> 若發行拓撲所用的帳戶具有適當的使用者權限，您可以在發行拓撲時建立監控資料庫。 您也可以稍後再建立資料庫（包括安裝程式的一部分）。

> [!NOTE]
> 若要在以 SQL Server 為基礎的伺服器上安裝及部署資料庫，您必須是要安裝資料庫檔案之 SQL server 的伺服器的 SQL Server 系統管理員群組成員。 如果您不是 SQL Server 系統管理員群組的成員，則必須要求您新增至群組，直到部署資料庫檔案為止。 如果您無法成為系統管理員群組的成員，則應該為 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。 如需您完成程序所需之使用者權利和權限的詳細資訊，請參閱部署文件中的＜[Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)＞。


