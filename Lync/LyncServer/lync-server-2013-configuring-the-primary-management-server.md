---
title: Lync Server 2013：設定主要管理伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d6cb7d0f27413449873cb8a0d8498aec230fdfd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>在 Lync Server 2013 中設定主要管理伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-19_

若要充分利用 Microsoft Lync Server 2013 中包含的新健康情況監視功能，系統管理員必須先指定電腦作為您的主要管理伺服器;在該電腦上，您必須安裝 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。 此外，您必須安裝受支援版本的 SQL Server，才能充當 Operations Manager 後端資料庫。 如果您使用系統中心作業管理器2012，您可以使用下列任一版本的 SQL Server 做為後端資料庫：

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

如果您使用的是 System Center Operations Manager 2007 R2，建議您安裝 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。 您也可以使用 SQL Server 2008 R2 作為 System Center Operations Manager 2007 R2 的後端資料庫。 如需有關設定 SQL Server 2008 R2 以搭配 System Center Operations Manager 2007 R2 的詳細資訊，請參閱本檔的附錄1。

當您安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 時，您必須安裝該產品的所有元件，包括：

  - 運算元據庫

  - 伺服器

  - 控制

  - Windows PowerShell Cmdlet

  - 網頁主控台

  - 報告

  - 資料倉儲

這些元件及其安裝將不會在這份檔中詳細討論。 如需 System Center Operations Manager 2007 R2 的詳細資料，請參閱 Operations Manager 2007 R2 <http://go.microsoft.com/fwlink/p/?linkid=257526>檔，以及系統中心作業管理員2012檔<http://go.microsoft.com/fwlink/p/?linkid=257527>。 如果您要使用 SQL Server 2005 或 SQL Server 2008 Service Pack 1 做為後端資料庫，請遵循這些指示。

如果您使用系統中心作業管理器2012，則可以使用 SQL Server 2012 做為後端資料庫。 如需有關 SQL Server 2012 的詳細資訊，請參閱 SQL Server 2012 [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)的線上圖書。

請記住，每個 Lync Server 部署只能有一個主要管理伺服器。 此外，雖然您可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，但您無法同時執行這兩個應用程式，您必須選擇其中一個。 例如，如果您執行的是 System Center Operations Manager 2012，那麼您所有的 System Center agent 也必須執行 System Center Operations Manager 2012。 您不能有一些代理程式正在執行 System Center Operations Manager 2012，以及其他執行 System Center Operations Manager 2007 R2 的代理程式。

</div>

<span> </span>

</div>

</div>

</div>

