---
title: 新增前端封存存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 封存需要 Microsoft SQL Server 資料庫軟體支援的64位版本，才能儲存歸檔資料。 您可以選取先前定義的 SQL Server 資料庫來進行封存，或透過指定 sql Server 資料庫所駐留之伺服器的完整功能變數名稱（FQDN），以及 SQL Se 的實例來定義新的 SQL Server 資料庫。您想要用於新的 SQL Server 資料庫的 rver （可以是預設實例，或是您指定的命名實例）。
ms.openlocfilehash: e315e27ddb96d018ca0bead13564ad88e944cd34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820925"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="f3fc4-104">新增前端封存存放區</span><span class="sxs-lookup"><span data-stu-id="f3fc4-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="f3fc4-105">封存需要 Microsoft SQL Server 資料庫軟體支援的64位版本，才能儲存歸檔資料。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="f3fc4-106">您可以選取先前定義的 SQL Server 資料庫來進行封存，或透過指定 sql Server 資料庫所駐留之伺服器的完整功能變數名稱（FQDN），以及 SQL Se 的實例來定義新的 SQL Server 資料庫。您想要用於新的 SQL Server 資料庫的 rver （可以是預設實例，或是您指定的命名實例）。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="f3fc4-107">如果用於發佈拓朴的帳戶具有適當的使用者權利和許可權，您可以在發佈拓撲時建立監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="f3fc4-108">您也可以在稍後建立資料庫，並將它納入安裝程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="f3fc4-109">若要在進行監視的 SQL Server server 伺服器上安裝及部署資料庫，您必須是安裝資料庫檔案之 SQL server 系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="f3fc4-110">如果您不是 SQL Server 系統管理員群組的成員，您必須先將其新增至群組，直到部署資料庫檔案。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="f3fc4-111">如果您無法成為系統管理員群組的成員，您應該使用腳本來提供您的 SQL Server 資料庫系統管理員，以設定及部署資料庫。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="f3fc4-112">如需有關完成程式所需的使用者權利和許可權的詳細資訊，請參閱部署檔中的[SQL Server 部署許可權](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


