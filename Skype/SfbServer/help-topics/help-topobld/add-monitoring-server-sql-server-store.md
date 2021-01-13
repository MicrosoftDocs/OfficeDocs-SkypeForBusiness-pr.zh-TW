---
title: 新增監控伺服器 SQL Server 存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 監控伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存監控資料。 您可以選取先前定義的 SQL Server 資料庫，以用於監控，或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的 (FQDN) ，也就是您想要用於新 SQL Server 資料庫的 SQL Server 實例 (（可以是預設實例），或是您指定) 的命名實例。
ms.openlocfilehash: 53e8a95b179c3e15f52b694710248b5155ef8d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828693"
---
# <a name="add-monitoring-server-sql-server-store"></a><span data-ttu-id="321e5-104">新增監控伺服器 SQL Server 存放區</span><span class="sxs-lookup"><span data-stu-id="321e5-104">Add Monitoring Server SQL Server Store</span></span>

<span data-ttu-id="321e5-105">監控伺服器需要支援的64位版本的 SQL Server 資料庫軟體才能儲存監控資料。</span><span class="sxs-lookup"><span data-stu-id="321e5-105">Monitoring Server requires a supported 64-bit edition of SQL Server database software to store the monitoring data.</span></span> <span data-ttu-id="321e5-106">您可以選取先前定義的 SQL Server 資料庫，以用於監控，或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的 (FQDN) ，也就是您想要用於新 SQL Server 資料庫的 SQL Server 實例 (（可以是預設實例），或是您指定) 的命名實例。</span><span class="sxs-lookup"><span data-stu-id="321e5-106">You can either select a previously defined SQL Server database to be used for monitoring, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

<span data-ttu-id="321e5-107">如需 SQL Server 支援的詳細資訊，請參閱支援檔中的 [資料庫軟體和群集支援](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="321e5-107">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="321e5-108">如需監控資料庫（包括監控資料庫的組合）的詳細資訊，請參閱支援檔中的[支援伺服器位置](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)、規劃檔和[SQL Server 資料](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)中的[監控](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)，以及部署檔中的記錄檔位置。</span><span class="sxs-lookup"><span data-stu-id="321e5-108">For details about the monitoring database, including collocation of the monitoring database, see [Supported Server Location](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation,[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="321e5-109">若發行拓撲所用的帳戶具有適當的使用者權限，您可以在發行拓撲時建立監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="321e5-109">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="321e5-110">您也可以之後再建立資料庫，包括在安裝程序中。</span><span class="sxs-lookup"><span data-stu-id="321e5-110">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="321e5-111">> 若要在 SQL Server 型伺服器上安裝及部署資料庫以進行監視，您必須是要安裝資料庫檔案之 SQL Server 之伺服器的 SQL Server 系統管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="321e5-111">> To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="321e5-112">如果您不是 SQL Server 系統管理員群組的成員，則必須要求加入至群組，直到部署資料庫檔案為止。</span><span class="sxs-lookup"><span data-stu-id="321e5-112">If you are not a member of the SQL Server sysadmin group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="321e5-113">如果您無法成為系統管理員群組的成員，則應該為 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。</span><span class="sxs-lookup"><span data-stu-id="321e5-113">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="321e5-114">如需完成這些程式所需之使用者權利和許可權的詳細資訊，請參閱部署檔中的 [SQL Server 部署許可權](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="321e5-114">For details about the user rights and permissions that you need to accomplish these procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


