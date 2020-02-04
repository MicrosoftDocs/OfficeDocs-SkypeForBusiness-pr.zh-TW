---
title: Lync Server 2013 持續聊天資源套件工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a827892dac61ff88d0527eafb7d94948afa21885
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Lync Server 2013 持續聊天資源套件工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

Lync Server 2013 持續性聊天資源套件工具可協助您更輕鬆地為部署和管理 Lync Server 2013 持久聊天伺服器的 IT 系統管理員進行例行工作。 除了安裝指示之外，本主題還說明每個工具的用途，以及其用法範例。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>資源套件工具的安裝

若要安裝 Lync Server 2013、資源套件工具，請下載**PersistentChatReskit**。 執行**PersistentChatReskit**以進行簡單的安裝。 .Msi 會安裝下列路徑中的所有工具： \\ **Program\\ Files Microsoft Lync Server 2013\\持續聊天伺服器資源套件**。 可自包含的可執行檔的工具位於此資料夾中。 也有檔案的工具位於自己的子資料夾中。

<div>


> [!IMPORTANT]  
> 安裝 Lync Server 2013、資源套件工具之後，您必須安裝<STRONG>psexec</STRONG>並將<STRONG>psexec</STRONG>複製到下列路徑： \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ 持續聊天伺服器資源 Kit\ChatStressTool</STRONG>。 如果您不復制<STRONG>PsExec</STRONG>，持續聊天的壓力工具將會引發錯誤例外狀況，且無法正確執行。 在執行此工具前，請確定您符合這個必備需求。 如需有關安裝<STRONG>PsExec</STRONG>的詳細資訊， <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>請參閱。



</div>

</div>

<div>

## <a name="supported-environments"></a>支援的環境

為了獲得最佳效能，Lync Server 2013、資源套件工具應該安裝在相同的環境中，且與 Lync Server 2013 所需的規格相同。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>資源套件工具概述

以下是 Lync Server 2013 持續聊天資源套件中提供的工具。 下節提供每個工具的描述，包括需求與範例用法。

  - AffCheck

  - ChatMonitoringSummary

  - ChatStress 工具

  - ChatUpgradeVerifier

  - ChatUsageReport

  - ScheduleADSyncforPrincipal

</div>

<div>

## <a name="affcheck"></a>AffCheck

<div>

## <a name="description"></a>說明

AffCheck 工具會確認持久的聊天后端資料庫使用者和群組隸屬關係記錄與 Active Directory 網域服務相符。

</div>

<div>

## <a name="requirements"></a>需求

此工具是與加入網域的電腦上的 PersistentChatResKit 安裝程式一起安裝。

運行該工具的使用者帳戶必須具備永久聊天后端資料庫和 Active Directory 網域服務的讀取存取權。

</div>

<div>

## <a name="usage"></a>用法

根據 config 檔案中的指示來設定 AffCheck 檔案，並在不含命令列參數的情況下執行 AffCheck 工具。 以下是預設 AffCheck 的內容。

**AffCheck：**

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a>ChatMonitoringSummary

<div>

## <a name="description"></a>說明

PersistentChatMonitoringSummary 工具會將持續聊天監視資訊從監視資料庫移至指定的 CSV 記錄檔。

CSV 檔案將會包含持續交談會話的細目分類，包括總會話數、成功的會話、意外的失敗、預期的失敗，以及診斷識別碼、失敗數與失敗描述所造成的意外失敗細目分類。

</div>

<div>

## <a name="requirements"></a>需求

在可存取監視資料庫的已加入網域的電腦上，安裝持續式聊天資源套件工具。

執行工具所使用的使用者帳戶必須具備監視資料庫的讀取存取權。

檔案（PersistentChatMonitoringSummary）必須包含一個\<connectionStrings\>節，以定義監視資料庫的連線字串。 它也必須包含要收集監視資料之 PersistentChatEndpointUri 的索引鍵，以及將產生的 CSV 檔案位置的檔案路徑。 如需範例，請參閱已安裝的設定檔。 檔案必須與工具位於同一個目錄中。

</div>

<div>

## <a name="usage"></a>用法

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

這些參數定義資料的選取範圍：

**StartDateTime：** 或者，您也可以指定選取期間的開始日期。 預設值： 1/1/1753 12:00:00 AM

**EndDateTime：** 或者，您也可以指定選取期間的最後一個日期。 預設值： Now

</div>

<div>

## <a name="example"></a>範例

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a>持續聊天的壓力工具

<div>

## <a name="description"></a>說明

持續聊天的壓力工具提供一種簡單的方法來模擬持久聊天的使用方式，以測試真實世界的效能，包括各種使用者模型，以更適合您預期的使用方式。

</div>

<div>

## <a name="requirements"></a>需求

將持續性聊天資源套件工具安裝在可存取持久聊天后端資料庫的網域加入的電腦上。

除了此*控制器*電腦之外，您還需要幾個*載入程式*電腦。 針對使用者模型中的每個10K 使用者，您在載入程式電腦上至少需要4GB 的可用 RAM。 例如，執行80K 的使用者將需要在所有載入程式電腦上散佈 32GB RAM。 建議您至少擁有三個載入程式電腦，而不考慮預期的載入。

載入程式電腦必須裝有 .NET 4.5 架構以及安裝 Visual c + + 2012 可再發行的元件。

</div>

<div>

## <a name="configuration"></a>Configuration

將 ChatStressTool 檔案複製到可從所有載入程式電腦存取的共用資料夾。

建立使用者和頻道，以在壓力執行中使用：

  - 建立與您的使用者模型通話對應的使用者數目、啟用 Lync 並將其持續聊天原則設定為 [啟用]。

  - 為您的壓力通道建立類別，然後根據該類別所需建立的會議室。 該類別應該將所有壓力使用者放在其**允許**清單中（透過新增其 OU），而壓力室應該有**開啟**的隱私權設定。

  - 我們建議您建立額外的壓力房間。 您可以使用下列 Windows PowerShell 命令列介面命令來建立50000聊天室：
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

編輯設定檔以符合您的拓撲：

在**LoaderProcess**中，將 "controller.contoso.com" 變更為控制器電腦的完整功能變數名稱（FQDN）。

在**StressLauncher：**

1.  將 "LoaderBinary" 設定值變更為共用資料夾的路徑。

2.  將 "AdminUser"/"AdminPassword" 變更為具備載入程式電腦系統管理員存取權的認證。

3.  將 "ChannelCategory" 變更為已建立應力通道的類別名稱。

4.  將 "UserNamePattern" 和 "UserPasswordPattern" 變更為符合您的壓力使用者認證的範本。 {0}會以使用者的索引號碼取代。

5.  將 "Domain" 變更為您測試拓朴的 SIP 網域。

6.  將 "ConnectionString" 變更為持續式聊天后端資料庫的連線字串。

7.  將 "UserIndexStart" 變更為第一個壓力使用者的索引。

8.  將 "LyncFQDN" 變更為您的前臺端池的 FQDN。

9.  修改 [電腦] 清單，以包含所有載入程式電腦的電腦名稱稱。

10. 將服務端點的 baseAddress （預設為 "controller.contoso.com"）變更為控制器電腦的 FQDN。

</div>

<div>

## <a name="usage"></a>用法

完成設定之後，請在控制器電腦上開啟 StressLauncher。 您可以以任何使用者的身分啟動 StressLauncher。 在載入程式電腦上開機載入程式的認證，必須在 config 檔案中指定。 您也必須提供具有永久聊天后端資料庫讀取存取權的連線字串。 如果這個連線字串使用集成的 Windows 驗證，您必須以擁有此存取權的使用者身分啟動 StressLauncher。

視需要變更使用者模型設定。 按一下 [**開始載入**] 以啟動執行。 一分鐘之後，使用者就會開始登入，進度列就會開始進行填入。 此時，控制器電腦可能能正常運作並採取效能測量。

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>說明

ChatUpgradeVerifier 是一種持續聊天的特定資料庫比較工具。 此工具會將群組聊天 2007 R2 或群組聊天2010資料庫（2007/2010Db）與永久聊天2013資料庫（2013Db）進行比較。

此工具會逐一檢查、每個類別、持續聊天室，以及 2007/2010Db 中的增益集，以查看它是否出現在2013Db 中。 比較包括檢查類別、聊天室、增益集、類別範圍中的所有設定，以及類別或聊天室上角色中的任何承擔者。 如果在2013Db 中沒有正確顯示類別或聊天室，則會將差異輸出到衝突檔案。 如果在進行升級之後，會變更 2007/2010Db，然後執行此工具，就會有與衝突檔案有關的差異輸出。 請注意，此應用程式只是資料庫比較工具，不會驗證升級程式。

</div>

<div>

## <a name="requirements"></a>需求

在已加入網域的電腦上，安裝持續式聊天資源套件工具（可存取持續聊天后端資料庫）。

執行工具所使用的使用者帳戶必須具備對持續聊天資料庫的讀取存取權。

ChatUpgradeVerifier 檔案必須包含 GroupChat2007R2Db 參數或 GroupChat2010Db 參數，並將連接字串連至適當的群組聊天資料庫（Groupchat 2007R2 或2010）。 它也必須包含 PersistentChat2013Db 參數，以及將連接字串連至持久聊天2013資料庫。

</div>

<div>

## <a name="usage"></a>用法

不需任何參數就能執行**ChatUpgradeVerifier** 。

</div>

<div>

## <a name="example"></a>範例

![執行 ChatUpgradeVerifier.exe。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "執行 ChatUpgradeVerifier.exe。")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>持續聊天使用方式報告

<div>

## <a name="description"></a>說明

ChatUsageReport 工具會產生持續聊天服務用法的 HTML 報告。

</div>

<div>

## <a name="requirements"></a>需求

在有權存取持久聊天后端資料庫的網域加入電腦上，安裝持續式聊天資源套件工具。

運行該工具的使用者帳戶必須具備永久聊天后端資料庫的讀取存取權。

檔案（ChatUsageReport）必須包含一個\<connectionStrings\>區段，以定義持續聊天后端資料庫的連線字串。 預設設定檔的內容如下所示，供您參考。

</div>

<div>

## <a name="usage"></a>用法

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
這些參數定義資料的選取範圍：

開始**日期：**（選擇性）指定選取期間的 UTC 開始日期。 預設值：最早日期

**結束日期：**（選擇性）指定選取期間的 UTC 結束日期。 預設值： Now

這些參數定義資料的顯示方式及顯示方式：

**TopActiveUsers：** 如果指定此選項，報告將會包含 n 個最活躍的使用者，就是使用者在所選期間在聊天室中張貼的訊息數目。 預設值：10

**TopActiveRooms：** 如果指定此選項，報告將會包含 n 個最活躍的聊天室，就是在所選期間內的會議室中張貼的訊息數目。 預設值：10

**LeastActiveRooms：** 如果已指定此選項，報告將會包含 n 個最小作用中的聊天室，就是在所選期間的聊天室中張貼的訊息數目。 會議室將至少公佈一封郵件。 預設值：10

**RoomsInactiveSince：** 如果指定此選項，報告將會包含自指定日期之後處於非作用中狀態的聊天室清單。 預設值：整個時間

**OutputFolder：** 將放置 ChatUsageReport 及圖形影像的資料夾。 這必須在 config 檔案或命令列中定義。

您也可以在與工具位於同一個目錄中的 ChatUsageReport 檔案中，指定所有的命令列參數值。 如果在 config 檔案和命令列中都指定了任何值，命令列值將會覆寫 config 檔值。

</div>

<div>

## <a name="output"></a>收

報告將永遠包含下列輸出：

  - 最多 n 個最活躍的聊天室，由所選時段內的訊息文章數量所組成。

  - 最多 n 個作用中的使用者，由所選時段內的郵件投遞數來排列。

  - 前 n 個最小作用中的聊天室，由所選時段內的訊息文章數量所組成。

  - 在資料庫的整個生命週期中，或從指定的日期起停用的聊天室。

  - 所選期間的每日訊息後續趨勢。

  - 所選期間的每週訊息張貼趨勢。

  - 所選期間的每月訊息文章趨勢。

  - 所選期間內的郵件投遞總數。

  - 已啟用的會議室總數。

</div>

<div>

## <a name="example"></a>範例

下列範例會產生整個2001年的使用方式報告，並將報告放在 ChatUsageReport 中指定的 OutputFolder 中。

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport：

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a>ScheduleADSyncForPrincipal

<div>

## <a name="description"></a>說明

ScheduleADSyncForPrincipal 是 Microsoft SQL Server 2012 腳本，在連線至持久聊天后端資料庫時，必須直接在 SQL Server Management Studio 中執行。 此腳本可讓您強制持續聊天與 Active Directory 網域服務的使用者記錄同步處理，而不是等待排程的同步處理時間。

</div>

<div>

## <a name="requirements"></a>需求

執行腳本的使用者帳戶必須擁有持久聊天后端資料庫的擁有者存取權。

</div>

<div>

## <a name="usage"></a>用法

以下是預設腳本的內容：

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

