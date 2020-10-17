---
title: Lync Server 2013：還原 Standard Edition Server
description: Lync Server 2013：還原 Standard Edition Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2cd6976324492e0539c47999f78434e1a82706
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542389"
---
# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中還原 Standard Edition server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

若未裝載中央管理存放區的 Standard Edition 伺服器失敗，請遵循本節中的程式。 若中央管理存放區失敗，請參閱 [在 Lync server 2013 中還原主控中央管理存放區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。

<div>


> [!TIP]  
> 建議您先取得系統的影像複本，再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生問題。 您可以在安裝作業系統及 SQL Server 之後擷取影像複本，然後再還原或重新註冊憑證。



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>還原 Standard Edition server

1.  從具有相同完整功能變數名稱 (FQDN) 與失敗電腦相同的全新伺服器開始，安裝作業系統，然後還原或重新註冊憑證。
    
    <div>
    

    > [!NOTE]  
    > 遵循貴組織的伺服器部署程序執行此步驟。

    
    </div>

2.  從屬於 RTCUniversalServerAdmins 群組和本機 Administrators 群組成員的使用者帳戶，登入您要還原的伺服器。

3.  將適當的檔案存放區從 $Backup 複製到伺服器上的檔案存放區位置，然後共用資料夾，以還原檔案存放區。
    
    <div>
    

    > [!IMPORTANT]  
    > 還原的檔案存放區的路徑和檔案名應該與備份的檔案存放區完全相同，以便使用該檔案的元件可以存取這些檔案。

    
    </div>

4.  執行拓撲產生器：
    
    1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。
    
    2.  按一下 [從現有部署下載拓撲]****，然後按一下 [確定]****。
    
    3.  選取拓撲，然後按一下 [儲存]****。按一下 [是]**** 確定您的選擇。

5.  流覽至 [Lync Server 安裝] 資料夾或媒體，然後啟動位於 \\ setup amd64Setup.exe 的 Lync Server 部署 \\ 嚮導 \\ 。 使用 Lync Server 部署嚮導執行下列作業：
    
    1.  執行 [步驟 1: 安裝本機組態存放區]****，以安裝本機設定檔。
    
    2.  執行 **步驟2：安裝或移除 Lync Server 元件** ，以安裝 lync server 伺服器角色。
    
    3.  執行 [步驟 3: 要求、安裝或指派憑證]****，以指派憑證。
    
    4.  執行 [步驟 4: 啟動服務]****，以啟動伺服器上的服務。
    
    如需執行 [部署精靈] 的詳細資料，請參閱您要還原之伺服器角色的＜部署＞文件。

6.  執行下列動作還原使用者資料：
    
    1.  將 ExportedUserData.zip 從 $Backup 複製 \\ 到本機目錄。
    
    2.  在您還原使用者資料之前，您必須停止 Lync 服務。 若要這麼做，請輸入：
        
            Stop-CsWindowsService
    
    3.  若要還原使用者資料，請在命令列上輸入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  輸入下列命令以重新開機 Lync 服務：
        
            Start-CsWindowsService

7.  如果您已在此 Standard Edition server 上部署回應群組，請還原回應群組設定資料。 如需詳細資訊，請參閱 [在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。

8.  如果您已在此 Standard Edition server 上部署持續性聊天，請還原 Persistent Chat database (mgc) 。
    
    如果您使用 SQL Server 備份來備份 Persistent 聊天資料庫，請使用 SQL Server 還原程式還原。
    
    如果您使用 Export-CsPersistentChatData Cmdlet 來備份它，請使用 Import-CsPersistentChatData 還原該指令。

</div>

</div>

<span> </span>

</div>

</div>

</div>

