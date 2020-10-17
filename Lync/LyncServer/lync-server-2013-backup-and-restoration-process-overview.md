---
title: Lync Server 2013：備份及還原程式概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94cebbc9a11e1857bed419c97f52f065326b1772
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504870"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Lync Server 2013 的備份與還原程式概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-26_

本節提供 Lync Server 2013 備份與還原程式運作方式的概述。 不論其位置為何，所有的 Standard Edition server 和 Enterprise Edition 伺服器都使用相同的處理常式。

一般來說，備份程式的運作方式如下：

  - 您將備份位置建立為獨立電腦上的共用資料夾，而不是任何集區的一部分。 備份的位置參照于 **$Backup**。

  - 在定期、排程的基礎上，您會以 [Lync server 2013](lync-server-2013-backup-and-restoration-requirements-data.md) 中所述的程式備份所有的 lync 伺服器資料庫和所有檔案存放區，如備份與還原需求中所述的程式，請遵循 [備份 lync server 2013](lync-server-2013-backing-up-lync-server.md) 中所述的程式。中央管理存放區包括所有的伺服器設定及設定。

  - 每次執行後續備份時，會建立新的共用資料夾，並變更 **$Backup** 參照的路徑。

一般來說，還原程式的運作方式如下：

  - 當發生故障或中斷時，您會將 **$Backup** 所參照的位置資料還原至新的或全新的電腦。
    
    <div>
    

    > [!IMPORTANT]  
    > 這種還原程式不會將資料還原到現有的伺服器狀態。 也就是說，此程式要求伺服器為全新或全新。

    
    </div>

  - 若要讓您的使用者和會議資訊可恢復至失敗點，您可以使用成對的前端集區來執行災難修復拓撲，如在 [Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。

  - 所有網域名稱系統 (DNS) 設定、動態主機設定通訊協定 (DHCP) 設定、功能變數名稱、電腦完全限定功能變數名稱 (Fqdn) 、檔案存放區路徑等等，在還原時，必須在備份時相同。

如果執行 Lync Server 的伺服器失敗，復原作業會包含下列步驟：

  - 使用與失敗電腦相同的 FQDN，在新的或全新的電腦上安裝作業系統。

  - 重新安裝憑證。

  - 如果伺服器主控資料庫，請安裝 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2。

  - 一般來說，如果伺服器主控資料庫，請執行拓撲產生器以建立及安裝資料庫，並設定 (ACLs) 的存取控制清單。

  - 一般來說，如果伺服器主控伺服器角色，請執行 Lync Server 部署嚮導的步驟1到步驟4，以安裝本機設定檔、安裝伺服器角色元件、指派憑證，以及啟動服務。
    
    <div>
    

    > [!NOTE]  
    > 如果伺服器主控的資料庫組合是伺服器角色，則執行 Lync Server 部署嚮導的步驟2，會重新建立資料庫。

    
    </div>

  - 如果伺服器主控資料庫，請還原備份的資料。

</div>

<span> </span>

</div>

</div>

</div>

