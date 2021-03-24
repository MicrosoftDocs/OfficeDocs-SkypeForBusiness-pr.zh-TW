---
title: 新增前端封存存放區
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 封存需要支援的64位版本的 Microsoft SQL Server 資料庫軟體才能儲存封存資料。 您可以選取先前定義的 SQL Server 資料庫，以用於封存。或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL SERVER 實例（可以是預設實例），或指定 () 所指定實例的名稱。
ms.openlocfilehash: 9f3ee74944ca19f827229bcfcaea2a1e37d2bfcb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107839"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="62c0c-104">新增前端封存存放區</span><span class="sxs-lookup"><span data-stu-id="62c0c-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="62c0c-105">封存需要支援的64位版本的 Microsoft SQL Server 資料庫軟體才能儲存封存資料。</span><span class="sxs-lookup"><span data-stu-id="62c0c-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="62c0c-106">您可以選取先前定義的 SQL Server 資料庫，以用於封存。或定義新的 SQL Server 資料庫，方法是指定 SQL Server 資料庫所在之伺服器的 (FQDN) ，以及您想要用於新 SQL Server 資料庫的 SQL SERVER 實例（可以是預設實例），或指定 () 所指定實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="62c0c-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="62c0c-107">若發行拓撲所用的帳戶具有適當的使用者權限，您可以在發行拓撲時建立監控資料庫。</span><span class="sxs-lookup"><span data-stu-id="62c0c-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="62c0c-108">您也可以稍後再建立資料庫（包括安裝程式的一部分）。</span><span class="sxs-lookup"><span data-stu-id="62c0c-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="62c0c-109">若要在以 SQL Server 為基礎的伺服器上安裝及部署資料庫，您必須是要安裝資料庫檔案之 SQL server 的伺服器的 SQL Server 系統管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="62c0c-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="62c0c-110">如果您不是 SQL Server 系統管理員群組的成員，則必須要求您新增至群組，直到部署資料庫檔案為止。</span><span class="sxs-lookup"><span data-stu-id="62c0c-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="62c0c-111">如果您無法成為系統管理員群組的成員，則應該為 SQL Server 資料庫管理員提供腳本，以設定及部署資料庫。</span><span class="sxs-lookup"><span data-stu-id="62c0c-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="62c0c-112">如需您完成程序所需之使用者權利和權限的詳細資訊，請參閱部署文件中的＜[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)＞。</span><span class="sxs-lookup"><span data-stu-id="62c0c-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>