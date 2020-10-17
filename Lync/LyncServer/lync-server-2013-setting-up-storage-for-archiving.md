---
title: Lync Server 2013：設定封存的存放區
description: Lync Server 2013：設定封存的存放區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ee431b17b31c49ace7fae1f90d79ec6de2ada4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554239"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中設定儲存區封存

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-17_

Lync Server 2013 的封存儲存區包括下列各項：

  - **資料儲存**    需要有資料存放區才能儲存 IM 內容。

  - **檔存放區**    需要有檔案存放區，才能儲存會議 (會議) 內容資料儲存區和檔案儲存區。

<div>

## <a name="setting-up-data-storage"></a>設定資料儲存區

在 Lync Server 2013 中設定封存資料儲存的需求，取決於您想要儲存封存資料的方式：

  - 整合 Lync Server 2013 封存與 Exchange 部署，以儲存使用 Exchange 儲存體的封存資料。

  - 設定個別的 SQL Server 資料庫伺服器以儲存封存資料。

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>設定用於封存資料的 Exchange 存放區

若要設定 Exchange 封存資料的儲存，您的 Exchange 部署必須執行 Exchange 2013。 此外，使用者信箱必須位於 Exchange 2013 伺服器上，而且其信箱必須置於 In-Place 保留狀態。 如需設定 Exchange 2013 的詳細資訊，請參閱 Exchange 產品檔。

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>設定用於儲存封存資料的 SQL Server 資料庫伺服器

Lync Server 2013 中的封存需要 SQL Server 資料庫軟體儲存封存的資料，除非您將部署與 Exchange 整合。

針對 SQL Server 封存資料庫，您必須在將裝載封存資料庫的電腦上安裝 SQL Server。 您可以使用相同的 SQL 實例，用於前端集區的後端資料庫。 為了達到最佳效能，您應該在與中央管理存放區分開的電腦上部署封存資料庫。 如需組合 Lync Server 2013 元件的詳細資訊，請參閱支援檔中的 [支援的伺服器組合（Lync server 2013](lync-server-2013-supported-server-collocation.md) ）。

每個資料庫伺服器都必須執行支援的 SQL Server 版本。 如需支援的版本的詳細資訊，請參閱規劃檔中的在 [Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) 中封存的技術需求。

在部署及啟用封存之前，您必須先設定 SQL Server 平臺。 若要用來發行拓撲的帳戶具有適當的系統管理員許可權，您可以在發行拓撲時，建立封存資料庫 (LcsLog) 。 您也可以之後再建立資料庫，包括在安裝程序中。 如需 SQL Server 的詳細資訊，請參閱 SQL Server TechCenter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) 。

<div>


> [!NOTE]  
> 確定 SQL Server Agent Service 的啟動類型為 [自動]，且 SQL Server 代理程式服務執行的是存放封存資料庫的 SQL 實例，因此預設的封存 SQL Server 維護工作可以根據 SQL Server 代理程式服務的控制，以排程的方式來執行。



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>設定檔存放區

封存會使用您在設定前端集區或 Standard Edition Server 時所指定的 Lync Server 2013 檔案共用。 您無法變更封存所用的檔案共用。 如需支援的檔案儲存系統的詳細資訊，請參閱支援檔中的檔案 [儲存支援（Lync Server 2013](lync-server-2013-file-storage-support.md) ）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

