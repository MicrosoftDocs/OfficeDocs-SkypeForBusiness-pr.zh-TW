---
title: Lync Server 2013： 新的災害復原和高可用性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7845f919f04985e67d6825b8722904a9158606b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>新的災害復原和 Lync Server 2013 中的高可用性功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-20 個_

如同 Lync Server 2010、 Lync Server 2013 的主要高可用性 (HA) 配置根據經由共用伺服器備援。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。 這適用於前端伺服器、Edge Server、中繼伺服器和 Director。

Lync Server 2013 新增新的災害復原措施如此可讓您位於兩個資料中心的配對前端集區。 如果配對的集區中有一個故障，系統管理員可以將使用者從該集區容錯移轉至配對中的另一個集區，以便繼續提供服務。 這項功能不需要昂貴的網路或硬體解決方案，例如存放網路或共用磁碟。

Lync Server 2013 也會新增後端伺服器高可用性。 這是選用的拓樸您部署兩個後端伺服器的前端集區]，並設定同步 SQL 鏡像在後端伺服器上執行的所有 Lync 資料庫。 您可以選擇是否要部署鏡像見證。

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中的高可用性和災害復原](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

