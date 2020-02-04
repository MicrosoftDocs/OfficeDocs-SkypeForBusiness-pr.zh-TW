---
title: Lync Server 2013：常設聊天室伺服器的必要資源
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31683641e50a3e3bc898841b0cf4b0911e046262
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中的常設聊天室伺服器的必要資源

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-02-05_

持續性聊天伺服器的高可用性和災難復原需要額外的資源，超出完整操作所需的資源。 在針對高可用性和災害復原設定持續聊天伺服器前，請確定您有下列資源，以及標準持續聊天伺服器作業所需的內容。 如需其他配置資訊，請參閱[在 Lync server 2013 中設定持久聊天伺服器](lync-server-2013-configuring-persistent-chat-server.md)。

  - 一個專用的資料庫實例位於與持久性聊天伺服器服務的主前端相同的物理資料中心。 此資料庫將充當主要持久聊天資料庫的 SQL Server mirror。 或者，如果您想要將自動容錯移轉到鏡像資料庫，請指定額外的 SQL Server 作為鏡像見證。

  - 一個位於另一個物理資料中心的專用資料庫實例。 此資料庫將充當主要資料中心中資料庫的 SQL Server 記錄傳送次要資料庫。

  - 要作為次要資料庫之 SQL Server mirror 的一個專用資料庫實例。 或者，您也可以將其他 SQL Server 指派給伺服器做為鏡像見證。 這兩者必須位於與次要資料庫相同的物理資料中心。

  - 如果已啟用持續聊天伺服器合規性，則需要額外的三個專用資料庫實例。 其分配與先前在持續聊天資料庫中所述的相同。 雖然合規性資料庫可以與持久聊天資料庫共用相同的 SQL Server 實例，但我們建議獨立的實例提供高可用性和災害復原。

  - 必須針對 SQL Server 記錄傳送事務記錄記錄建立並指派檔案共用。 在兩個資料中心中的所有 SQL 伺服器都執行持續聊天資料庫，必須擁有此檔案共用的讀/寫存取權。 此共用沒有定義為 [您的顯示格式] 角色的一部分。

  - 次要資料庫伺服器上的檔案共用，可作為從主要伺服器檔案共用複製的 SQL Server 事務日誌的目的地資料夾。

<div>


> [!NOTE]  
> 持續聊天伺服器池中的作用中持續聊天伺服器，必須位於與拓撲中定義的下一個躍點 Lync 池相同的時區中。



</div>

下列圖表提供在兩個不同延伸池拓撲中如何設定整個持續聊天伺服器池的範例：

  - 當資料中心位於具有高頻寬/低延遲的地理位置時，延伸持久聊天伺服器池。

  - 當資料中心位於具有低頻寬/高延遲的地理位置時，延伸持久聊天伺服器池。

下圖顯示延伸持續聊天伺服器池拓撲，其中資料中心是具有高頻寬/低延遲的地理位置。

**當資料中心位於具有高頻寬/低延遲的地理位置時，延伸持久聊天伺服器池。**

![Persistent Chat Server 集區 HBW 組態範例](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server 集區 HBW 組態範例")

下圖顯示延伸的持久聊天伺服器池拓撲，其中資料中心是具有低頻寬/高延遲的地理位置。

**當資料中心位於具有低頻寬/高延遲的地理位置時，延伸持久聊天伺服器池。**

![Persistent Chat Server 集區 LBW 組態範例](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server 集區 LBW 組態範例")

</div>

<span> </span>

</div>

</div>

</div>

