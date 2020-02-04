---
title: Lync Server 2013：針對常設聊天室伺服器主要資料庫設定 SQL Server 記錄傳送
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
ms.openlocfilehash: ae44d410ef165cdd4f77b877afcfb9349dd0ec00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>在 Lync Server 2013 中針對常設聊天室伺服器主要資料庫設定 SQL Server 記錄傳送

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-12_

使用 SQL Server Management Studio，連線至持續聊天伺服器次要記錄傳送資料庫實例，並確認 SQL Server 代理程式正在執行。

如果您使用的 SQL Server Management Studio 已連接至持續聊天的主要資料庫實例，請執行下列步驟：

1.  請確定 SQL Server 代理程式正在執行。

2.  以滑鼠右鍵按一下 mgc 資料庫，然後按一下 [**屬性**]。

3.  在 [**選取頁面**] 底下，按一下 [**事務記錄傳送**]。

4.  選取 [將**此項啟用為記錄傳送設定的主要資料庫**] 核取方塊。

5.  在 [**事務記錄備份**] 底下，按一下 [**備份設定**]。

6.  在 [**備份檔案夾的網路路徑**] 方塊中，輸入您針對 [事務記錄備份] 資料夾建立之共用的網路路徑。

7.  如果備份檔案夾位於主要伺服器上，請在 [如果備份檔案夾位於主要伺服器上] 中輸入備份檔案夾的本機路徑 **，請輸入資料夾的本機路徑（範例： [c：\\備份]）** ] 方塊。 （如果備份檔案夾不在主要伺服器上，您可以將此方塊保留空白。）
    
    <div>
    

    > [!IMPORTANT]  
    > 如果主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶下執行，您必須在主要伺服器上建立您的備份檔案夾，並指定該資料夾的本機路徑。

    
    </div>

8.  設定 [**刪除舊**檔的檔案]，並在參數**中不執行任何備份時發出警示**。

9.  查看 [**備份作業**] 底下 [**排程**] 方塊中所列的備份排程。 若要自訂您的安裝排程，請按一下 [**排程**]，然後根據需要調整 SQL Server 代理程式排程。

10. 在 [**壓縮**] 底下，選取 **[使用預設伺服器設定**]，然後按一下 **[確定]**。

11. 在 [**次要伺服器實例與資料庫**] 底下，按一下 [**新增**]。

12. 按一下 **[連線]** 並聯機到您已設定為次要伺服器的 SQL Server 實例。

13. 在 [**次要資料庫**] 方塊中，從清單中選取**mgc**資料庫。

14. 在 [**初始化次要資料庫**] 索引標籤上，選擇 [**是]、[產生主資料庫的完整備份]，然後將它還原到次要資料庫（如果不存在，則建立次要資料庫）**。

15. 在 [**複製**檔案] 索引標籤的 [複製的檔案**目的地資料夾**] 方塊中，輸入應將事務記錄備份複製到其中的資料夾路徑。 這個資料夾通常位於副伺服器上。

16. 請注意，[**複製作業**] 底下 [**排程**] 方塊中所列的複製排程。 若要自訂您的安裝排程，請按一下 [**排程**]，然後根據需要調整 SQL Server 代理程式排程。 此排程應該與備份排程大致相同。

17. 在 [**還原**] 索引標籤上，在 [**還原備份時資料庫狀態**] 底下，選擇 [**無復原模式]** 選項。

18. 在 [**延遲還原備份至少：**] 底下，選取 [ **0 分鐘**]。

19. 在 [警示] 底下，選擇 [**如果沒有進行任何還原**]。

20. 查看 [**還原作業**] 底下 [**排程**] 方塊中所列的還原排程。 若要自訂您的安裝排程，請按一下 [**排程**]，根據需要調整 SQL Server 代理排程，然後按一下 **[確定]**。 此排程應該與備份排程大致相同。

21. 在 [**資料庫屬性**] 對話方塊中，按一下 **[確定]** 以開始設定程式。

</div>

<span> </span>

</div>

</div>

</div>

