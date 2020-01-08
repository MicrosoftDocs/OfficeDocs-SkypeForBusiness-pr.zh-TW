---
title: Lync Server 2013 版本資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a93fabf10355dcc4ba7873921c0aaf35475927c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Lync Server 2013 的版本資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-08_

歡迎使用 Lync Server 2013 版本資訊。 請參閱此檔案，以取得有關 Lync Server 2013 已知問題的相關資訊。

<div>

## <a name="about-this-document"></a>關於這份檔

此檔包含您在部署和使用 Lync Server 2013 之前應該知道的重要資訊。 如需 Lync Server 2013 的詳細資訊，請參閱[Microsoft Lync server 2013](microsoft-lync-server-2013.md)檔。

本檔包含下列各節：

  - Lync 2013 用戶端

  - Lync Server

  - 安裝

  - 行動性

  - 會議

  - 企業語音

  - 目前狀態

  - 回應群組應用程式與通話駐留應用程式

  - Lync Server 控制台、拓撲產生器及規劃工具

  - 翻譯

  - 著作權

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Lync 2013 用戶端

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>如果檔案已在另一個應用程式中開啟，則在立即訊息中轉移檔案失敗

**出現**

如果您嘗試傳送檔案（例如 Word 檔），並將它納入至另一個 Lync 使用者的立即訊息中，則傳輸會顯示為成功，但實際上無法傳輸檔案。 該檔案類型的圖示會顯示在 Lync 用戶端中，但預期的接收器無法開啟該檔案。 不會顯示任何錯誤訊息，通知您傳輸未成功。

**避免**

若要解決此問題，請先關閉開啟的檔案或應用程式，然後再嘗試在立即訊息中傳輸檔案。

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>如果 Lync Server Storage Services 資料複製失敗，系統管理員將需要檢查陳舊儲存服務佇列專案的效能計數器

**出現**

Lync Server Storage Service 使用 Windows Fabric 進行複製。 如果資料是在主前端伺服器上刪除，但在副前端伺服器上的刪除失敗（例如，如果前端伺服器出現意外的關閉或錯誤），則資料可以留下並「孤立」。 孤立的資料可能會造成效能下降，並浪費磁片磁碟機空間。

**避免**

\_若要解決此問題，如果使用\_\_\_中的事件 LYSS DB 空間錯誤（id = 32058），\_且\_已\_使用\_的 LYSS DB 空間（Id = 32059）是在事件記錄檔中產生，系統管理員應該檢查前端伺服器上的效能計數器，其中的**LS： LYSS-storage service API**的名稱為**LYSS-目前數量的 storage services 過時佇列專案**。 如果這個效能計數器具有高值（例如，大於50000），系統管理員應該在 Lync Server 2013 資源套件中執行 CleanuUpStorageServiceData 工具，這會從池中刪除所有孤立的資料。 如需有關工具的詳細資訊，請參閱 Lync Server 2013 資源套件檔。

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>每當伺服器或池中的 IP 位址設定變更時，必須重新開機 Lync Server 服務

**出現**

當 Lync Server 2013 部署的 IP 位址設定變更時（例如從 IPv4 改為雙堆疊，或從雙堆疊變更到 Ipv6 時），並不是所有伺服器元件都會在重新開機服務之前，選取設定的變更。

**避免**

若要解決此問題，請在變更部署的 IP 位址設定後重新開機 Lync Server services。 若要這樣做，請在 Lync Server 管理命令介面中執行下列 Cmdlet：

   ```
    Stop-CsWindowsService -graceful
   ```

   ```
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>Lync Server 2013 管理套件中不再提供電話撥入式會議綜合交易 Cmdlet

**出現**

Lync Server 2013 管理套件中的電話撥入式會議綜合交易 Cmdlet Cmdlet **CsDialInConferencing**已不再提供。

**避免**

使用電話撥入式會議綜合交易 Cmdlet**的 CsDialInConferencing**僅限在企業內部支援。

系統管理員可能會繼續使用 Lync Server Management Shell 中的 Cmdlet 來進行疑難排解。 如有需要，企業也可以開發私人管理套件來在內部執行 Cmdlet。

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>如果在將記錄檔案複製到網路共用時，網路流量會中斷，集中式記錄服務就會停止

**出現**

當集中式記錄服務設定為使用網路路徑時（CsClsConfiguration Cmdlet 的 CacheFileNetworkFolder 參數值是有效的 UNC 路徑），系統會將**快取的**記錄檔複製到網路共用。 如果在複製檔案時網路流量中斷，就會發生例外狀況，導致集中式記錄服務停止。

此服務會設定為自動重新開機多達三次，因此服務將會從前三個例外狀況中復原。

**避免**

這個問題目前沒有解決方法。 若要找出問題，請從 [服務控制管理員] 監視記錄「Lync Server 中央記錄服務代理程式」意外終止的事件 ID 7031 事件記錄。 如果發生這種情況超過三次，請使用**CsWindowService** Cmdlet 手動重新開機服務。

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>必須手動匯入儲存服務佇列專案

**出現**

Lync Server 2013 儲存關於會議與立即訊息的資料，例如封存的郵件，以及呼叫詳細資料錄製（CDR），在每個前端伺服器上的資料庫上。 資料會在處理期間儲存在資料庫中，然後才能傳送到預定的目的地。 若要改善效能，Lync Server 2013 會定期從本機資料庫匯出不是經過長時間處理的佇列專案，並將它們儲存在檔案存放區。 如果檔案存放區無法使用，這些專案會儲存在每個前端伺服器上。 在池容錯移轉期間，發生相同的操作，以避免資料遺失。

在匯出作業期間，Lync Server Storage Service 會在事件日誌中記錄每個階段，且事件 Id 為32075（完整刷新作業已開始）、32076（完全清除已完成）、32082（維護層級 flush 開始）、32083（維護層級 flush）已完成），32089（因填滿資料庫而發生清洗）。 此資料將不會自動匯入到系統，即可處理並傳送到其最終目的地（SQL Server 或 Exchange 伺服器）。

**避免**

若要匯入資料至系統，系統管理員必須在 Lync Server 資源套件中使用 ImportStorageServiceData 工具，這會將資料重新加入系統，以進行處理並傳送到最終目的地。

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>如果 UseNormalizationRules 的預設值變更為 False，通訊錄網頁查詢搜尋就會失敗

**出現**

如果 UseNormalizationRules 的預設值變更為 False，通訊錄網頁查詢搜尋將會失敗。 預設值變更之後，Lync 用戶端使用者將無法使用 Lync 通訊錄網頁查詢來搜尋使用者。

**避免**

如果 UseNormalizationRules 的預設值設為 False，所以使用者可以使用在 Active Directory 網域服務中定義的電話號碼（不含 Lync Server 2013）應用正常化規則，請執行下列動作來解決此問題：

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  請執行下列其中一項操作：
    
      - 如果您的部署只包含 Lync Server 2013 伺服器，請在全域層級執行下列 Cmdlet，將 UseNormalizationRules 和 IgnoreGenericRules 的值變更為 True：
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果您的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的組合，請執行下列 Cmdlet，並將它指派給拓撲中的每個 Lync Server 2013 池：
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等待 CMS 複製在所有的池中進行。

4.  針對您的部署修改電話正常化規則檔案，以清除內容。 檔案位於每個 Lync Server 2013 池的檔案共用位置。 如果檔案不存在，請建立名為「\_公司電話\_號碼\_正常化\_Rules .txt」的空檔案。

5.  針對所有前端池，請等候幾分鐘，以讀取新檔案。

6.  在您部署中的每個 Lync Server 2013 池中，執行下列 Cmdlet。
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>每個 Lync 2013 池每天都會產生通訊錄服務器錯誤事件21054

**出現**

Lync Server 2013 通訊錄服務器會在執行日常維護時每天產生錯誤事件21054。 每當系統管理員執行**更新 csAddressBook** Cmdlet 時，也會產生錯誤，即使更新成功也一樣。 不過，更新成功時，可以安全地忽略此錯誤事件。

**避免**

當您遇到此錯誤事件時，請執行下列 Cmdlet：

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

如果 Cmdlet 報告沒有任何未編制或已放棄的物件，就可以放心地忽略錯誤事件21054。

此外，系統中心操作管理員應該已關閉 [正確編制索引的主要狀況指示（KHI）] 的 [通訊錄使用者]。

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>在 Edge 池中設定 IPv6 時，可能會發生要求失敗

**出現**

當您在 Edge 池中設定 IPv6 時，對邊緣池的一些要求可能會失敗。

**避免**

若要解決此問題，請不要使用 IPv6 設定 Edge 池。

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>CsPoolFailback Cmdlet 在 pool 切回期間可能失敗

**出現**

當您嘗試將池進行容錯回復時， **csPoolFailback** Cmdlet 可能會失敗，並出現錯誤 "無法在重複嘗試之後完成 hydration 程式。」

**避免**

若要解決此問題，請再次執行 Cmdlet，然後等到 Cmdlet 成功為止。 請注意，容錯回復程式可能需要幾分鐘的時間才能完成。 有20000個使用者的池可能需要長達60分鐘的時間。

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>當您將前端伺服器新增到已建立的 pool （混合式、商務用 Skype Online）時，可能會發生資料遺失問題

**出現**

您可能會在擁有多個前端伺服器的環境中遇到這個問題，而且您可以重新開機其中一個前端伺服器，或新增先前不屬於該池的新前端伺服器。

已封存資料的使用者可能會在資料封存建立到該池之前，遇到資料遺失的問題。 此期間的潛在資料遺失時間限制為15分鐘，讓人員對人員交談，以及30分鐘的會議。

**避免**

如果您執行的是維護，而不是將前端伺服器逐一啟動，您應該將該池容錯移轉到另一個池，然後在伺服器上執行維護任務。 您也可以在執行維護工作前，讓服務無法使用，然後在維護完成時還原可用性。

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>系統管理員無法使用 CsClientAccessLicense Cmdlet 取得受許可人人數

**出現**

系統管理員無法使用**CsClientAccessLicense** Cmdlet 取得精確的客戶授權使用。

**避免**

若要檢查伺服器授權類型，您可以執行**CsService** Cmdlet，以取得所有資料庫的完整功能變數名稱（FDQNs）。 如果前端伺服器的 FQDN 與後端資料庫的 FQDN 相同，則該授權是標準版授權。 否則，授權就是企業版授權。

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>未準確報告用戶端獲許可人數量

**出現**

在判斷用戶端授權計數時，您可能會遇到下列情況：

1.  **行動使用者不准確的授權計數**
    
    授權計數是以針對裝置的使用者的唯一 IP 位址數量為基礎。 授權計數會受到下列幾種限制：
    
      - 如果使用者的 IP 位址在 Lync 會話期間發生變更，就會 overcounted 授權。 當使用者從多個位置使用桌面用戶端連線到 Lync Server 時，可能會發生這種情況。
    
      - 如果使用者與行動用戶端連線，則會 undercounted 授權，因為無法判斷裝置的 IP 位址。

2.  **授權的計算數量是將公用交換電話網絡（PSTN）呼叫傳送到 Lync 用戶端、Lync 用戶端呼叫 PSTN 線路，以及將 Lync 來電轉接至 PSTN 線路**
    
    在下列案例中，將會計算兩個額外的授權，而不是一份，因為電話號碼和 Lync 使用者都會計算在內，以決定所使用的授權數量。 若要取得精確的授權資料，請手動移除電話號碼所產生的授權。
    
      - Lync 的 PSTN 電話通話
    
      - 對 PSTN 線路進行 Lync 通話
    
      - Lync 的 PSTN 呼叫，然後 Lync 會將呼叫轉寄到 PSTN 線路。 其中一個 PSTN 線路會計算在內。

3.  **授權不會對已登入的 Lync 手機計數**
    
    當使用者使用 Lync 認證的手機時，如果電話登入並保持連線，這會保留其登入狀態，但如果在登入電話之後，就會將該電話算作授權。

4.  **為 PSTN 手機加入會議所計算的授權**
    
    當使用者使用 PSTN 手機加入會議時，系統會不准確地計算授權加入會議。 不過，不需要授權，就能使用 PSTN 手機加入會議。

**避免**

1.  **行動使用者不准確的授權計數**
    
      - 您可以手動識別屬於同一個裝置的 IP 位址，然後在 [授權計數] 中移除其中一個。
    
      - 使用 Lync 用戶端連線的行動裝置無法解決此問題。

2.  **授權是針對 Lync 用戶端、Lync 用戶端呼叫 PSTN 線路，以及轉寄到 PSTN 線路的 PSTN 呼叫進行兩次計數**
    
    您必須手動識別 PSTN 電話號碼，並移除為其所產生的授權計數。

3.  **授權不會對已登入的 Lync 手機計數**
    
    您可以將 Lync phone 設定為 [登出]，然後以定期間隔（例如每3個月）重新登入。

4.  **為 PSTN 手機加入會議所計算的授權**
    
    您可以手動識別用來加入會議並移除電話號碼所產生之授權的 PSTN 電話號碼。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>升級至 Silverlight 5 之後，Lync Server 控制台在 VMware 環境中停止運作

**出現**

如果您在 VMware 環境中使用 Lync Server 控制台，在您將 Microsoft Silverlight 升級到版本5之後，Lync Server 控制台可能會停止運作。

**避免**

若要解決此問題，請執行下列其中一項操作：

  - 卸載 Silverlight 5，然後從[https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)安裝 silverlight 4。

  - 從非 VMware 虛擬電腦的電腦存取 Lync Server [控制台]。
    
    若要這樣做，您可以從伺服器上的 Windows [**開始**] 功能表中啟動 lync Server [控制台] （如果電腦上已安裝 Lync server 管理工具）。
    
    您也可以使用網頁瀏覽器存取 Lync Server [控制台]。 URL 會類似\<HTTPs://前端\_池\_fqdn/cscp.\>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>在 Active Directory 中修改使用者的辨識名稱之後，通訊錄服務中的使用者資訊並未更新

**出現**

如果在 Active Directory 網域服務中，使用者的判別名（也稱為 DN）已變更，任何其他變更將不會在通訊錄服務（ABS）中更新。 這不會影響使用者的登入或目前狀態，但如果 SIP 位址也有所變更，就會防止使用者進行通訊，因為搜尋會傳回過時的 SIP 位址。

**避免**

若要解決此問題，請不要變更使用者的 DN。 如果您將使用者的 DN 還原為前一個值，更新將會反映在通訊錄服務中。

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>安裝

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>在 Lync server 無法啟動的情況中，使用非 ASCII 字元可能會導致

**出現**

如果目的地資料夾名稱包含非 ASCII 字元（包括 UNICODE、雙位元組字元集（DBCS）、UTF-8 和 UTF-16），安裝將會失敗。 此外，安裝程式可能會成功，但如果下列任何一項中包含非 ASCII 字元，則伺服器無法啟動：

  - 電腦名稱稱

  - 網功能變數名稱稱

  - 使用者名稱

  - 使用者 SIP URI

  - 服務帳戶名稱

**避免**

在目的地資料夾名稱、[電腦名稱稱]、[功能變數名稱]、[使用者名稱]、[使用者 SIP URI] 及服務帳戶名稱中，只能使用 ASCII 字元。

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>在安裝 Lync Server 2013 之前，必須先安裝模組呼叫 IIS 7.5 中的 InsertEntityBody 方法時，會發生「堆損毀」的修復程式

**出現**

在安裝 Lync Server 2013 之前，必須先安裝 Microsoft 知識庫文章264886（[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)）中所述的「堆損7.5 毀」的修復程式，才能使用此功能。

**避免**

從 Microsoft 下載中心下載並安裝修複程式[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)。

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 無法在 ITA Windows Server 2012 作業系統 RTM 版本上安裝

**出現**

由於 Windows Fabric 安裝失敗，所以在 ITA Windows Server 2012 上安裝 Lync Server 2013 失敗。

Windows Fabric 安裝失敗，因為使用 HH： MM： SS 的時間格式建立結構追蹤。 不過，在 ITA Windows Server 中，時間格式為 HH。MM.SS。

**避免**

若要解決此問題，請在安裝 Lync Server 2013 之前更新系統登錄。 需要更新的登錄機碼為： HKEY\_使用者。\\預設\\控制台 [\\國際\\sTimeFormat]。 若要將 sTimeFormat 的值變更為 HH： mm： ss，請使用 Windows PowerShell 命令列介面，如下所示：

1.  啟動 Windows PowerShell 並執行下列 Cmdlet：
    
       ```
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  若要查看目前的值，請執行下列 Cmdlet：
    
        Get-itemproperty $a -Name sTimeFormat
    
    記下 sTimeFormat 的目前值，以便在安裝完成後進行還原。

3.  若要設定為新值，請執行下列 Cmdlet：
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  成功安裝 Lync Server 2013 之後，請執行下列 Cmdlet 來還原 sTimeFormat 的原始值：
    
        - 在步驟3中，設定 ItemProperty $a 名稱 sTimeFormat-值 "<值。 上方> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>行動性

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>在伺服器容錯移轉程式期間，行動用戶端的問題

**出現**

當 Lync 伺服器失敗且容錯移轉進程開始時，下列問題可能會影響行動用戶端使用者：

  - 在容錯移轉開始之後，沒有最多10分鐘的撥入 Lync 通話或信號。

  - 無法接受傳入的聊天要求

  - 如果發生故障的伺服器是使用者的主伺服器，則無法加入會議

**避免**

這個問題目前沒有解決方法。 當容錯移轉程式完成後，就會還原正常的功能。

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>如果行動使用者拒絕來自另一個 Lync 端點的來電，該通話會在 Lync 行動用戶端上顯示為未接的轉換

**出現**

如果行動使用者拒絕來電，而呼叫是從另一個 Lync 端點發出，則該通話會在 Lync 行動用戶端中顯示為未接的交談，而不是在裝置通話清單中的通話。

**避免**

這個問題目前沒有解決方法。

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>在搜尋連絡人時，行動用戶端可能不會顯示同盟連絡人的顯示名稱

**出現**

在某些情況下（例如在連絡人清單中搜尋同盟連絡人時），同盟連絡人的顯示名稱可能不會顯示。 在 Lync 行動用戶端沒有連絡人的有效目前狀態訂閱時，就會發生這種情況。

**避免**

這個問題目前沒有解決方法。

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>在行動用戶端中，來自會議邀請的未接來電缺少被邀請者和 timestamp 資訊

**出現**

在行動用戶端中，當未接的交談是會議邀請時，未接的交談訊息中的被邀請者和時間戳記資訊就會消失。

**避免**

這個問題目前沒有解決方法。

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>使用 VoIP 進行呼叫的行動用戶端使用者無法讓語音信箱針對 Exchange 2010 或較舊版本中設定的使用者留下語音信箱

**出現**

如果行動用戶端使用者使用 VoIP 來進行通話，使用者將無法為已設定為在 Microsoft Exchange Server 2007 或 Microsoft Exchange Server 2010 中使用語音信箱的使用者留下語音信箱訊息。

**避免**

若要解決此問題，請將 Exchange 2010 與 SP1 或更新版本的 Microsoft Exchange Server 搭配使用。

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>在行動用戶端上使用 Block 與用戶端版本設定的 URL 時，可能會顯示不正確的錯誤訊息

**出現**

在行動用戶端上使用**Block 與**用戶端版本設定的 URL 時，可能會在用戶端版本不受支援時顯示不正確的錯誤訊息。

**避免**

若要解決此問題，請將用戶端版本配置設定為使用**區塊**，而不是使用**URL 區塊**。

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>會議

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>在 Lync Server 2013 前端伺服器上執行的防毒軟體可能會造成應用程式網域回收，這會暫時中斷 Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013 用戶端的服務

**出現**

防毒軟體可以觸發應用程式網域重新開機，這可能會導致 Lync 行動裝置服務2013和整合通訊（UC） Web API 用戶端應用程式（Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013）損失其狀態。

**避免**

若要解決此問題，請從防病毒掃描中排除包含網頁元件和 .NET framework 的資料夾。 如需詳細資訊，請參閱 Microsoft 知識庫文章312592、"PRB： ASP.NET 中的應用程式重新開機時發生隨機應用程式重新開機[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)] 錯誤（位於）。

下列資料夾應被排除：

  - % ProgramFiles%\\Microsoft Lync Server 2013\\網頁元件\\Mcx\\Ext

  - % ProgramFiles%\\Microsoft Lync Server 2013\\網頁元件\\Mcx\\Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\網頁元件\\Ucwa\\Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\網頁元件\\Ucwa\\Ext

  - % Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\Config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>必須啟用 Windows Internet Explorer 中的 ActiveX 控制項或原生 XMLHTTP 支援，才能成功加入會議

**出現**

如果使用者已停用 Windows Internet Explorer Internet 瀏覽器設定中的 ActiveX 控制項和原生 XMLHTTP 支援，且選取 [Internet Explorer] 做為預設瀏覽器，使用者將無法加入會議。

**避免**

啟用 Internet Explorer 中的 ActiveX 控制項或「原生 XMLHTTP 支援」。

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Lync Server Web 會議服務無法從緊急模式復原

**出現**

如果已開啟 [關鍵模式] 進行封存，則在系統失敗時，系統會啟動重要模式，且會議將不再適用于參與者。 在管理員修正系統失敗（例如修正資料庫問題）之後，資料會議服務不會自動復原，而且管理員必須手動重新開機會議服務才能繼續進行會議。

**避免**

系統管理員必須在系統失敗修正之後，手動重新開機會議服務。

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>網路會議服務會忽略外部 Office Web App 伺服器的 HTTP proxy

**出現**

如果您已在網際網路、周邊網路和網路會議服務中部署網路會議服務外部的 Office Web Apps 伺服器（也就是不在內部公司網路中的伺服器），請使用 HTTP proxy 連線至這項，Office Web Apps Server 探索將會失敗。 網路會議服務會忽略 HTTP proxy 設定，如在 [Office Web Apps 伺服器設定] 的 [拓撲建立器] 中定義。 因此，Lync 用戶端將無法與會議中的其他參與者共用 Microsoft PowerPoint 2010。 如果您是在內部部署安裝 Lync Server，而且也在內部網路中設定 Office Web Apps Server 內部部署，則不需要使用 proxy 配置。

**避免**

唯一的因應措施是不需要使用 HTTP proxy 來與外部 Office Web Apps 伺服器通訊的部署設定。

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>不支援在音訊會議提供者會議中新增影片

**出現**

如果使用者已加入音訊會議提供者會議，則不支援新增影片。

**避免**

這個問題目前沒有解決方法。

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>啟用 IPv6 的拓撲會強制 Lync Web App Silverlight 外掛程式自動更新，以確保螢幕共用功能可從 Lync Web App 運作

**出現**

當拓撲已設定為啟用 IPv6 時，如果已安裝舊版的螢幕共用外掛程式，使用者就無法從 Lync Web App 用戶端共用其螢幕。

**避免**

若要在透過 Lync Web App 加入會議時，強制更新最新版本的螢幕共用外掛程式，請在下列兩個檔案中，將**MinSupportedBuildVersion**的值從 "4.0.7457.0" 修改為 "4.0.7577.380"：

  - % ProgramFiles%\\Microsoft Lync Server 15\\網頁元件\\是\\Int\\個\\客戶\\端外掛程式 ReachAppShPluginProperties .xml

  - % ProgramFiles%\\Microsoft Lync Server 15\\網頁元件\\無法\\延伸\\至\\Ext\\用戶端外掛程式 ReachAppShPluginProperties .xml

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>企業語音

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>在某些情況下，在設定為使用 IPv4 和 IPv6 雙堆疊的電腦上執行的 Lync 用戶端，可能不支援依賴電腦的 IP 子網（例如 E911、媒體旁路、通話許可控制和位置式路由）的功能。

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。



</div>

**出現**

當 Lync 用戶端在啟用 IPv4 與 IPv6 雙堆疊的電腦上執行時，且根據 proxy 伺服器的 DNS 解析，用戶端可以使用電腦的 IPv6 位址登入。 如此一來，Lync 用戶端將只支援 IPv6 支援的功能，不包括 E911、媒體旁路、通話許可控制和位置路由。

**避免**

若要解決此問題，請在用戶端電腦上停用 IPv6 支援。

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>如果沒有為使用者設定企業語音，使用者將需要使用 E164 格式從會議撥出

**出現**

如果沒有為使用者設定企業語音，該使用者將需要使用 E164 格式，才能從會議成功撥號。 如果未使用 E164 格式，則使用者將無法從會議撥出。

**避免**

若要解決這個問題，沒有啟用企業語音的使用者應該使用 E164 格式的號碼來撥打電話給會議。

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>目前狀態

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>如果使用者已選取 [封鎖所有邀請與通訊]，而整合連絡人存放區已開啟給使用者，目前狀態不會遭到拒絕

**出現**

如果使用者已選取 [封鎖所有邀請與通訊]，而整合連絡人存放區已開啟給使用者，目前狀態不會遭到拒絕。

**避免**

若要解決此問題，您可以關閉使用者的整合連絡人存放區。 若要這樣做，請執行下列 Cmdlet：

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

例如：

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office 通訊伺服器 2007 R2 使用者駐留內部部署無法在混合式部署中查看商務用 Skype Online 使用者的目前狀態（混合式部署）

**出現**

當您使用 Lync Server 2013 控制器時，混合式部署中可能會發生這個問題。

[託管至商務用 Skype Online] 使用者的目前狀態顯示為內部部署使用者的目前狀態為未知。 此外，駐留在商務用 Skype Online 的使用者無法查看 Office 通訊伺服器 R2 內部部署使用者的目前狀態。

**避免**

若要解決此問題，請將商務用 Skype Online 使用者的主伺服器（msrtcsip-presencehomeserver）變更為指向 Lync Server 2013 內部部署池，而不是 Lync Server 2013 控制器。 您可以在內部部署前端伺服器上修改此設定。

此因應措施會將駐留到 Office 通訊伺服器 2007 R2 的使用者目前狀態正確顯示在商務用 Skype Online 使用者。

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>回應群組應用程式、通話駐留應用程式，以及群組通話提貨

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>在使用檢索方建立通話期間，來電者可能會聽到一秒的音樂暫停狀態

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。



</div>

**出現**

透過群組呼叫分揀來檢索通話時，呼叫者在與交叉檢索方進行通話期間，可能會聽到一秒的音樂暫停狀態。

**避免**

這個問題目前沒有解決方法。

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>回應群組代理程式可以透過 Lync Server 2010 代理程式主控台登入並登出至 Lync Server 2010 正式代理群組

**出現**

Lync Server 2013 回應群組代理程式可以透過 Lync server 2010 代理程式主控台登入，並將其登出至 Lync Server 2010 正式代理程式群組。 在 Lync Server 2010 代理程式主控台中，使用者只能看到其所屬的 Lync Server 2010 回應群組。 他們看不到他們所屬的任何 Lync Server 2013 回應群組。

**避免**

如果回應群組代理是 Lync Server 2013 的使用者，而且是 Lync Server 2013 正式代理群組的一部分，使用者必須透過瀏覽器中的網頁連結直接存取 Lync Server 2013 代理程式主控台，才能從 Lync Server 2013 代理程式群組登入和登出。

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Lync server 2010 回應群組代理程式無法代表 Lync Server 2013 回應群組撥打來電

**出現**

Lync server 2013 回應群組代理的 Lync Server 2010 使用者無法代表回應群組撥打電話給您。 Lync Server 2013 回應群組將無法在 Lync 用戶端中使用，以進行通話。

**避免**

若要解決此問題，您必須將 Lync Server 2010 使用者移至 Lync Server 2013。

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>在將回應群組遷移至 Lync Server 2013 之後，將其從 Lync Server 2010 移除之後，將會導致回應群組無法接受任何來電

**出現**

如果從 lync server 2010 遷移到 Lync server 2013 的回應群組已從 lync server 2010 透過 Lync server [控制台] 或 [Lync Server 管理命令介面] 移除，則 Lync Server 2013 中的 [回應] 群組將停止接收任何來電。

**避免**

若要解決此問題，請不要從 lync server 2010 （已從 Lync Server 2010 遷移到 Lync Server 2013）移除任何回應群組。

如果回應群組已移除，您應該在 Lync Server 2013 中重新部署。

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>當新的受管理工作流程在建立時設定為非使用中時，工作流程部署將會失敗

**出現**

當新的受管理工作流程在建立時設定為非使用中時，工作流程部署將會失敗。 此問題是在建立工作流程時將它設為 [非使用中] 時，但不會影響已編輯為在部署後將其設為非使用中的工作流程。

**避免**

建立及部署工作流程時，請將工作流程設定為 [作用中]，然後進行部署。 成功部署工作流程之後，即可編輯工作流程並將其設為非使用中。

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>從擁有者池中移除回應群組，將會在回應群組已匯入到備份池中時，防止在容錯移轉期間，備份池的回應群組接受任何來電。

**出現**

如果主要池所擁有的回應群組已匯入到備份池中，且未覆蓋擁有者，且已從擁有者池中移除回應群組，則在容錯移轉期間，備份池中的回應群組將不會接受任何來電。

**避免**

您將需要在主要池中重新部署回應群組。 接著，您必須從主要的池中匯出回應群組設定，然後再次將它匯入到備份池中。

您也可以在備份池中重新建立回應群組。 在這種情況下，備份池會是回應群組的擁有者池。

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>如果是代表回應群組完成檢索要求，則無法從通話駐留應用程式中檢索寄存通話

**出現**

當下列條件成立時，寄存式呼叫的檢索要求將會失敗：

  - 代理程式是匿名回應群組的一部分

  - 代理程式嘗試透過匿名回應群組從通話駐留應用程式中檢索暫停的呼叫

  - 工程師會嘗試透過 [代表撥號] 選項或在 Lync 助理用戶端中的相同選項撥打軌道編號來取回通話。

**避免**

這個問題沒有解決方法。 停用通話應該在未代表回應群組的情況下進行檢索。

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Lync Server 控制台、拓撲產生器及規劃工具

<div>

## <a name="planning-tool-limitations"></a>規劃工具限制

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。



</div>

**出現**

規劃工具在規劃部署時有下列限制：

  - 最多可支援10個中央網站

  - 每個中央網站最多可以有14個分支網站

  - 每個中央網站最多可有240000個使用者

此外，在計算建議的拓朴時，規劃工具不會包含下列值：

  - 線上駐留的使用者數目

  - 已啟用 XMPP 同盟的使用者百分比

  - 使用 Lync Web App 之使用者的百分比

**避免**

這些問題目前沒有解決方法。 如需規劃工具的詳細資訊，請參閱[使用規劃工具設計 Lync Server 2013 的拓撲](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)。

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>在更新選項時，規劃工具可能不會針對 Edge 網路使用先前定義的 IP 位址

**出現**

使用規劃工具完成設計後，如果您變更 Edge 網路選項，可能會新增額外的 IP 位址，而不是更新現有的 IP 位址。 這可能會在您查看 Edge 網狀圖表的詳細資料時，請選取 [**按一下這裡以更新您的選項**]，然後在 [設定選項] 對話方塊中選取 [邊緣網路] 選取**我想要使用相同的 fqdn 和 IP 位址，但在我的 edge 伺服器上則邊緣服務的埠不同**。 如果套用任何變更，可能會導致新的 IP 位址與邊緣伺服器新增到設計中。

**避免**

目前沒有此問題的解決方法。

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>在 Lync Server 控制台中，"將所有使用者移至資源庫" 可能無法如期運作

**出現**

當您使用 Lync Server [控制台] 將所有使用者從一個池移至複雜的 Active Directory 環境中的另一個池（例如有多個網網域控制站和父/子網域），可能會傳回錯誤訊息，指出「指定的使用者不是舊版使用者，請改用 Move-csuser Cmdlet」。 這是在複雜的 Active Directory 環境中複製時間較長的結果。

**避免**

若要解決此問題，請執行下列其中一項操作：

  - 在 Lync Server [控制台] 中使用篩選來搜尋舊版使用者，選取這些使用者，然後使用 [**將選取的使用者移至池中] 命令**，而不是 [**將所有使用者移至資源庫**]。

  - 使用 Lync server 管理命令介面，透過 Lync Server Cmdlet，以批次方式移動舊版使用者。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>在將 Microsoft Silverlight 瀏覽器外掛程式更新為版本5之後，Lync Server 控制台在 VMware 環境中停止運作

**出現**

如果您在 VMware 環境中使用 Lync Server 控制台，在您將 Silverlight 升級到版本5之後，Lync Server 的 [控制台] 可能會停止運作。

**避免**

若要解決此問題，請執行下列其中一項操作：

  - 卸載 Silverlight 5，然後從[https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)安裝 silverlight 4。

  - 從不是 VMware 虛擬電腦的電腦開啟 Lync Server [控制台]。
    
    若要從遠端電腦開啟 Lync Server 控制台，請在電腦上安裝 Lync Server 管理工具，然後從 Windows [**開始**] 功能表啟動 [Lync server 控制台]。
    
    您也可以透過在網頁瀏覽器中輸入 URL 來開啟 Lync Server [控制台]。 URL 會類似\<HTTPs://前端\_池\_fqdn/cscp.\>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>在拓撲建立器中移除鏡像資料庫之後，系統管理員無法執行 csMirrorDB Cmdlet

**出現**

當管理員在拓撲結構建立器中停用鏡像資料庫，然後在 [拓撲建立器] 中刪除鏡像資料庫時，系統會在 [待辦事項] 清單中顯示一則訊息，以執行**csMirrorDatabase** Cmdlet，以從 SQL Server 中移除鏡像。 當系統管理員嘗試執行 Cmdlet 時失敗。

**避免**

若要在拓撲建立器中移除某個池的 SQL 鏡像，您必須先使用 Cmdlet，才能在 SQL Server 中移除該鏡像。 然後，您就可以使用 [拓撲建立器] 從拓撲中移除鏡像。 若要在 SQL Server 中移除鏡像，請使用下列 Cmdlet：

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

例如，若要移除鏡像並刪除使用者資料庫的資料庫，請輸入下列內容：

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

*DropExistingDatabasesOnMirror*參數會使受影響的資料庫從鏡像中刪除。 接著，若要從拓撲中移除鏡像，請執行下列動作：

1.  在拓撲建立器中，以滑鼠右鍵按一下該池，然後按一下 [**編輯屬性**]。

2.  清除 [**啟用 SQL Store 鏡像**]，然後按一下 **[確定]**。

3.  發佈拓撲。

<div class="">


> [!IMPORTANT]  
> 每當您對後端資料庫鏡像關聯進行變更時，您必須重新開機池中的所有前端伺服器。



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>當系統管理員嘗試移除具有關聯見證存放區之前端池的部署時，會在拓撲產生器中傳回驗證錯誤

**出現**

如果系統管理員嘗試使用拓撲建立器中的 [**移除部署**] 命令來移除包含含關聯見證存儲區之 [前端] 池的部署，拓撲建立器中會顯示驗證錯誤，且不會繼續執行此動作。

**避免**

若要解決此問題，請執行下列其中一項操作：

  - 在嘗試移除部署之前，請先移除見證儲存區。

  - 為前端池新增見證存儲區，然後將它移除。

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>在規劃工具與拓撲建立器之間，持久聊天伺服器部署資訊不一致

**出現**

當 Lync Server 2013、計畫工具在啟用災害復原的情況下，輸出持續聊天伺服器部署的網站拓撲圖時，網站拓撲圖會包含多個（物理）網站，每個網站都有均勻指派的永久聊天伺服器網站地圖. 在 [拓撲結構建立器] 中，所有持久的聊天伺服器都是由屬於單一（邏輯）網站，且列在相同的永久聊天伺服器池節點底下。

**避免**

我們目前沒有此問題的解決方法。 使用者應該分析持續聊天伺服器部署的規劃工具輸出，並修改方案以滿足其特定需求。

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>翻譯

<div>

## <a name="monitoring"></a>監視

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>使用東亞版 Lync Server 時，[部署監視報告] 嚮導會在某些情況下顯示不正確的字元

**出現**

使用東亞版的 Lync Server 2013 （例如，中文（簡體）、中文（繁體）、日文或韓語），在系統區域設定未設為東亞語言的作業系統上，[部署監視報告] 嚮導將會顯示問號或其他字元，而不是當地語系化的郵件。

**避免**

若要修正此問題，請將作業系統和 Lync Server 2013 的地區設定設為相同的語言，這樣就會正確顯示所有訊息。

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server 控制台

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>在某些情況下，當您按一下上方導覽列中的最後一個專案時，Lync Server [控制台] 頁面頂端流覽列中的第一個專案就會消失

**出現**

在下列情況中，有三個已知案例，按一下 Lync Server [控制台] 頁面上方流覽列中的最後一個專案，就會使上方流覽列中的第一個專案消失：

  - 在法文版中，在頁面「Féderation et accès externe 中，「專案」 Stratégie d'accès externe」會在按一下 [Partenaires fédérés XMPP] 時消失。

  - 在德文版本的 [用戶端] 頁面上，按一下 [Pushbenachrichtigungskonfiguration] 時，專案 "Clientversionskonfiguration" 會消失。

  - 在俄語版本的 [Конфигурациясети] 頁面上，按一下 [Маршрутрегиона] 時，專案「Глобально」就會消失。

**避免**

若要解決此問題，請重新整理瀏覽器中 Lync Server [控制台] 的頁面。 隨即會在瀏覽器中載入頁面，並顯示上方導覽列中的所有專案。

</div>

</div>

<div>

## <a name="address-book"></a>通訊錄

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>在通訊錄中編制索引時，在某些語言中無法如期運作

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。



</div>

如果使用者的屬性包含索引欄位，而該欄位只包含無法編制索引的字元，則使用者不會出現在通訊錄中執行的搜尋中。

下列字元和地區設定無法編制索引：

  - 小寫字母、希臘文及亞美尼亞文字元

  - 大小寫符號的大寫字元

  - 泰語

  - 寮國

  - 緬甸

  - 字母

  - 分

  - 藏文

  - 孟加拉文

  - 古吉拉特文

  - 特拉古文

  - 所有其他印度文腳本

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App、網頁排程程式及網頁元件

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Lync Web 排程器中特定語言的語言回退、撥入、加入啟動器、持續聊天室管理，以及 OCTab 可能無法如期運作

**出現**

在網頁瀏覽器中選取非特定地區設定（在 Internet Explorer 中）時，例如，沒有進一步規範的語言名稱（ \[例如\]「挪威 no」），而不是指定語言、腳本和區域設定（例如「挪威文、 \[博克瑪律文\]（挪威） nb-no」）的特定語言，可能會在 Lync Web 排程器、撥入、加入啟動器、持續聊天室管理以及 OCTab 中導致意外的顯示行為。 例如，當選取下列其中一種語言時，使用者可能會看到英文頁面：

  - 挪威語

  - 葡萄牙文

  - 塞爾維亞文

**避免**

如果您想要選取具有中立區域設定的語言，請務必務必在瀏覽器的語言喜好設定清單中，使用特定地區設定（使用腳本和/或國家/地區代碼）來新增語言。

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>使用 Lync Web 排程器、撥入、加入啟動器、持續聊天室管理，以及在某些網頁瀏覽器中 OCTab 時，對阿澤裡語和烏茲別克地區設定有限的支援

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：2月2013。



</div>

**出現**

當您使用 Internet Explorer 8 或 Internet Explorer 9，並將瀏覽器語言設定為阿澤裡語（拉丁）或烏茲別克（拉丁）時，系統會以英文或瀏覽器中設定的喜好語言來顯示撥入與加入連接啟動器頁面。

當您使用 Firefox 或 Chrome 瀏覽器，並將瀏覽器語言設定為阿澤裡語（拉丁）或烏茲別克（拉丁），Lync Web App、Lync Web 排程程式和 RGS OCTab 將會以英文顯示，或針對瀏覽器設定的喜好語言。

在 Safari 瀏覽器中不支援烏茲別克（拉丁）區域設定。

**避免**

這些問題不提供因應措施。

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>在羅馬尼亞文版本的 Lync Web App 中，[從下列來源加入會議] 清單中缺少下拉式箭號

**出現**

當使用羅馬尼亞文版本的 Lync Web App 的使用者執行下列步驟時，下拉式清單中不會顯示 [**加入會議**] 下拉式箭號：

1.  在 [**一般**] 索引標籤上選取 [**在這台電腦上記住我**]。

2.  選取 [**電話**] 索引標籤。

3.  按一下下拉式清單中的 [**加入會議**]。
    
    使用者將不會看到指出有超過預設**Lync Web App**的選項，包括：**不加入音訊**（在羅馬尼亞文中，"Nu se asociaža la componenta 音訊"）和**新數位**"（在羅馬尼亞文中，" Număr nou "）。

**避免**

雖然不會顯示此下拉式清單的箭號，但使用者仍然可以按一下預設值，在清單中選取其他設定。

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>使用土耳其文版本的 Lync Web 排程器時，使用「誰是簡報者」下的「我選擇的人員」選項無法儲存會議

**出現**

在土耳其文版本的 Lync Web 排程器中建立或編輯會議時，不支援 [誰是簡報者] 下的選項 [我選擇的人員]。 選取此選項時，會議無法儲存。 相反地，會出現錯誤訊息，指出無法將一或多位人員設為簡報者。

**避免**

若要解決此問題，使用者可以使用預設選項 [來自公司的人員] 或任何其他選項，例如「只有召集人」或「所有人在內，包括公司以外的人員」。 召集人在加入會議之後，可以將人員降級或宣傳給他們的正確角色。

或者，瞭解其他語言的使用者也可以將其瀏覽器中的語言選取變更為其他其中一個43支援的語言，然後嘗試使用「我選擇的人員」選項。

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>著作權

本檔支援軟體產品的預發行版本本，在最終的商業發行之前可能會有很大的變更，且是 Microsoft Corporation 的機密及專有資訊。 在收件者與 Microsoft 之間的保密協定中，會依據此條款披露。 本檔僅提供提供資訊的目的，Microsoft 在本檔中不做任何明示或暗示的保證。 本檔中的資訊（包括 URL 及其他網際網路網站參考）可能會變更，恕不另行通知。 使用本檔所帶來的全部風險或後果由使用者自行承擔。 除非另有說明，否則在本文範例中描述的公司、組織、產品、功能變數名稱、電子郵件地址、標誌、人員、位置及事件都是虛構的。 與任何真實的公司、組織、產品、功能變數名稱、電子郵件地址、標誌、人員、地點或事件不相關。 遵守所有適用的著作權法是使用者的責任。 在不限制版權所依據的權利的情況下，本檔的任何部分都不會複製、儲存或引進檢索系統，或是以任何形式或任何方式（電子、機械、複製、錄製或其他）進行傳播。沒有 Microsoft Corporation 的明確書面許可權。

Microsoft 可能具有專利、專利申請、商標、版權或其他智慧財產權，涵蓋本檔中的相關主題。 除了 Microsoft 的任何書面授權合約中明確提供之外，提供這份檔並不代表擁有這些專利、商標、版權或其他智慧財產權的授權。

© 2012 Microsoft Corporation。 保留擁有權利。

Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook 及 SQL Server 都是 Microsoft Corporation 在美國和/或其他國家/地區的注冊商標或商標。

所有其他商標都是其各自擁有者的財產。

</div>

</div>

<span> </span>

</div>

</div>

</div>

