---
title: Lync Server 2013：將監控報告與鏡像資料庫相關聯
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
ms.openlocfilehash: 655c6ec788b934a533295fee577e72febb7818de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527100"
---
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>在 Lync Server 2013 中將監控報告與鏡像資料庫相關聯

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

[！注意] 如果您為監控資料庫設定鏡像，則在發生容錯移轉時，鏡像資料庫將會以主資料庫的方式接管。 不過，如果您使用 Lync Server 監控報告，而且發生容錯移轉，您可能會發現監控報告未連接至鏡像資料庫。 這是因為，當您安裝監控報告時，只會指定主要資料庫的位置;您不會指定鏡像資料庫的位置。

若要取得監控報告自動容錯移轉至鏡像資料庫，您必須將鏡像資料庫新增為「容錯移轉協力廠商」，以供監視報告 (一個資料庫用於通話詳細資料記錄資料，另一個用於 (經驗品質 QoE) 資料) 。  (請注意，安裝監控報告之後，應該執行此步驟。 ) 您可以手動編輯這兩個資料庫所使用的連線字串值，以新增容錯移轉夥伴資訊。 若要執行這項作業，請完成下列程序：

1.  使用 Internet Explorer 開啟 [ **SQL Server Reporting Services** ] 首頁。 Reporting Services 首頁 URL 包含：
    
      - **Http：** 前置詞。
    
      - 安裝 Reporting Services 之電腦的完整功能變數名稱 (FQDN)  (例如， **atl-sql-001.litwareinc.com**) 。
    
      - 字元字串 **/Reports \_ **。
    
      - 安裝監視報告的資料庫實例名稱 (例如， **而 archinst**) 。
    
    例如，如果已在電腦 atl-sql-001.litwareinc.com 上安裝 SQL Server Reporting Services，且監控報告使用資料庫實例而 archinst，則首頁 URL 會如下所示：
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  存取 Reporting Services 首頁之後，請按一下 [ **LyncServerReports**]，然後按一下 [ **報表 \_ 內容**]。 這將帶您前往 Lync Server Monitoring Reports 的「 **報告 \_ 內容** 」頁面。

3.  在 [ **報告 \_ 內容** ] 頁面上，按一下 [ **CDRDB** ] 資料來源。

4.  在 [ **CDRDB** ] 頁面的 [ **屬性** ] 索引標籤上，尋找標示為 [連線 **字串**] 的文字方塊。 目前的連接字串將如下所示：
    
    **資料來源 = (local) \\ 而 archinst; 初始目錄 = LcsCDR**

5.  編輯連接字串，以包含鏡像資料庫的伺服器名稱和資料庫實例。 例如，如果伺服器命名為 atl-001，且鏡像資料庫位於而 archinst 實例中，您將需要使用下列語法來新增以指定鏡像資料庫：
    
    **容錯移轉夥伴 = atl-mirror-001 \\ 而 archinst**
    
    您已編輯的連接字串看起來如下所示：
    
    **資料來源 = (local) \\ 而 archinst;容錯移轉夥伴 = atl-mirror-001 \\ 而 archinst; 初始目錄 = LcsCDR**

6.  更新連接字串後 **，按一下 [** 套用]。

7.  在 [ **CDRDB** ] 頁面上，按一下 [ **報表 \_ 內容** ] 連結。 按一下 [ **QMSDB** ] 資料來源，然後編輯 QoE 資料庫的連接字串。 例如：
    
    **資料來源 = (local) \\ 而 archinst;容錯移轉夥伴 = atl-mirror-001 \\ 而 archinst; 初始目錄 = QoEMetrics**

8.  按一下 **[套用]**。

<div>

## <a name="see-also"></a>另請參閱


[安裝 Lync Server 2013 監控報告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[在 Lync Server 2013 中使用監控報告](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

