---
title: 移除前端集區的 SQL Server 資料庫
description: 移除前端集區的 SQL Server 資料庫。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c5d47e4c52197c5792fa3b7770da7bbd1b26cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551259"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>移除前端集區的 SQL Server 資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

移除 Microsoft Lync Server 2010 前端集區或重新設定集區以使用其他資料庫之後，您可以移除主控集區資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1.  從 Lync Server 2013 前端伺服器開啟拓撲產生器，並下載現有的拓撲。

2.  在 [拓撲產生器] 中，流覽至 [**共用元件**]，然後按一下 [ **Sql server 存放區**]，以滑鼠右鍵按一下與已移除或重新設定的前端集區相關聯的 SQL Server 實例，然後按一下 [**刪除**

3.  發行拓撲，然後檢查複寫狀態。

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>從 SQL Server 移除使用者和應用程式資料庫

1.  若要移除 SQL Server 上的資料庫，您必須是要移除資料庫檔案之 SQL Server 的 SQL Server sysadmins 群組成員。

2.  開啟 Lync Server 管理命令介面

3.  移除集區使用者存放區的資料庫，請輸入：
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中 \<FQDN\> 是資料庫伺服器的 FQDN) 的完整功能變數名稱 (，也就是 \<instance\> 指定的資料庫實例 (也就是說，如果有一個定義) 。

4.  移除集區應用程式存放區的資料庫，請輸入：
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中 \<FQDN\> 是資料庫伺服器的 FQDN，也 \<instance\> 就是指定的資料庫實例 (，也就是) 中已定義。

5.  當 **Uninstall-CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 **Y** (或按 Enter) 繼續作業，或是依序按 **N** 及 Enter 停止 Cmdlet (例如發生錯誤時)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

