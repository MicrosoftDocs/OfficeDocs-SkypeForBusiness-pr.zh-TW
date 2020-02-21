---
title: Lync Server 2013： 建立與前端集區的關聯監控存放區
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
ms.openlocfilehash: dfdff8863c0e629c99d0e64aca0b7f84dcb63a43
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>將監控存放區與 Lync Server 2013 中的前端集區產生關聯

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-04-22_

在 [Microsoft Lync Server 2013 中已與監控存放區相關聯的前端集區只可收集監視資料，通常實行您的工作會定義在拓撲產生器的前端集區。 若要將監控存放區與新的前端集區產生關聯，請確定您選取 [定義新前端集區精靈] 的 [**選取功能**] 頁面上的選項**監視 （詳細通話記錄和品質經驗計量的記錄）** 。 請注意，是否您選取此選項，您也必須指定 SQL 存放區才能完成這個精靈;不過，此儲存區不需要執行精靈時存在的。 這表示，您可以先集區關聯監控存放區，然後稍後安裝和設定該儲存區。

或者，您可以將關聯的現有前端集區新的或其他監控存放區，請完成下列程序：

1.  按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在 **[拓撲產生器]** 對話方塊中，選取 **[從現有的部署下載拓撲]**，然後按一下 **[確定]**。

3.  在 [另**存**新檔] 對話方塊中，輸入您目前的拓撲的檔案名稱，然後按一下 [**儲存**。 儲存的拓撲可以稍後再擷取並重新發佈以防有新的拓撲的問題。

4.  在拓撲產生器中，依序展開 [ **Lync Server 2013**中，展開包含前端集區]，網站的名稱，然後按一下以展開 [ **Enterprise Edition 前端集區**。

5.  以滑鼠右鍵按一下與監控存放區產生關聯，然後按一下 [**編輯內容**之集區的名稱。

6.  在 [**編輯內容**] 對話方塊的 [**一般**] 索引標籤中選取 [**監控 （CDR 和 QoE 計量）** ] 選項，然後從 [**監控 SQL Server 儲存區**] 下拉式清單中選取現有的 SQL Server 資料庫。 （或者，按一下 [**新增**]，以新的資料庫存放區建立關聯的集區）。如果您選擇使用新的資料庫儲存區，然後在 [**定義新 SQL 存放區**] 對話方塊中，輸入 [ **Sql Server FQDN** ] 方塊中的 SQL Server 電腦的完整的網域名稱。 如果您想要針對該儲存區選取 [**預設執行個體**; 使用預設 SQL Server 執行個體否則請選擇 [**具名執行個體**，然後在**具名執行個體]** 方塊中輸入的執行個體名稱。
    
    [**編輯內容**] 對話方塊也會提供您建立 SQL 鏡像監控資料庫 （SQL 鏡像可讓您維護兩個副本的監控資料庫、 一個副本儲存在監控 SQL 鏡像電腦上儲存的電腦，而另一個） 的選項。 若要啟用鏡像，請選取 T**他 SQL 執行個體為鏡像關係]** ，輸入 [**鏡像連接埠號碼**] 方塊中的鏡像伺服器的連接埠號碼。

7.  在 [**編輯內容**] 對話方塊中，按一下 [**確定]**。

之後將監控存放區與前端集區產生關聯中，您必須發佈新拓撲前所做的變更才會生效。 若要發行新拓撲，完成下列步驟在拓撲產生器：

1.  按一下 [**動作]**，並指向 [**拓撲**]，然後按一下 [**發佈**]。

2.  在 [發行拓撲精靈] 上 [**發行拓撲**] 頁面中，按一下 [**下一步**]。

3.  在 **[發行精靈完成]** 頁面上，按一下 **[完成]**。

已發行拓撲之後就可以安裝監控資料庫將裝載監控存放區的電腦上。 可以透過使用 Lync Server 管理命令介面和 Windows PowerShell 安裝監控資料庫。 若要安裝在本機上的資料庫 (亦即執行 Lync Server 管理命令介面的相同電腦上安裝資料庫)，啟動 Management Shell 上適當的電腦，然後輸入下列命令並按 ENTER:

    Install-CsDatabase -LocalDatabases

當您執行上述命令時，Install-csdatabase 將讀取目前的 Lync Server 拓撲、 判斷哪些資料庫需要安裝在本機電腦，然後再自動安裝和設定每一個資料庫。

若要安裝資料庫 （也就是管理命令介面執行所在之電腦以外的電腦） 的遠端電腦上，您必須包含至少兩個參數： ConfiguredDatabases 參數與 SqlServerFqdn 參數。 這些參數會告訴 Install-csdatabase 指令程式來擷取 Lync Server 拓撲，然後安裝並設定必要的資料庫 SqlServerFqdn 參數所指定的電腦上。 SqlServerFqdn 參數必須使用參數值，代表電腦的完整的網域名稱之資料庫的安裝位置。

例如，此命令在電腦 atl-sql-001.litwareinc.com 安裝監控資料庫的 sql-001.litwareinc.com:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

或者，您可以藉由將裝載監控存放區的電腦上執行 Lync Server 部署精靈安裝監控資料庫。 若要這麼做，請登入適當的電腦，然後完成下列程序：

1.  按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 部署精靈**。

2.  在部署精靈中按一下 **[安裝或更新 Lync Server 系統]**。

3.  在 [**部署**] 頁面上 [**步驟 2： 安裝或移除 Lync Server 元件**，按一下 [**再執行一次**。

4.  在 [安裝 Lync Server 元件精靈] 在**安裝 Lync Server 元件**] 頁面上，按一下 [**下一步**]。

5.  在 [**指定 Msi 的路徑**] 頁面上輸入 ocscore.msi 檔 （包含 Lync Server 安裝媒體檔案） 的路徑，然後按一下 [**下一步**。

6.  在 **[執行命令]** 頁面上，按一下 **[完成]**。

若要確保所需的 Lync Server 服務已啟動，請按一下 [**執行**] 標題下**步驟 4： 啟動服務**在 [**部署**] 頁面

</div>

<span> </span>

</div>

</div>

</div>

