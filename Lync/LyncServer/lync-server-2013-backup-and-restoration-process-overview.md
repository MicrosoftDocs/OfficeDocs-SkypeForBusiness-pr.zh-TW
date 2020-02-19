---
title: Lync Server 2013： 備份和還原程序概觀
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
ms.openlocfilehash: 249e60cfaaadcc0bb615d3388ef6dce818c79966
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>針對 Lync Server 2013 的備份和還原程序概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-26_

本章節提供 Lync Server 2013 的備份和還原程序的運作方式的概觀。 您可以使用相同的程序的所有 Standard Edition 伺服器和 Enterprise Edition 伺服器，不論其位置為何。

一般而言，備份程序的運作方式，如下所示：

  - 您不屬於任何集區的獨立電腦上建立共用資料夾與備份位置。 **$Backup**中參照的備份位置。

  - 根據定期、 排程，您備份所有的 Lync Server 資料庫以及 > 中所述的所有檔案存放區[Lync Server 2013 中的備份和還原需求： 資料](lync-server-2013-backup-and-restoration-requirements-data.md)來[備份 Lync Server 2013](lync-server-2013-backing-up-lync-server.md)的中央管理所述的程序存放區包含所有的伺服器設定和組態。

  - 每次執行後續備份時，您建立新的共用的資料夾及變更路徑該 **$Backup**參照。

一般來說，還原程序的運作方式，如下所示：

  - 失敗或中斷發生時，您會還原至新的或乾淨電腦 **$Backup**所參照的位置中的資料。
    
    <div>
    

    > [!IMPORTANT]  
    > 此還原程序不會還原到現有的伺服器狀態資料。 亦即，此程序需要的伺服器是全新或新。

    
    </div>

  - 若要啟用您的使用者和會議的資訊設為 [可復原至失敗點，您可以實作配對前端集區的災害復原拓撲中[規劃高可用性及嚴重損壞修復 Lync Server 2013 中的](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。

  - 所有的網域名稱系統 (DNS) 設定、 動態主機設定通訊協定 (DHCP) 設定、 網域名稱、 電腦的完整網域名稱 (Fqdn)、 檔案存放區路徑等等必須是還原的相同的交易當時時間備份。

如果在執行 Lync Server 的伺服器失敗，復原作業包含下列步驟：

  - 與失敗電腦相同的 FQDN 全新的電腦上安裝作業系統。

  - 重新安裝憑證。

  - 若該伺服器主控資料庫，安裝 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2。

  - 一般而言，若該伺服器主控資料庫，執行拓撲產生器來建立並安裝資料庫，並設定存取控制清單 (Acl)。

  - 一般而言，若該伺服器主控伺服器角色，請執行步驟 1 到步驟 4 若要安裝本機設定檔，[Lync Server 部署精靈] 的安裝伺服器角色元件、 指派憑證]，並啟動服務。
    
    <div>
    

    > [!NOTE]  
    > 若該伺服器主控資料庫與伺服器的伺服器角色組合在一起，Lync Server 部署精靈執行步驟 2，重建資料庫。

    
    </div>

  - 若該伺服器主控資料庫，還原備份的資料。

</div>

<span> </span>

</div>

</div>

</div>

