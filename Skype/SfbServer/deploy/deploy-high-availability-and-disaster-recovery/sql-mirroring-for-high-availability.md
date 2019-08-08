---
title: 在商務用 Skype Server 2015 中部署適用于後端伺服器高可用性的 SQL 鏡像
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: '若要能夠部署 SQL 鏡像, 您的伺服器必須執行至少 SQL Server 2008 R2。 這個版本必須在所有涉及的伺服器上執行: 主要、鏡像和見證。 如需詳細資訊, 請參閱 SQL Server 2008 的累積更新套件 9 (Service Pack 1)。'
ms.openlocfilehash: 61f479adaf5c93833ece65b9781e635d16d696cd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240006"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中部署適用于後端伺服器高可用性的 SQL 鏡像


若要能夠部署 SQL 鏡像, 您的伺服器必須執行至少 SQL Server 2008 R2。 這個版本必須在所有涉及的伺服器上執行: 主要、鏡像和見證。 如需詳細資訊, 請參閱[SQL Server 2008 的累積更新套件 9 (Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921))。

一般來說, 在具有見證的兩台後端伺服器之間設定 SQL 鏡像需要下列事項:

- 主伺服器版本的 SQL Server 必須支援 SQL 鏡像。

- [主要]、[鏡像] 和 [見證伺服器] (如果已部署) 必須有相同版本的 SQL Server。

- 主要和鏡像必須擁有相同版本的 SQL Server。 見證可能會有不同的版本。

如需針對見證角色支援哪些 SQL 版本的 SQL 最佳做法, 請參閱[資料庫鏡像見證](https://go.microsoft.com/fwlink/p/?LinkId=247345)。

您可以使用拓撲產生器來部署 SQL 鏡像。 您可以在 [拓撲建立器] 中選取一個選項來鏡像資料庫, 而 [拓撲建立器] 會在您發佈拓撲時設定鏡像 (包括設定見證)。 請注意, 您可以在設定或移除鏡像的同時, 設定或移除見證。 不需要單獨部署或移除見證的個別命令。

若要設定伺服器鏡像, 您必須先正確設定 SQL 資料庫許可權。 如需詳細資訊, 請參閱為[資料庫鏡像或 AlwaysOn 可用性群組 (SQL Server) 設定登入帳戶](https://go.microsoft.com/fwlink/p/?LinkId=268454)。

有了 SQL 鏡像, 資料庫復原模式永遠都設為**Full**, 這表示您必須密切監視事務日誌大小, 並定期備份事務日誌, 以免在後端伺服器上耗盡磁碟空間。 事務記錄備份的頻率取決於記錄的增長率, 而這取決於前端池中使用者活動所產生的資料庫事務。 我們建議您決定您的部署工作負載預期的事務日誌增長量, 讓您可以據此進行規劃。 下列文章提供有關 SQL 備份與記錄管理的其他資訊:

- [資料庫恢復模型](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [備份概述](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [備份事務日誌](https://go.microsoft.com/fwlink/p/?LinkId=268452)

有了 SQL 鏡像, 您可以在建立池時, 或在已建立池之後, 設定拓撲以進行鏡像。

> [!IMPORTANT]
> 只有在主要、鏡像和見證 (如果需要) 伺服器都屬於同一個網域時, 才支援使用拓撲建立器或 Cmdlet 來設定及移除 SQL 鏡像。 如果您想要在不同網域中的伺服器之間設定 SQL 鏡像, 請參閱您的 SQL Server 檔。

> [!IMPORTANT]
> 每當您對後端資料庫鏡像關聯進行變更時, 您必須重新開機池中的所有前端伺服器。 > 進行鏡像變更 (例如變更鏡像的位置), 您必須使用拓撲建立器來執行這三個步驟:

1. 從舊的鏡像伺服器移除鏡像。

2. 將 [鏡像] 新增至新的鏡像伺服器。

3. 發佈拓撲。

> [!NOTE]
> 必須針對要寫入的鏡像檔案建立檔案共用, 而且 SQL Server 和 SQL 代理程式在其上執行的服務需要讀/寫存取權。 如果 SQL Server 服務是在網路服務的內容下執行, 您可以將網域\< \> \\<SQLSERVERNAME\>$ 的使用者新增至主體和鏡像 SQL server, 以進行共用許可權。 $ 對於確認這是電腦帳戶而言, 這是很重要的。

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>在拓撲建立器中建立池時設定 SQL 鏡像

1. 在 [**定義 SQL store** ] 頁面上, 按一下 [ **SQL 存放區**] 方塊旁的 [**新增**]。

2. 在 [**定義新的 SQL**市集中] 頁面上, 指定主要商店, 選取 [**此 sql 實例是在鏡像關聯中**], 指定 sql 鏡像埠號碼 (預設值為 5022), 然後按一下 **[確定]**。

3. 回到 [**定義 sql store** ] 頁面上, 選取 [**啟用 SQL store 鏡像**]。

4. 在 [**定義新的 SQL store** ] 頁面中, 指定要用來做為鏡像的 SQL 存放區。 選取 [**這個 SQL 實例是在鏡像關聯中**], 指定埠號碼 (預設值為 5022), 然後按一下 **[確定]**。

5. 如果您想要此鏡像的見證, 請執行下列動作:

    是. 選取 **[使用 SQL 鏡像見證] 來啟用自動容錯移轉**。

    乙. 在 [**定義 SQL 書店**] 頁面中, 選取 **[使用 SQL 鏡像見證來啟用自動容錯移轉**], 然後指定要用作見證的 SQL Store。

    c-clip. 指定埠號碼 (預設值為 7022), 然後按一下 **[確定]**。

6. 在拓撲中定義完您的 [前端] 池及所有其他角色之後, 請使用 [拓撲建立器] 發佈拓撲。 當拓撲發佈時, 如果主機中央管理儲存區的前端池已啟用 SQL 鏡像, 您會看到建立主要和鏡像 SQL store 資料庫的選項。

    按一下 [**設定**], 然後輸入要做為鏡像備份之檔案共用使用的路徑。

    按一下 **[確定]** , 然後按一下 **[下一步**], 建立資料庫併發布拓撲。 將會部署鏡像與見證 (如果已指定)。

您可以使用 [拓撲建立器] 來編輯已存在的 [池] 的屬性, 以啟用 SQL 鏡像。

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>在拓撲建立器中新增 SQL 鏡像至現有的前端池

1. 在拓撲建立器中, 以滑鼠右鍵按一下該池子, 然後按一下 [**編輯屬性**]。

2. 選取 [**啟用 SQL Store 鏡像**], 然後按一下 [**鏡像 SQL store**] 旁的 [**新增**]。

3. 指定您要用來做為鏡像的 SQL 存放區。

4. 選取 [**這個 sql 實例是在鏡像關聯中**], 指定 [SQL 鏡像埠號碼] 預設埠為 5022), 然後按一下 **[確定]**。

5. 如果您想要設定見證, 請選取 **[使用 SQL 鏡像見證來啟用自動容錯移轉**], 然後按一下 [**新增**]。

6. 指定您要用來做為見證的 SQL store。

7. 選取 [**這個 sql 實例是在鏡像關聯中**], 指定 SQL 鏡像埠號碼 (預設埠為 7022), 然後按一下 **[確定]**。

8. 按一下 [確定]****。

9. 發佈拓撲。 當您這麼做時, 系統會提示您安裝資料庫。

    在拓撲發佈程式期間, 系統會要求您定義檔案共用路徑。 參與鏡像的 SQL 伺服器必須擁有此檔案共用的讀/寫存取權, 才能建立鏡像。

接著, 您必須先安裝資料庫, 然後再繼續進行下一個步驟。

設定 SQL 鏡像時, 請記住下列事項:

- 如果鏡像端點已存在, 則會使用在該處定義的埠來重複使用它, 並將略過您在拓撲中指定的埠。

- 已針對相同伺服器上的其他應用程式 (包括適用于其他 SQL 實例的任何埠) 已分配的任何埠, 都不應該用於目前已安裝的 SQL 實例。 這表示如果您在同一個伺服器上安裝了多個 SQL 實例, 就不一定要使用相同的埠進行鏡像。 如需詳細資訊, 請參閱下列文章:

  - [指定伺服器網路位址 (資料庫鏡像)](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [資料庫鏡像端點 (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>使用商務用 Skype Server 2015 管理命令介面 Cmdlet 來設定 SQL 鏡像

設定鏡像最簡單的方法是使用拓撲建立器, 不過您也可以使用 Cmdlet 來執行此操作。

1. 開啟商務用 Skype Server 2015 管理命令介面視窗, 並執行下列 Cmdlet:

   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    例如：

   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    您會看到下列內容:

   <pre>
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
   </pre>

2. 確認下列事項:

    - 如果在主要 SQL Server e04-ocs 中啟用 Windows 防火牆, 則可透過防火牆存取埠5022。 local\rtc。

    - 如果在鏡像 SQL Server K16-ocs 中啟用 Windows 防火牆, 則可透過防火牆存取埠5022。 local\rtc。

    - 如果在見證 SQL Server AB14-lct 中啟用 Windows 防火牆, 則可透過防火牆存取埠7022。 local\rtc。

   - 在所有主要和鏡像 SQL 伺服器上執行 SQL Server 的帳戶, 都有讀取/寫入檔案共用\\E04-OCS\csdatabackup 的許可權

   - 確認 Windows 管理工具 (WMI) 提供者正在所有這些伺服器上執行。 這個 Cmdlet 使用這個提供者來尋找在所有主要、鏡像伺服器和見證伺服器上執行之 SQL Server 服務的帳戶資訊。

   - 確認執行此 Cmdlet 的帳戶具有為所有鏡像伺服器的資料和記錄檔案建立資料夾的許可權。

   - 請注意, SQL 實例執行所用的使用者帳戶必須具備檔案共用的讀/寫許可權。 如果檔案共用位於不同的伺服器上, 且 SQL 實例執行的是本機系統帳戶, 則您必須將檔案共用許可權授與託管 SQL 實例的伺服器。

3. 輸入 A, 然後按 ENTER。

    將會設定鏡像。

    **安裝-CsMirrorDatabase**會安裝鏡像, 並針對主要 SQL 市集中存在的所有資料庫設定鏡像。 如果您只想針對特定的資料庫設定鏡像, 您可以使用-DatabaseType 選項, 或者, 如果您想要針對除幾個資料庫以外的所有資料庫設定鏡像, 您可以使用-ExcludeDatabaseList 選項, 以及逗號分隔的資料庫清單要排除的名稱。

    例如, 如果您將下列選項新增至**安裝-CsMirrorDatabase**, 除了 rtcab 和 rtcxds 以外的所有資料庫都將會進行鏡像。

    `-ExcludeDatabaseList rtcab,rtcxds`

   例如, 如果您將下列選項新增至**安裝-CsMirrorDatabase**, 則只會鏡像 rtcab、rtcshared 和 rtcxds 資料庫。

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>移除或變更 SQL 鏡像

若要在拓撲建立器中移除池的 SQL 鏡像, 您必須先使用 Cmdlet, 才能在 SQL Server 中移除該鏡像。 然後, 您就可以使用 [拓撲建立器] 從拓撲中移除鏡像。 若要在 SQL Server 中移除鏡像, 請使用下列 Cmdlet:

```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

例如, 若要移除鏡像並刪除使用者資料庫的資料庫, 請輸入下列內容:

```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

此`-DropExistingDatabasesOnMirror`選項會使受影響的資料庫從鏡像中刪除。

接著, 若要從拓撲中移除鏡像, 請執行下列動作:

1. 在拓撲建立器中, 以滑鼠右鍵按一下該池, 然後按一下 [**編輯屬性**]。

2. 取消核取 [**啟用 SQL Store 鏡像**], 然後按一下 **[確定]**。

3. 發佈拓撲。

## <a name="removing-a-mirroring-witness"></a>移除鏡像見證

如果您需要從後端伺服器鏡像設定中移除見證, 請使用此程式。

1. 在拓撲建立器中, 以滑鼠右鍵按一下該池, 然後按一下 [**編輯屬性**]。

2. 取消核取 **[使用 SQL Server 鏡像見證來啟用自動容錯移轉**], 然後按一下 **[確定]**。

3. 發佈拓撲。

    發佈拓撲之後, 您會看到一則訊息, 其中包含下列內容

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    不過, 請勿遵循該步驟, 而且不要輸入`Uninstall-CsMirrorDatabase` , 否則就會卸載整個鏡像設定。

4. 若要只從 SQL Server 設定中移除見證, 請依照[從資料庫鏡像會話中移除見證伺服器 (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456)中的指示進行。


