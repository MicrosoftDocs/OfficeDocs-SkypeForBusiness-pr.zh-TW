---
title: Lync Server 2013 資料庫軟體支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4c39a51f742266c12f618f687c23c645977ffdb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Lync Server 2013 中的資料庫軟體支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-01_

Lync Server 2013 支援下列資料庫管理系統：

  - **前端集區的後端資料庫、封存資料庫、監控資料庫、常設聊天室資料庫以及常設聊天室規範資料庫**
    
      - Microsoft SQL Server 2008 R2 Enterprise 資料庫軟體 (64 位元版本)。建議額外執行最新的 Service Pack。
    
      - Microsoft SQL Server 2008 R2 Standard (64 位元版本)。 建議額外執行最新的 Service Pack。
    
      - Microsoft SQL Server 2012 Enterprise (64 位元版本)。建議額外執行最新的 Service Pack。
    
      - Microsoft SQL Server 2012 Standard (64 位元版本)。建議額外執行最新的 Service Pack。

  - **標準版伺服器資料庫與前端伺服器資料庫**
    
      - Microsoft SQL Server 2012 Express (64 位元版本)。 另外建議執行最新的 Service Pack。
        
        我們支援在前端伺服器和標準版伺服器上進行 Microsoft SQL Server 的修補與升級。 不過，當您在前端伺服器上進行任何類型的升級或修補程式時，您必須考慮仲裁需求。 如需詳細資訊，請參閱[Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)及 [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express （64位版本）是由 Lync Server 2013 在每個標準 Edition 伺服器和每個前端伺服器伺服器上自動安裝。

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 不支援32位版本的 SQL Server。 您必須使用 64 位元版本。</P>
> <LI>
> <P>SQL Server Web edition 與 SQL Server Workgroup edition 不受支援。 您無法搭配 Lync Server 2013 使用。</P>
> <LI>
> <P>Lync Server 2013 不支援原生資料庫鏡像。</P>
> <LI>
> <P>若要使用監視伺服器角色，您應該安裝 SQL Server Reporting Services。</P></LI></UL>



</div>

在前端池中，後端資料庫可以是單一 SQL Server 電腦。

<div>


> [!IMPORTANT]  
> 如果您 collocate Lync Server 資料庫與其他資料庫，我們強烈建議您評估可能會影響可用性和效能的所有因素，並確保如果一個節點發生故障，剩餘的節點就能處理載入。 若要確認容錯移轉功能，建議測試所有容錯移轉案例。



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>使用 SQL 鏡像與 SQL 叢集

Lync Server 2013 支援針對每個 Lync Server 資料庫使用 SQL 鏡像或 SQL 群集。 您可以使用 Lync Server 2013 中的 [拓撲建立器] 工具，輕鬆設定 SQL 鏡像。 對於 SQL 容錯移轉叢集，您必須使用 SQL Server 進行設定。

Lync Server 2013 支援所有部署的 SQL 鏡像與 SQL 群集拓朴，包括從舊版 Lync Server 升級的嶄新部署和組織。

SQL 叢集支援適用於主動/被動組態。基於效能因素，被動節點不應由任何其他 SQL 執行個體共用。

以下支援包含在內：

  - 適用於下列項目的雙節點容錯移轉叢集：
    
      - Microsoft SQL Server 2012 Standard (64 位元版本)。建議額外執行最新的 Service Pack。
    
      - Microsoft SQL Server 2008 R2 Standard (64 位元版本)。建議額外執行最新的 Service Pack。

  - 適用於下列項目、最多可有 16 個節點的容錯移轉叢集：
    
      - Microsoft SQL Server 2012 Enterprise (64 位元版本)。建議額外執行最新的 Service Pack。
    
      - Microsoft SQL Server 2008 R2 Enterprise 資料庫軟體 (64 位元版本)。建議額外執行最新的 Service Pack。

如需有關 SQL 鏡像的詳細資訊，請參閱[Lync Server 2013 中的後端伺服器高可用性](lync-server-2013-back-end-server-high-availability.md)。 如需如何部署 SQL 群集的詳細資料，請參閱[設定 Lync server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)。

如需 SQL Server 2012 中容錯移轉叢集的詳細資訊和最佳做法<http://technet.microsoft.com/en-us/library/hh231721.aspx>，請參閱。 針對 SQL Server 2008 中的容錯移轉叢集<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>，請參閱。

</div>

</div>

<span> </span>

</div>

</div>

</div>

