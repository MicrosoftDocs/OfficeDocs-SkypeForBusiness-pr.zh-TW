---
title: 針對後端伺服器高可用性部署 SQL 鏡像
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577d6bb312ae2b31f96fed5f3e5b02e84844adf6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-08_

若要得以部署 SQL 鏡像，您的伺服器至少必須執行 SQL Server 2008 R2。 此版本必須執行於以下所有相關伺服器：主要伺服器、鏡像伺服器、見證伺服器。 如需詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) 。

一般而言，使用見證伺服器在兩個後端伺服器間設定 SQL 鏡像，需要下列各項：

  - 主要伺服器的 SQL Server 版本必須支援 SQL 鏡像。

  - 主要、鏡像與見證伺服器 (若已部署) 必須具有相同的 SQL Server 版本。

  - 主要與鏡像伺服器必須具有相同的 SQL Server 版本，見證伺服器可能有不同的版本。

如需有關見證角色支援哪些 SQL 版本的 SQL 最佳作法，請參閱 MSDN Library 中的「資料庫鏡像見證」 [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) 。

您可以使用拓撲產生器來部署 SQL 鏡像。 您可以在 [拓撲產生器] 中選取一個選項，以鏡像資料庫，而拓撲產生器會設定鏡像 (包括設定見證，如果您想要在發行拓撲時) 。 請注意，設定或移除鏡像伺服器也會同時設定或移除見證伺服器。 僅部署或移除見證伺服器並無個別的命令。

若要設定伺服器鏡像，您必須先正確設定 SQL 資料庫權限。 如需詳細資訊，請參閱設定資料庫鏡像的登入帳戶或 AlwaysOn 可用性群組 (SQL Server) " [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) 。

有了 SQL 鏡像，資料庫復原模式會一律設為 **[完整]**，這表示您必須密切監控交易紀錄的大小並定期備份交易紀錄，以避免用盡後端伺服器上的磁碟機空間。交易記錄的備份頻率取決於記錄的成長率，即根據使用者在前端集區上活動所發生的資料庫交易。建議您針對 Lync 部署工作負載判斷交易記錄的預期成長率，以便進行相應的規劃。下列文章提供 SQL 備份以及記錄管理的其他資訊：

  - 資料庫復原模型： "Recovery 模型 (SQL Server) "，網址為[https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)

  - 備份概述：「備份概述 (SQL Server) "[https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)

  - 備份交易記錄檔：「備份 SQL Server (的交易記錄檔) 」[https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)

有了 SQL 鏡像，您可在建立集區時或在建立集區後設定鏡像的拓撲。



> [!IMPORTANT]
> 只有當主要、鏡像及)  (見證伺服器都屬於相同的網域時，才支援使用拓撲產生器或 Cmdlet 來設定及移除 SQL 鏡像。 若要在不同網域的伺服器間設定 SQL 鏡像，請參閱 SQL Server 文件。





> [!IMPORTANT]
> 每當您變更為後端資料庫鏡像關係時，皆必須重新啟動集區中的前端伺服器。<BR>如需鏡像的變更， (例如變更鏡像) 的位置），您必須使用拓撲產生器來執行下列三個步驟： 
> <OL>
> <LI>
> <P>從舊鏡像伺服器移除鏡像。</P>
> <LI>
> <P>將鏡像新增至新鏡像伺服器。</P>
> <LI>
> <P>發行拓撲。</P></LI></OL>




> [!NOTE]
> 必須針對要寫入的鏡像檔案建立檔案共用，而且執行 SQL Server 與 SQL 代理程式的服務必須具有讀取/寫入存取權。 如果 SQL Server 服務是在 [網路服務] 內容下執行，您可以將 &lt; &gt; &lt; &gt; 主體和鏡像 SQL server 的網域&#92;SQLSERVERNAME $ 新增至 [共用] 許可權。 $ 對識別這是電腦帳戶很重要。


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>在拓撲產生器中建立集區時設定 SQL 鏡像

1.  在 **[定義 SQL 存放區]** 頁面上，按一下 **[SQL 存放區]** 方塊旁邊的 **[新增]**。

2.  在 **[定義新的 SQL 存放區]** 頁面上，指定主要存放區，並選取 **[此 SQL 執行個體為鏡像關係]**，接著指定 SQL 鏡像連接埠號碼 (預設值為 5022)，然後按一下 **[確定]**。

3.  返回 **[定義 SQL 存放區]** 頁面，選取 **[啟用 SQL 存放區鏡像]**。

4.  在 **[定義新的 SQL 存放區]** 頁面中，指定要做為鏡像使用的 SQL 存放區。選取 **[此 SQL 執行個體為鏡像關係]**，指定連接埠號碼 (預設值為 5022)，然後按一下 **[確定]**。

5.  若您想要此鏡像的見證，請執行下列動作：
    
    1.  選取 **[使用 SQL 鏡像見證啟用自動容錯移轉]**。
    
    2.  在 **[定義 SQL 存放區]** 頁面中，選取 **[使用 SQL 鏡像見證啟用自動容錯移轉]**，並指定 SQL 存放區做為見證使用。
    
    3.  指定連接埠號碼 (預設值為 7022)，並按一下 **[確定]**。

6.  在您完成定義您的前端集區和拓撲中的所有其他角色後，請使用拓撲產生器來發佈拓撲。 當發佈拓撲時，如果主控中央管理存放區的前端集區已啟用 SQL 鏡像，您將會看到同時建立主要和鏡像 SQL 存放區資料庫的選項。
    
    按一下 **[設定]**，輸入做為鏡像備份檔案共用的路徑。
    
    依序按一下 **[確定]** 及 **[下一步]** 以建立資料庫和發行拓撲，即會部署鏡像與見證 (若已指定)。

您可以使用拓撲產生器編輯現有集區的屬性，以啟用 SQL 鏡像。

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>在拓撲產生器中將 SQL 鏡像新增至現有前端集區

1.  在 [拓撲產生器] 中，以滑鼠右鍵按一下集區，然後按一下 [**編輯屬性**]。

2.  選取 **[啟用 SQL 存放區鏡像]**，然後按一下 **[鏡像 SQL 存放區]** 旁邊的 **[新增]**。

3.  指定您要做為鏡像使用的 SQL 存放區。

4.  選取 **[此 SQL 執行個體為鏡像關係]**，指定 SQL 鏡像連接埠號碼 (預設值為 5022)，然後按一下 **[確定]**。

5.  如果您要設定見證，請選取 **[使用 SQL 鏡像見證啟用自動容錯移轉]**，再按一下 **[新增]**。

6.  指定您要做為見證使用的 SQL 存放區。

7.  選取 **[此 SQL 執行個體為鏡像關係]**，指定 SQL 鏡像連接埠號碼 (預設值為 7022)，然後按一下 **[確定]**。

8.  按一下 **[確定]**。

9.  發行拓撲。執行此動作時，系統會提示您安裝資料庫。
    
    在拓撲發佈過程中，系統會要求您定義檔共用路徑。 參與鏡像的 SQL 伺服器必須具有此檔案共用的讀/寫存取權，才可建立鏡像。

然後，您必須在進入下個程序前安裝資料庫。

在設定 SQL 鏡像時，請務必牢記下列事項：

  - 如果已存在鏡像端點，將會以定義的連接埠加以重複使用，而且會略過在拓撲中指定的其他連接埠。

  - 在相同伺服器上為其他應用程式配置的連接埠 (包含為其他 SQL 執行個體配置的)，均不應用於隨時可取用的已安裝 SQL 執行個體。這表示，如果您有一個以上的 SQL 執行個體安裝於相同的伺服器上，不得使用相同的連接埠進行鏡像處理。如需詳細資訊，請參閱以下文章：
    
      - 在 MSDN Library 中的「指定伺服器網路位址 (資料庫鏡像) 」[https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - 「資料庫鏡像端點 (SQL Server) "[https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>使用 Lync Server 管理命令介面 Cmdlet 設定 SQL 鏡像

設定鏡像最簡單的方法是使用拓撲產生器，但您也可以使用 Cmdlet 來執行。

1.  開啟 Lync Server 管理命令介面視窗，並執行下列 Cmdlet：
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    例如：
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    您會看到下列訊息：
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  請確認下列各項：
    
      - 如果在主要 SQL Server e04-ocs 中啟用 Windows 防火牆，則可以透過防火牆存取埠5022。 \_ lsipt 本機 \\ rtc。
    
      - 如果已在鏡像 SQL Server K16-ocs 中啟用 Windows 防火牆，則可以透過防火牆存取埠5022。 \_ lsipt 本機 \\ rtc。
    
      - 如果在見證 SQL Server AB14-lct 中啟用 Windows 防火牆，則可以透過防火牆存取埠7022。 \_ lsipt 本機 \\ rtc。
    
      - 在所有主要和鏡像 SQL server 上執行 SQL Server 的帳戶都具有檔案共用 E04 的讀取/寫入權限 \\ \\ -OCS \\ csdatabackup
    
      - 確認 Windows Management Instrumentation (WMI) 提供者正執行於所有伺服器上。Cmdlet 會使用此提供者尋找執行於所有主要、鏡像及見證伺服器的 SQL Server 服務帳戶資訊。
    
      - 確認執行此 Cmdlet 的帳戶具有權限，可為所有鏡像伺服器建立資料與記錄檔的資料夾。
    
      - 請注意，SQL 執行個體用以執行的使用者帳戶必須具有檔案共用的讀取/寫入權限。如果檔案共用在其他的伺服器上，而且 SQL 執行個體執行本機系統帳戶，您必須將檔案共用權限授與託管 SQL 執行個體的伺服器。

3.  輸入 A 並按 ENTER 鍵。
    
    即會設定鏡像。

**Install-CsMirrorDatabase** 會安裝鏡像伺服器，並設定位於主要 SQL 存放區所有資料庫的鏡像。 如果您只想要設定指定資料庫的鏡像，可使用 DatabaseType 選項；或是，如果您想要設定所有 (但部分除外) 資料庫的鏡像，則可使用 ExcludeDatabaseList 選項，並搭配資料庫名稱以逗號分隔的清單加以排除。

例如，如果您將下列選項新增至 **Install-CsMirrorDatabase**，所有資料庫即會作鏡像處理，Rtcab 和 Rtcxds 除外。

`-ExcludeDatabaseList rtcab,rtcxds`

例如，如果您將下列選項新增至 **Install-CsMirrorDatabase**，則只有 Rtcab、Rtcshared 及 Rtcxds 資料庫會作鏡像處理。

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>移除或變更 SQL 鏡像

若要在拓撲產生器中移除集區的 SQL 鏡像，您必須先使用 Cmdlet 將 SQL Server 中的鏡像移除，然後，您可使用拓撲產生器從拓撲移除鏡像。若要移除 SQL Server 中的鏡像，請使用下列 Cmdlet：

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

例如，若要移除鏡像並捨棄使用者資料庫的資料庫，請輸入：

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

此 `-DropExistingDatabasesOnMirror` 選項會從鏡像中刪除受影響的資料庫。

此外，若要從拓撲移除鏡像伺服器，請執行下列動作：

1.  在拓撲產生器中，以滑鼠右鍵按一下集區，再按一下 **[編輯內容]**。

2.  取消核取 **[啟用 SQL 存放區鏡像]** 並按一下 **[確定]**。

3.  發行拓撲。

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>移除鏡像見證

如果您需要從後端伺服器鏡像設定中移除見證，請使用此程式。

1.  在拓撲產生器中，以滑鼠右鍵按一下集區，再按一下 **[編輯內容]**。

2.  取消核取 **[使用 SQL Server 鏡像見證啟用自動容錯移轉]**，按一下 **[確定]**。

3.  發行拓撲。
    
    發行拓撲之後，拓撲產生器會顯示一則訊息，其中包含下列各項：
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    不過，請不要執行該步驟，也不要像那樣輸入 `Uninstall-CsMirrorDatabase` ，否則會卸載整個鏡像設定。

4.  若要從 SQL Server 設定中只移除見證，請依照「從資料庫鏡像會話移除見證 (SQL Server) 」中的指示進行 [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

