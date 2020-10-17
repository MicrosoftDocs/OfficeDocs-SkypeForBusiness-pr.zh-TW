---
title: Lync Server 2013：設定主要管理伺服器
description: Lync Server 2013：設定主要管理伺服器。
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
ms.openlocfilehash: 43f986f4f03e96cafa27dfdd302bb98a00d8b2ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544159"
---
# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>在 Lync Server 2013 中設定主要管理伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-19_

為了充分利用 Microsoft Lync Server 2013 中包含的新狀況監視功能，管理員必須先指定一部電腦做為您的主要管理伺服器;在該電腦上，您必須安裝 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。 此外，您必須安裝支援的 SQL Server 版本，以當作 Operations Manager 後端資料庫運作。 如果您使用 System Center Operations Manager 2012，您可以使用下列任何版本的 SQL Server 作為後端資料庫：

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

如果您使用 System Center Operations Manager 2007 R2，建議您安裝 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。 您也可以使用 SQL Server 2008 R2 作為 System Center Operations Manager 2007 R2 的後端資料庫。 如需設定 SQL Server 2008 R2 以搭配 System Center Operations Manager 2007 R2 的詳細資訊，請參閱本檔的附錄1。

當您安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 時，您需要安裝該產品的所有元件，包括：

  - 操作資料庫

  - 伺服器

  - 安慰

  - Windows PowerShell Cmdlet

  - Web 主控台

  - Reporting

  - 資料倉儲

本文件中不會詳細說明這些元件和其安裝。 如需 System Center Operations Manager 2007 R2 的詳細資訊，請參閱 Operations Manager 2007 R2 檔 <https://go.microsoft.com/fwlink/p/?linkid=257526> ，以及 System Center Operations manager 2012 檔，網址為 <https://go.microsoft.com/fwlink/p/?linkid=257527> 。 如果您要使用 SQL Server 2005 或 SQL Server 2008 Service Pack 1 作為後端資料庫，則應該遵循這些指示。

如果您使用 System Center Operations Manager 2012，您可以使用 SQL Server 2012 作為後端資料庫。 如需 SQL Server 2012 的詳細資訊，請參閱線上叢書 for SQL Server 2012 at [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528) 。

請記住，每個 Lync Server 部署只能有一個主要管理伺服器。 此外，當您可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 時，您無法同時執行這兩個應用程式，您必須選擇其中一個。 例如，如果您正在執行 System Center Operations Manager 2012，則所有 System Center agent 也必須執行 System Center Operations Manager 2012。 您無法讓部分代理程式執行 System Center Operations Manager 2012 及其他執行 System Center Operations Manager 2007 R2 的代理程式。

</div>

<span> </span>

</div>

</div>

</div>

