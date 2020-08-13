---
title: Lync Server 2013： Persistent Chat Server 所需的資源
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
ms.openlocfilehash: 3c925a695fd856c4e9c2d272d39f18a7c3d1f78c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持久聊天伺服器的必要資源

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-02-05_

Persistent Chat Server 的高可用性和嚴重損壞復原需要額外的資源，以超出完整作業的一般需求。 設定持續性聊天伺服器以取得高可用性和嚴重損壞修復之前，請先確定除了標準 Persistent Chat Server 作業所需的資源之外，還具備下列資源。 如需其他設定資訊，請參閱[在 Lync server 2013 中設定 Persistent Chat Server](lync-server-2013-configuring-persistent-chat-server.md)。

  - 一個專用的資料庫實例位於 Persistent Chat Server 服務的主前端所在的相同實體資料中心。 此資料庫會做為主要持久聊天資料庫的 SQL Server 鏡像。 （選用）如果您想要自動容錯移轉至鏡像資料庫，請指定其他 SQL Server 作為鏡像見證。

  - 一個位於其他實體資料中心的專用資料庫實例。 此資料庫會做為主要資料中心資料庫的 SQL Server 記錄傳送次要資料庫。

  - 一個專用的資料庫實例充當次要資料庫的 SQL Server 鏡像。 （選用）將另一部 SQL Server 指定給伺服器做為鏡像見證。 這兩者都必須與次要資料庫位於相同的實體資料中心。

  - 如果啟用 Persistent Chat Server 相容性，則需要額外三個專用資料庫實例。 其分配與先前對 Persistent 聊天資料庫所述的方式相同。 雖然相容性資料庫可能會與 Persistent 聊天資料庫共用相同的 SQL Server 實例，但我們建議在高可用性和嚴重損壞修復時採用獨立的實例。

  - 必須為 SQL Server 記錄傳送交易記錄檔建立及指定檔案共用。 執行持續性聊天資料庫之資料中心內的所有 SQL Server，都必須具有此檔案共用的讀取/寫入權限。 此共用並未定義為 FileStore 角色的一部分。

  - 輔助資料庫伺服器上的檔案共用，用作從主要伺服器檔案共用複製之 SQL Server 交易記錄檔的目的地資料夾。

<div>


> [!NOTE]  
> Persistent Chat Server 集區中的主動持久聊天伺服器必須與拓撲中所定義的下一個躍點 Lync 集區位於相同的時區。



</div>

下圖提供如何在兩個不同的延伸集區拓撲中設定整個 Persistent Chat Server 集區的範例：

  - 當資料中心具有高頻寬/低延遲時，延伸的持久聊天伺服器集區。

  - 資料中心地理位置具有低頻寬/高延遲的延伸 Persistent Chat Server 集區。

下圖顯示資料中心地理位置具有高頻寬/低延遲的延伸持久聊天伺服器集區拓撲。

**當資料中心具有高頻寬/低延遲時，延伸的持久聊天伺服器集區。**

![Persistent Chat Server 集區 HBW 設定考試](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server 集區 HBW 設定考試")

下圖顯示資料中心地理位置具有低頻寬/高延遲的延伸持久聊天伺服器集區拓撲。

**資料中心地理位置具有低頻寬/高延遲的延伸 Persistent Chat Server 集區。**

![Persistent Chat Server 集區 LBW 設定考試](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server 集區 LBW 設定考試")

</div>

<span> </span>

</div>

</div>

</div>

