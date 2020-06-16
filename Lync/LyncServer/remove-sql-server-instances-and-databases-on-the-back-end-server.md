---
title: 移除後端伺服器上的 SQL Server 執行個體與資料庫
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbd5a681be1395038116be32b3267be07213af1b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>移除後端伺服器上的 SQL Server 執行個體與資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

移除 Microsoft SQL Server 資料庫和實例之後，請移除執行 Lync Server 2010 的伺服器，或重新設定執行 Lync Server 2010 的伺服器以使用另一個資料庫之後。 當您淘汰目前的 SQL Server 或重新設定執行 Lync Server 2010 的目前伺服器時，您必須執行本主題中的程式，這樣一來，它會使資料庫過時或無法使用。

若要移除封存伺服器或監控伺服器的資料庫或實例，必須先移除伺服器角色。 同樣地，若要移除前端集區的實例或資料庫，您必須先移除或重新設定從屬伺服器角色。 不論是針對伺服器的組合資料庫或個別執行個體，這些程序都是一樣的。 組合資料庫並不會影響這些程序。

<div>

## <a name="in-this-section"></a>本章節內容

  - [移除前端集區的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [移除監控伺服器的 SQL Server 資料庫](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [移除封存伺服器的 SQL Server 資料庫](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

