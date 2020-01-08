---
title: Lync Server 2013：用於監控的元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0c848b3c404bc9bce3b54d6ed52157d1b9da679
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 中用於監控的元件與拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

因為統一資料收集代理程式會自動安裝並在每個前端伺服器上啟用，因此您不需要設定伺服器來充當監視伺服器;每個前端伺服器都已充當監視伺服器。 不過，您必須安裝並設定資料庫，以做為監視資料的後端資料存放區。 Microsoft Lync Server 2013 可以使用下列任何一種資料庫做為監視作業的後端存放區：

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 標準版

  - Microsoft SQL Server 2012 企業版

  - Microsoft SQL Server 2012 標準版

請注意，您必須使用64位版本的這些資料庫;32位版本的 SQL Server 無法用來做為監視的後端存放區。 同樣地，Lync Server 2013 不支援 SQL Server 2008 的速成版或 SQL Server 2012。 如需 Lync Server 2013 資料庫需求的詳細資訊，請參閱 Lync Server 2013 支援指南中的[Lync server 2013 主題資料庫軟體支援](lync-server-2013-database-software-support.md)。

請記住，必須先安裝並設定 SQL Server，然後才能部署和設定監視。 不過，您只需要部署 SQL Server 本身，您不需要提前設定監視資料庫。 相反地，當您發佈 Lync Server 拓撲時，系統會自動為您建立這些資料庫。

監視資料可以與其他類型的資料共用 SQL Server 實例。 通常，通話詳細資料記錄資料庫（LcsCdr）和體驗資料庫品質（QoEMetrics）會共用相同的 SQL 實例;在相同的 SQL 實例與封存資料庫（LcsLog）相同的情況下，通常也是這兩個監視資料庫。 關於 SQL Server 實例唯一的真正需求是，任何一個 SQL Server 實例都僅限於下列專案：

  - Lync Server 2013 後端資料庫的一個實例。 （作為一般規則，建議您不要在相同的 SQL 實例（甚至是同一台電腦）上 collocated 您的監視資料庫，就像是後端資料庫。 雖然技術上有可能，您可以使用後端資料庫所需的磁碟空間來執行監視資料庫的風險。

  - [通話詳細資料記錄] 資料庫的一個實例。

  - 體驗資料庫品質的一個實例。

  - 存檔資料庫的一個實例。

換句話說，在同一個 SQL Server 實例中，您無法使用 LcsCdr 資料庫的兩個實例。 如果您需要 LcsCdr 資料庫的多個實例，您就需要設定多個 SQL Server 實例。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

