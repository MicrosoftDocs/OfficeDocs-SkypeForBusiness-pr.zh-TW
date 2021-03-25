---
title: 新增封存伺服器 SQL Server 儲存區
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
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: 封存伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫來封存，或定義新的 SQL server 資料庫，方法是指定 SQL Server 資料庫所在伺服器的完整功能變數名稱 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL Server 實例 (（可以是) 指定的預設實例或命名實例）。
ms.openlocfilehash: 813b6f75db61153c704d2300341cac28bd16cc3c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119832"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="d1abd-104">新增封存伺服器 SQL Server 儲存區</span><span class="sxs-lookup"><span data-stu-id="d1abd-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="d1abd-105">封存伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存封存資料。</span><span class="sxs-lookup"><span data-stu-id="d1abd-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="d1abd-106">您可以選取先前定義的 SQL Server 資料庫來封存，或定義新的 SQL server 資料庫，方法是指定 SQL Server 資料庫所在伺服器的完整功能變數名稱 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL Server 實例 (（可以是) 指定的預設實例或命名實例）。</span><span class="sxs-lookup"><span data-stu-id="d1abd-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="d1abd-p103">如果用來發行拓撲的帳戶有適當的使用者權利和權限，您可以在發行拓撲時建立封存資料庫 (LcsLog)。您也可以之後再建立資料庫，作為安裝程序或其他程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="d1abd-p103">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology. You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="d1abd-109">若要在以 SQL Server 為基礎的伺服器上安裝及部署資料庫，您必須是要安裝資料庫檔案之 SQL server 的伺服器的 SQL Server 系統管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="d1abd-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="d1abd-110">如果您不是 SQL Server 系統管理員群組的成員，則必須要求加入至群組，直到部署資料庫檔案為止。</span><span class="sxs-lookup"><span data-stu-id="d1abd-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="d1abd-111">如果您無法成為系統管理員群組的成員，則應該為 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。</span><span class="sxs-lookup"><span data-stu-id="d1abd-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="d1abd-112">如需您完成程序所需之使用者權利和權限的詳細資訊，請參閱部署文件中的＜[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)＞。</span><span class="sxs-lookup"><span data-stu-id="d1abd-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>