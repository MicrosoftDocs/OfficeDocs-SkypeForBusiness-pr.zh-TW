---
title: Lync Server 2013：設定儲存空間以進行封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6728c02e9aa73faceaa8b3e681a5cf9cc4c700cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中設定儲存空間以進行歸檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-17_

Lync Server 2013 的歸檔儲存空間包括下列各項：

  - **需要資料儲存**   區資料儲存空間，才能儲存 IM 內容。

  - ****    需要有檔案儲存空間儲存空間，才能儲存會議（會議）內容資料儲存與檔案儲存空間。

<div>

## <a name="setting-up-data-storage"></a>設定資料儲存

在 Lync Server 2013 中設定存檔資料儲存空間的需求，取決於您要儲存存檔資料的方式：

  - 整合 Lync Server 2013 與 Exchange 部署的歸檔，以儲存使用 Exchange 儲存區的歸檔資料。

  - 設定個別的 SQL Server 資料庫伺服器來儲存存檔資料。

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>設定 Exchange 儲存空間以歸檔資料

若要設定 Exchange 儲存存檔資料，您的 Exchange 部署必須執行 Exchange 2013。 此外，使用者信箱必須駐留在 Exchange 2013 伺服器上，且其信箱必須放在就地保留中。 如需有關設定 Exchange 2013 的詳細資訊，請參閱 Exchange 產品檔。

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>設定用於儲存存檔資料的 SQL Server 資料庫伺服器

Lync Server 2013 中的封存需要 SQL Server 資料庫軟體來儲存已封存的資料，除非您將部署與 Exchange 整合。

針對 SQL Server 封存資料庫，您必須在將裝載存檔資料庫的電腦上安裝 SQL Server。 您可以使用與您用於前端池後端資料庫的同一個 SQL 實例。 為了獲得最佳效能，您應該將封存資料庫部署在與中央管理儲存體分開的電腦上。 如需 collocating Lync Server 2013 元件的詳細資訊，請參閱可支援性檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。

每個資料庫伺服器都必須執行受支援版本的 SQL Server。 如需支援版本的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的存檔技術需求](lync-server-2013-technical-requirements-for-archiving.md)。

您必須先設定 SQL Server 平臺，然後才能部署並啟用封存。 如果要用來發佈拓朴的帳戶具有適當的管理員權力和許可權，您可以在發佈拓撲時建立封存資料庫（LcsLog）。 您也可以日後建立資料庫，包括安裝程式的一部分。 如需 SQL Server 的詳細資料，請參閱 SQL Server [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)技術中心（位於）。

<div>


> [!NOTE]  
> 確定 SQL Server Agent 服務啟動類型為 [自動]，且 SQL Server Agent 服務正在針對存放封存資料庫的 SQL 實例執行，因此預設的 [存檔 SQL Server 維護作業] 可以在其排程的[SQL Server 代理程式服務] 的控制權。



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>設定檔案儲存空間

在您設定前端池或標準版伺服器時，存檔會使用您指定的 Lync Server 2013 檔案共用。 您無法變更用於封存的檔案共用。 如需支援的檔案存儲系統的詳細資料，請參閱支援檔中的[Lync Server 2013 檔案儲存支援](lync-server-2013-file-storage-support.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

