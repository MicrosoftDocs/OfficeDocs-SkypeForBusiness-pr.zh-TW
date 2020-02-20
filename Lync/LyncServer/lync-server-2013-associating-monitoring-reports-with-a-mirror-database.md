---
title: Lync Server 2013： 建立與鏡像資料庫的關聯監控報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48dbf5530a071bc1f23f9d2c05d82e151f51f645
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>與 Lync Server 2013 的鏡像資料庫建立關聯監控報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-07_

如果您設定監控資料庫鏡像，該鏡像資料庫會接管主要資料庫如果發生容錯移轉。 不過，如果您使用 Lync Server 監控報告，並發生容錯移轉，您可能會發現監視報告不會連線至鏡像資料庫。 這是因為當您安裝監控報告，您會指定位置的主要資料庫;您不指定之鏡像資料庫的位置。

若要取得自動容錯移轉至鏡像資料庫的監控報告，您必須新增鏡像資料庫為 「 容錯移轉夥伴 」 至兩個資料庫所使用的監控報告 （一個資料庫的通話詳細記錄資料，以及另一個用於品質經驗 (QoE) 資料）。 （請注意安裝監控報告之後，應該執行此步驟）。您可以新增的容錯移轉夥伴資訊以手動方式編輯這兩個資料庫所使用的連接字串值。 若要執行這項作業，請完成下列程序：

1.  若要開啟 [ **SQL Server Reporting Services**首頁] 頁面上使用 Internet Explorer。 Reporting Services 首頁的 URL 包括：
    
      - **Http:** 前置詞。
    
      - Reporting Services （例如， **atl-cs-sql-001.litwareinc.com**） 的安裝所在之電腦的完整的網域名稱 (FQDN)。
    
      - 字元字串 **/報告\_**。
    
      - 監控報告 （例如， **archinst**） 的安裝所在的資料庫執行個體名稱。
    
    例如，如果電腦 atl-cs-001.litwareinc.com sql-001.litwareinc.com 上都安裝 SQL Server Reporting Services 和監控報告使用資料庫執行個體 archinst，首頁的 URL 看起來會像這樣：
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  存取 [Reporting Services 首頁] 頁面之後，按一下 [ **LyncServerReports**，和 [**報告\_內容**。 會將帶您至**報告\_內容**的 Lync Server 監控報告] 頁面。

3.  在**報告\_內容**] 頁面上，按一下 [ **CDRDB**資料來源。

4.  在 [ **CDRDB** ] 頁面上的 [**屬性**] 索引標籤上尋找 [標示為**連接字串**] 文字方塊。 目前的連接字串看起來類似這樣：
    
    **資料 source=(local)\\archinst; 初始目錄 = LcsCDR**

5.  編輯若要包含之鏡像資料庫的伺服器名稱及資料庫執行個體的連接字串。 例如，如果伺服器名為 atl-cs-001.litwareinc.com-鏡像-001 和鏡像資料庫處於 archinst 執行個體，您必須將新增至指定的鏡像資料庫，使用下列語法：
    
    **容錯移轉夥伴 = atl-鏡像-001\\archinst**
    
    您已編輯的連接字串看起來像這樣：
    
    **資料 source=(local)\\archinst;容錯移轉夥伴 = atl-鏡像-001\\archinst; 初始目錄 = LcsCDR**

6.  更新後的連接字串，按一下 [**套用**]。

7.  在 [ **CDRDB** ] 頁面上，按一下 [**報告\_內容**連結。 按一下**QMSDB**資料來源]，然後編輯 QoE 資料庫連線字串。 例如：
    
    **資料 source=(local)\\archinst;容錯移轉夥伴 = atl-鏡像-001\\archinst; 初始目錄 = QoEMetrics**

8.  按一下 [套用]****。

<div>

## <a name="see-also"></a>另請參閱


[安裝 Lync Server 2013 監控報告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Lync Server 2013 中使用監控報告](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

