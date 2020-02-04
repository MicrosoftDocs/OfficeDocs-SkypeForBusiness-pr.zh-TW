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
ms.openlocfilehash: 8c617d323eb00476b53677b670c8cc6db0b8d05c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>在 Lync Server 2013 中使用 Lync Server 管理命令介面安裝資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-06-16_

伺服器管理員與 SQL Server 系統管理員之間的角色和職責之間的分離，可能會導致實現中的延遲。 Lync Server 2013 使用角色式存取控制（RBAC）來減輕這些困難。 在某些情況下，SQL Server 系統管理員必須在 RBAC 以外的 SQL Server 服務器上管理資料庫的安裝。 Lync Server 2013 管理命令介面提供一種方式，讓 SQL Server 系統管理員執行 Windows PowerShell Cmdlet，以使用正確的資料與記錄檔來設定資料庫。 如需詳細資訊，請參閱[Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。

<div class=" ">


> [!IMPORTANT]  
> 下列程式假設您至少安裝 Lync Server 2013 OCSCore、SQL Server 原生用戶端（sqlncli） Microsoft SQL Server 2012 管理物件、Microsoft sql server 2012 與 Microsoft SQL Server 2012 ADOMD.NET 的 CLR 類型。 OCSCore 位於 \Setup\AMD64\Setup 目錄中的安裝媒體上。 剩餘的元件位於 \Setup\amd64。 此外，Lync Server 2013 的 Active Directory 準備已順利完成。



</div>

**安裝-CsDatabase**是您用來安裝資料庫的 Windows PowerShell Cmdlet。 **CsDatabase** Cmdlet 有大量的參數，這裡只會討論幾個參數。 如需可能參數的詳細資訊，請參閱 Lync Server 2013 管理命令介面檔。

<div class=" ">


> [!WARNING]  
> 若要避免效能和可能的超時問題，請在參照 SQL Server 基礎伺服器時，永遠都使用完整的功能變數名稱（Fqdn）。 避免使用僅限主機名稱參照。 例如，使用 sqlbe01.contoso.net，但請避免使用 SQLBE01。



</div>

若要安裝資料庫，**安裝 CsDatabase**使用三種主要方法，將資料庫放在已準備好的 SQL server 型伺服器上：

  - 執行**安裝-** 不含 DatabasePaths 或 UseDefaultSqlPath 的 CsDatabase。 此 Cmdlet 使用內建演算法來判斷記錄和資料檔的最佳位置。 此演算法只適用于獨立的 SQL Server 實現。

  - 使用 DatabasePaths 參數執行**安裝-CsDatabase** 。 如果定義 DatabasePaths 參數，則不會使用內建演算法來優化記錄和資料檔案位置。 使用此參數可讓您定義將部署記錄及資料檔案的位置。

  - 執行**安裝-CsDatabase**與 UseDefaultSqlPaths。 這個選項不會使用內建演算法來優化記錄和資料檔案位置。 根據 SQL Server 系統管理員設定的預設值來部署記錄和資料檔案。 這些路徑通常是針對在 SQL Server 上自動記錄管理和資料檔案的目的而設定，且不與 Lync Server 2013 的設定相關聯。

  - DatabasePathMap 參數也可以用來明確指定每個資料庫及其各自記錄檔的位置。

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>若要使用 Windows PowerShell Cmdlet 來設定 SQL Server 中央管理存放區

1.  在任何電腦上，使用管理認證登入，在 SQL Server 服務器上建立資料庫。 如需詳細資訊，請參閱[Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。

2.  開啟 Lync Server 2013 管理命令介面。 如果您尚未調整 Windows PowerShell 的執行原則，您必須調整原則，以允許 Windows PowerShell 腳本執行。 如需詳細資訊，請參閱 "檢查執行原則[http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)"。

3.  使用**CsDatabase** Cmdlet 來安裝中央管理存放區。
    
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
    > 報表參數是選擇性的，但如果您正在記錄安裝程式，則會很有用。

    
    </div>

4.  **安裝-CsDatabase – DatabasePaths**可以使用最多六個路徑參數，每個都定義了在 SQL Server 資料和記錄檔位置中定義的磁碟機路徑。 根據 Lync Server 2013 中資料庫設定的邏輯規則，磁碟機會解析成兩個、四個或六個的 bucket。 視您的 SQL Server 設定和 bucket 數而定，您將會提供兩個路徑、四個路徑或六個路徑。
    
    如果您有三個磁片磁碟機，記錄會取得優先順序，並會在之後散佈資料檔案。 以6個磁碟機為基礎的 SQL Server server 設定範例：
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  資料庫安裝完成後，您可以關閉 Lync Server 2013 管理命令介面，或繼續安裝在拓撲建立器中定義的 Lync Server 2013 設定的資料庫。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>若要使用 Windows PowerShell Cmdlet 來設定 SQL Server 拓撲設定的資料庫

1.  若要安裝 Lync Server 2013 的 [拓撲建立器] 設定資料庫，Lync Server 2013 系統管理員必須發佈拓撲。 如需詳細資訊，請參閱在部署檔中[發佈 Lync Server 2013 中的拓撲](lync-server-2013-publish-the-topology.md)。

2.  在任何電腦上，使用管理認證登入，在 SQL Server 服務器上建立資料庫。 請參閱[Lync server 2013 中 SQL Server 的部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)主題。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 若要設定 SQL Server 的資料庫，請確定用於執行以下所述步驟的 SQL Server 管理員帳戶也是執行 SQL Server 並按住中央管理的伺服器上的系統管理員群組（或對等）的成員。伺服器角色。 若要檢查是否有任何其他需要 SQL Server 資料庫安裝或設定的 Lync Server 2013 池，這一點尤為重要。 例如，如果您要部署第二個池（pool02），但中央管理伺服器角色是由 pool01 所擁有。 SQL Server 系統管理員群組（或對等）在 SQL Server 型資料庫上都必須有許可權。

    
    </div>

3.  開啟 Lync Server 2013 管理命令介面（如果尚未開啟的話）。

4.  使用**CsDatabase** Cmdlet 來安裝 [拓撲建立器] 設定的資料庫。
    
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
    > 報表參數是選擇性的，但如果您正在記錄安裝程式，則會很有用。

    
    </div>

5.  資料庫安裝完成後，請關閉 Lync Server 2013 管理命令介面。

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>若要使用 Windows PowerShell Cmdlet 來使用 DatabasePathMap 參數設定 SQL Server 拓撲

1.  若要安裝 Lync Server 2013 的資料庫，Lync Server 管理員必須根據預先定義的一組規則來建立路徑，並部署資料庫檔案和記錄檔案。

2.  在任何電腦上，使用管理認證登入，在 SQL Server 服務器上建立資料庫。 請參閱[Lync server 2013 中 SQL Server 的部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)主題。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 若要設定 SQL Server 的資料庫，請確定用於執行以下所述步驟的 SQL Server 管理員帳戶也是執行 SQL Server 並按住中央管理的伺服器上的系統管理員群組（或對等）的成員。伺服器角色。 若要檢查任何需要 SQL Server 資料庫安裝或設定的其他 Lync 伺服器池，這一點尤為重要。 例如，如果您要部署第二個池（pool02），但中央管理伺服器角色是由 pool01 所擁有。 SQL Server 系統管理員群組（或對等）在 SQL Server 型資料庫上都必須有許可權。

    
    </div>

3.  開啟 Lync Server 管理命令介面（如果尚未開啟的話）。

4.  使用**CsDatabase** Cmdlet 與 DatabasePathMap 參數和 PowerShell 雜湊表來安裝拓撲建立器設定的資料庫。

5.  在範例程式碼中，您可以使用– DatabasePathMap 參數和定義的雜湊表，以精細的方式來判斷為資料庫定義的路徑，如下所示（這個範例針對\\所有的資料庫（.mdf）檔案使用 "c： CSData"，而\\[c： CSLogFiles] 則代表所有記錄（.ldf）檔案。 您可以視安裝所需建立資料夾-CsDatabase）：
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
6.  因為資料庫和記錄檔案是在目的地資料庫伺服器上以其位置明確命名，所以您可以針對每個服務類型的實際資料庫和記錄位置定義特定位置。 下列範例會將每個特定服務類型的資料庫放在不同磁片上，並將相關聯的記錄檔案放在另一個磁片上。 例如：
    
      - 所有 RTC 資料庫都設為 "\\D： RTCDatabase"
    
      - 所有 RTC 記錄檔案到 "E：\\RTCLogs"
    
      - 所有應用程式將資料庫儲存到 "\\F： CPSDatabases"
    
      - 所有應用程式商店記錄到 "G\\： CPSLogs"
    
      - 所有回應群組將資料庫儲存到 "H\\： RGSDatabases"
    
      - 所有回應群組商店記錄到「I：\\RGSLogs」
    
      - 所有通訊錄將資料庫儲存到 "J\\： ABSDatabases"
    
      - 所有通訊錄將記錄檔儲存到 "K\\： ABSLogs"
    
      - 所有封存儲存資料庫到 "L：\\ArchivingDatabases"
    
      - 所有封存存放區記錄到 "M\\： ArchivingLogs"
    
      - 所有監視商店資料庫到 "N：\\MonitoringDatabases"
    
      - 所有監視商店記錄檔案到 "O：\\MonitoringLogfiles"
    
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
    
    您可以使用– DatabasePathMap 參數定義任何邏輯磁片磁碟機字母對應，為您的 SQL Server 效能和位置需求提供最佳解決方案。

如果您使用**DatabasePathMap**方法來設定資料庫資料檔和記錄檔案，則在使用拓撲建立器時，您必須稍加變更您的標準程式。 通常，您會定義拓撲選項、發佈拓撲，以及選擇部署資料庫選項。

如果您已使用**DatabasePathMap** ，就表示您已經完成拓撲建立程式的第三個部分。 如果您在執行拓撲建立器之前有完全配置的資料庫伺服器，您仍然可以定義所有伺服器角色和選項，但不需選取此選項即可建立資料庫。

</div>

</div>

<span> </span>

</div>

</div>

</div>

