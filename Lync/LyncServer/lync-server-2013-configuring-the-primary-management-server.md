---
title: Lync Server 2013： 設定主要管理伺服器
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
ms.openlocfilehash: 68fc10ba0457b0ad29f6f3850c1d7056d27fd24d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>在 Lync Server 2013 中設定的主要管理伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-03-19_

若要完全利用新的狀況監控功能包含在 Microsoft Lync Server 2013 系統管理員必須先指定電腦，以做為主要管理伺服器;在該電腦上必須再安裝 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。 此外，您必須安裝支援的運作與您 Operations Manager 的後端資料庫的 SQL Server 版本。 如果您使用 System Center Operations Manager 2012 您可以使用任何下列版本的 SQL Server 後端資料庫：

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

如果您使用 System Center Operations Manager 2007 R2 建議您安裝 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。 您也可以使用為後端資料庫的 SQL Server 2008 R2 的 System Center Operations Manager 2007 R2。 設定為搭配 System Center Operations Manager 2007 R2 的 SQL Server 2008 R2，請參閱 < 附錄 1 的此文件的詳細資訊。

當您安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 您必須安裝該產品的所有元件時，包括：

  - 操作資料庫

  - 伺服器

  - 主控台

  - Windows PowerShell Cmdlet

  - Web 主控台

  - Reporting

  - 資料倉儲

本文件中不會詳細說明這些元件和其安裝。 如需 System Center Operations Manager 2007 R2 的詳細資訊，請參閱 Operations Manager 2007 R2 文件<https://go.microsoft.com/fwlink/p/?linkid=257526>和 System Center Operations Manager 2012 文件<https://go.microsoft.com/fwlink/p/?linkid=257527>。 如果您要為您的後端資料庫使用 SQL Server 2005 或 SQL Server 2008 Service Pack 1，您應該遵循這些指示。

如果您使用 System Center Operations Manager 2012 然後您就可以使用 SQL Server 2012 與您的後端資料庫。 如需 SQL Server 2012 的詳細資訊，請參閱線上叢書的在 SQL Server 2012 [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528)。

請記住，您可能只會有每個 Lync Server 部署在單一主要管理伺服器。 此外，雖然您可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，您無法在執行兩個應用程式同時，您必須選擇其中一個。 例如，如果您執行 System Center Operations Manager 2012 然後所有 System Center 代理程式也必須都執行 System Center Operations Manager 2012。 您不能有執行 System Center Operations Manager 2012 某些代理程式及其他執行 System Center Operations Manager 2007 R2 的代理程式。

</div>

<span> </span>

</div>

</div>

</div>

