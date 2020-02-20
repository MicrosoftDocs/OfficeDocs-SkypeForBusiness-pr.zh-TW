---
title: 移除封存伺服器的 SQL Server 資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1891e9a0ab61a64f74e877722689ce1e4d25231
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>移除封存伺服器的 SQL Server 資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-04_

移除 Microsoft Lync Server 2010 封存伺服器之後，您可以移除裝載的集區資料的 SQL Server 資料庫。 使用下列程序從拓撲產生器中，移除定義]，然後從資料庫伺服器中移除的資料庫和記錄檔。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>若要移除使用拓撲產生器的 SQL Server 資料庫

1.  在 Lync Server 2013 前端伺服器上，開啟拓撲產生器]。

2.  在拓撲產生器中，瀏覽至**共用元件**] 後再按一下 [ **SQL Server 存放區**SQL Server 執行個體相關聯與已移除或重新設定封存伺服器，以滑鼠右鍵按一下，然後按一下 [**刪除**。

3.  發行拓撲，然後檢查複寫狀態。

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>從 SQL Server 移除資料庫檔案

1.  若要移除 SQL Server 上的資料庫，您必須是要移除資料庫檔案之 SQL Server 的 SQL Server sysadmins 群組成員。

2.  開啟 Lync Server 管理命令介面。

3.  在命令列輸入下列命令：
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<FQDN\>是完整的網域名稱 (FQDN) 的資料庫伺服器，以及\<執行個體\>（亦即，如果已定義） 是已命名的資料庫執行個體。

4.  當 **Uninstall-CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 **Y** (或按 Enter) 繼續作業，或是依序按 **N** 及 Enter 停止 Cmdlet (例如發生錯誤時)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

