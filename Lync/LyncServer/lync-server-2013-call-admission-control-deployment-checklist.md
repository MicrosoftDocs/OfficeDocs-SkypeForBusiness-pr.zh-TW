---
title: Lync Server 2013： 通話許可控制部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e5250bf82353876e36109a6b2e34442e5ef7dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 的通話許可控制部署檢查清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

若要確認您已完成所有必要的組態工作，以部署通話許可控制 (CAC) 使用下列檢查清單。

  - 如果部署一或多個 Edge Server，每個外部介面 IP 位址必須新增至 [子網路] 清單中的網路組態設定，32 位元遮罩。 您應該也關聯此子網路 （IP 位址） 的地理位置的網路網站識別碼其中 A / V Edge service 部署。
    
    <div>
    

    > [!NOTE]  
    > 若要實作 CAC 不需要 edge server。

    
    </div>

  - 請務必啟用 CAC，透過 Lync Server Control Panel 或執行[Lync Server 2013 中的啟用通話許可控制](lync-server-2013-enable-call-admission-control.md)中所指定的指令程式。

  - 請確定所有的中央網站中已啟用 CAC。 這可以透過 [拓撲產生器]。 如果當您發佈時，會產生警告，*不*忽略它。

  - 請確定網路組態設定中的設定受管理的企業網路中的所有子網路。 它也是不可或缺的每一個子網路是與相關聯的網路網站，[建立關聯的子網路與網路網站在 Lync Server 2013 中](lync-server-2013-associate-a-subnet-with-a-network-site.md)所述。

  - 請確定所有前端伺服器、 Survivable Branch Appliance (Sba)、 音訊/視訊會議伺服器 （如果位於不同集區），和中繼伺服器的 IP 位址的子網路的網路組態設定中設定。

</div>

<span> </span>

</div>

</div>

</div>

