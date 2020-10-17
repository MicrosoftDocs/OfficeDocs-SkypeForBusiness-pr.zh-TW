---
title: Lync Server 2013 資料庫軟體支援
description: Lync Server 2013 資料庫軟體支援。
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
ms.openlocfilehash: 1c5d7b44e5febc4123dbcdf7072b98fcfd004609
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558149"
---
# <a name="database-software-support-in-lync-server-2013"></a>Lync Server 2013 中的資料庫軟體支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-01_

Lync Server 2013 支援下列資料庫管理系統：

  - **前端集區的後端資料庫、封存資料庫、監控資料庫、persistent chat database 及 persistent chat 規範資料庫**
    
      - Microsoft SQL Server 2008 R2 Enterprise database 軟體 (64-位版本) 。 建議您另外執行最新的 service pack。
    
      - Microsoft SQL Server 2008 R2 Standard (64-bit edition) 。 建議您另外執行最新的 service pack。
    
      - Microsoft SQL Server 2012 Enterprise (64-位版本) 。 建議您另外執行最新的 service pack。
    
      - Microsoft SQL Server 2012 Standard (64-bit edition) 。 建議您另外執行最新的 service pack。

  - **Standard Edition server 資料庫和前端伺服器資料庫**
    
      - Microsoft SQL Server 2012 Express (64-位版本) 。 建議您另外執行最新的 service pack。
        
        我們支援在前端伺服器和 Standard Edition server 上修補及升級 Microsoft SQL Server。 不過，當您在前端伺服器上進行任何類型的升級或修補程式時，您必須考慮仲裁需求。 如需詳細資訊，請參閱 [Upgrade or Update 前端伺服器 In Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) 和 [拓撲及元件中的前端伺服器、立即訊息及顯示狀態在 lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)中。
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64-位版本) 會由 Lync Server 2013 于每個 Standard Edition server 和每一部前端伺服器伺服器自動安裝。

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 不支援32位版本的 SQL Server。 您必須使用64位版本。</P>
> <LI>
> <P>不支援 SQL Server Web edition 和 SQL Server Workgroup edition。 您無法使用 Lync Server 2013。</P>
> <LI>
> <P>Lync Server 2013 不支援原生資料庫鏡像功能。</P>
> <LI>
> <P>若要使用監控伺服器角色，您應該安裝 SQL Server Reporting Services。</P></LI></UL>



</div>

在前端集區中，後端資料庫可以是單一的 SQL Server 電腦。

<div>


> [!IMPORTANT]  
> 如果您使用其他資料庫組合 Lync Server 資料庫，我們強烈建議評估可能影響可用性和效能的所有因素，並確保如果一個節點失敗，則剩餘的節點可以處理該負載。 若要確認容錯移轉功能，建議您測試所有容錯移轉狀況。



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>使用 SQL 鏡像與 SQL 叢集

Lync Server 2013 支援對每個 Lync Server 資料庫使用 SQL 鏡像或 SQL 叢集。 您可以使用 Lync Server 2013 中的拓撲產生器工具，輕鬆地設定 SQL 鏡像。 針對 SQL 容錯移轉叢集，您必須使用 SQL Server 進行安裝。

Lync Server 2013 同時支援所有部署的 SQL 鏡像與 SQL 叢集拓撲，包括已從舊版 Lync Server 升級的嶄新部署和組織。

SQL 叢集支援適用于主動/被動設定。 基於效能考慮，被動節點不應該由任何其他 SQL 實例共用。

包含下列支援：

  - 下列兩個節點的容錯移轉叢集：
    
      - Microsoft SQL Server 2012 Standard (64-bit edition) 。 建議您另外執行最新的 service pack。
    
      - Microsoft SQL Server 2008 R2 Standard (64-bit edition) 。 建議您另外執行最新的 service pack。

  - 最多十六個節點的容錯移轉叢集可用於下列各項：
    
      - Microsoft SQL Server 2012 Enterprise (64-位版本) 。 建議您另外執行最新的 service pack。
    
      - Microsoft SQL Server 2008 R2 Enterprise database 軟體 (64-位版本) 。 建議您另外執行最新的 service pack。

如需 SQL 鏡像的詳細資訊，請參閱 [Lync server 2013 中的後端伺服器高可用性](lync-server-2013-back-end-server-high-availability.md)。 如需如何部署 SQL 叢集的詳細資訊，請參閱 [CONFIGURE Sql Server 叢集 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)。

如需 SQL Server 2012 中容錯移轉叢集的詳細資訊與最佳作法，請參閱 <https://technet.microsoft.com/library/hh231721.aspx> 。 如需 SQL Server 2008 中的容錯移轉叢集，請參閱 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

