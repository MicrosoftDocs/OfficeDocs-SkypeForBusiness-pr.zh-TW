---
title: Lync Server 2013： 增強及保護資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e1ef045253f6733ea3356baa6254a6c90926762
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>增強及保護 Lync Server 2013 的資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-12-05_

Microsoft Lync Server 2013 也取決於用來儲存使用者資訊、 會議狀態，封存資料和詳細通話記錄 (Cdr) 的 SQL Server 資料庫。 您可以藉由分割應用程式資料的方式，提高容錯性及簡化疑難排解最大化 Lync Server 後端資料庫上的 Lync Server 2013 資料的可用性。 若要達到這些目標，分割應用程式資料：

  - **使用伺服器分割最佳做法**   分隔您的作業系統、 應用程式及程式檔案與資料檔案。

  - **儲存交易記錄檔和資料庫檔案**   儲存這些檔案分開以提高容錯性及復原，並將它們儲存到加密的磁碟或磁碟區上。

  - **使用伺服器叢集**   叢集以最佳化 Lync Server 2013 系統的可用性的後端伺服器。

  - **確定所有資料備份會加密及正確地處理**   遺失，已捨棄，或找不到備份媒體可能會造成重大威脅 Lync Server 2013 部署的資料安全性

任何 Lync Server 2013 伺服器上除了 Standard Edition server，SQL Server Express 的執行個體 （RTCLOCAL 執行個體） 從遠端存取，並不會建立沒有本機防火牆例外狀況，但不包括在 Standard Edition server 上的 SQL Server Express。 在 Standard Edition server、 後端資料庫及中央管理存放區 (CMS) 設為可從遠端存取。 若要強化 SQL Server 資料庫，您可以執行下列動作：

  - 自訂 Standard Edition 伺服器，限制的範圍可以從遠端存取資料庫的伺服器上的 SQL Server Express 防火牆。 根據預設，任何 IP 位址可以從遠端存取資料庫。

  - 使用 SQL Server 組態管理員指定的通訊協定、 IP 位址和 SQL Server 遠端存取的連接埠：
    
      - Lync Server 2013 使用 TCP/IP 通訊協定。 它支援 IP 版本 4 (IPv4)，而非 IP 第 6 版 (IPv6)。
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 可以在啟用雙重 IP 堆疊的網路中運作。

        
        </div>
    
      - Lync Server 2013 支援多個 IP 位址 （多重網路地址卡）。 您可以指定特定 IP 位址只有該 SQL Server 接聽 (個別的地址或子網路)，並只使用特定的通訊協定。
    
      - Lync Server 2013 支援靜態及動態的 SQL Server 連接埠。

  - 靜態 （非預設值） 連接埠上執行 SQL Server，但不要執行 SQL Server Browser （讓它不能用戶端報告的聆聽連接埠）。 這需要在每個 SQL Server 用戶端，其中包括前端伺服器、 監控伺服器、 封存伺服器，以及系統管理主控台 （執行 Lync Server 管理命令介面，Lync Server Control Panel 或拓撲產生器]），和所有其他自訂設定伺服器執行 Lync Server 資料庫）。

<div>


> [!NOTE]  
> 存取資料庫必須受限於受信任的資料庫管理員。 惡意資料庫管理員無法插入或修改資料到以取得權限在 Lync Server 2013 伺服器上或從服務，取得敏感資訊的資料庫，即使不已直接存取授與資料庫系統管理員或Lync Server 2013 伺服器的控制項。



</div>

如需自訂設定及強化 SQL Server 資料庫的詳細資訊，請參閱 NextHop 部落格文章，「 使用 Lync Server 2010 搭配自訂 SQL Server 網路組態，「 在[http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)。

<div>


> [!NOTE]  
> 您也可以強化作業系統與應用程式伺服器，您可以使用群組原則實作安全性鎖定 Lync Server 部署中。 如需詳細資訊，請參閱<A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">強化和保護伺服器及 Lync Server 2013 的應用程式</A>。



</div>

</div>

<span> </span>

</div>

</div>

</div>

