---
title: Lync Server 2013：將監視報告與鏡像資料庫建立關聯
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
ms.openlocfilehash: 93e5f10e3e4bd3c063cafcb2fd984098482ebf22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>在 Lync Server 2013 中將監視報告與鏡像資料庫建立關聯

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

如果您為監視資料庫設定鏡像，則在發生容錯移轉時，鏡像資料庫將會作為主要資料庫。 不過，如果您使用 Lync Server Monitoring 報告，且發生容錯移轉，您可能會發現監視報告無法連線到鏡像資料庫。 這是因為，當您安裝監視報告時，只會指定主要資料庫的位置;您不會指定鏡像資料庫的位置。

若要取得監視報告以自動容錯移轉到鏡像資料庫，您必須將鏡像資料庫新增為「容錯移轉夥伴」，以供監視報告所使用的兩個資料庫（一個資料庫用於呼叫詳細資料記錄資料，另一個資料庫的品質為體驗（QoE）資料）。 （請注意，在您安裝監控報告之後，應該執行此步驟）。您可以手動編輯這兩個資料庫所使用的連線字串值，以新增容錯移轉合作夥伴資訊。 若要這樣做，請完成下列程式：

1.  使用 Internet Explorer 開啟 [ **SQL Server Reporting Services** ] 首頁。 [報表服務] 首頁 URL 包括：
    
      - [ **Http：** prefix]。
    
      - 安裝 Reporting Services 的電腦的完整功能變數名稱（FQDN）（例如， **atl-sql-001.litwareinc.com**）。
    
      - 字元字串 **/Reports\_**。
    
      - 安裝監視報告的資料庫實例名稱（例如， **archinst**）。
    
    例如，如果 SQL Server Reporting Services 已安裝在電腦 atl-sql-001.litwareinc.com 上，而監視報告使用資料庫實例 archinst，則首頁 URL 看起來會像這樣：
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  在您存取完報表服務首頁之後，請按一下 [ **LyncServerReports**]，然後按一下 [**報表\_內容**]。 這會將您帶到 Lync Server Monitoring 報告的 [**報告\_內容**] 頁面。

3.  在 [**報表\_內容**] 頁面上，按一下 [ **CDRDB**資料來源]。

4.  在 [ **CDRDB** ] 頁面的 [**屬性**] 索引標籤上，尋找標示為 [**連接字串**] 的文字方塊。 目前的連接字串看起來會像這樣：
    
    **資料來源 = （local）\\archinst; 初始目錄 = LcsCDR**

5.  編輯連接字串，以包含鏡像資料庫的伺服器名稱和資料庫實例。 例如，如果伺服器已命名為 atl-001 且鏡像資料庫位於 archinst 實例中，您將需要新增才能使用下列語法來指定鏡像資料庫：
    
    **容錯移轉合作夥伴 = atl-mirror-\\001 archinst**
    
    您編輯的連線字串看起來會像這樣：
    
    **資料來源 = （local）\\archinst;容錯移轉合作夥伴 = atl-mirror-\\001 archinst; 初始目錄 = LcsCDR**

6.  更新連接字串之後 **，按一下 [** 套用]。

7.  在 [ **CDRDB** ] 頁面上，按一下 [**報告\_內容**] 連結。 按一下 [ **QMSDB**資料來源]，然後編輯 QoE 資料庫的連線字串。 例如：
    
    **資料來源 = （local）\\archinst;容錯移轉合作夥伴 = atl-mirror-\\001 archinst; 初始目錄 = QoEMetrics**

8.  按一下 **[** 套用]。

<div>

## <a name="see-also"></a>請參閱


[安裝 Lync Server 2013 監視報告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[在 Lync Server 2013 中使用監視報告](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

