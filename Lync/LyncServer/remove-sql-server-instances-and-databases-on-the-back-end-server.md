---
title: 移除後端伺服器上的 SQL Server 執行個體與資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>移除後端伺服器上的 SQL Server 執行個體與資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

移除伺服器上執行 Lync Server 2010 的伺服器之後，或當您將執行 Lync Server 2010 的伺服器重新設定為使用另一個資料庫之後，就會移除 Microsoft SQL Server 資料庫和實例。 當您淘汰目前的 SQL Server，或重新設定執行 Lync Server 2010 的目前伺服器時，您必須執行本主題中的程式，讓它呈現的資料庫過時或無法使用。

若要移除存檔伺服器或監視伺服器的資料庫或實例，您必須先移除伺服器角色。 同樣地，若要移除前臺端池的實例或資料庫，您必須先移除或重新設定相依伺服器角色。 這些程式不會區分 collocated 資料庫或伺服器的個別實例。 程式不會受到資料庫 collocation 的影響。

<div>

## <a name="in-this-section"></a>本節內容

  - [移除前端集區的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [移除監控伺服器的 SQL Server 資料庫](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [移除封存伺服器的 SQL Server 資料庫](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

