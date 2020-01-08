---
title: Lync Server 2013：定義和設定拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660ac75e325e5737ceb5df59e9463c88ef1c077
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中定義和設定拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-14_

您可以使用 [拓撲建立器] 來定義及設定您的拓撲。 拓撲建立器不需要您是本機管理員群組或許可權網域群組的成員（例如網域管理員）。 您可以將拓朴定義為標準使用者。 當您在第一次使用及後續編輯會話時啟動拓撲產生器時，系統會提示您輸入您想要拓撲建立器載入目前設定檔的位置。 選項如下：

  - 從現有部署下載拓撲

  - 從本機檔案開啟拓撲

  - 新拓撲

如果您已定義拓撲，且已建立中央管理儲存區，您應該選擇從現有的部署下載拓撲。 拓撲建立器將會讀取資料庫並檢索目前的定義。 如果您有現有的中央管理存放區，請務必選擇此選項。

如果您沒有建立中央管理儲存體，且想要編輯先前儲存的設定，您應該選擇從本機檔案開啟拓撲。 您要開啟的檔案會是儲存在先前會話中的設定檔。 您可以使用這個選項來編輯先前儲存的拓撲。

<div>


> [!WARNING]  
> 如果您已經有已發佈的拓撲，則不應載入本機設定檔。 您應該選擇從現有的部署下載拓撲。



</div>

如果您想要建立新的拓撲建立器配置，請選擇建立新的拓撲。 除非您選擇將先前儲存的設計儲存為與您在舊版設計會話中建立的檔案，否則不會覆寫。

在這些選項中，系統會提示您輸入拓撲建立器設定檔的儲存位置。 檔案的位置可以是本機位置、已建立的檔案共用上的共用位置或卸除式媒體。

<div>

## <a name="in-this-section"></a>本節內容

  - [針對 Lync Server 2013 在拓撲建置器中定義和設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [在 Lync Server 2013 中定義和設定前端集區或 Standard Edition Server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [在 Lync Server 2013 中針對災害復原部署配對前端集區](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [在 Lync Server 2013 中編輯或設定簡單 URL](lync-server-2013-edit-or-configure-simple-urls.md)

  - [在 Lync Server 2013 中選取中央管理伺服器](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

