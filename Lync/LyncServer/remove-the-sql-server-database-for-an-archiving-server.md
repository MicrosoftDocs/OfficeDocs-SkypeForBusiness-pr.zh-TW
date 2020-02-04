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
ms.openlocfilehash: 57a820780b7ca3646ba9fa6cc5d02a3c5022db9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>移除封存伺服器的 SQL Server 資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

移除 Microsoft Lync Server 2010 封存伺服器之後，您可以移除裝載該池資料的 SQL Server 資料庫。 使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1.  在 Lync Server 2013 前端伺服器上，開啟 [拓撲建立器]。

2.  在拓撲建立器中，流覽至 [**共用元件**]，然後按一下 [ **sql server 商店**]，以滑鼠右鍵按一下與已移除或重新配置的存檔伺服器相關的 SQL Server 實例，然後按一下 [**刪除**]。

3.  發佈拓撲，然後檢查 [複製狀態]。

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>從 SQL Server 移除資料庫檔案

1.  若要移除 SQL Server 上的資料庫，您必須是您要移除資料庫檔案之 SQL Server 的 SQL Server 系統管理員群組的成員。

2.  開啟 Lync Server 管理命令介面。

3.  在命令列中，輸入下列內容：
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<FQDN\>是資料庫伺服器的完整功能變數名稱（fqdn），而\<實例\>是命名的資料庫實例（也就是已定義）。

4.  當**CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按**Y** （或按 enter）繼續，或按 N，然後按**N** ，然後輸入您是否要停止 Cmdlet （也就是在發生錯誤時）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

