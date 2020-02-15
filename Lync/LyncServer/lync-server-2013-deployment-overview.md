---
title: Lync Server 2013： 部署概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d5fd5de9a72002d6ee8bd58ef5367b96634b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Lync Server 2013 的部署概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-12_

Lync Server 2013 Enterprise Edition 與 Lync Server 2013 Standard Edition 的主要差異是，Standard Edition 不支援 Enterprise Edition 隨附的高可用性功能。 高可用性，您需要部署多部前端伺服器集區，然後您可以鏡像執行 SQL Server 的伺服器。 企業版，您可以選擇將組合在一起，或定義獨立中繼伺服器。 監控伺服器和封存伺服器可以使用執行 SQL Server 在獨立伺服器。 或者，他們可以執行資料庫伺服器上的前端伺服器和集區的 SQL Server 執行個體。

執行 Lync Server 2013 Standard Edition 伺服器被適用於小型組織和遠端位置] 中，依地理位置移除組織的主要部署。 成對發生災害時容錯移轉的兩個 Standard Edition server 伺服器可支援最多 5000 個使用者。 您無法在像可以中 Enterprise Edition 前端伺服器集區 Standard Edition server。 此外，Standard Edition 使用 SQL Server 資料庫已組合的伺服器執行 SQL Server Express 是設計用來處理 Standard Edition server 工作負載。 這並不是說的所有角色都必須都位於 Standard Edition server 上。 您可以獨立中繼伺服器和 Edge Server。 都必須位於 Standard Edition 伺服器組合與執行 SQL Server 之伺服器上的 SQL Server 資料庫的中央管理存放區和 Lync Server 2013 的目的。 封存伺服器與監控伺服器搭配 SQL Server 資料庫的獨立伺服器。

</div>

<span> </span>

</div>

</div>

</div>

