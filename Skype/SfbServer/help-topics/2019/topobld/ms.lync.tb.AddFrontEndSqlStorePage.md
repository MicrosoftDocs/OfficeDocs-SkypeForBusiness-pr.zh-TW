---
title: 新增前端 SQL Server 存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Standard Edition server 部署會自動安裝必要的 Microsoft SQL Server Express 資料庫軟體和 SQL Server 資料庫。 因此，所有選項都會預先填入，您無法變更預設設定。
ms.openlocfilehash: d1a3fd6a27ab6229f84e8b74259be6a2da7652f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811623"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="c1f20-104">新增前端 SQL Server 存放區</span><span class="sxs-lookup"><span data-stu-id="c1f20-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="c1f20-105">Standard Edition server 部署會自動安裝必要的 Microsoft SQL Server Express 資料庫軟體和 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="c1f20-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="c1f20-106">因此，所有選項都會預先填入，您無法變更預設設定。</span><span class="sxs-lookup"><span data-stu-id="c1f20-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="c1f20-107">Enterprise Edition server 部署的前端集區需要支援後端資料庫的64位版本的 SQL Server 資料庫軟體。</span><span class="sxs-lookup"><span data-stu-id="c1f20-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="c1f20-108">您可以選取先前定義的 SQL Server 資料庫，以用於後端資料庫。或定義新的 SQL Server 資料庫，方法是指定要在其上放置 SQL Server 資料庫之伺服器的 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL SERVER 實例（可以是預設實例），或是您指定)  (的命名實例。</span><span class="sxs-lookup"><span data-stu-id="c1f20-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="c1f20-109">您也可以選擇啟用 SQL Server 儲存區上的鏡像，並指定自動容錯移轉的鏡像見證。</span><span class="sxs-lookup"><span data-stu-id="c1f20-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="c1f20-110">如需 SQL Server 支援的詳細資訊，請參閱支援檔中的 [資料庫軟體和群集支援](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="c1f20-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="c1f20-111">如需針對後端資料庫設定 SQL Server 的詳細資訊，請參閱部署檔中的 [CONFIGURE SQL server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="c1f20-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="c1f20-112">若發行拓朴所用的帳戶具有適當的使用者權限及許可權，您可以在發行拓撲時，建立後端資料庫 (即時通訊 (RTC) # A3。</span><span class="sxs-lookup"><span data-stu-id="c1f20-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="c1f20-113">您也可以之後再建立資料庫，包括在安裝程序中。</span><span class="sxs-lookup"><span data-stu-id="c1f20-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="c1f20-114">若要在適用于企業版的 SQL server 伺服器上安裝及部署資料庫，您必須是要安裝資料庫檔案之 SQL server 之伺服器的 SQL Server 系統管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="c1f20-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="c1f20-115">如果您不是 SQL Server 系統管理員群組的成員，則必須要求加入至群組，直到部署資料庫檔案為止。</span><span class="sxs-lookup"><span data-stu-id="c1f20-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="c1f20-116">如果您無法成為系統管理員群組的成員，則應該為 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。</span><span class="sxs-lookup"><span data-stu-id="c1f20-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="c1f20-117">如需完成程式所需之使用者權利和許可權的詳細資訊，請參閱 [SQL Server 的部署許可權](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c1f20-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


