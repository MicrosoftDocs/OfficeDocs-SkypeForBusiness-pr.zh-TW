---
title: Lync Server 2013： 設定 Lync Server 的 SQL Server
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
ms.openlocfilehash: 77f6357d38731438555b2c9e3af7ec6a22e9df7c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>針對 Lync Server 2013 設定 SQL Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-08-12_

本節中的主題將討論如何部署及設定 SQL Server 在 Lync Server 的企業部署中使用。 Standard Edition 伺服器使用是正確的 Standard Edition server 的工作負載的長條調整大小的 SQL Server 組合的 SQL Server Express 的版本。

Lync Server 2013 中央管理存放區中集區]，會保留所有 Enterprise Edition server 的使用者資料，而且設計來位於 SQL Server-型後端伺服器。 為集中存放庫，無法與任何其他的 Lync Server 2013 角色相同的電腦上安裝中央管理存放區。 中央管理存放區不能位於 Enterprise Edition server 集區中。 當您第一次發行拓撲，並選取 [建立資料庫時，會自動建立的中央管理存放區。 您將指定為後端伺服器的電腦必須已執行 SQL Server 資料庫軟體，才能成功安裝順序。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 的 SQL Server 資料和記錄檔位置](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [在 Lync Server 2013 中設定 SQL Server](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013 中的 SQL Server 的部署權限](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [資料庫安裝 Lync Server 2013 中使用 Lync Server 管理命令介面](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [了解搭配 Lync Server 2013 的 SQL Server 的防火牆需求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [設定 Lync Server 2013 的 SQL Server 叢集](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

