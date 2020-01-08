---
title: Lync Server 2013：設定主要鏡像與記錄傳送次要資料庫之間的 SQL Server 記錄傳送
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a>在 Lync Server 2013 中設定主要鏡像與記錄傳送次要資料庫之間的 SQL Server 記錄傳送

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

如果主要持久聊天資料庫發生故障，請執行下列步驟，繼續進行記錄傳送至其鏡像資料庫。

1.  手動將主要持久聊天資料庫容錯移轉到鏡像。 這是使用 Lync Server 管理命令介面和**CsDatabaseFailover** Cmdlet 來完成。 如需詳細資訊，請參閱在[Lync server 2013 中部署 SQL 鏡像以取得後端伺服器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的「使用 Lync Server 管理命令介面 Cmdlet」。

2.  使用 SQL Server Management Studio，連線到主要持久聊天伺服器鏡像實例。

3.  請確定 SQL Server 代理程式正在執行。

4.  以滑鼠右鍵按一下 mgc 資料庫，然後按一下 [**屬性**]。

5.  在 [**選取頁面**] 底下，按一下 [**事務記錄傳送**]。

6.  選取 [將**此項啟用為記錄傳送設定的主要資料庫**] 核取方塊。

7.  在 [**事務記錄備份**] 底下，按一下 [**備份設定**]。

8.  在 [**備份檔案夾的網路路徑**] 方塊中，輸入您針對 [事務記錄備份] 資料夾建立之共用的網路路徑。

9.  如果備份檔案夾位於主要伺服器上，請在 [**如果備份檔案夾位於主要伺服器上**] 中輸入備份檔案夾的本機路徑，請在 [資料夾] 方塊中輸入本機路徑。 （如果備份檔案夾不在主要伺服器上，您可以將此方塊保留空白。）
    
    <div>
    

    > [!IMPORTANT]  
    > 如果主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶下執行，您必須在主要伺服器上建立您的備份檔案夾，並指定該資料夾的本機路徑。

    
    </div>

10. 設定 [**刪除舊**檔的檔案]，並在參數**中不執行任何備份時發出警示**。

11. 查看 [**備份作業**] 底下 [**排程**] 方塊中所列的備份排程。 若要自訂您的安裝排程，請根據需要按一下 [**排程**]，然後調整 SQL Server 代理程式排程。
    
    <div>
    

    > [!IMPORTANT]  
    > 使用您在主要資料庫中使用的相同設定。

    
    </div>

12. 在 [**壓縮**] 底下，選取 **[使用預設伺服器設定**]，然後按一下 **[確定]**。

13. 在 [**次要伺服器實例與資料庫**] 底下，按一下 [**新增**]。

14. 按一下 **[連線]**，然後連線到您已設定為次要伺服器的 SQL Server 實例。

15. 在 [**次要資料庫**] 方塊中，從清單中選取**mgc**資料庫。

16. 在 [**初始化次要資料庫**] 索引標籤上，選取 [**否，次要資料庫已初始化**]。

17. 在 [**複製**檔案] 索引標籤上，于 [**複製的檔案目的地] 資料夾**中，輸入應將事務記錄備份複製到哪個資料夾的路徑，然後按一下 **[確定]**。 這個資料夾通常位於副伺服器上。

18. 開啟 [**腳本**設定] 下拉式清單，然後選取 [**腳本設定至新查詢] 視窗**。

19. 在 [新增查詢] 視窗的 [**資料庫屬性**] 中，按一下 **[確定]** 以開始設定程式。

20. 選取並執行查詢的前半部分（請參閱步驟18）至行：-- \* \* \* \* \* \*結束\* \* \* \* \* \*：要在主要：執行的腳本。
    
    <div>
    

    > [!IMPORTANT]  
    > 手動執行此腳本是必要的，因為 SQL Server Management Studio 不支援 SQL Server 記錄傳送設定中的多個主要資料庫。

    
    </div>

21. 選取 [**取消**] 以關閉 [記錄檔案傳送設定] 面板，並建立能正確實現主要和鏡像資料庫（如果是容錯移轉）的記錄檔傳送的工作設定。

22. 手動將主要持久聊天資料庫容錯回復到主要。 這是使用 Lync Server 管理命令介面和**CsDatabaseFailover** Cmdlet 來完成。 如需詳細資訊，請參閱在[Lync server 2013 中部署 SQL 鏡像以取得後端伺服器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的「使用 Lync Server 管理命令介面 Cmdlet」。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

