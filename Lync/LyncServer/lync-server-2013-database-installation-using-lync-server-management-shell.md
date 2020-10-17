---
title: Lync Server 2013：使用 Lync Server 管理命令介面安裝資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b602e29e0f90a49a031c25d6bb919337bef87b8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516540"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Lync Server 管理命令介面安裝資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-06-16_

伺服器管理員和 SQL Server 系統管理員之間的角色與責任的分離，可能會導致執行延遲。 Lync Server 2013 使用以角色為基礎的存取控制 (RBAC) ，以減輕這些困難。 在某些情況下，SQL Server 系統管理員必須在不是以 SQL Server 為基礎的伺服器上，管理資料庫在 RBAC 之外的安裝。 Lync Server 2013 管理命令介面提供一種方式，讓 SQL Server 管理員執行 Windows PowerShell Cmdlet，以設定具有正確資料和記錄檔的資料庫。 如需詳細資訊，請參閱 [Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。

<div class=" ">


> [!IMPORTANT]  
> 下列程式假設最低的 Lync Server 2013 OCSCore.msi，SQL Server Native Client ( # A1) Microsoft SQL Server 2012 管理物件，已安裝 Microsoft SQL Server 2012 和 Microsoft SQL Server 2012 ADOMD.NET 的 CLR 類型。 OCSCore.msi 位於 \Setup\AMD64\Setup 目錄的安裝媒體中。 其餘的元件位於 \Setup\amd64。 此外，Lync Server 2013 的 Active Directory 準備作業已成功完成。



</div>

**Install-CsDatabase** 是用來安裝資料庫的 Windows PowerShell Cmdlet。 **Install-CsDatabase** Cmdlet 的參數數目很多，但這裡只有少數部分會加以討論。 如需可能的參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面檔。

<div class=" ">


> [!WARNING]  
> 若要避免效能及可能的超時問題，請在參照 SQL Server 服務器的伺服器時，永遠 (Fqdn) 使用完整功能變數名稱。 避免使用僅限主機名稱稱參照。 例如，使用 sqlbe01.contoso.net，但避免使用 SQLBE01。



</div>

若要安裝資料庫， **Install-CsDatabase** 會使用三種主要方法將資料庫放入已準備好的 SQL server 伺服器上：

  - 在未 DatabasePaths 或 UseDefaultSqlPath 的情況下執行 **Install-CsDatabase** 。 Cmdlet 會使用內建的演算法，判斷記錄檔及資料檔的最佳位置。 此演算法只適用于獨立的 SQL Server 實施。

  - 使用 DatabasePaths 參數執行 **Install-CsDatabase** 。 如果定義了 DatabasePaths 參數，則不會使用內建演算法來優化記錄及資料檔案位置。 使用此參數可讓您定義將部署記錄檔和資料檔案的位置。

  - 使用 UseDefaultSqlPaths 執行 **Install-CsDatabase** 。 此選項不使用內建的演算法來優化記錄檔和資料檔案位置。 會根據 SQL Server 系統管理員所設定的預設值來部署記錄檔和資料檔案。 這些路徑通常是為了預先自動管理 SQL Server 上的記錄檔與資料檔的目的，不會與 Lync Server 2013 的設定產生關聯。

  - DatabasePathMap 參數也可以用來明確指定每個資料庫及其各自記錄檔的位置。

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>使用 Windows PowerShell Cmdlet 來設定 SQL Server 中央管理存放區

1.  在任何電腦上，請使用管理認證登入，以在 SQL Server 服務器上建立資料庫。 如需詳細資訊，請參閱 [Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。

2.  開啟 [Lync Server 2013 管理命令介面]。 如果您未調整 Windows PowerShell 的執行原則，則必須調整原則，以允許 Windows PowerShell 腳本執行。 如需詳細資訊，請參閱 at 中的「檢查執行原則」 [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) 。

3.  使用 **Install-CsDatabase** Cmdlet 來安裝中央管理存放區。
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Report 參數是選用的，但如果您要記錄安裝程式，會很有用。

    
    </div>

4.  **Install-CsDatabase – DatabasePaths** 最多可以使用六個路徑參數，每個參數都會定義在 SQL Server 資料和記錄檔放置中所定義的磁片磁碟機路徑。 依照 Lync Server 2013 中的資料庫設定邏輯規則，會將磁片磁碟機分解成2、4或6的桶。 視您的 SQL Server 設定和 bucket 數目而定，您將會提供兩個路徑、四個路徑或六個路徑。
    
    如果您有三個磁片磁碟機，則記錄會取得優先順序，而且會將資料檔案散佈。 使用六個磁片磁碟機設定之 SQL Server 服務器的範例：
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  資料庫安裝完成時，您可以關閉 Lync Server 2013 管理命令介面，或繼續安裝拓撲產生器中定義的 Lync Server 2013 設定的資料庫。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>使用 Windows PowerShell Cmdlet 設定 SQL Server 拓撲設定的資料庫

1.  若要安裝 Lync Server 2013 的拓撲產生器設定資料庫，Lync Server 2013 管理員必須發行此拓撲。 如需詳細資訊，請參閱部署檔中的 [發行 Lync Server 2013 中的拓撲](lync-server-2013-publish-the-topology.md) 。

2.  在任何電腦上，請使用管理認證登入，以在 SQL Server 服務器上建立資料庫。 請參閱 [Lync server 2013 中 SQL Server 的部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)主題。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 若要設定 SQL Server 資料庫的資料庫，請確定用來執行下列所述步驟的 SQL Server 系統管理員帳戶也是執行 SQL Server 之伺服器上的系統管理員群組 (或同等) 成員，並且持有中央管理伺服器角色。 這對檢查是否有需要 SQL Server 資料庫安裝或設定的任何其他 Lync Server 2013 集區尤為重要。 例如，如果您要部署第二個集區 (pool02) 但是中央管理伺服器角色是由 pool01 所保留。 SQL Server sysadmin 群組 (或同等) 都必須具備 SQL Server 資料庫上的許可權。

    
    </div>

3.  開啟 Lync Server 2013 管理命令介面（若尚未開啟）。

4.  使用 **Install-CsDatabase** Cmdlet 安裝拓撲產生器設定的資料庫。
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Report 參數是選用的，但如果您要記錄安裝程式，會很有用。

    
    </div>

5.  資料庫安裝完成時，請關閉 [Lync Server 2013 管理命令介面]。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>使用 Windows PowerShell Cmdlet 使用 DatabasePathMap 參數設定 SQL Server 拓撲

1.  若要安裝 Lync Server 2013 的資料庫，Lync Server 系統管理員必須建立路徑，並根據一組預先定義的規則來部署資料庫檔案和記錄檔。

2.  在任何電腦上，請使用管理認證登入，以在 SQL Server 服務器上建立資料庫。 請參閱 [Lync server 2013 中 SQL Server 的部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)主題。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 若要設定 SQL Server 資料庫的資料庫，請確定用來執行下列所述步驟的 SQL Server 系統管理員帳戶也是執行 SQL Server 之伺服器上的系統管理員群組 (或同等) 成員，並且持有中央管理伺服器角色。 這對檢查是否有需要 SQL Server 資料庫安裝或設定的任何其他 Lync Server 集區尤為重要。 例如，如果您要部署第二個集區 (pool02) 但是中央管理伺服器角色是由 pool01 所保留。 SQL Server sysadmin 群組 (或同等) 都必須具備 SQL Server 資料庫上的許可權。

    
    </div>

3.  開啟 Lync Server 管理命令介面（若尚未開啟）。

4.  使用 **Install-CsDatabase** Cmdlet 搭配 DatabasePathMap 參數和 PowerShell 雜湊表，以安裝拓撲產生器設定的資料庫。

5.  在範例程式碼中，您可以使用– DatabasePathMap 參數及定義的雜湊表，以細微的方式判斷定義的資料庫路徑，如下所示 (此範例會使用 "C： \\ CSData" ( 所有 \\ 的記錄 ( .ldf) 檔的所有資料庫的資料庫 .mdf) 檔案及 "c： CSLogFiles"。 Install-CsDatabase) 時，將會視需要建立資料夾：
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  因為資料庫和記錄檔是以其在目的地資料庫伺服器上的位置明確命名，所以您可以為每個服務類型的實際資料庫和記錄位置定義特定位置。 下列範例會將每個特定服務類型的資料庫放在不同的磁片上，並將關聯的記錄檔放在另一部。 例如：
    
      - 所有 RTC 資料庫為 "D： \\ RTCDatabase"
    
      - 所有 RTC 記錄檔至 "E： \\ RTCLogs"
    
      - 所有應用程式存放區資料庫至 "F： \\ CPSDatabases"
    
      - 所有應用程式存放區記錄為 "G： \\ CPSLogs"
    
      - 所有回應群組存放區資料庫為 "H： \\ RGSDatabases"
    
      - 所有回應群組存放區記錄至 "I： \\ RGSLogs"
    
      - 所有通訊錄存放區資料庫至 "J： \\ ABSDatabases"
    
      - 所有通訊錄儲存記錄檔至 "K： \\ ABSLogs"
    
      - 所有封存存放區資料庫至 "L： \\ ArchivingDatabases"
    
      - 所有封存儲存區記錄為 "M： \\ ArchivingLogs"
    
      - 所有監控存放區資料庫至 "N： \\ MonitoringDatabases"
    
      - 所有監控存放區記錄檔案為 "O： \\ MonitoringLogfiles"
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    使用– DatabasePathMap 參數，您可以定義任何邏輯磁片磁碟機號對應組合，為您的 SQL Server 效能與放置需求提供最佳的解決方案。

如果您使用 **DatabasePathMap** 方法來設定資料庫資料檔案和記錄檔，當您使用拓撲產生器時，您將需要略微變更正常的處理常式。 一般來說，您會定義拓撲選項、發行拓撲，並選擇部署資料庫選項。

如果您已使用 **DatabasePathMap** ，您已完成拓撲產生器程式的第三個部分。 在執行拓撲產生器的情況下，如果有完全設定的資料庫伺服器，您仍會定義所有的伺服器角色和選項，但取消選取此選項以建立資料庫。

</div>

</div>

<span> </span>

</div>

</div>

</div>

