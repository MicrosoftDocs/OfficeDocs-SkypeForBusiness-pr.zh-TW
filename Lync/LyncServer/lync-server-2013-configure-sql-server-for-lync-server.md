---
title: Lync Server 2013：設定 Lync Server 的 SQL Server
description: Lync Server 2013：設定 Lync Server 的 SQL Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9ac7d8f14c64f3b7935df3f48602a6df1791c7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576719"
---
# <a name="configure-sql-server-for-lync-server-2013"></a>針對 Lync Server 2013 設定 SQL Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-08-12_

本節中的主題將討論如何部署及設定要在 Lync Server 的企業部署中使用的 SQL Server。 Standard Edition server 使用適合 Standard Edition Server 工作負載大小的 sql server Express 版本的 SQL Server Express 版本。

Lync Server 2013 中央管理存放區保留集區中所有 Enterprise Edition 伺服器的使用者資料，且設計為位於以 SQL Server 為基礎的後端伺服器上。 集中式存放庫會將中央管理存放區與任何其他 Lync Server 2013 角色安裝在相同的電腦上。 中央管理存放區不可位於集區中的 Enterprise Edition 伺服器上。 當您第一次發行拓撲並選取建立資料庫時，會自動建立中央管理存放區。 指定為後端伺服器的電腦必須已執行 SQL Server 資料庫軟體，安裝才能成功。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 的 SQL Server 資料和記錄檔位置](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [在 Lync Server 2013 中設定 SQL Server](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013 中 SQL Server 的部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [在 Lync Server 2013 中使用 Lync Server 管理命令介面安裝資料庫](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [瞭解具有 Lync Server 2013 之 SQL Server 的防火牆需求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [設定 Lync Server 2013 的 SQL Server 叢集](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

