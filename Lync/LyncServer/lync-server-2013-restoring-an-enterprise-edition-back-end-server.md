---
title: Lync Server 2013：還原 Enterprise Edition 後端伺服器
description: Lync Server 2013：還原 Enterprise Edition 後端伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2147aec00714704195399449e5d5e4d6ce609fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555209"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>在 Lync Server 2013 中還原 Enterprise Edition 後端伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

在下列兩個案例中，請使用本主題中所述的程式：

  - 鏡像 Enterprise Edition 後端伺服器的主要和鏡像資料庫都會失敗。

  - 未鏡像的 Enterprise Edition 後端伺服器失敗。

如果您有鏡像的 Enterprise Edition 後端，而且只有鏡像或主資料庫失敗，請參閱 [在 lync server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) 用於還原主資料庫，以及 [在 Lync Server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-鏡像](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) 以還原鏡像。

若中央管理存放區失敗，請參閱 [在 Lync server 2013 中還原主控中央管理存放區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是後端伺服器的 Enterprise Edition 成員伺服器失敗，請參閱 [在 Lync server 2013 中還原 Enterprise edition 成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

<div>


> [!TIP]  
> 建議您先取得系統的影像複本，再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生問題。 在您安裝作業系統和 SQL Server 之後，您可能會想要使用影像副本，並還原或重新註冊憑證。



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>若要還原 Enterprise Edition 後端伺服器

1.  從具有相同完整功能變數名稱 (FQDN) 與失敗電腦相同的全新伺服器開始，安裝作業系統，然後還原或重新註冊憑證。
    
    <div>
    

    > [!NOTE]  
    > 遵循貴組織的伺服器部署程序執行此步驟。

    
    </div>

2.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入您要還原的伺服器。

3.  安裝 SQL Server 2012 或 SQL Server 2008 R2，並保持實例名稱與失敗之前相同。
    
    <div>
    

    > [!NOTE]  
    > 視您的部署而定，後端伺服器可能包含多個組合或個別的資料庫。請遵循相同程序來安裝您原本用來部署伺服器的 SQL Server，包括 SQL Server 權限和登入。

    
    </div>

4.  安裝 SQL Server 之後，請執行下列動作：
    
    1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。
    
    2.  按一下 [從現有部署下載拓撲]****，然後按一下 [確定]****。
    
    3.  選取拓撲，然後按一下 [儲存]****。按一下 [是]**** 確定您的選擇。
    
    4.  在 [ **Lync Server 2013** ] 節點上按一下滑鼠右鍵，然後按一下 [ **發行拓撲**]。
    
    5.  依序執行 [發行拓撲精靈]**** 中的步驟。 在 [ **建立資料庫** ] 頁面上，選取您要重新建立的資料庫。
        
        <div>
        

        > [!NOTE]  
        > 只有獨立資料庫會顯示在 [建立資料庫]<STRONG></STRONG> 頁面上。

        
        </div>
    
    6.  若要還原已鏡像的後端，請繼續遵循其餘的嚮導，直到出現提示 **建立鏡像資料庫** 為止。 選取您要安裝的資料庫，然後完成此程式。
    
    7.  依序執行精靈中剩餘的步驟，然後按一下 [完成]****。
    
    <div>
    

    > [!TIP]  
    > 您可以使用 <STRONG>Install-CsDatabase</STRONG> Cmdlet 來建立每個資料庫，並使用 <STRONG>Install-CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不是執行拓撲產生器。 如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。

    
    </div>

5.  執行下列動作還原使用者資料：
    
    1.  將 ExportedUserData.zip 從 $Backup 複製 \\ 到本機目錄。
    
    2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。
    
    3.  在您還原使用者資料之前，您必須停止 Lync 服務。 若要這麼做，請輸入：
        
            Stop-CsWindowsService
    
    4.  若要還原使用者資料，請在命令列上輸入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  輸入下列命令以重新開機 Lync 服務：
        
            Start-CsWindowsService

6.  如果您已在此集區上部署回應群組，請還原回應群組設定資料。 如需詳細資訊，請參閱 [在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。

7.  若您要還原的後端伺服器其中包含封存與監控資料庫，請使用 SQL Server 工具，如 SQL Server Management Studio，來還原封存與監控資料。 如需詳細資訊，請參閱 [在 Lync Server 2013 中還原監控或封存資料](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

