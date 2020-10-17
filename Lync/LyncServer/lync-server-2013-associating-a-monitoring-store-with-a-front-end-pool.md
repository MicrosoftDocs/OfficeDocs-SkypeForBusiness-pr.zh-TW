---
title: Lync Server 2013：關聯監控存放區與前端集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e80c6f7482787d448709beaf98e796519860d22c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520633"
---
# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>在 Lync Server 2013 中關聯監控儲存區與前端集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-04-22_

在 Microsoft Lync Server 2013 監控資料只能在已與監控存放區產生關聯的前端集區上收集，通常會執行您在拓撲產生器中定義前端集區的工作。 若要將監控存放區與新的前端集區產生關聯，請務必在 [定義新的前端集區] 嚮導的 [**選取功能**] 頁面上，選取 [**監視 (的詳細資料記錄及記錄品質的) 統計**資料] 選項。 請注意，如果您選取此選項，您也必須指定 SQL 存放區，才可完成該嚮導;不過，當您執行該嚮導時，不需要有這種存放區。 這表示您可以先將集區與監控存放區產生關聯，然後再安裝及設定該儲存區。

或者，您可以完成下列程式，將現有的前端集區與新的或不同的監視存放區產生關聯：

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 **[拓撲產生器]** 對話方塊中，選取 **[從現有的部署下載拓撲]**，然後按一下 **[確定]**。

3.  在 [ **另存** 新檔] 對話方塊中，輸入目前拓撲的檔案名，然後按一下 [ **儲存**]。 當新的拓撲發生問題時，可在以後檢索並重新發佈已儲存的拓撲。

4.  在 [拓撲產生器] 中，依序展開 [ **Lync Server 2013**] 和包含前端集區的網站名稱，然後按一下 [擴充 **Enterprise Edition 前端**集區]。

5.  以滑鼠右鍵按一下要與監視存放區產生關聯的集區名稱，然後按一下 [ **編輯屬性**]。

6.  在 [ **編輯** 內容] 對話方塊的 [ **一般** ] 索引標籤上，選取 [ **監視] (CDR 和 QoE 度量值) ** 然後從 [ **監控 sql server 儲存區** ] 下拉式清單中選取現有的 SQL server 資料庫。  (或按一下 [ **新增** ]，將集區與新的資料庫存放區產生關聯。 ) 如果您選擇使用新的資料庫存放區，請在 [ **定義新的 SQL 存放區** ] 對話方塊的 [ **sql server FQDN** ] 方塊中，輸入 sql server 電腦的完整功能變數名稱。 如果您想要使用該儲存體的預設 SQL Server 實例，請選取 [ **預設實例**];否則，請選取 [ **命名實例** ]，並在 [ **命名實例** ] 方塊中輸入實例名稱。
    
    [ **編輯** 內容] 對話方塊也可讓您選擇為監視資料庫建立 SQL 鏡像 (sql 鏡像可讓您維護監控資料庫的兩個複本，一個副本儲存在監控存放區電腦上，另一個則在 SQL 鏡像電腦上的副本) 。 若要啟用鏡像，請選取 [T**他的 SQL 實例為鏡像關係** ]，然後在 [ **鏡像埠號碼** ] 方塊中輸入鏡像伺服器的埠號碼。

7.  在 [ **編輯屬性** ] 對話方塊中，按一下 **[確定]**。

將監控儲存區與前端集區關聯之後，您必須先發行新的拓撲，變更才會生效。 若要發佈新的拓撲，請在拓撲產生器中完成下列步驟：

1.  按一下 [ **動作**]，指向 [ **拓撲**]，然後按一下 [ **發佈**]。

2.  在 [發佈拓撲] 嚮導的 [ **發行拓撲** ] 頁面上，按 **[下一步]**。

3.  在 **[發行精靈完成]** 頁面上，按一下 **[完成]**。

發行拓撲之後，您就可以在將裝載監控存放區的電腦上安裝監控資料庫。 使用 Lync Server 管理命令介面和 Windows PowerShell 可以安裝監控資料庫。 若要在本機安裝資料庫 (也就是說，若要在執行 Lync Server 管理命令介面) 的同一部電腦上安裝資料庫，請在適當的電腦上啟動管理命令介面，然後輸入下列命令，然後按 ENTER：

    Install-CsDatabase -LocalDatabases

當您執行上述命令時，Install-CsDatabase 會讀取目前的 Lync Server 拓撲，判斷哪些資料庫需要安裝在本機電腦上，然後自動安裝和設定每個資料庫。

若要在遠端電腦上安裝資料庫 (也就是執行管理命令介面之電腦之外的電腦) 您必須至少包含兩個參數： ConfiguredDatabases 參數和 SqlServerFqdn 參數。 這些參數會告訴 Install-CsDatabase Cmdlet 檢索 Lync Server 拓撲，然後在 SqlServerFqdn 參數所指定的電腦上安裝及設定所需的資料庫。 SqlServerFqdn 參數必須使用參數值，代表要安裝資料庫之電腦的完整功能變數名稱。

例如，此命令會在電腦 atl-sql-001.litwareinc.com 上安裝監視資料庫：

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

或者，您也可以在主控監控存放區的電腦上執行 Lync Server 部署嚮導，以安裝監控資料庫。 若要這麼做，請登入適當的電腦，並完成下列程式：

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 部署嚮導]**。

2.  在部署精靈中按一下 **[安裝或更新 Lync Server 系統]**。

3.  在 [ **部署** ] 頁面的 [ **步驟2：安裝或移除 Lync Server 元件**] 底下，按一下 [ **再執行一次**]。

4.  在 [安裝 Lync Server 元件] 嚮導的 [ **安裝 Lync server 元件** ] 頁面上，按 **[下一步]**。

5.  在 [ **指定 MSIs 的路徑** ] 頁面上，輸入檔案 Ocscore.msi 的路徑， (Lync Server 安裝媒體隨附的檔案) 然後按 **[下一步]**。

6.  在 **[執行命令]** 頁面上，按一下 **[完成]**。

若要確認所有必要的 Lync Server 服務已啟動，請在 [**部署**] 頁面的 [**步驟4：啟動服務**] 下，按一下 [**執行**]。

</div>

<span> </span>

</div>

</div>

</div>

