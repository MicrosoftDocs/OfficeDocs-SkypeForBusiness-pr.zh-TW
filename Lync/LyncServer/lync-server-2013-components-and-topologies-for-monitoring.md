---
title: Lync Server 2013：監控的元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 072dbc882940bc0f28217bcf7c41663bf9ed3708
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 中監控的元件與拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

由於整合資料集合代理程式會在每一部前端伺服器上自動安裝及啟用，因此您不需要將伺服器設定為監視伺服器;每一部前端伺服器都已做為監控伺服器的功能。 不過，您必須安裝並設定資料庫，以充當監控資料的後端資料儲存區。 Microsoft Lync Server 2013 可使用下列任何資料庫做為監視的後端存放區：

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

請注意，您必須使用這些資料庫的64位版本;32位版本的 SQL Server 無法用作監視的後端存放區。 同樣地，Lync Server 2013 不支援 SQL Server 2008 的速成版或 SQL Server 2012。 如需 Lync Server 2013 資料庫需求的詳細資訊，請參閱 Lync Server 2013 支援指南中的主題[資料庫軟體支援（Lync server 2013](lync-server-2013-database-software-support.md) ）。

請記住，必須先安裝及設定 SQL Server，才能部署及設定監視。 不過，您只需要部署 SQL Server 本身;您不需要事先設定監視資料庫。 相反地，當您發佈 Lync Server 拓撲時，會自動為您建立這些資料庫。

監視資料可以與其他類型的資料共用 SQL Server 實例。 一般來說，詳細通話記錄資料庫 (LcsCdr) 和經驗品質資料庫 (QoEMetrics) 共用相同的 SQL 實例;這兩個監視資料庫也一般都位於與封存資料庫 (LcsLog) 相同的 SQL 實例中。 關於 SQL Server 實例的唯一實際需求是，任何一個 SQL Server 實例都限制為下列各項：

  - Lync Server 2013 後端資料庫的一個實例。  (一般規則，不建議您在相同的 SQL 實例（甚至是在相同的電腦上），將監控資料庫組合至後端資料庫。 您可以使用後端資料庫所需的磁碟空間來執行監控資料庫的風險，但從技術上講可行。 ) 

  - 通話詳細資料記錄資料庫的一個實例。

  - 經驗品質資料庫的一個實例。

  - 封存資料庫的一個實例。

換句話說，在相同的 SQL Server 實例中，您不能有兩個 LcsCdr 資料庫實例。 如果您需要 LcsCdr 資料庫的多個實例，則需要設定多個 SQL Server 實例。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中部署監控](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

