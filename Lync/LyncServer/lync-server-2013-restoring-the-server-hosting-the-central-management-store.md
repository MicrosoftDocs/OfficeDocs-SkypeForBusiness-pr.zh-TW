---
title: Lync Server 2013：還原主控中央管理存放區的伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772646b8122e228aa43818aa5fe7fe2fb6689366
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>在 Lync Server 2013 中還原主控中央管理存放區的伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

Lync Server 部署具有單一中央管理存放區，其副本會複製到執行 Lync Server 伺服器角色的每個伺服器。 本主題說明如何還原主控中央管理存放區的後端伺服器或 Standard Edition Server。

若要尋找中央管理伺服器所在的集區，請開啟拓撲產生器，按一下 [ **Lync Server**]，然後在 [**中央管理伺服器**] 底下的右窗格中查看。

如果裝載中央管理存放區的後端伺服器是在鏡像安裝中，而且鏡像資料庫仍可運作，建議您備份此仍運作的鏡像，然後使用此備份執行主要資料庫與鏡像資料庫的完整還原，方法是遵循下列的還原過程進行。 這是必要的，因為後端還原需要修改和發行拓撲，而且只有在主控 CMS 的主資料庫運作時才能執行。 另外請注意，如果無法發佈拓撲，則主要和鏡像資料庫角色無法互換。

<div>


> [!NOTE]  
> 如果未裝載中央管理存放區的後端伺服器或 Standard Edition 伺服器失敗，請參閱在 lync server <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">2013 中還原 Enterprise Edition 後端伺服器</A>或<A href="lync-server-2013-restoring-a-standard-edition-server.md">還原 lync server 2013 中的 Standard Edition server</A>。 如果裝載中央管理存放區的後端伺服器是在鏡像設定中，且只有鏡像失敗，請參閱<A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync server 2013-鏡像中還原鏡像的 Enterprise Edition 後端伺服器</A>。 如果有任何其他伺服器失敗，請參閱<A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync server 2013 中還原 Enterprise Edition 成員伺服器</A>。



</div>

<div>


> [!TIP]  
> 建議您先取得系統的影像複本，再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生問題。 在您安裝作業系統和 SQL Server 之後，您可能會想要使用影像副本，並還原或重新註冊憑證。



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>還原中央管理存放區

1.  從具有相同完整功能變數名稱 (FQDN) 與失敗電腦相同的全新伺服器開始，安裝作業系統，然後還原或重新註冊憑證。
    
    <div>
    

    > [!NOTE]  
    > 遵循貴組織的伺服器部署程序執行此步驟。

    
    </div>

2.  從屬於 RTCUniversalServerAdmins 群組和本機 Administrators 群組成員的使用者帳戶，登入您要還原的伺服器。

3.  若要還原 Standard Edition server，請將適當的檔案存放區從 $Backup 複製到伺服器上的檔案存放區位置，以還原檔案存放區，然後再共用該資料夾。
    
    <div>
    

    > [!IMPORTANT]  
    > 還原的檔案存放區的路徑和檔案名應該與備份的檔案存放區完全相同，以便使用該檔案的元件可以存取這些檔案。

    
    </div>

4.  執行下列其中一項：
    
      - 若要安裝 Standard Edition server，請流覽至 [Lync Server 安裝] 資料夾或媒體，然後啟動位於 \\ setup amd64Setup.exe 的 Lync Server 部署嚮導 \\ \\ 。 在 [部署嚮導] 中，按一下 [**準備第一個 Standard Edition server** ]，然後依照嚮導安裝中央管理存放區。
    
      - 如果您要安裝企業後端伺服器，請安裝 SQL Server 2012 或 SQL Server 2008 R2，並保持實例名稱與失敗之前相同。
        
        <div>
        

        > [!NOTE]  
        > 根據您要還原的伺服器和您的部署，該伺服器可能會包含多個組合或不同的資料庫。 請遵循您原先用來部署伺服器的相同程序來安裝 SQL Server，包括 SQL Server 權限及登入。

        
        </div>

5.  在前端伺服器上，啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

6.  重新建立中央管理存放區。 在命令列中輸入：
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例如：
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  設定中央管理存放區的 Active Directory 網域服務控制點。 在命令列中輸入：
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例如：
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > 如果您遺失連線點，可以重新執行此 Cmdlet。

    
    </div>

8.  從 $Backup 匯入中央管理存放區資料。 在命令列中輸入：
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    例如：
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  啟用您剛才進行的變更。在命令列中輸入：
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 啟用拓撲之後，即可在資料庫中找到拓撲文件。

    
    </div>

10. 如果您要還原的 Enterprise Edition 後端伺服器也是主控 CMS，或者您需要重新建立 CMS 的鏡像，請遵循此步驟。 否則，請跳至步驟11。
    
    執行下列動作，以安裝獨立資料庫：
    
    1.  啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。
    
    2.  按一下 [從現有部署下載拓撲]****，然後按一下 [確定]****。
    
    3.  選取拓撲，然後按一下 [儲存]****。按一下 [是]**** 確定您的選擇。
    
    4.  在 [ **Lync Server 2013** ] 節點上按一下滑鼠右鍵，然後按一下 [**安裝資料庫**]。
    
    5.  遵循 [**安裝資料庫**] 嚮導。 若要還原此伺服器上的中央管理存放區以外的資料庫，請在 [**建立資料庫**] 頁面上，選取您要重新建立的資料庫。
        
        <div>
        

        > [!NOTE]  
        > 只有獨立資料庫會顯示在 [建立資料庫]<STRONG></STRONG> 頁面上。 組合資料庫是在您執行 Lync Server 部署嚮導時建立的。

        
        </div>
    
    6.  若要還原鏡像後端伺服器，請繼續依照嚮導的其餘部分進行，直到您到達建立鏡像資料庫的提示為止。 選取您要安裝的資料庫，然後完成此程式。
    
    7.  依序執行精靈中剩餘的步驟，然後按一下 [完成]****。
    
    <div>
    

    > [!TIP]  
    > 您可以使用<STRONG>Install-CsDatabase</STRONG> Cmdlet 來建立每個資料庫，並使用<STRONG>Install-CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不是執行拓撲產生器。 如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>。

    
    </div>

11. 若要還原 Standard Edition server，請流覽至 [Lync Server 安裝] 資料夾或媒體，然後啟動位於 \\ setup amd64Setup.exe 的 Lync Server 部署 \\ 嚮導 \\ 。 使用 Lync Server 部署嚮導執行下列作業：
    
    1.  執行 [步驟 1: 安裝本機組態存放區]****，以安裝本機設定檔。
    
    2.  執行**步驟2：安裝或移除 Lync Server 元件**，以安裝 lync server 伺服器角色。
    
    3.  執行 [步驟 3: 要求、安裝或指派憑證]****，以指派憑證。
    
    4.  執行 [步驟 4: 啟動服務]****，以啟動伺服器上的服務。
    
    如需執行部署嚮導的詳細資訊，請參閱部署檔中您要還原的伺服器角色。

12. 執行下列動作還原使用者資料：
    
    1.  將 ExportedUserData.zip 從 $Backup 複製 \\ 到本機目錄。
    
    2.  在您還原使用者資料之前，您必須停止 Lync 服務。 若要這麼做，請輸入：
        
            Stop-CsWindowsService
    
    3.  若要還原使用者資料，請在命令列上輸入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  輸入下列命令以重新開機 Lync 服務：
        
            Start-CsWindowsService

13. 將位置資訊資料還原至中央管理存放區。 在命令列中輸入：
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    例如：
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. 如果您已在此集區或 Standard Edition server 上部署回應群組，請還原回應群組設定資料。 如需詳細資訊，請參閱[在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。

15. 若要還原包含封存或監控資料庫的後端伺服器，請使用 SQL Server 管理工具（例如 SQL Server Management Studio）還原封存或監控資料。 如需詳細資訊，請參閱[在 Lync Server 2013 中還原監控或封存資料](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

