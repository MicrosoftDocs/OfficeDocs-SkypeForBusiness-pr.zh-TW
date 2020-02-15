---
title: 移除前端集區的 SQL Server 資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a6aba3f084be6c40d5019af5da37f1a682f6eb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>移除前端集區的 SQL Server 資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

在您移除 Microsoft Lync Server 2010 前端集區或重新設定要使用不同的資料庫之集區之後，您可以移除裝載的集區資料的 SQL Server 資料庫。 使用下列程序從拓撲產生器中，移除定義]，然後從資料庫伺服器中移除的資料庫和記錄檔。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>若要移除使用拓撲產生器的 SQL Server 資料庫

1.  從 Lync Server 2013 前端伺服器，開啟拓撲產生器，並下載現有的拓撲。

2.  在拓撲產生器中，瀏覽至**共用元件**] 後再按一下 [ **SQL Server 存放區**移除或重新設定前端集區，相關聯的 SQL Server 執行個體上按一下滑鼠右鍵，然後按一下 [**刪除**。

3.  發行拓撲，然後檢查複寫狀態。

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>從 SQL Server 移除使用者和應用程式資料庫

1.  若要移除 SQL Server 上的資料庫，您必須是要移除資料庫檔案之 SQL Server 的 SQL Server sysadmins 群組成員。

2.  開啟 Lync Server 管理命令介面

3.  移除集區使用者存放區的資料庫，請輸入：
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<FQDN\>是完整的網域名稱 (FQDN) 的資料庫伺服器，以及\<執行個體\>（亦即，如果已定義） 是已命名的資料庫執行個體。

4.  移除集區應用程式存放區的資料庫，請輸入：
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<FQDN\>是資料庫伺服器的 FQDN 和\<執行個體\>（亦即，如果已定義） 是已命名的資料庫執行個體。

5.  當 **Uninstall-CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 **Y** (或按 Enter) 繼續作業，或是依序按 **N** 及 Enter 停止 Cmdlet (例如發生錯誤時)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

