---
title: Lync Server 2013 持久聊天資源套件工具
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
ms.openlocfilehash: 80a9116374914c212d305ef2e55d0b8c4fecb782
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533666"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Lync Server 2013 持久聊天資源套件工具

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

Lync Server 2013 持續性聊天資源套件工具可協助您讓部署及管理 Lync Server 2013 Persistent Chat Server 的 IT 系統管理員更輕鬆進行日常工作。 除了安裝指示之外，本主題也會說明每個工具的用途及其用法範例。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>安裝資源工具組工具

若要安裝 Lync Server 2013，資源工具組工具，請下載 **PersistentChatReskit.msi**。 執行 **PersistentChatReskit.msi** 以執行簡單安裝。 .Msi 會安裝下列路徑中的所有工具： \\ **Program Files \\ Microsoft Lync Server 2013 \\ Persistent Chat Server Resource 工具組**。 屬於自包含可執行檔的工具位於此資料夾中。 也有檔案的工具位於自己的子資料夾中。

<div>


> [!IMPORTANT]  
> 安裝 Lync Server 2013 （資源套件工具）之後，您必須安裝<STRONG>PsExec.exe</STRONG> ，並將<STRONG>PsExec.exe</STRONG>複製到下列路徑： \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ Persistent Chat Server Resource Kit\ChatStressTool</STRONG>。 如果您未複製 <STRONG>PsExec.exe</STRONG>，Persistent 聊天工具將會引發錯誤例外狀況，而不會正確執行。 在執行工具之前，請先確定您符合此必要條件。 如需安裝 <STRONG>PsExec.exe</STRONG>的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> 。



</div>

</div>

<div>

## <a name="supported-environments"></a>支援的環境

為了達到最佳效能，Lync Server 2013，資源工具組工具應該安裝在相同的環境中，且使用 Lync Server 2013 所需的相同規格。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>資源工具組工具概述

以下是 Lync Server 2013 Persistent Chat Resource 工具組中所提供的工具。 下節提供每個工具的描述，包括需求和範例用法。

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

## <a name="description"></a>描述

AffCheck 工具會確認 Persistent 後端資料庫使用者和群組從屬記錄符合 Active Directory 網域服務。

</div>

<div>

## <a name="requirements"></a>需求

工具是隨加入網域的機器上的 PersistentChatResKit 安裝程式一起安裝。

執行此工具的使用者帳戶必須具有對 Persistent 後端資料庫和 Active Directory 網域服務的讀取權限。

</div>

<div>

## <a name="usage"></a>Usage

根據 config 檔案中的指示設定 AffCheck.exe.config 檔案，並執行不含命令列參數的 AffCheck 工具。 以下是預設 AffCheck.exe.config 的內容。

**AffCheck.exe.config：**

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

## <a name="description"></a>描述

PersistentChatMonitoringSummary 工具會將持續性聊天監控資訊從監控資料庫移至指定的 CSV 記錄檔。

CSV 檔案會包含持續性聊天會話的分解，依總數：會話總數、成功的會話、意外失敗、預期的失敗，以及診斷識別碼、失敗次數和失敗描述的失敗的失敗情況。

</div>

<div>

## <a name="requirements"></a>需求

在有權存取監控資料庫的已加入網域的機器上安裝 Persistent Chat Resource 工具組工具。

執行工具所使用的使用者帳戶，必須具備監控資料庫的讀取權限。

檔案（PersistentChatMonitoringSummary.exe.config）必須包含一個 \<connectionStrings\> 區段，以定義監控資料庫的連接字串。 它還必須包含要針對其收集監控資料之 PersistentChatEndpointUri 的索引鍵，以及將產生之 CSV 檔案位置的檔案路徑。 如需範例，請參閱已安裝的設定檔。 檔案必須與工具位於相同的目錄中。

</div>

<div>

## <a name="usage"></a>Usage

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

這些參數會定義資料的選取專案：

**StartDateTime：** （選用）指定選取期間的開始日期。 預設值： 1/1/1753 12:00:00 AM

**EndDateTime：** （選用）指定選取期間的最後一個日期。 預設值：現在

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

## <a name="persistent-chat-stress-tool"></a>Persistent Chat 應力工具

<div>

## <a name="description"></a>描述

Persistent Chat 應力工具提供一種簡單的方法，可模擬持續性聊天的使用方式，以測試實際效能，包括各種使用者模型，以更好地符合預期的使用案例。

</div>

<div>

## <a name="requirements"></a>需求

將 Persistent Chat Resource 工具組工具安裝至可存取 Persistent 後端資料庫的已加入網域的電腦上。

除了此 *控制器* 電腦之外，您還需要數個 *載入程式* 電腦。 針對使用者模型中的每個10K 使用者，您至少要有4GB 載入器電腦上的可用記憶體。 例如，以80K 使用者執行的使用者將需要所有載入程式電腦上的 RAM 散佈32GB。 建議您至少有三個載入程式電腦，不論預期的負載為何。

載入程式機器必須已安裝 .NET 4.5 Framework 和 Visual c + + 2012 可轉散發元件。

</div>

<div>

## <a name="configuration"></a>組態

將 ChatStressTool 檔案複製到可從所有載入程式機器存取的共用資料夾。

建立用於壓力執行的使用者和通道：

  - 建立您的使用者模型所撥打的任意數目的使用者、啟用 Lync 的使用者，並將其 Persistent 聊天原則設定為 [啟用]。

  - 建立壓力通道的類別，然後建立該類別下所需的任意會議室。 類別應該會在其 **允許** 的清單中有所有壓力使用者 (以加入其 OU) 的方式，而壓力房間應具備 **開啟**的隱私權設定。

  - 我們建議您建立額外的壓力房間。 您可以使用下列 Windows PowerShell 命令列介面命令來建立50000聊天室：
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

編輯設定檔，以符合您的拓撲：

在 **LoaderProcess.exe.config**中，將 "controller.contoso.com" 變更為 controller MACHINE (FQDN) 的完整功能變數名稱。

在 **StressLauncher.exe.config 中：**

1.  將 "LoaderBinary" 設定值變更為共用資料夾的路徑。

2.  將 "AdminUser"/"AdminPassword" 變更為具備載入程式電腦系統管理員存取權的認證。

3.  將 "ChannelCategory" 變更為已在其下建立壓力通道的類別名稱。

4.  將 "UserNamePattern" 和 "UserPasswordPattern" 變更為符合您的壓力使用者認證的範本。 {0} 會取代為使用者的索引編號。

5.  將 "Domain" 變更為測試拓撲的 SIP 網域。

6.  將 "ConnectionString" 變更為您的持久聊天后端資料庫的連接字串。

7.  將 "UserIndexStart" 變更為第一個應力使用者的索引。

8.  將 "LyncFQDN" 變更為前端集區的 FQDN。

9.  修改「電腦」清單，以包含所有載入程式機器的電腦名稱稱。

10. 變更服務 (端點的 baseAddress 預設值為 "controller.contoso.com" ) 至您的控制器機器的 FQDN。

</div>

<div>

## <a name="usage"></a>Usage

設定完成後，請開啟控制器機器上的 StressLauncher.exe。 您可以以任何使用者的身分啟動 StressLauncher。 必須在 config 檔案中指定增益集電腦上開機載入程式處理的認證。 您也必須提供可讀取持久聊天后端資料庫之讀取權的連接字串。 如果此連線字串使用整合式 Windows 驗證，您必須以具有這種存取權的使用者身分啟動 StressLauncher。

視需要變更使用者模型設定。 按一下 [ **開始載入** ] 以啟動 run。 一分鐘之後，使用者就會開始登入，進度列就會開始填滿。 此時，您可能可以運作控制器機器並取得效能度量。

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>描述

ChatUpgradeVerifier 是一種持續聊天特有的資料庫比較工具。 該工具會將群組聊天 2007 R2 或群組聊天2010資料庫 (2007/2010Db) 與 Persistent Chat 2013 資料庫 (2013Db) 進行比較。

在 2007/2010Db 中，該工具會逐一檢查一個、每個類別、持續聊天室和增益集，以查看它是否出現在2013Db 中。 比較包含檢查類別、聊天室或增益集、類別範圍中的任何主體，以及類別或聊天室中某一角色的任何主體的所有設定。 當2013Db 中的類別或聊天室未正確顯示時，會將差異輸出至衝突檔案。 在升級完成之後，如果發生升級，則會變更 2007/2010Db，然後執行此工具時，會有差異輸出到衝突檔案。 請注意，此應用程式只是資料庫比較工具，不會驗證升級程式。

</div>

<div>

## <a name="requirements"></a>需求

在已加入網域的機器上安裝 Persistent chat Resource 工具組工具，該機器可以存取持久聊天)  (舊版和目前版本。

執行此工具的使用者帳戶必須具有對 Persistent 聊天資料庫的讀取權限。

ChatUpgradeVerifier.exe.config 檔必須包含 GroupChat2007R2Db 參數或 GroupChat2010Db 參數，並將連接字串連至適當群組聊天資料庫 (Groupchat.contoso Nm-opsmgr-2007r2-2nd 或 2010) 。 它還必須包含 PersistentChat2013Db 參數，並將連接字串連至 Persistent Chat 2013 資料庫。

</div>

<div>

## <a name="usage"></a>Usage

執行不含任何參數的 **ChatUpgradeVerifier** 。

</div>

<div>

## <a name="example"></a>範例

![執行 ChatUpgradeVerifier.exe。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "執行 ChatUpgradeVerifier.exe。")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Persistent Chat 使用方式報告

<div>

## <a name="description"></a>描述

ChatUsageReport 工具會產生持久聊天服務使用方式的 HTML 報告。

</div>

<div>

## <a name="requirements"></a>需求

在具有 Persistent Chat 後端資料庫存取權的已加入網域的機器上安裝 Persistent Chat Resource 工具組工具。

執行此工具的使用者帳戶必須具有對 Persistent 後端資料庫的讀取權限。

檔案 ChatUsageReport.exe.config，必須包含一個區段，用以 \<connectionStrings\> 定義持久聊天后端資料庫的連接字串。 預設的設定檔內容會包含在這裡供您參考。

</div>

<div>

## <a name="usage"></a>Usage

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
這些參數會定義資料的選取專案：

**StartDate：** （選用）指定選取期間的 UTC 開始日期。 預設值：最早日期

**EndDate：** （選用）指定選取期間的 UTC 結束日期。 預設值：現在

這些參數定義顯示資料的方式和方式：

**TopActiveUsers：** 如果指定此值，則報告將會包含 n 個最活躍的使用者，其條件是使用者在選取的期間內已在聊天室中張貼的郵件數目。 預設值：10

**TopActiveRooms：** 如果指定此值，則報告將會包含 n 個最活躍的聊天室，其條件是針對所選期間在會議室中張貼的郵件數目。 預設值：10

**LeastActiveRooms：** 如果指定此值，則報告將會包含 n 個最少的使用中聊天室，其條件是針對所選期間在聊天室中張貼的郵件數目。 會議室至少會有一封發表郵件。 預設值：10

**RoomsInactiveSince：** 如果指定此專案，報告將會包含從指定的日期起已非使用中的聊天室清單。 預設值：整個時間

**OutputFolder：** 會放置 ChatUsageReport.html 與圖形影像的資料夾。 這必須在 config 檔案或命令列上定義。

您也可以在與工具位於相同目錄的 ChatUsageReport.exe.config 檔案中指定所有的命令列參數值。 如果在設定檔和命令列中指定任何值，則命令列值將會覆寫 config 檔值。

</div>

<div>

## <a name="output"></a>輸出

報告會永遠包含下列輸出：

  - 在選取的期間內，最高排名個最活躍的聊天室，郵件投遞的數目。

  - 最高排名的前 n 個最活躍的使用者選取期間的郵件投遞數目。

  - 在選取的期間內，最小的使用中聊天室的郵件投遞數目。

  - 在資料庫整個生命週期中非使用中或自指定日期之後的聊天室。

  - 所選期間的每日郵件投遞趨勢。

  - 所選期間的每週郵件投遞趨勢。

  - 所選期間的每月郵件投遞趨勢。

  - 所選期間內的郵件投遞總數。

  - 已啟用的會議室總數。

</div>

<div>

## <a name="example"></a>範例

下列範例會產生整年2001的使用方式報告，並將報表放在 ChatUsageReport.exe.config 所指定的 OutputFolder 中。

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport.exe.config：

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

## <a name="description"></a>描述

ScheduleADSyncForPrincipal 是 Microsoft SQL Server 2012 腳本，當連線至 Persistent Chat 後端資料庫時，必須直接在 SQL Server Management Studio 中執行。 此腳本可讓您強制持續聊天將使用者的記錄同步處理至 Active Directory 網域服務的使用者，而不是等待排程的同步處理時間。

</div>

<div>

## <a name="requirements"></a>需求

執行腳本的使用者帳戶必須具有對 Persistent 後端資料庫的擁有者存取權。

</div>

<div>

## <a name="usage"></a>Usage

預設腳本的內容如下：

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

