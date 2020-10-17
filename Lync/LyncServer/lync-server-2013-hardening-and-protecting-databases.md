---
title: Lync Server 2013：強化及保護資料庫
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
ms.openlocfilehash: 0254c77bb276add6f55ccff623c1fc2bec590102
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536910"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>強化及保護 Lync Server 2013 的資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-05_

Microsoft Lync Server 2013 也取決於 SQL Server 資料庫，以儲存使用者資訊、會議狀態、封存資料，以及 (Cdr) 的詳細通話記錄。 您可以透過分割應用程式資料的方式，以提升容錯和簡化疑難排解的方式，以最大化 lync server 後端資料庫上的 Lync Server 2013 資料的可用性。 若要達到這些目標，請依下列方式分割應用程式資料：

  - **使用伺服器分割最佳作法**    從資料檔案中分隔您的作業系統、應用程式和程式檔案。

  - **儲存交易記錄檔和資料庫檔案**    請分開儲存這些檔案，以提升容錯能力及優化復原，並將其儲存在加密的磁片或磁片區。

  - **使用伺服器集群**    將後端伺服器集群集中，以優化 Lync Server 2013 系統可用性。

  - **確定所有資料備份已加密且已正確處理**    遺失、捨棄或錯放備份媒體可能會對 Lync Server 2013 部署的資料安全性造成重大威脅。

在任何 Lync Server 2013 Server 上，除了 Standard Edition server 之外，無法從遠端存取 RTCLOCAL 實例) 的 SQL Server Express (實例，也不會建立本機防火牆例外狀況，但在 Standard Edition Server 上的 SQL Server Express 除外。 在 Standard Edition server 上，後端資料庫與中央管理存放區 (CMS) 會設定為可遠端存取。 若要強化 SQL Server 資料庫，您可以執行下列作業：

  - 自訂 Standard Edition server 上的 SQL Server Express 防火牆，以限制可遠端存取資料庫的伺服器範圍。 根據預設，任何 IP 位址都可以遠端存取資料庫。

  - 使用 SQL Server Configuration Manager 指定 SQL Server 遠端存取的通訊協定、IP 位址及埠：
    
      - Lync Server 2013 使用 TCP/IP 通訊協定。 它支援 IP 版本 4 (IPv4) ，但不支援 IP 版本 6 (IPv6) 。
        
        <div>
        

        > [!NOTE]  
        > 在啟用雙重 IP 堆疊的網路中，Lync Server 2013 可以運作。

        
        </div>
    
      - Lync Server 2013 支援多個 IP 位址 (多穴網路位址卡) 。 您可以指定 SQL Server 只聽取特定的 IP 位址 (個別的位址或子網) ，只使用特定的通訊協定。
    
      - Lync Server 2013 支援靜態和動態 SQL Server 埠。

  - 在靜態 (非預設) 埠上執行 SQL Server，但不要執行 SQL Server 瀏覽器 (使其無法向用戶端) 報告聆聽埠。 這需要在每個 SQL Server 用戶端上進行自訂設定，包括前端伺服器、監控伺服器、封存伺服器和管理主控台 (執行 Lync Server 管理命令介面、Lync Server 控制台或拓撲產生器) ，以及其他執行 Lync Server 資料庫) 的伺服器。

<div>


> [!NOTE]  
> 資料庫的存取權必須限制為受信任的資料庫管理員。 惡意資料庫管理員可以插入或修改資料庫中的資料，以取得 Lync Server 2013 伺服器的許可權，或從服務取得機密資訊，即使資料庫管理員尚未授與 Lync Server 2013 伺服器的直接存取權或控制權。



</div>

如需自訂設定及強化 SQL Server 資料庫的詳細資訊，請參閱 NextHop 的博客文章：「使用 Lync Server 2010 搭配自訂 SQL Server 網路設定」 [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) 。

<div>


> [!NOTE]  
> 您也可以強化作業系統與應用程式伺服器，也可以使用群組原則，在 Lync Server 部署中實施安全性鎖定。 如需詳細資訊，請參閱 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">強化及保護 Lync Server 2013 的伺服器和應用程式</A>。



</div>

</div>

<span> </span>

</div>

</div>

</div>

