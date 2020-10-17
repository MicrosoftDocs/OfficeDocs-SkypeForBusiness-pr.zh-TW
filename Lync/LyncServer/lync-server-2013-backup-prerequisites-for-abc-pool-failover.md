---
title: Lync Server 2013： ABC 集區容錯移轉的備份必要條件
description: Lync Server 2013： ABC 集區容錯移轉的備份必要條件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05eb0d2ad50f1ed4f04964158fb5d22d079f3b50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552329"
---
# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Lync Server 2013 中的 ABC 集區容錯移轉的備份必要條件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-26_

若要取得使用 ABC 集區容錯移轉程式的最大好處，您必須先執行某些備份，然後才會發生災難和容錯移轉：

  - 您必須使用 **export-cslisconfiguration 指令程式** ，定期備份組區 A 中 (.lis) 設定資料的位置資訊服務。
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - 您必須使用 **Export-CsRgsConfiguration** Cmdlet，定期備份組區 A 中的回應群組設定資料。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    一般而言，我們會建議您執行每日備份，但是如果您有大量變更，也許會想要排定更多次的備份。 發生嚴重損壞時，您可能會遺失的資訊量取決於備份頻率，以及變更的頻率與數量。
    
    回應群組應用程式只能為每個集區儲存一組應用層級設定。 您可以透過 **Get-CsRgsConfiguration** Cmdlet 來存取這些設定。 這些設定包含預設的等候音樂設定、預設的等候音樂音訊檔、代理程式的環回寬限期及呼叫內容設定。 您可以使用**ReplaceExistingSettings**參數，透過**Import-CsRgsConfiguration** Cmdlet 從一個集區轉接至另一個集區，但此作業將會覆寫目的地集區中的任何應用層級設定。
    
    <div>
    

    > [!TIP]  
    > 在不同的位置，保留已用來設定回應群組應用程式之所有原始音訊檔案的備份副本， (也就是說，任何錄製或暫止的音樂檔案) 。

    
    </div>
    
    如果您有任何已針對集區中的通話駐留上傳的任何自訂已等候音樂檔案，您應該將這些檔案複本保留在其他位置。 這些檔案不會作為 Lync Server 2013 嚴重損壞修復程式的一部分進行備份，如果上傳至集區的檔案損毀、損毀或已被清除，將會遺失。
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > 通話駐留應用程式只能為每個集區儲存一組設定及一個自訂的等候音樂音訊檔。 您可以透過 <STRONG>CsCpsConfiguration</STRONG> Cmdlet 來存取這些設定。 由於通話駐留的嚴重損壞復原機制取決於備份組區的通話駐留應用程式，因此當發生災難時，不會備份或保留主要集區的設定。 如果丟失主要集區，將無法復原這些設定，而且當部署新集區以取代主要集區時，必須重新設定通話駐留設定和任何自訂的等候音樂音訊檔。

    
    </div>

  - 如果您將任何宣告設定為「未指派的號碼語音」功能的一部分，我們建議您保留另一個位置，以供初始設定期間使用的任何原始音訊檔的副本。 如果您未這麼做，您可以在匯入音訊檔的伺服器或集區的檔案存放區中取得所設定的音訊檔複本。 這些檔案不會作為 Lync Server 2013 嚴重損壞修復程式的一部分進行備份，如果上傳至集區的檔案損毀、損毀或已被清除，將會遺失。 若要從伺服器或集區的檔案存放區中複製所有用來設定未指派號碼語音功能的音訊檔，請使用：
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - 如果您在集區中有監控和封存資料庫，您應該使用 SQL Server 管理工具來備份資料庫。 在 ABC 容錯移轉程式中，如果在集區 A 中組合這些資料庫，則不會保留監控和封存資料庫，因為這些資料庫不是透過 Lync Server 備份服務來備份。

</div>

<span> </span>

</div>

</div>

</div>

