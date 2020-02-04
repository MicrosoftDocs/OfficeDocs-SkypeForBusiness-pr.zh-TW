---
title: Lync Server 2013：為 Lync Server 2013 設定 SQL Server
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
ms.openlocfilehash: efdd9d8fa7b010b420c7c532d422c9b52b6d69ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>為 Lync Server 2013 設定 SQL Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-08-12_

本節中的主題將討論如何部署和設定 SQL Server，以便在 Lync Server 的企業部署中使用。 標準版伺服器使用 collocated SQL Server Express 版本的 SQL Server Express 版本，適合標準版伺服器的工作負載。

Lync Server 2013 中央管理存放區保留一個池中所有企業版伺服器的使用者資料，且專門設計為位於 SQL Server 的後端伺服器上。 在集中式儲存庫中，中央管理儲存區無法與任何其他 Lync Server 2013 角色安裝在同一部電腦上。 中央管理儲存庫無法存放在池中的企業版伺服器上。 當您第一次發佈拓撲時，系統會自動建立中央管理儲存區，然後選取以建立資料庫。 您指定為後端伺服器的電腦必須已執行 SQL Server 資料庫軟體，才能成功安裝。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 的 SQL Server 資料和記錄檔位置](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [在 Lync Server 2013 中設定 SQL Server](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013 中 SQL Server 的部署權限](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [在 Lync Server 2013 中使用 Lync Server 管理命令介面安裝資料庫](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [瞭解與 Lync Server 2013 搭配使用時之 SQL Server 的防火牆需求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [設定 Lync Server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

