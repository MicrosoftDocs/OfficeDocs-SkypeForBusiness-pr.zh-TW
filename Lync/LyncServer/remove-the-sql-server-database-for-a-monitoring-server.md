---
title: 移除監控伺服器的 SQL Server 資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdb2888a6c3dc7cc5dd4e3b77b70310a405f607d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>移除監控伺服器的 SQL Server 資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

移除 Microsoft Lync Server 2010 監視伺服器之後，您可以移除託管伺服器資料的 SQL Server 資料庫。 使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1.  在 Lync Server 2013 前端伺服器上，開啟 [拓撲建立器]。

2.  在拓撲建立器中，流覽至 [**共用元件**]，然後按一下 [ **sql server 商店**]，以滑鼠右鍵按一下與已移除或重新配置之監視伺服器相關聯的 SQL Server 實例，然後按一下 [**刪除**]。

3.  發佈拓撲，然後檢查 [複製狀態]。

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>從 SQL Server 移除資料庫檔案

1.  若要在 SQL Server 的伺服器上移除資料庫，您必須是您要移除資料庫檔案之 SQL Server 系統管理員群組的成員。

2.  開啟 Lync Server 管理命令介面。

3.  在命令列中，輸入下列內容：
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中\<FQDN\>是資料庫伺服器的完整功能變數名稱（fqdn），而\<實例\>是選用的命名資料庫實例。

4.  當**CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按**Y** （或按 enter）繼續，或按 N，然後按**N** ，然後輸入您是否要停止 Cmdlet （也就是在發生錯誤時）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

