---
title: Lync Server 2013：部署概述
description: Lync Server 2013：部署概述。
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
ms.openlocfilehash: 5bb3bac4261783a765b64ab2e81adb107599496b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575749"
---
# <a name="deployment-overview-for-lync-server-2013"></a>Lync Server 2013 的部署概況

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-12_

Lync Server 2013 Enterprise Edition 和 Lync Server 2013 Standard Edition 兩者之間的主要差異是，Standard Edition 不支援 Enterprise Edition 中包含的高可用性功能。 若要取得高可用性，您必須將多部前端伺服器部署至集區，然後才能鏡像執行 SQL Server 的伺服器。 搭配 Enterprise Edition，您可以選擇組合或定義獨立的轉送伺服器。 監控伺服器和封存伺服器可以使用執行 SQL Server 的獨立伺服器。 您也可以在資料庫伺服器上執行前端伺服器及集區的 SQL Server 實例。

執行 Lync Server 2013 Standard Edition 的伺服器是針對小型組織和遠端位置所設計，其地理位置是從組織的主要部署中移除。 兩個搭配搭配搭配進行容錯移轉的 Standard Edition server servers，在發生災難時，可支援最多5000的使用者。 您無法將 Standard Edition 伺服器集在一起，像是 Enterprise Edition 前端伺服器。 此外，Standard Edition 所用的 SQL Server 資料庫也是一個執行 SQL Server Express 的組合伺服器，其設計目的是用來處理 Standard Edition Server 工作負載。 這不是說所有角色都必須位於 Standard Edition server 上。 您可以有獨立的轉送伺服器和 Edge Server。 中央管理存放區的 SQL Server 資料庫和 Lync Server 2013 的目的，必須位於執行 SQL Server 之伺服器的 Standard Edition Server 組合上。 監控伺服器和封存伺服器會搭配使用 SQL Server 資料庫的獨立伺服器。

</div>

<span> </span>

</div>

</div>

</div>

