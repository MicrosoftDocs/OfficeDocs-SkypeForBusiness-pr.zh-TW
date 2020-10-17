---
title: Lync Server 2013：定義及設定拓撲
description: Lync Server 2013：定義及設定拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec444a1ddf434c5a80fdc2d56bdba27573da14ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542079"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中定義及設定拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-14_

您可以使用拓撲產生器來定義及設定拓撲。 拓撲產生器不需要您是本機系統管理員群組的成員，或具有許可權的網域群組 (，例如 Domain Admins) 。 您可以標準使用者身分定義拓撲。 當您在第一次使用時啟動拓撲產生器和後續的編輯會話時，系統會提示您輸入您想要拓撲產生器載入目前設定檔的位置。 選項如下：

  - 從現有部署下載拓撲

  - 從本機檔案開啟拓撲

  - 新增拓撲

如果您已定義拓撲，且已建立中央管理存放區，則應該選擇從現有的部署下載拓撲。 拓撲產生器會讀取資料庫，並取得目前的定義。 如果您有現有的中央管理存放區，則一定要選擇此選項。

若尚未建立中央管理存放區，且想要編輯先前儲存的設定，您應該選擇從本機檔案開啟拓撲。 您將開啟的檔案，必須是先前工作階段中儲存的組態檔。 您可以透過這個選項，編輯先前儲存的拓撲。

<div>


> [!WARNING]  
> 如果您已經有發行的拓撲，請勿載入本機組態檔。您應該選擇從現有部署下載拓撲。



</div>

如果您想要建立新的拓撲產生器設定，請選擇建立新的拓撲。 除非您選擇將先前儲存的設計儲存您在先前設計工作階段裡建立的相同檔案，否則不會複寫先前儲存的設計。

在這些選項中，系統會提示您輸入存放拓撲產生器設定檔的位置。 該檔案位置可以是本機位置、已建立的檔案共用之共用位置，或是卸除式媒體。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 的拓撲產生器中定義及設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [在 Lync Server 2013 中定義及設定前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [在 Lync Server 2013 中為嚴重損壞修復部署成對的前端集區](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [在 Lync Server 2013 中編輯或設定簡單 URLs](lync-server-2013-edit-or-configure-simple-urls.md)

  - [在 Lync Server 2013 中選取中央管理伺服器](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

