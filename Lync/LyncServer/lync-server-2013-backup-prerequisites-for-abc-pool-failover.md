---
title: Lync Server 2013： ABC 池容錯移轉的備份先決條件
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
ms.openlocfilehash: 37a6b5694d8eaa9467fafa8923bb97423fd6e33f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Lync Server 2013 中 ABC 池容錯移轉的備份先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-26_

若要利用 ABC pool 容錯移轉程式來充分發揮最大益處，您必須先執行特定備份，然後才能發生災難及容錯移轉。

  - 您必須使用**Export CsLISConfiguration** Cmdlet，定期備份來自 pool A 的位置資訊服務（.lis）配置資料。
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - 您必須定期使用**Export CsRgsConfiguration** Cmdlet 來備份 [pool A] 中的回應群組設定資料。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    一般來說，我們建議您執行每日備份，但如果您有大量的變更，您可能會想要排程更頻繁的備份。 災難事件中可能會遺失的資訊量，取決於您的備份頻率，以及變更的頻率與數量。
    
    回應群組應用程式只能儲存一組每個池的應用層級設定。 您可以透過**CsRgsConfiguration** Cmdlet 來存取這些設定。 這些設定包括預設的 [隨用音樂保留] 設定、預設的 [音樂保留中] 音訊檔案、代理程式震鈴-回寬期間，以及通話內容配置。 透過**Import CsRgsConfiguration** Cmdlet，您可以使用**ReplaceExistingSettings**參數，將這些設定從一個池中轉移到另一個池中，但此操作會覆寫目的地池中的任何應用程式層級設定。
    
    <div>
    

    > [!TIP]  
    > 在個別位置，保留已用來設定回應群組應用程式的所有原始音訊檔案（也就是任何錄製或音樂保留盤案檔案）的備份複本。

    
    </div>
    
    如果您有任何自訂的已封存檔案，且已針對某個池中的通話駐留程式上傳，您應該在其他位置保留這些檔案的複本。 這些檔案不會作為 Lync Server 2013 災害復原程式的一部分進行備份，如果上傳到該池的檔案遭到損毀、損毀或清除，這些檔案就會遺失。
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > 通話駐留應用程式只能儲存一組設定，以及每個池中有一個自訂的音樂保留音訊檔案。 您可以透過<STRONG>CsCpsConfiguration</STRONG> Cmdlet 來存取這些設定。 因為通話駐留的災害復原機制依賴于備份池的通話駐留應用程式，所以如果發生災難，主要池的設定就不會備份或保留。 如果主要的池遺失，則無法復原這些設定，而且當部署新的池來取代主要池時，通話寄存設定及任何自訂的音樂保留音訊檔案都必須重新設定。

    
    </div>

  - 如果您將任何宣告設定為「未指派的數位語音」功能的一部分，我們建議您在初始配置期間，將任何原始音訊檔案的複本保留在其他位置。 如果您未執行此動作，您可以在已匯入音訊檔案的伺服器或池的檔案存放區中取得已設定音訊檔案的複本。 這些檔案不會作為 Lync Server 2013 災害復原程式的一部分進行備份，如果上傳到該池的檔案遭到損毀、損毀或清除，這些檔案就會遺失。 若要從伺服器或文件庫的檔案存放區中複製所有用來設定 [未指派數位語音] 功能的音訊檔案，請使用：
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - 如果您已在池中監視及封存資料庫，您應該使用 SQL Server 管理工具將其備份。 在 ABC 容錯移轉程式中，如果 collocated 在 pool A 中，系統不會保留監視和封存資料庫，因為這些資料庫不是透過 Lync Server 備份服務來備份。

</div>

<span> </span>

</div>

</div>

</div>

