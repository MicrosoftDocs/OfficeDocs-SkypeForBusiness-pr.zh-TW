---
title: Lync Server 2013：容錯移轉持久聊天伺服器
description: Lync Server 2013：容錯移轉 Persistent Chat Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42a3a8f5df203cc23be39a4a691ad713330eab59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554959"
---
# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中容錯移轉 Persistent Chat Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

Persistent Chat Server 的容錯移轉是設計為主要是手動處理常式。

容錯移轉程式的假設是在次要資料中心啟動並執行，但主要 Persistent Chat 資料庫所在的 Persistent Chat Server 服務完全無法使用，包括下列各項：

  - Persistent Chat Server 主資料庫和 Persistent Chat Server 鏡像資料庫已停機。

  - Lync Server 前端伺服器已關機。

此程序主要有兩個基本步驟：

  - 復原主要 Persistent Chat database (mgc) 。

  - 建立新主要資料庫的鏡像。

Persistent Chat 規範資料庫 (mgccomp) 未進行容錯移轉。 此資料庫的內容僅為暫時性，且會在規範介面卡處理資料時被清除。 您的責任是 Persistent Chat Administrator，可正確管理配接器輸出以避免資料遺失。

<div>

## <a name="to-fail-over-persistent-chat-server"></a>若要容錯移轉持久聊天伺服器

1.  從 Persistent Chat Server 備份記錄傳送資料庫中移除記錄傳送。
    
    1.  使用 SQL Server Management Studio，連接至 Persistent Chat Server backup mgc 資料庫所在的資料庫實例。
    
    2.  開啟 Master 資料庫的查詢視窗。
    
    3.  使用下列命令移除記錄傳送：
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  從備份共用複製所有未複製的備份檔案至備份伺服器的複製目的地資料夾。

3.  依序將所有未套用的交易記錄備份套用至次要資料庫。 如需詳細資訊，請參閱 how to： Apply Transaction Log Backup (Transact-SQL) 」 at https://go.microsoft.com/fwlink/p/?linkid=247428 。

4.  若要使備份 mgc 資料庫上線。請使用步驟 1b 中開啟的查詢視窗，執行下列動作：
    
    1.  結束所有 mgc 資料庫的連線 (若有連線)：
        
        1.  **exec sp \_ who2** ，以識別 mgc 資料庫的連線。
        
        2.  **kill \<spid\> **以結束這些連線。
    
    2.  使資料庫上線：
        
        1.  **restore database mgc with recovery**。

5.  在 Lync Server 管理命令介面中，使用命令 **Set-CsPersistentChatState 身分識別 "服務： atl-ws-01" –PoolState FailedOver** 以容錯移轉至 mgc 備份資料庫。 請務必將 Persistent Chat 集區的完整功能變數名稱取代為 atl-cs-001.litwareinc.com。
    
    現在 mgc 備份資料庫已是主要資料庫。

6.  在 Lync Server 管理命令介面中，使用 **Install-CsMirrorDatabase** Cmdlet 來建立現在用作主資料庫之備份資料庫的高可用性鏡像。 使用備份資料庫執行個體作為主要資料庫，而使用備份鏡像資料庫執行個體作為鏡像執行個體。 此鏡像並不是安裝程式期間，最初為主要資料庫設定的鏡像。 如需詳細資訊，請參閱在 [Lync server 2013 中針對後端伺服器高可用性部署 SQL 鏡像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)中的「使用 Lync Server 管理命令介面 Cmdlet」一節。

7.  設定 Persistent Chat Server active server。 在 Lync Server 命令命令介面中，使用 **Set-CsPersistentChatActiveServer** Cmdlet 來設定作用中的伺服器清單。
    
    <div>
    

    > [!IMPORTANT]  
    > 所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。

    
    </div>
    
    此時，從 Persistent Chat Server 主資料庫到 Persistent Chat Server backup 資料庫的容錯移轉已成功完成。

</div>

</div>

<span> </span>

</div>

</div>

</div>

