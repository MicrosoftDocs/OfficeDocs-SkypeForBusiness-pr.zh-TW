---
title: Lync Server 2013： 定義和設定拓撲
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
ms.openlocfilehash: a443aaa7cf523e1cb02beb3d944ec53632732291
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>定義和設定 Lync Server 2013 中的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-14_

您定義，並使用拓撲產生器設定您的拓撲。 拓撲產生器不需要是本機 Administrators 群組或特殊權限的網域群組 （如網域系統管理員） 的成員。 您可以標準使用者身分定義拓撲。 當您啟動拓撲產生器中第一次使用以及後續編輯工作階段，會提示您輸入您希望拓撲產生器來載入目前的設定文件的位置。 選項如下：

  - 從現有部署下載拓撲

  - 從本機檔案開啟拓撲

  - 新增拓撲

如果您已定義拓撲，並已建立的中央管理存放區，您應該選擇 [從現有部署下載拓撲。 拓撲產生器將讀取資料庫，並擷取目前的定義。 如果您有現有的中央管理存放區，您應該一律選擇此選項。

如果您不具有建立中央管理存放區，並想要編輯先前儲存的設定，您應該選擇 [從本機檔案開啟拓撲。 您將開啟的檔案，必須是先前工作階段中儲存的組態檔。 您可以透過這個選項，編輯先前儲存的拓撲。

<div>


> [!WARNING]  
> 如果您已經有發行的拓撲，請勿載入本機組態檔。您應該選擇從現有部署下載拓撲。



</div>

選擇建立新的拓撲中，如果您想要建立新的拓撲產生器設定。 除非您選擇將先前儲存的設計儲存您在先前設計工作階段裡建立的相同檔案，否則不會複寫先前儲存的設計。

在每個這些選項，將會提示您用於儲存拓撲產生器設定檔的位置。 該檔案位置可以是本機位置、已建立的檔案共用之共用位置，或是卸除式媒體。

<div>

## <a name="in-this-section"></a>本章節內容

  - [定義和設定拓撲中的 Lync Server 2013 的拓撲產生器](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013 的災害復原部署配對的前端集區](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [部署 SQL 鏡像後端伺服器高可用性的 Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [編輯或 Lync Server 2013 中設定簡單 Url](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Lync Server 2013 中選取中央管理伺服器](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

