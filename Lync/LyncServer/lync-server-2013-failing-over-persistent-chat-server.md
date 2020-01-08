---
title: Lync Server 2013：容錯移轉常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 021b34cafd91397cc36da1dbc22f91b8665aea96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中容錯移轉常設聊天室伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

持續性聊天伺服器的容錯移轉主要是手動程式設計。

容錯移轉程式的假設是次要資料中心已啟動且正在執行，但主要持久聊天資料庫所在的持久聊天伺服器服務完全無法使用，包括下列各項：

  - 持續聊天伺服器主資料庫和持續聊天伺服器鏡像資料庫已關閉。

  - Lync Server 前端伺服器已關閉。

此程式是以兩個基本步驟為基礎：

  - 復原主要持久聊天資料庫（mgc）。

  - 為新的主資料庫建立鏡像。

永久聊天規範資料庫（mgccomp）未進行容錯移轉。 此資料庫的內容是暫時性的，而且會在合規性配接器處理資料時清除。 您的責任是永久聊天管理員，正確管理配接器輸出以避免資料遺失。

<div>

## <a name="to-fail-over-persistent-chat-server"></a>若要容錯移轉持久聊天伺服器

1.  從持續聊天伺服器備份記錄傳送資料庫中移除記錄傳送。
    
    1.  使用 SQL Server Management Studio，連線到持久聊天伺服器備份 mgc 資料庫所在的資料庫實例。
    
    2.  開啟 [查詢] 視窗至 [主資料庫]。
    
    3.  使用下列命令來刪除記錄傳送：
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  將備份共用中的任何 uncopied 備份檔案複製到備份伺服器的 [複製目的地] 資料夾。

3.  將任何未套用的事務記錄備份以順序套用到次要資料庫。 如需詳細資訊，請參閱「如何：套用事務記錄備份（Transact-sql）」 http://go.microsoft.com/fwlink/p/?linkid=247428。

4.  讓備份 mgc 資料庫在線上。 使用在步驟1b 中開啟的 [查詢] 視窗，執行下列動作：
    
    1.  結束所有 mgc 資料庫連線（如果有的話）：
        
        1.  **exec sp\_who2**可識別 mgc 資料庫的連線。
        
        2.  **kill \<spid\> **以結束這些連線。
    
    2.  讓資料庫處於線上狀態：
        
        1.  **使用恢復來還原資料庫 mgc**。

5.  在 Lync Server 管理命令介面中，使用命令**CsPersistentChatState 身分識別 "服務： atl-cs-001.litwareinc.com" – PoolState FailedOver**容錯移轉至 mgc 備份資料庫。 請務必以 atl-cs-001.litwareinc.com 的持久聊天池來取代完整的功能變數名稱。
    
    Mgc 備份資料庫現在是作為主要資料庫。

6.  在 Lync Server 管理命令介面中，請使用**CsMirrorDatabase** Cmdlet 來為現在作為主要資料庫的備份資料庫建立高可用性鏡像。 使用備份資料庫實例作為主要資料庫，將備份鏡像資料庫實例做為鏡像實例。 這與在安裝期間最初為主要資料庫設定的同一個鏡像。 如需詳細資訊，請參閱在 Lync Server 2013 中的 [使用 Lync Server Management Shell Cmdlet][部署 SQL 鏡像以取得後端伺服器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的章節。

7.  設定持續聊天伺服器的使用中伺服器。 從 Lync Server 命令 Shell，使用**CsPersistentChatActiveServer** Cmdlet 來設定作用中伺服器的清單。
    
    <div>
    

    > [!IMPORTANT]  
    > 所有的作用中伺服器都必須位於與新的主資料庫相同的資料中心內，或是在具有低延遲/高頻寬連接的資料中心中。

    
    </div>
    
    此時，來自持久聊天伺服器主要資料庫的容錯移轉至持續聊天伺服器備份資料庫成功完成。

</div>

</div>

<span> </span>

</div>

</div>

</div>

