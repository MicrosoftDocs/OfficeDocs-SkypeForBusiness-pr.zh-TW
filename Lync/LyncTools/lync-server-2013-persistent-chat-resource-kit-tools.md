---
title: Lync Server 2013 常設聊天室 Resource Kit 工具
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
ms.openlocfilehash: 726e6bb537a16ece5c2955f005e91872f11f6a79
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Lync Server 2013 常設聊天室 Resource Kit 工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-24_

Lync Server 2013 常設聊天室 Resource Kit 工具可協助簡化例行工作 IT 管理員部署及管理 Lync Server 2013 常設聊天室伺服器。 安裝指示，除了本主題會說明每個工具和其使用範例的目的。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Resource Kit 工具的安裝

若要安裝 Lync Server 2013 Resource Kit 工具，下載**PersistentChatReskit.msi**。 執行**PersistentChatReskit.msi**執行簡單的安裝。 .msi 安裝的所有工具在下列路徑： \\ **Program Files\\ Microsoft Lync Server 2013\\常設聊天室伺服器 Resource Kit**。 是獨立的可執行檔的工具是此資料夾中。 工具，也有檔案位於其自己的子資料夾中。

<div>


> [!IMPORTANT]  
> 安裝 Lync Server 2013 Resource Kit 工具之後，您必須安裝<STRONG>PsExec.exe</STRONG>並將<STRONG>PsExec.exe</STRONG>複製到下列路徑： \\<STRONG>程式 Files\ Microsoft Lync Server 2013\Persistent 聊天伺服器資源 Kit\ChatStressTool</STRONG>。 如果您不要複製<STRONG>PsExec.exe</STRONG>，常設聊天室壓力工具會擲回錯誤的例外狀況，並不會正確地執行。 請確定您符合此必要條件的需求，再執行此工具。 如需安裝<STRONG>PsExec.exe</STRONG>的詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>。



</div>

</div>

<div>

## <a name="supported-environments"></a>支援的環境

以獲得最佳效能，Lync Server 2013 Resource Kit 工具應該安裝在相同的環境與相同規格所需的 Lync Server 2013。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Resource Kit 工具概觀

以下是 Lync Server 2013 常設聊天室 Resource Kit 中所提供的工具。 下節提供每一種工具，包括需求和範例流量的描述。

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

AffCheck 工具確認常設聊天室後端資料庫的使用者和群組 affiliation 記錄符合的 Active Directory 網域服務。

</div>

<div>

## <a name="requirements"></a>需求

使用網域聯結電腦上的 PersistentChatResKit 安裝程式安裝的工具。

執行此工具會在其下的使用者帳戶必須具有 Active Directory 網域服務與常設聊天室後端資料庫的讀取權限。

</div>

<div>

## <a name="usage"></a>Usage

組態檔中設定根據指示 AffCheck.exe.config 檔案並執行 AffCheck 工具不含命令列參數。 以下是預設 AffCheck.exe.config 的內容。

**AffCheck.exe.config:**

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

PersistentChatMonitoringSummary 工具會將常設聊天室監視資訊從監控資料庫移至指定的 CSV 記錄檔。

CSV 檔案會包含的常設聊天室工作階段的工作階段總數，成功的工作階段、 未預期的失敗，預期的失敗，會以明細與未預期的失敗的診斷識別碼、 失敗及錯誤描述的數字明細。

</div>

<div>

## <a name="requirements"></a>需求

具有監控資料庫的存取權的已加入網域的機器上安裝的常設聊天室 Resource Kit 工具。

執行工具的使用者帳戶必須具備監控資料庫的讀取權限。

該檔案，PersistentChatMonitoringSummary.exe.config，必須包含\<connectionStrings\> ] 區段中定義的連接字串至監控資料庫。 它也必須包含索引鍵的監視資料那裡，PersistentChatEndpointUri 並將產生的 CSV 檔案的位置的檔案路徑。 請參閱安裝的組態檔中的範例。 檔案必須位於與工具相同的目錄。

</div>

<div>

## <a name="usage"></a>Usage

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

這些參數定義資料的選取範圍：

**StartDateTime:**（選用） 指定的選取範圍期間的開始日期。 預設值： 1/1/1753年 12:00:00 AM

**EndDateTime:**（選用） 指定的選取範圍期間的最後一個日期。 預設值： 現在

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

## <a name="persistent-chat-stress-tool"></a>常設聊天室壓力工具

<div>

## <a name="description"></a>描述

常設聊天室壓力工具提供簡單的方法來模擬的常設聊天室，來測試真實世界的效能，包括具有不同的使用者模型，才能滿足您的預期的使用情況的使用狀況。

</div>

<div>

## <a name="requirements"></a>需求

安裝到具有常設聊天室後端資料庫的存取權的已加入網域的機器上的常設聊天室 Resource Kit 工具。

除了這*控制站*台機器中，您將需要數個*載入*機器。 針對使用者模型中的每個 10k 使用者，您必須至少 4 GB 的可用 RAM 載入機器上。 例如，與 80 K 使用者執行時，需要約 32 GB 的 RAM 散佈於載入程式的所有機器。 我們建議您具有至少三個載入機器，不論預期的負載。

載入機器必須.NET 4.5 架構，以及 Visual c + + 2012年可轉散發套件安裝。

</div>

<div>

## <a name="configuration"></a>組態

將 ChatStressTool 檔案複製到可從載入程式的所有機器存取的共用資料夾。

建立使用者和通道的使用中執行的負荷：

  - 建立會呼叫您的使用者模型的使用者數目、 啟用這些 lync，並將其常設聊天室原則設定為 [已啟用。

  - 建立類別，您壓力通道，並建立多個會議室，視需要在該類別下。 類別 （透過新增其 OU），它**允許**清單中應設有壓力的所有使用者和壓力會議室都應有的隱私權設定為**開啟**。

  - 我們建議您建立額外的壓力聊天室。 您可以使用下列 Windows PowerShell 命令列介面命令來建立 50000 會議室：
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

編輯設定檔，以符合您的拓撲：

在**LoaderProcess.exe.config**，變更 「 controller.contoso.com 」 控制器電腦的完整的網域名稱 (FQDN)。

在 [ **StressLauncher.exe.config:**

1.  將 「 LoaderBinary 」 設定值變更為共用的資料夾的路徑。

2.  變更 「 機器 」 / 「 AdminPassword 」 至已載入機器的系統管理存取權的認證。

3.  變更 「 ChannelCategory 」 名稱的壓力通道類別已建立在之下。

4.  變更 「 UserNamePattern 」 和 「 UserPasswordPattern 」 為範本相符壓力使用者認證。 {0}會取代使用者的索引編號。

5.  將 「 網域 」 變更為您的測試拓撲的 SIP 網域。

6.  將 「 ConnectionString 」 變更為您常設聊天室後端資料庫連線字串。

7.  將 「 UserIndexStart 」 變更為第一個壓力使用者的索引。

8.  將 「 LyncFQDN 」 變更為前端集區的 FQDN。

9.  修改 「 機器 」 清單中包含的所有載入機器的機器名稱。

10. 變更服務端點的 baseAddress （預設值為 「 controller.contoso.com 」） 至您的控制器電腦的 FQDN。

</div>

<div>

## <a name="usage"></a>Usage

完成設定之後，請開啟 StressLauncher.exe 控制器機器上。 您可以啟動 StressLauncher 的任何使用者。 必須在組態檔中指定下載入機器，啟動載入程序的認證。 您也必須提供具有讀取存取權的常設聊天室後端資料庫連線字串。 如果此連接字串會使用整合式的 Windows 驗證，您必須啟動 StressLauncher 具有此存取權的使用者。

視需要變更的使用者模型設定。 按一下 [啟動執行**啟動載入**。 後一分鐘左右，使用者就會開始正在登入，進度列會並開始以填滿。 此時，您可能可以控制站的機器 working 和採取效能測量。

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>描述

ChatUpgradeVerifier 是常設聊天室的特定資料庫比較工具。 工具會比較 [群組聊天 2007 R2] 或 [群組聊天 2010年資料庫 (2007年/2010Db) 至常設聊天室 2013年資料庫 (2013Db)。

在工具會檢查，請逐一，每個類別，常設聊天室的會議室，和 2007年/2010Db 以查看它會出現在 2013Db 中增益集。 比較包括檢查上類別、 聊天室，或增益集、 在 [範圍] 類別中，任何主體和任何主體角色上類別或聊天室中的所有設定。 如果類別或聊天室未正確出現在 2013Db，差異就會輸出至衝突檔。 如果在升級之後發生，2007年/2010Db 變更並再執行此工具之後，會有衝突檔差異輸出。 請注意，此應用程式資料庫比較只是工具並不會驗證升級程序。

</div>

<div>

## <a name="requirements"></a>需求

具有常設聊天室後端資料庫 （先前和目前版本，如常設聊天室） 的存取權的已加入網域的機器上安裝的常設聊天室 Resource Kit 工具。

執行工具的使用者帳戶必須具備的常設聊天室資料庫的讀取權限。

ChatUpgradeVerifier.exe.config 檔案必須包含 GroupChat2007R2Db 參數或 GroupChat2010Db 參數，以連接字串至適當的群組聊天資料庫 （Groupchat 2007R2 或 2010年）。 它也必須包含一個 PersistentChat2013Db 參數，以常設聊天室 2013年資料庫的連接字串。

</div>

<div>

## <a name="usage"></a>Usage

執行**ChatUpgradeVerifier**不含任何參數。

</div>

<div>

## <a name="example"></a>範例

![執行 ChatUpgradeVerifier.exe。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "執行 ChatUpgradeVerifier.exe。")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>常設聊天室使用情況報告

<div>

## <a name="description"></a>描述

ChatUsageReport 工具產生 HTML 報告的常設聊天室服務流量。

</div>

<div>

## <a name="requirements"></a>需求

具有常設聊天室後端資料庫的存取權的已加入網域的機器上安裝的常設聊天室 Resource Kit 工具。

下執行此工具的使用者帳戶必須具備的常設聊天室後端資料庫的讀取權限。

該檔案，ChatUsageReport.exe.config，必須包含\<connectionStrings\> ] 區段中定義的連接字串的常設聊天室後端資料庫。 預設設定檔的內容會包含在這裡，供您參考。

</div>

<div>

## <a name="usage"></a>Usage

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
這些參數定義資料的選取範圍：

**StartDate:**（選用） 指定 UTC 的開始日期的選取範圍期間。 預設值： 最早日期

**EndDate:**（選用） 指定的選取範圍期間的 UTC 結束日期。 預設值： 現在

這些參數定義方式並要顯示的資料：

**TopActiveUsers:** 如果指定此參數，報表會在選取時段內就在聊天室中包含方面的使用者已張貼的訊息數目 n 個最活躍的使用者。 預設值：10

**TopActiveRooms:** 如果指定此參數，報表會包含在選取時段內聊天室中張貼的訊息數目方面 n 最活躍聊天室。 預設值：10

**LeastActiveRooms:** 如果指定此參數，報告都會包含 n 至少作用中的聊天室數方面的聊天室中張貼在選取時段內的郵件數目。 聊天室必須至少一個張貼的訊息。 預設值：10

**RoomsInactiveSince:** 如果指定此參數，報表會包含指定日期之後已停用的聊天室清單。 預設值： 整個時間

**OutputFolder:** 要放置 ChatUsageReport.html 和 graph 圖像] 資料夾。 這必須定義在組態檔中或在命令列上。

所有命令列參數的值也可以指定 ChatUsageReport.exe.config 檔案位於工具的相同目錄中。 如果未指定任何值，組態檔和命令列中，命令列的值會覆寫設定檔值。

</div>

<div>

## <a name="output"></a>輸出

報表永遠會包含下列輸出：

  - 所選期間內張貼 top n 最活躍聊天室的訊息數目。

  - 最 n 最活躍的使用者所選取的期間的郵件文章數。

  - 所選期間內張貼 top n 至少 active 聊天室的訊息數目。

  - 非作用中的整個生命週期的資料庫，或指定日期之後的聊天室。

  - 每日訊息張貼趨勢針對選取的期間。

  - 每週的郵件所選期間內張貼趨勢。

  - 針對每月訊息張貼趨勢選取期間。

  - 所選期間內張貼訊息總數。

  - 已啟用的聊天室總數。

</div>

<div>

## <a name="example"></a>範例

下列範例會使用情況報告產生整個 2001 年的並置於 OutputFolder ChatUsageReport.exe.config 中指定的報表。

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport.exe.config:

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

ScheduleADSyncForPrincipal 是必須在 SQL Server Management Studio 連線至常設聊天室後端資料庫時的 [直接從執行 Microsoft SQL Server 2012 指令碼。 此指令碼可讓您強制常設聊天室與進行同步處理其記錄的使用者的 Active Directory 網域服務，而不是等待排定的同步處理的時間。

</div>

<div>

## <a name="requirements"></a>需求

在其下執行指令碼的使用者帳戶必須擁有者存取權的常設聊天室後端資料庫。

</div>

<div>

## <a name="usage"></a>Usage

以下是預設的指令碼的內容：

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

