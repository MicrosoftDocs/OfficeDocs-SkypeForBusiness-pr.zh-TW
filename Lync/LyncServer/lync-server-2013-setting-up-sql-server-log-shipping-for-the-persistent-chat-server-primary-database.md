---
title: Lync Server 2013：設定 Persistent Chat Server 主資料庫的 SQL Server 記錄傳送
description: Lync Server 2013：設定 Persistent Chat Server 主資料庫的 SQL Server 記錄傳送。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72b7e68bd0cb7b9f544b86a15204d3e832692ec1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554259"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>在 Lync Server 2013 中為 Persistent Chat Server 主資料庫設定 SQL Server 記錄傳送

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-12_

使用 SQL Server Management Studio 連線至 Persistent Chat Server 次要記錄傳送資料庫實例，並確定 SQL Server 代理程式正在執行中。

使用 SQL Server Management Studio 連線至 Persistent Chat 主要資料庫實例，請執行下列步驟：

1.  確定 SQL Server 代理程式正在執行中。

2.  用滑鼠右鍵按一下 mgc 資料庫，然後按一下 **[屬性]**。

3.  在 **[選取頁面]** 下，按一下 **[交易記錄傳送]**。

4.  選取 **[將此啟用為記錄傳送組態的主要資料庫]** 核取方塊。

5.  在 [交易記錄備份]**** 底下，按一下 [備份設定]****。

6.  在 [備份資料夾的網路路徑]**** 方塊中，輸入您為交易記錄備份資料夾建立之共用的網路路徑。

7.  如果備份檔案夾位於主伺服器上，請輸入備份檔案夾的本機路徑（ **如果備份檔案夾位於主伺服器上），請輸入資料夾的本機路徑 (例如： c： \\ backup) ** ] 方塊中。  (如果備份檔案夾不在主伺服器上，您可以將此方塊保留空白。 ) 
    
    <div>
    

    > [!IMPORTANT]  
    > 若主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶之下執行，則必須在主伺服器上建立備份檔案夾，並指定該資料夾的本機路徑。

    
    </div>

8.  設定 **[指定刪除檔案的時限]** 和 **[如果未在此時間內進行備份，則發出警示]** 參數。

9.  查看列在 **[備份作業]** 下的 **[排程]** 方塊中的備份排程。 若要自訂安裝的排程，請按一下 [ **排程**]，然後視需要調整 SQL Server 代理程式排程。

10. 在 [壓縮]**** 底下選取 [使用預設伺服器設定]****，然後按一下 [確定]****。

11. 在 [次要伺服器執行個體與資料庫]**** 底下，按一下 [新增]****。

12. 按一下 **[連線]** ，並聯機至您已設定為次要伺服器的 SQL Server 實例。

13. 在 **[次要資料庫]** 方塊中，從清單中選取 **[mgc]** 資料庫。

14. 在 [ **初始化次要資料庫** ] 索引標籤上，選擇 [ **是]，產生主資料庫的完整備份，並將其還原至次要資料庫 (，並在) 中建立次要資料庫 **。

15. 在 [複製檔案]**** 索引標籤上的 [複製之檔案的目的資料夾]**** 方塊中，輸入複製交易記錄備份的目的資料夾路徑。此資料夾通常位在次要伺服器上。

16. 在 [複製工作]**** 底下，注意列示在 [排程]**** 方塊中的複製排程。 若要自訂安裝的排程，請按一下 [ **排程**]，然後視需要調整 SQL Server 代理程式排程。 此排程應與備份排程大致相同。

17. 在 [還原]**** 索引標籤上的 [還原備份時的資料庫狀態]**** 底下，選擇 [不復原模式]**** 選項。

18. 在 [延遲還原備份至少:]**** 底下，選取 [0 分鐘]****。

19. 在 [如果未在此時間內進行還原，則發出警示]**** 底下，選擇警示臨界值。

20. 在 [還原工作]**** 底下，查看列示在 [排程]**** 方塊中的還原排程。 若要自訂安裝的排程，請按一下 [ **排程**]，並視需要調整 SQL Server 代理程式排程，然後按一下 **[確定]**。 此排程應與備份排程大致相同。

21. 在 [資料庫內容]**** 對話方塊上按一下 [確定]****，即開始設定程序。

</div>

<span> </span>

</div>

</div>

</div>

