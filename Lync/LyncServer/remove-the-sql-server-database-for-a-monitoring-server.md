---
title: 移除監控伺服器的 SQL Server 資料庫
description: 移除監控伺服器的 SQL Server 資料庫。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99bf734f0a9978fe14055fb36b01ce37f77e14a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570189"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>移除監控伺服器的 SQL Server 資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

移除 Microsoft Lync Server 2010 監控伺服器之後，您可以移除主控伺服器資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1.  在 Lync Server 2013 前端伺服器上，開啟拓撲產生器。

2.  在 [拓撲產生器] 中，流覽至 [**共用元件**]，然後按一下 [ **Sql server 存放區**]，以滑鼠右鍵按一下與已移除或已重新設定之監控伺服器關聯的 SQL Server 實例，然後按一下 [**刪除**

3.  發行拓撲，然後檢查複寫狀態。

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>從 SQL Server 移除資料庫檔案

1.  若要移除 SQL Server 之伺服器上的資料庫，您必須是要移除資料庫檔案之 SQL Server 的 SQL server 系統管理員群組成員。

2.  開啟 Lync Server 管理命令介面。

3.  在命令列輸入下列命令：
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    其中 \<FQDN\> 是資料庫伺服器的 FQDN) 的完整功能變數名稱 (，也 \<instance\> 就是選用的命名資料庫實例。

4.  當 **Uninstall-CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 **Y** (或按 Enter) 繼續作業，或是依序按 **N** 及 Enter 停止 Cmdlet (例如發生錯誤時)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

