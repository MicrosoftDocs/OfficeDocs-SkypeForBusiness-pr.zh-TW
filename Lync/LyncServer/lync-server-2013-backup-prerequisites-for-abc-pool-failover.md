---
title: 'Lync Server 2013: ABC 備份先決條件集區容錯移轉'
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
ms.openlocfilehash: b9b609a9867b9ca0e6a01f0ced38445ae55c7367
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Lync Server 2013 中的 ABC 集區容錯移轉備份先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-26_

若要獲得最大效益使用 ABC 集區容錯移轉程序，您必須執行特定備份之前發生容錯移轉與嚴重損壞：

  - 您必須定期備份位置資訊服務 (LIS) 組態資料從集區的使用**Export-cslisconfiguration** cmdlet。
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - 您必須定期備份集區的回應群組組態資料使用**Export-csrgsconfiguration** cmdlet。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    一般而言，我們會建議您執行每日備份，但是如果您有大量變更，也許會想要排定更多次的備份。 您可能會遺失發生嚴重損壞的資訊數量取決於頻率的備份，以及在頻率與數量變更。
    
    回應群組應用程式可以儲存只有一組每個集區的應用程式層級設定。 這些設定可透過**Get-csrgsconfiguration**指令程式。 設定包括預設的等候音樂上保留設定、 預設的等候音樂上保留音訊檔案、 代理回響鈴的寬限期，以及來電內容設定。 這些設定可以從一個集區中轉接至另一個透過**Import-csrgsconfiguration** cmdlet，使用**ReplaceExistingSettings**參數，但這項作業將會覆寫目的集區中的任何應用程式層級設定。
    
    <div>
    

    > [!TIP]  
    > 在不同的位置，保留所有的原始音訊檔案已用來設定回應群組應用程式 （亦即，任何錄製或在保留音樂檔案） 的備份複本。

    
    </div>
    
    如果您有任何自訂等候音樂上保留檔案已上載的通話駐留的集區中，您應保留一份這些在另一個位置。 這些檔案不會備份 Lync Server 2013 災害復原程序的一部分，他們將會遺失如果損毀、 損毀，或清除上傳至集區的檔案。
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > 通話駐留應用程式可以儲存只有一組設定與一個自訂等候音樂上保留音訊檔案每個集區。 這些設定可透過<STRONG>取得 CsCpsConfiguration</STRONG>指令程式。 通話駐留災害復原機制取決於備份集區的通話駐留應用程式，因為主要集區的設定不會備份或保留如果發生損毀。 如果主要集區是遺失，不能復原這些設定，以及新集區部署來取代主要集區]、 [通話駐留設定和 [任何自訂等候音樂-上-保留音訊檔案就必須重新設定。

    
    </div>

  - 如果您未指派的號碼語音功能的一部分設定任何宣告，我們建議您保留在另一個位置的初始設定期間使用任何原始音訊檔案的複本。 如果您沒有這樣做，您可以取得一份伺服器或集區的音訊檔案都已匯入的檔案存放區中設定的音訊檔案。 這些檔案不會備份 Lync Server 2013 災害復原程序的一部分，他們將會遺失如果損毀、 損毀，或清除上傳至集區的檔案。 若要複製用來設定未指派號碼語音功能，從伺服器或集區的檔案存放區的所有音訊檔案，請使用：
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - 如果您有監控和封存的集區中的資料庫，您應將其備份使用 SQL Server 管理工具。 ABC 容錯移轉程序中，監控和封存資料庫不會保留如果他們組合在集區 A，因為這些資料庫不會備份透過 Lync Server 備份服務。

</div>

<span> </span>

</div>

</div>

</div>

