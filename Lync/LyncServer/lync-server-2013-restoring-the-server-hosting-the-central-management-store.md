---
title: Lync Server 2013：還原託管中央管理儲存區的伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>在 Lync Server 2013 中還原託管中央管理儲存區的伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

Lync Server 部署只有一個中央管理存儲，複本會複製到執行 Lync Server 伺服器角色的每個伺服器。 本主題說明如何還原託管中央管理存放區的後端伺服器或標準版伺服器。

若要尋找中央管理伺服器所在的池中，請開啟 [拓撲建立器]，按一下 [ **Lync Server**]，然後在右窗格的 [**中央管理伺服器**] 底下尋找。

如果裝載中央管理儲存體的後端伺服器位於鏡像設定中，而且鏡像資料庫仍在運作，我們建議您對這個仍正常運作的鏡像進行備份，然後在主要資料庫和使用此備份進行鏡像資料庫，請遵循下列還原程式。 這是必要的，因為背面端還原需要修改及發佈拓撲，而且只有在主要資料庫託管 CMS 正常運作時才能執行。 另請注意，如果無法發佈拓撲，則無法互換主要和鏡像資料庫角色。

<div>


> [!NOTE]  
> 如果沒有託管中央管理儲存區的後端伺服器或標準版伺服器失敗，請參閱<A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">在 Lync server 2013 中還原企業版後端伺服器</A>，或<A href="lync-server-2013-restoring-a-standard-edition-server.md">在 lync Server 2013 中還原標準版伺服器</A>。 如果裝載中央管理儲存體的後端伺服器是在鏡像設定中，而且只有鏡像失敗，請參閱<A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync Server 2013-mirror 中還原鏡像企業版後端伺服器</A>。 如果有任何其他伺服器失敗，請參閱<A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync server 2013 中還原企業版成員伺服器</A>。



</div>

<div>


> [!TIP]  
> 我們建議您先取得系統的影像複本，然後再開始還原。 您可以使用這個影像做為復原點，以防還原期間發生的問題。 您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>若要還原中央管理存放區

1.  從包含與失敗電腦相同的完整功能變數名稱（FQDN）的乾淨或新伺服器開始，安裝作業系統，然後還原或重新註冊證書。
    
    <div>
    

    > [!NOTE]  
    > 遵循貴組織的伺服器部署程式來執行此步驟。

    
    </div>

2.  從屬於 [RTCUniversalServerAdmins] 群組和 [本機管理員] 群組成員的使用者帳戶登入您要還原的伺服器。

3.  如果您要還原的是標準版伺服器，請將適當的檔案存放區從 $Backup 複製到伺服器上的檔案存放位置，然後共用資料夾，以還原檔案存放區。
    
    <div>
    

    > [!IMPORTANT]  
    > 已還原之檔案存放區的路徑和檔案名應該與已備份的檔案存放區完全相同，以便使用檔案的元件可以存取它們。

    
    </div>

4.  請執行下列其中一項操作：
    
      - 如果您安裝的是標準版伺服器，請流覽至 Lync Server 安裝資料夾或媒體，然後啟動位於\\安裝程式\\Amd64\\setup.exe 的 lync server 部署嚮導。 在 [部署嚮導] 中，按一下 [**準備第一個標準版伺服器**]，然後遵循嚮導來安裝中央管理存放區。
    
      - 如果您要安裝企業後端伺服器，請安裝 SQL Server 2012 或 SQL Server 2008 R2，並保持實例名稱與失敗前相同。
        
        <div>
        

        > [!NOTE]  
        > 根據您要還原的伺服器和您的部署，伺服器可能會包含多個 collocated 或個別的資料庫。 遵循相同的程式，安裝您最初用來部署伺服器的 SQL Server，包括 SQL Server 許可權和登錄名。

        
        </div>

5.  從前端伺服器，啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

6.  重新建立中央管理存放區。 在命令列中，輸入：
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例如：
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  針對中央管理存放區設定 Active Directory 網域服務控制點。 在命令列中，輸入：
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    例如：
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > 如果您遺失連接點，您可以重新執行這個 Cmdlet。

    
    </div>

8.  從 $Backup 匯入集中式管理儲存資料。 在命令列中，輸入：
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    例如：
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  啟用您剛進行的變更。 在命令列中，輸入：
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 啟用拓撲之後，您就可以在資料庫中找到 [拓撲] 檔。

    
    </div>

10. 如果您要還原的是託管 CMS 的企業版後端伺服器，或者您需要重新建立 CMS 的鏡像，請依照此步驟進行。 否則，請跳至步驟11。
    
    您可以執行下列動作來安裝獨立資料庫：
    
    1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。
    
    2.  按一下 [**從現有部署下載拓朴**]，然後按一下 **[確定]**。
    
    3.  選取拓撲，然後按一下 [**儲存**]。 按一下 **[是]** 以確認您的選取專案。
    
    4.  以滑鼠右鍵按一下**Lync Server 2013**節點，然後按一下 [**安裝資料庫**]。
    
    5.  遵循 [**安裝資料庫**] 嚮導。 如果您要還原此伺服器中央管理儲存體以外的資料庫，請在 [**建立資料庫**] 頁面上，選取您要重建的資料庫。
        
        <div>
        

        > [!NOTE]  
        > [<STRONG>建立資料庫</STRONG>] 頁面上只會顯示獨立的資料庫。 Collocated 資料庫是在您執行 Lync Server 部署嚮導時建立的。

        
        </div>
    
    6.  如果您要還原鏡像的後端伺服器，請繼續按照嚮導中的其餘步驟進行，直到您收到建立鏡像資料庫的提示。 選取您要安裝的資料庫，並完成程式。
    
    7.  依照嚮導的其餘部分進行，然後按一下 **[完成**]。
    
    <div>
    

    > [!TIP]  
    > 您可以使用<STRONG>CsDatabase</STRONG> Cmdlet 來建立每個資料庫，以及<STRONG>安裝 CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不需要執行拓撲建立器。 如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">安裝 CsDatabase</A>及<A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">安裝 CsMirrorDatabase</A>。

    
    </div>

11. 如果您要還原的是標準版伺服器，請流覽至 Lync Server 安裝資料夾或媒體，然後啟動位於\\安裝程式\\Amd64\\setup.exe 的 lync server 部署嚮導。 使用 Lync Server 部署嚮導來執行下列動作：
    
    1.  執行**步驟1：安裝本機配置存放區**以安裝本機配置檔案。
    
    2.  執行**步驟2：設定或移除 Lync Server 元件**以安裝 lync server 伺服器角色。
    
    3.  執行**步驟3：要求、安裝或指派憑證**來指派憑證。
    
    4.  執行**步驟4：啟動服務**以在伺服器上啟動服務。
    
    如需執行 [部署嚮導] 的詳細資訊，請參閱您要還原之伺服器角色的部署檔。

12. 若要還原使用者資料，請執行下列動作：
    
    1.  從 $Backup\\將 ExportedUserData 複製到本機目錄。
    
    2.  您必須先停止 Lync services，才能還原使用者資料。 若要這麼做，請輸入：
        
            Stop-CsWindowsService
    
    3.  若要還原使用者資料，請在命令列輸入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  輸入以下內容以重新開機 Lync services：
        
            Start-CsWindowsService

13. 將位置資訊資料還原到中央管理儲存區。 在命令列中，輸入：
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    例如：
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. 如果您已在此 pool 或標準版伺服器上部署回應群組，請還原回應群組設定資料。 如需詳細資訊，請參閱[在 Lync Server 2013 中還原回應群組設定](lync-server-2013-restoring-response-group-settings.md)。

15. 如果您要還原包含封存或監視資料庫的後端伺服器，請使用 SQL Server 管理工具（例如 SQL Server Management Studio）還原封存或監視資料。 如需詳細資訊，請參閱[在 Lync Server 2013 中還原監視或封存資料](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

