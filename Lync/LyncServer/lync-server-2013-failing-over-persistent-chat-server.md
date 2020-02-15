---
title: Lync Server 2013： 容錯移轉常設聊天室伺服器
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
ms.openlocfilehash: a0d5ac758c1e4c87fd5559da1c2a9cf388dc8834
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>容錯移轉 Lync Server 2013 中的常設聊天室伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-05_

Persistent Chat Server 的容錯移轉設計為主要是手動程序。

容錯移轉程序是根據其假設次要資料中心，且是且正在執行，但主要的常設聊天室資料庫所在的 Persistent Chat Server 服務已完全無法使用，包括下列：

  - 常設聊天室伺服器主要資料庫與 Persistent Chat Server 鏡像資料庫已關閉。

  - Lync Server 前端伺服器已離線。

此程序主要有兩個基本步驟：

  - 復原主要常設聊天室資料庫 (mgc)。

  - 建立新主要資料庫的鏡像。

常設聊天室規範資料庫 (mgccomp) 不容錯移轉。 此資料庫的內容僅為暫時性，且會在規範介面卡處理資料時被清除。 是您的責任，常設聊天室系統管理員身分，正確地管理介面卡輸出，以避免資料遺失。

<div>

## <a name="to-fail-over-persistent-chat-server"></a>容錯移轉常設聊天室伺服器

1.  移除記錄傳送從常設聊天室伺服器備份記錄傳送資料庫。
    
    1.  使用 SQL Server Management Studio，連線至 Persistent Chat Server 備份 mgc 資料庫所在的資料庫執行個體。
    
    2.  開啟 Master 資料庫的查詢視窗。
    
    3.  使用下列命令移除記錄傳送：
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  從備份共用複製所有未複製的備份檔案至備份伺服器的複製目的地資料夾。

3.  依序將所有未套用的交易記錄備份套用至次要資料庫。 如需詳細資訊，請參閱 「 How to： 套用一個交易記錄備份 (TRANSACT-SQL) 」 在http://go.microsoft.com/fwlink/p/?linkid=247428。

4.  若要使備份 mgc 資料庫上線。請使用步驟 1b 中開啟的查詢視窗，執行下列動作：
    
    1.  結束所有 mgc 資料庫的連線 (若有連線)：
        
        1.  **exec sp\_who2**來識別 mgc 資料庫的連線。
        
        2.  **kill \<spid\>** 結束這些連線。
    
    2.  使資料庫上線：
        
        1.  **還原使用復原資料庫 mgc**。

5.  Lync Server 管理命令介面中使用命令**Set-cspersistentchatstate-身分識別 」 服務： atl-cs-atl-cs-001.litwareinc.com"– PoolState FailedOver**容錯移轉至 mgc 備份資料庫。 務必確定替代 atl-cs-001.litwareinc.com 的常設聊天室集區的完整的網域名稱。
    
    現在 mgc 備份資料庫已是主要資料庫。

6.  在 Lync Server 管理命令介面，使用**Install-csmirrordatabase** cmdlet 來建立備份資料庫中現在做為主要資料庫的高可用性鏡像。 使用備份資料庫執行個體作為主要資料庫，而使用備份鏡像資料庫執行個體作為鏡像執行個體。 此鏡像並不是安裝程式期間，最初為主要資料庫設定的鏡像。 如需詳細資訊，請參閱 「 使用 Lync Server 管理命令介面 Cmdlet 」 中[的 Lync Server 2013 中的後端伺服器高可用性部署 SQL 鏡像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)。

7.  設定作用中 Persistent Chat Server 的伺服器。 從 Lync Server 命令介面中，使用**Set-cspersistentchatactiveserver** cmdlet 可設定的作用中的伺服器清單。
    
    <div>
    

    > [!IMPORTANT]  
    > 所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。

    
    </div>
    
    此時，從常設聊天室伺服器主要資料庫 Persistent Chat Server 的備份資料庫的容錯移轉即可成功完成。

</div>

</div>

<span> </span>

</div>

</div>

</div>

