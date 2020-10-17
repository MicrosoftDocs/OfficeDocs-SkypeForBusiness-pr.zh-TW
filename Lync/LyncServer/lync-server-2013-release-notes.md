---
title: Lync Server 2013 版本資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f98a19e81ebf52d97b4c6807dbb97dc8110b0f34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536560"
---
# <a name="release-notes-for-lync-server-2013"></a>Lync Server 2013 的版本資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-08_

歡迎使用 Lync Server 2013 版本資訊。 如需有關 Lync Server 2013 之已知問題的相關資訊，請參閱此檔案。

<div>

## <a name="about-this-document"></a>關於此檔

此檔包含您在部署和使用 Lync Server 2013 之前應該知道的重要資訊。 如需 Lync Server 2013 的詳細資訊，請參閱 [Microsoft Lync server 2013](microsoft-lync-server-2013.md) 檔。

此文件包含下列章節：

  - Lync 2013 用戶端

  - Lync Server

  - 安裝

  - 行動性

  - 會議

  - 設定使用者

  - 目前狀態

  - 回應組應用程式和通話駐留應用程式

  - Lync Server 控制台、拓撲產生器和規劃工具

  - 當地語系化

  - 著作權

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Lync 2013 用戶端

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>如果檔案已在另一個應用程式中開啟，則在立即訊息中傳輸檔案會失敗。

**問題：**

如果您嘗試將檔案（例如 Word 檔）以立即訊息傳送到另一個 Lync 使用者，則該轉移似乎會成功，但實際上無法傳輸檔案。 該檔案類型的圖示會顯示在 Lync 用戶端中，但目標接收器無法開啟該檔案。 不會顯示錯誤訊息，通知您傳輸未成功。

**解決 方案：**

若要解決此問題，請先關閉開啟的檔案或已開啟的應用程式，再嘗試在立即訊息中傳輸檔案。

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>如果 Lync Server Storage Service 資料複寫失敗，系統管理員將需要檢查陳舊儲存體服務佇列專案的效能計數器

**問題：**

Lync Server Storage Service 使用 Windows Fabric 進行複寫。 如果在主要前端伺服器上刪除資料，但在次要前端伺服器上刪除失敗（例如，如果前端伺服器上有未預期的關機或錯誤），則資料可以留下，而且「孤立」。 孤立資料可能會導致效能降低，並浪費磁片磁碟機空間。

**解決 方案：**

若要解決此問題，如果使用中的事件 LYSS 的 \_ db \_ 空間 \_ \_ 錯誤 (識別碼 = 32058) 和 LYSS \_ DB \_ 空間 \_ \_ 已使用關鍵型 (識別碼 = 32059) 會在事件記錄檔中產生，管理員應該在 **LS： LYSS-storage service API** 中檢查前端伺服器的效能計數器，其名稱為 **LYSS-目前的 storage service 陳舊佇列專案數目**。 如果此效能計數器具有高值（例如大於50000），則系統管理員應該在 Lync Server 2013 資源套件中執行 CleanuUpStorageServiceData.exe 工具，該工具會刪除集區中的所有孤立資料。 如需有關此工具的詳細資訊，請參閱 Lync Server 2013 資源套件檔。

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>每當伺服器或集區的 IP 位址設定變更時，必須重新開機 Lync Server 服務

**問題：**

當 Lync Server 2013 部署的 IP 位址設定變更時（例如，從 IPv4 變更為雙重堆疊，或從雙堆疊變更為 Ipv6），直到重新開機服務之後，所有的伺服器元件才會選取設定變更。

**解決 方案：**

若要解決此問題，請在變更部署的 IP 位址設定後，重新開機 Lync Server 服務。 若要這麼做，請在 Lync Server 管理命令介面中執行下列 Cmdlet：

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>Lync Server 2013 管理元件已無法再使用電話撥入式會議綜合交易 Cmdlet

**問題：**

Lync Server 2013 管理元件已不再提供撥入式會議綜合交易 Cmdlet Cmdlet **Test-CsDialInConferencing** 。

**解決 方案：**

只有在企業內部才支援使用 Dial-In 會議綜合交易 Cmdlet **Test-CsDialInConferencing** 。

管理員可以繼續使用 Lync Server 管理命令介面中的 Cmdlet 進行疑難排解。 如有需要，企業也可以開發私人管理套件，以在內部執行 Cmdlet。

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>當將記錄檔複製到網路共用時，如果網路流量中斷，集中式記錄服務便會停止。

**問題：**

當集中式記錄服務設定成使用網路路徑時 (**Get-CsClsConfiguration** Cmdlet 的 CacheFileNetworkFolder 參數值是有效的 UNC 路徑) 時，會將快取的記錄檔複製到網路共用。 若複製檔案時網路流量中斷，將會發生例外狀況，以導致集中式記錄服務停止。

服務設定為自動重新開機三次，所以服務會從前三個例外狀況復原。

**解決 方案：**

此問題沒有任何解決方法。 若要找出問題，請從「服務控制管理員」監視事件識別碼7031的事件記錄檔，以記錄「Lync Server 集中式記錄服務代理程式」服務意外終止的情況。 如果發生三次以上，請使用 **CsWindowService** Cmdlet 手動重新開機服務。

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>需要手動匯入 Storage Service 佇列專案

**問題：**

Lync Server 2013 儲存有關會議和立即訊息的資料，例如封存的郵件，以及在每一部前端伺服器上的資料庫中 (CDR) 的詳細資料記錄。 在處理資料庫時，會將資料儲存在資料庫中，然後再傳遞至預定的目的地。 為了改善效能，Lync Server 2013 會定期從本機資料庫匯出佇列專案，而這些專案不會在一段時間內處理，並將它們儲存在檔案存放區。 如果檔案存放區無法使用，這些專案會儲存在每一部前端伺服器上。 執行相同的作業，以防止集區容錯移轉時發生資料遺失。

在匯出作業期間，Lync Server Storage Service 會記錄事件記錄中的每個階段，事件 IDs 32075 (完整清除作業已啟動) ，32076 (完全清除已完成) ，32082 (維護層級清理已完成) ，32083 (維護層級清理已完成) ，由於填滿資料庫 (，因此會進行 32089) 的清洗。 此資料將不會自動匯入回系統，以進行處理，並傳遞至其最終目的地 (SQL Server 或 Exchange Server) 。

**解決 方案：**

若要將資料匯入系統，系統管理員必須使用 Lync Server 資源套件中的 ImportStorageServiceData 工具，該工具會將資料送回系統，以進行處理並傳遞至其最終目的地。

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>如果 UseNormalizationRules 的預設值變更為 False，則通訊錄 Web 查詢搜尋會失敗。

**問題：**

如果 UseNormalizationRules 的預設值變更為 False，通訊錄 Web 查詢搜尋會失敗。 預設值變更後，Lync 用戶端使用者將無法使用 Lync 通訊錄 web 查詢來搜尋使用者。

**解決 方案：**

如果 UseNormalizationRules 的預設值設為 False，讓使用者可以使用 Active Directory 網域服務中定義的電話號碼，但不包括 Lync Server 2013。在使用正規化規則時，請執行下列動作來解決此問題：

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列其中一項：
    
      - 如果您的部署只包含 Lync Server 2013 server，請在全域層級執行下列 Cmdlet，將 UseNormalizationRules 和 IgnoreGenericRules 的值變更為 True：
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果您的部署包含 Lync Server 2013 和 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的組合，請執行下列 Cmdlet，並將其指派給拓撲中的每個 Lync Server 2013 集區：
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等待在所有集區上進行 CMS 複寫。

4.  修改您部署的電話正規化規則檔案，以清除內容。 檔位於每個 Lync Server 2013 集區的檔案共用上。 如果檔案不存在，請建立名為 "Company Phone Number 正規化Rules.txt 的空檔案 \_ \_ \_ \_ 。

5.  請等候幾分鐘，讓所有前端集區讀取新的檔案。

6.  在您部署中的每個 Lync Server 2013 集區上執行下列 Cmdlet。
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>針對每個 Lync 2013 集區每天產生一次 Address Book Server 錯誤事件21054

**問題：**

Lync Server 2013 Address Book Server 會在每日執行每日維護時產生錯誤事件21054一次。 每當管理員執行 **update-csaddressbook** Cmdlet 時，即使更新成功，也會產生此錯誤。 不過，當更新成功時，可以安全地忽略此錯誤事件。

**解決 方案：**

當您遇到此錯誤事件時，請執行下列 Cmdlet：

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

如果此 Cmdlet 報告沒有任何未編制索引或已放棄的物件，則可以放心忽略錯誤事件21054。

此外，在 System Center Operations Manager 中應關閉 KHI) 「通訊錄使用者已正確編制索引」的主要健康情況 (指示器。

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>在 Edge 集區上設定 IPv6 時，可能會失敗要求

**問題：**

在 Edge 集區上設定 IPv6 時，某些對 Edge 集區的要求可能會失敗。

**解決 方案：**

若要解決此問題，請不要使用 IPv6 設定 Edge 集區。

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>集區回復時，invoke-csPoolFailback Cmdlet 可能會失敗

**問題：**

嘗試容錯回復集區時， **invoke-csPoolFailback** Cmdlet 可能會失敗，錯誤為「重複嘗試後，無法完成分解處理常式」。」

**解決 方案：**

若要解決此問題，請再次執行 Cmdlet，然後等到 Cmdlet 成功為止。 請注意，容錯移轉程式可能需要數分鐘才能完成。 在有20000使用者的集區中，可能需要長達60分鐘。

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>當您將前端伺服器新增至已建立的集區時，可能會發生資料遺失-混合式、商務用 Skype Online

**問題：**

在集區有多部前端伺服器的環境中，您可能會遇到此問題，您必須重新開機其中一部前端伺服器，或是新增先前沒有集區的前端伺服器。

資料封存的使用者可能會發生資料遺失，直到為集區建立資料封存的穩定散佈。 此週期的潛在資料遺失限制為15分鐘供人員對人員交談，而30分鐘用於會議。

**解決 方案：**

當您執行維護時，您應該將集區容錯移轉至另一個集區，然後在伺服器上執行維護工作，而不是將集區容錯移轉到另一個集區。 您也可以在執行維護工作之前將服務變為不可用，然後在維護完成時還原可用性。

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>管理員無法使用 Get-CsClientAccessLicense Cmdlet 取得獲許可人計數

**問題：**

管理員無法使用 **Get-CsClientAccessLicense** Cmdlet 取得正確的用戶端授權用法。

**解決 方案：**

若要檢查伺服器授權類型，您可以執行 **Get-CsService** Cmdlet，以 (所有資料庫的 FDQNs) 中取得完整功能變數名稱。 如果前端伺服器的 FQDN 與後端資料庫的 FQDN 相同，則授權為 Standard edition 授權。 否則，授權是 Enterprise edition 授權。

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>未正確報告用戶端獲許可人計數

**問題：**

決定用戶端授權計數時，您可能會遇到下列情況：

1.  **行動使用者的不正確授權計數**
    
    授權計數是以裝置型使用者的唯一 IP 位址數目為基礎。 授權數目會以下列方式限制：
    
      - 如果使用者的 IP 位址在 Lync 會話期間變更，將會 overcounted 授權。 當使用者使用桌面用戶端從多個位置連接至 Lync Server 時，可能會發生這種情況。
    
      - 若使用者與行動用戶端進行連線，將會低估授權，因為無法判斷裝置的 IP 位址。

2.  **針對公用交換電話網路 (PSTN) 呼叫 Lync 用戶端、Lync 用戶端通話至 PSTN 線路，以及轉接至 PSTN 線路的 Lync 來電，計算兩次的授權**
    
    在下列案例中，會同時計算兩個額外的授權，而不是一個授權，因為電話號碼和 Lync 使用者都會進行計算，以決定所使用的授權數目。 若要取得正確的授權資料，請手動移除電話號碼所產生的授權。
    
      - 對 Lync 的 PSTN 通話
    
      - 對 PSTN 線路的 Lync 通話
    
      - 對 Lync 的 PSTN 通話，然後 Lync 會將通話轉寄至 PSTN 線路。 其中一條 PSTN 線會計算在內。

3.  **不會計算已登入之 Lync phone 的授權**
    
    當使用者使用 Lync 認證的電話時，如果電話登入並保持連線，這會保留其登入狀態，如果在電話登入後發生授權的查詢，則不會將電話計為使用授權。

4.  **針對加入會議的 PSTN 電話所計算的授權**
    
    當使用者加入使用 PSTN 電話的會議時，會不准確地計算授權加入會議。 不過，使用 PSTN 電話加入會議時，不需要授權。

**解決 方案：**

1.  **行動使用者的不正確授權計數**
    
      - 您可以手動識別屬於相同裝置的 IP 位址，然後在許可證計數中移除其中一個。
    
      - 使用 Lync 用戶端連線的行動裝置，無法解決此問題。

2.  **對 Lync 用戶端、Lync 用戶端撥打到 PSTN 線路的 PSTN 呼叫進行兩次的授權，以及轉接至 PSTN 線路的 Lync 來電。**
    
    您將需要手動識別 PSTN 電話號碼，並移除其所產生的授權計數。

3.  **登入的 Lync phone 不會計算授權**
    
    您可以設定 Lync phone 登出，然後定期登入（如每三個月）。

4.  **針對加入會議的 PSTN 電話所計算的授權**
    
    您可以手動識別用來加入會議的 PSTN 電話號碼，並移除電話號碼所產生的授權。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>在升級至 Silverlight 5 後，Lync Server 控制台在 VMware 環境中停止運作

**問題：**

如果您使用 VMware 環境中的 Lync Server 控制台，當您將 Microsoft Silverlight 升級為第5版之後，Lync Server 控制台可能會停止運作。

**解決 方案：**

若要解決此問題，請執行下列其中一個動作：

  - 卸載 Silverlight 5，然後從安裝 Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) 。

  - 從非 VMware 虛擬電腦的電腦存取 Lync Server 控制台。
    
    若要這麼做，您可以從伺服器上的 Windows [ **開始** ] 功能表啟動 Lync server 控制台（如果電腦上已安裝 lync Server 系統管理工具）。
    
    您也可以使用網頁瀏覽器來存取 Lync Server 控制台。 URL 會類似 HTTPs:// \<frontend\_pool\_fqdn\> /cscp。

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>在 Active Directory 中修改使用者的辨識名稱後，通訊錄服務中的使用者資訊未更新

**問題：**

如果使用者的辨識名稱 (也稱為 DN) 在 Active Directory 網域服務中已變更，則任何額外的變更將不會更新于通訊錄服務 (ABS) 。 這不會影響使用者的登入或顯示狀態，但是如果 SIP 位址也會變更，則會防止使用者進行通訊，因為搜尋會傳回過期的 SIP 位址。

**解決 方案：**

若要解決此問題，請不要變更使用者的 DN。 如果您將使用者的 DN 還原為上一個值，更新將會反映在通訊錄服務中。

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>安裝

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>使用非 ASCII 字元可能會導致 Lync server 啟動失敗

**問題：**

若目的地資料夾名稱包含非 ASCII 字元 (包括 UNICODE、雙位元組字元集 (DBCS) 、UTF-8 及 UTF-16) ，安裝程式將會失敗。 此外，安裝程式可能會成功，但是如果有下列任何一種非 ASCII 字元，則伺服器不會啟動：

  - 電腦名稱

  - 網域名稱

  - 使用者名稱

  - 使用者 SIP URI

  - 服務帳戶名稱

**解決 方案：**

使用目的資料夾名稱、電腦名稱稱、功能變數名稱、使用者名稱、使用者 SIP URI 及服務帳戶名稱中的 ASCII 字元。

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>在安裝 Lync Server 2013 之前必須安裝模組呼叫 IIS 7.5 中的 InsertEntityBody 方法時，就會發生「堆損毀」的修復程式。

**問題：**

當 module 7.5 InsertEntityBody 呼叫在 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) 安裝 Lync Server 2013 之前，必須先安裝 Microsoft 知識庫文章 264886 () 中所述的「 () 的「堆損毀」的修復程式，才會發生堆損毀。

**解決 方案：**

從 Microsoft 下載中心下載並安裝修複程式 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) 。

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 無法在 ITA Windows Server 2012 作業系統 RTM 版本上安裝

**問題：**

由於 Windows Fabric 安裝失敗，所以 Lync Server 2013 在 ITA Windows Server 2012 上安裝失敗。

Windows Fabric 安裝失敗，因為會以 HH： MM： SS 的時間格式建立 Fabric 追蹤。 不過，在 ITA Windows Server 中，時間格式為 HH。MM.SS。

**解決 方案：**

若要解決此問題，請在安裝 Lync Server 2013 之前，先更新系統登錄。 需要更新的登錄機碼是： HKEY \_ 使用者 \\ 。預設 \\ 控制台 \\ 國際化 \\ sTimeFormat。 使用 Windows PowerShell 命令列介面，將 sTimeFormat 的值變更為 HH： mm： ss，如下所示：

1.  啟動 Windows PowerShell，並執行下列 Cmdlet：
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  若要查看目前的值，請執行下列 Cmdlet：
    
        Get-itemproperty $a -Name sTimeFormat
    
    記下 sTimeFormat 的目前值，以便在安裝完成後能夠進行還原。

3.  若要設定為新值，請執行下列 Cmdlet：
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  成功安裝 Lync Server 2013 之後，請執行下列 Cmdlet 來還原 sTimeFormat 的原始值：
    
        - Set-ItemProperty $a 名稱 sTimeFormat-值「步驟3中所述 <的值。 以上> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>行動性

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>在伺服器容錯移轉過程中行動用戶端的問題

**問題：**

當 Lync 伺服器失敗，且容錯移轉程式開始時，下列問題可能會影響行動用戶端使用者：

  - 容錯移轉開始之後，不會有最多10分鐘的傳入 Lync 通話或信號。

  - 無法接受傳入的交談要求

  - 如果失敗的伺服器是使用者的主伺服器，就無法加入會議

**解決 方案：**

此問題沒有任何解決方法。 容錯移轉程式完成後，就會還原正常功能。

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>如果行動使用者拒絕來自其他 Lync 端點的來電，則此呼叫會在 Lync Mobile 用戶端上顯示為未接轉換

**問題：**

如果行動使用者拒絕來電，且呼叫來自其他 Lync 端點，則此呼叫會顯示為 Lync Mobile 用戶端中未接的交談，而不是在 [裝置呼叫] 清單中通話。

**解決 方案：**

此問題沒有任何解決方法。

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>行動用戶端在搜尋連絡人時，可能不會顯示同盟連絡人的顯示名稱

**問題：**

同盟連絡人的顯示名稱可能不會顯示在某些案例中，例如在連絡人清單中搜尋同盟連絡人時。 當 Lync mobile 用戶端的連絡人沒有任何作用中的目前狀態訂閱時，可能會發生這種情況。

**解決 方案：**

此問題沒有任何解決方法。

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>在行動用戶端中，未接來電（即會議邀請）的被邀請者和時間戳記資訊缺失

**問題：**

在行動用戶端中，當錯過交談是邀請參加會議時，未接的交談郵件中遺漏了被邀請者和時間戳記資訊。

**解決 方案：**

此問題沒有任何解決方法。

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>使用 VoIP 進行通話的行動用戶端使用者無法留下語音信箱給其語音信箱已設定在 Exchange 2010 或更早版本中的使用者

**問題：**

若行動用戶端使用者正在使用 VoIP 進行通話，則使用者將無法為設定為使用 Microsoft Exchange Server 2007 或 Microsoft Exchange Server 2010 中的語音信箱的使用者留下語音信箱訊息。

**解決 方案：**

若要解決此問題，請將 Exchange 2010 與 SP1 或更新版本的 Microsoft Exchange Server 搭配使用。

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>在行動用戶端上使用 Block 搭配用戶端版本設定的 URL 時，可能會顯示不正確的錯誤訊息

**問題：**

在行動用戶端上使用 Block 搭配用戶端版本設定的 **URL** 時，當用戶端版本不受支援時，可能會顯示不正確的錯誤訊息。

**解決 方案：**

若要解決此問題，請將 Client Version Configuration 設定**Block**為使用區塊 **，** 而不是使用 URL 的 block。

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>會議

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>在 Lync Server 2013 前端伺服器上執行的防毒軟體可能會造成應用程式網域回收，這會暫時中斷 Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013 用戶端的服務

**問題：**

防毒軟體可能會觸發應用程式網域重新開機，這可能會導致 Lync Mobile Service 2013 和整合通訊 (UC) 網頁 API 用戶端應用程式 (Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013) 以失去其狀態。

**解決 方案：**

若要解決此問題，請從防病毒掃描中排除包含網頁元件及 .NET framework 的資料夾。 如需詳細資訊，請參閱 Microsoft 知識庫文章312592：「PRB：在 ASP.NET 中重新開機應用程式的隨機應用程式」錯誤，「at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) 。

應該排除下列資料夾：

  - %ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 元件 \\ Mcx \\ Ext

  - %ProgramFiles% \\ Microsoft Lync Server 2013 \\ 網頁元件 \\ Mcx \\ Int

  - %ProgramFiles% \\ Microsoft Lync Server 2013 \\ 網頁元件 \\ Ucwa \\ Int

  - %ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 元件 \\ Ucwa \\ Ext

  - % Windir% \\ Microsoft.NET \\ Framework64 \\ v 4.0.30319 \\ Config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>必須在 Windows Internet Explorer 中啟用 ActiveX 控制項或原生 XMLHTTP 支援，才能成功加入會議

**問題：**

如果使用者在 Windows Internet Explorer Internet browser 設定中同時停用 ActiveX 控制項和原生 XMLHTTP 支援，當已選取 [Internet Explorer] 做為預設瀏覽器時，使用者將無法加入會議。

**解決 方案：**

在 Internet Explorer 中啟用 ActiveX 控制項或「原生 XMLHTTP 支援」。

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Lync Server Web 會議服務無法從重要模式復原

**問題：**

如果已開啟關鍵模式進行封存，則在發生系統失敗時，將會啟動重要模式，並且會議將不再為參與者運作。 在管理員修正系統失敗 (例如修復資料庫問題時) ，[資料會議服務] 不會自動復原，而且系統管理員必須手動重新開機會議服務才能繼續會議。

**解決 方案：**

系統管理員需要在修復系統失敗後，手動重新開機會議服務。

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Web 會議服務會忽略外部 Office Web App 伺服器的 HTTP proxy

**問題：**

如果您已將 Office Web Apps Server 部署在 Web 會議服務外 (也就是說，Internet、周邊網路和 Web 會議服務中不是內部公司網路) 中的伺服器，則 Office Web Apps Server 探索將會失敗。 Web 會議服務會忽略 HTTP proxy 設定，如 Office Web Apps Server 安裝程式的拓撲產生器所定義。 因此，Lync 用戶端將無法與會議中的其他參與者共用 Microsoft PowerPoint 2010。 如果您要在內部網路安裝 Lync Server，並在內部網路中設定 Office Web Apps Server 內部部署，則不需要 proxy 設定。

**解決 方案：**

唯一的解決方法是不需要使用 HTTP proxy 來與外部 Office Web Apps Server 通訊的部署設定。

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>不支援將影片加入音訊會議提供者會議

**問題：**

如果使用者加入音訊的音訊會議提供者會議，則不支援新增影片。

**解決 方案：**

此問題沒有任何解決方法。

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>啟用 IPv6 的拓撲會強制 Lync Web App Silverlight 外掛程式自動更新，以確保螢幕共用功能可從 Lync Web App 運作

**問題：**

當拓撲設定為啟用 IPv6 時，如果已安裝舊版的螢幕共用外掛程式，使用者就無法從 Lync Web App 用戶端共用其畫面。

**解決 方案：**

若要在透過 Lync Web App 加入會議時，強制更新至最新版本的螢幕共用外掛程式，請在下列兩個檔案中，將 **MinSupportedBuildVersion** 的值從 "4.0.7457.0" 修改為 "4.0.7577.380"：

  - %ProgramFiles% \\ Microsoft Lync Server 15 \\ 網頁元件是以 \\ \\ Int \\ 用戶端 \\ 外掛程式送達 \\ReachAppShPluginProperties.xml

  - %ProgramFiles% \\ Microsoft Lync Server 15 網頁元件都無法連線至 \\ \\ 外部的 \\ \\ 用戶端 \\ 外掛程式 \\ReachAppShPluginProperties.xml

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>設定使用者

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>在某些情況下，在設定成使用 IPv4 和 IPv6 雙堆疊的電腦上執行的 Lync 用戶端，可能不支援依賴電腦的 IP 子網（如 E911、媒體旁路、通話許可控制和位置基礎路由）的功能。

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。



</div>

**問題：**

當 Lync 用戶端在已啟用 IPv4 和 IPv6 雙堆疊的電腦上執行，且以 proxy 伺服器的 DNS 解析為基礎時，用戶端可能會使用該電腦的 IPv6 位址登入。 這樣做之後，Lync 用戶端只會支援 IPv6 所支援的功能，但不包括 E911、媒體旁路、通話許可控制和位置基礎路由。

**解決 方案：**

若要解決此問題，請在用戶端電腦上停用 IPv6 支援。

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>如果沒有為使用者設定 Enterprise Voice，使用者將需要使用 E164 格式從會議撥出

**問題：**

如果使用者未設定 Enterprise Voice，該使用者將需要使用 E164 格式才能從會議中成功撥出。 若未使用 E164 格式，則使用者將無法從會議撥出。

**解決 方案：**

若要解決此問題，未啟用 Enterprise Voice 的使用者，應使用 E164 格式的數位來撥出會議。

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>目前狀態

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>如果使用者在開啟統一連絡人存放區時已選取「封鎖所有邀請和通訊」，則不會拒絕目前狀態，應為

**問題：**

如果使用者已選取「封鎖所有邀請與通訊」，當統一連絡人存放區開啟時，就不會拒絕其狀態。

**解決 方案：**

若要解決此問題，您可以關閉使用者的整合連絡人存放區。 若要這麼做，請執行下列 Cmdlet：

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

例如：

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office 通訊伺服器 2007 R2 使用者在內部部署中無法看到混合式部署中商務用 Skype Online 使用者的目前狀態-混合式

**問題：**

當您使用 Lync Server 2013 Director 時，可能會在混合部署中發生此問題。

屬於內部部署使用者的目前狀態為「商務用 Skype Online」之使用者的狀態為「未知」。 此外，位於商務用 Skype Online 的使用者無法查看 Office 通訊伺服器 R2 內部部署使用者的狀態。

**解決 方案：**

若要解決此問題，請將商務用 Skype Online 使用者的「家用伺服器」 (系-presencehomeserver) 變更為指向 Lync Server 2013 內部部署集區，而不是 Lync Server 2013 Director。 您可以在內部部署前端伺服器上修改此設定。

此解決方法會正確顯示位於 Office 通訊伺服器 2007 R2 的使用者目前狀態，以供商務用 Skype Online 使用者。

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>回應群組應用程式、通話駐留應用程式和群組呼叫收取

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>來電者使用「檢索方」建立通話期間，來電者可能會聽到一秒的等待音樂。

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。



</div>

**問題：**

透過群組呼叫收取通話時，來電者可能會在使用檢索程式建立通話時，聽到一秒的等待音樂。

**解決 方案：**

此問題沒有任何解決方法。

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>回應群組代理程式只能透過 Lync Server 2010 Agent 主控台登入並登出，以僅限 Lync Server 2010 正式代理群組

**問題：**

Lync Server 2013 回應群組代理程式只能透過 Lync Server 2010 代理程式主控台登入並登出，以供 Lync Server 2010 正式代理群組。 在 Lync Server 2010 Agent 主控台中，使用者只能看到他們所屬的 Lync Server 2010 回應群組。 他們無法看到任何屬於的 Lync Server 2013 回應群組。

**解決 方案：**

若回應群組代理程式是 Lync Server 2013 使用者，以及 Lync Server 2013 正式代理群組的一部分，使用者必須透過瀏覽器中的網路連結直接存取 Lync Server 2013 代理程式主控台，以登入並登出 Lync Server 2013 Agent 群組。

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Lync Server 2010 回應群組代理程式無法代表 Lync Server 2013 回應群組進行呼叫

**問題：**

Lync server 2010 使用者是 Lync Server 2013 回應群組的代理人，無法代表回應群組撥打電話。 Lync Server 2013 回應群組將無法在 Lync 用戶端中使用，以進行呼叫。

**解決 方案：**

若要解決此問題，您必須將 Lync Server 2010 使用者移至 Lync Server 2013。

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>從 Lync Server 2010 遷移至 Lync Server 2013 之後移除回應群組，將會使回應群組無法接受任何來電

**問題：**

如果已從 Lync server 2010 遷移至 Lync Server 2013 的回應群組是透過 Lync Server 控制台或 Lync Server 管理命令介面從 Lync server 2010 中移除，則 Lync Server 2013 中的回應群組會停止接收任何來電。

**解決 方案：**

若要解決此問題，請勿移除從 Lync server 2010 遷移至 Lync Server 2013 之 Lync Server 2010 的任何回應群組。

若回應群組已移除，您應該在 Lync Server 2013 中重新部署它。

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>當新的受管理工作流程在建立時設定為非使用中時，工作流程的部署會失敗

**問題：**

當新的受管理工作流程在建立時設定為非使用中時，工作流程的部署會失敗。 當工作流程在建立時設定為非使用中時，就會發生此問題，但不會影響已編輯的工作流程，以在部署後將其設定為非使用中。

**解決 方案：**

建立及部署工作流程時，請將工作流程設定為使用中，然後加以部署。 成功部署工作流程之後，即可編輯工作流程，並將其設為非使用中狀態。

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>若回應群組已匯入到備份組區，則從擁有者集區移除回應群組將會防止備份組區的回應群組接受任何來電時接受所有來電。

**問題：**

如果主要集區所擁有的回應群組已匯入到備份組區，但未覆寫擁有者，且回應群組已從擁有者集區中移除，則備份組區中的回應群組將不會接受容錯移轉期間的任何來電。

**解決 方案：**

您將需要在主要集區中重新部署回應群組。 然後，您必須從主要集區中匯出回應群組設定，並重新將它匯入至備份組區。

您也可以在備份組區中重新建立回應群組。 在此情況下，備份組區將是回應群組的擁有者集區。

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>如果代表回應群組執行取回要求，則無法從通話駐留應用程式中檢索寄存通話

**問題：**

當下列條件為 true 時，對寄存通話的檢索要求會失敗：

  - 代理程式屬於匿名回應群組

  - 代理程式會嘗試透過匿名回應群組來從通話駐留應用程式取得寄存的呼叫。

  - 工程師會嘗試透過 [代表來電] 選項或透過 Lync 語音應答用戶端中的相同選項，撥打軌道號碼，以取回通話。

**解決 方案：**

此問題沒有任何解決方法。 停用呼叫應以無回應群組的方式，加以取回。

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Lync Server 控制台、拓撲產生器和規劃工具

<div>

## <a name="planning-tool-limitations"></a>規劃工具限制

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。



</div>

**問題：**

規劃部署時，規劃工具具有下列限制：

  - 最多可支援10個中央網站

  - 每個中央網站最多可以有14個分支網站

  - 每個中央網站最多可以有240000位使用者

此外，在計算建議的拓撲時，規劃工具並未包含下列值：

  - 線上中的使用者人數

  - 啟用 XMPP 同盟的使用者百分比

  - 使用 Lync Web App 的使用者百分比

**解決 方案：**

這些問題沒有任何解決方法。 如需規劃工具的相關資訊，請參閱 [使用規劃工具設計 Lync Server 2013 的拓撲](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)。

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>在更新選項時，規劃工具可能不會對 Edge 網路使用先前定義的 IP 位址

**問題：**

使用規劃工具完成設計後，如果您對 Edge 網路選項進行變更，則其他的 IP 位址可能會新增至設計，而不是更新現有的 IP 位址。 當您查看 Edge Network 圖表的詳細資料時，可能會發生這種情況，請選取 [ **按一下這裡以更新您的選項**]，然後在 [設定選項] 對話方塊中選取 [edge 網路]。 **我想要使用相同的 fqdn 和 IP 位址，但在 edge Server 上使用 edge service 的不同埠**。 套用任何變更可能會導致新的 IP 位址和 Edge server 新增到設計中。

**解決 方案：**

目前尚無此問題的解決方法。

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>在 [Lync Server 控制台] 中，[將所有使用者移至集區] 可能無法如預期般運作

**問題：**

使用 Lync Server 控制台將所有使用者從一個集區移至複雜的 Active Directory 環境中的另一個集區時（例如有多個網域控制站和父/子系網域的一個集區），可能會傳回錯誤訊息：「指定的使用者不是舊版使用者，請改用 Move-CsUser Cmdlet」。 這是在複雜的 Active Directory 環境中較長時間複寫的結果。

**解決 方案：**

若要解決此問題，請執行下列其中一個動作：

  - 使用 Lync Server 控制台中的篩選器來搜尋舊版使用者，請選取這些使用者，然後使用 [ **將選取的使用者移至集** 區] 命令，而不是 **將所有使用者移至集**區。

  - 使用 Lync Server 管理命令介面，透過 Lync Server Cmdlet 以批次移動舊版使用者。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>在 Microsoft Silverlight 瀏覽器外掛程式更新為第5版之後，Lync Server 控制台會在 VMware 環境中停止運作

**問題：**

如果您使用 VMware 環境中的 Lync Server 控制台，當您將 Silverlight 升級為第5版之後，Lync Server 控制台可能會停止運作。

**解決 方案：**

若要解決此問題，請執行下列其中一個動作：

  - 卸載 Silverlight 5，然後從安裝 Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) 。

  - 從非 VMware 虛擬電腦的電腦上，開啟 Lync Server [控制台]。
    
    若要從遠端電腦開啟 Lync Server 控制台，請在電腦上安裝 Lync Server 系統管理工具，然後從 Windows [ **開始** ] 功能表啟動 lync Server [控制台]。
    
    您也可以在網頁瀏覽器中輸入 URL，以開啟 Lync Server [控制台]。 URL 會類似 HTTPs:// \<frontend\_pool\_fqdn\> /cscp。

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>在拓撲產生器中移除鏡像資料庫之後，管理員無法執行 Uninstall-csMirrorDB Cmdlet

**問題：**

當系統管理員在拓撲產生器中停用鏡像資料庫，然後刪除拓撲產生器中的鏡像資料庫時，系統會在 [待辦事項] 清單中顯示一則訊息，以執行 **uninstall-csmirrordatabase 指令程式** ，以從 SQL Server 中移除鏡像。 當系統管理員嘗試執行 Cmdlet 時，它會失敗。

**解決 方案：**

若要在拓撲產生器中移除集區的 SQL 鏡像，您必須先使用 Cmdlet 來移除 SQL Server 中的鏡像。 然後您就可以使用拓撲產生器，從拓撲中移除鏡像。 若要在 SQL Server 中移除鏡像，請使用下列 Cmdlet：

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

例如，若要移除使用者資料庫的鏡像並放下資料庫，請輸入下列專案：

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

*DropExistingDatabasesOnMirror*參數會從鏡像中刪除受影響的資料庫。 此外，若要從拓撲移除鏡像伺服器，請執行下列動作：

1.  在拓撲產生器中，以滑鼠右鍵按一下集區，再按一下 **[編輯內容]**。

2.  清除 [ **啟用 SQL 存放區鏡像** ]，然後按一下 **[確定]**。

3.  發行拓撲。

<div class="">


> [!IMPORTANT]  
> 當您變更後端資料庫鏡像關係時，必須重新開機集區中的所有前端伺服器。



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>當系統管理員嘗試移除具有相關見證存放區之前端集區的部署時，拓撲產生器會傳回驗證錯誤。

**問題：**

如果系統管理員嘗試使用拓撲產生器中的 [ **移除部署** ] 命令，以移除包含具有相關見證存放區之前端集區的部署，則會在拓撲產生器中顯示驗證錯誤，且不會繼續執行該動作。

**解決 方案：**

若要解決此問題，請執行下列其中一個動作：

  - 在嘗試移除部署之前，請先移除見證存放區。

  - 新增前端集區的見證存放區，然後將其移除。

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>在規劃工具和拓撲產生器之間，Persistent Chat Server 部署資訊不一致

**問題：**

當 Lync Server 2013 （計畫工具）在啟用嚴重損壞修復的情況下，針對 Persistent Chat Server 部署輸出網站拓撲圖表時，網站拓撲圖表會包含多個 (實體) 網站，且每個網站上都有均勻指派的持久聊天伺服器。 在 [拓撲產生器] 中，所有的持久聊天伺服器都代表屬於單一 (邏輯) 網站，而且會列在相同 Persistent Chat Server 集區節點底下。

**解決 方案：**

目前，我們沒有此問題的解決方法。 使用者應分析 Persistent Chat Server 部署規劃工具的輸出，並修改計畫以滿足其特定需求。

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>當地語系化

<div>

## <a name="monitoring"></a>監視

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>使用東亞版的 Lync Server 時，「部署監控報告嚮導會在某些情況下顯示不正確的字元

**問題：**

使用東亞版的 Lync Server 2013 （例如，中文 (簡體) 、中文 (傳統) 、日文或韓文）在系統地區設定未設定為東亞語言的作業系統上，「部署監控報告」嚮導會顯示試題符號或其他字元，而非當地語系化的郵件。

**解決 方案：**

若要修正此問題，請將作業系統和 Lync Server 2013 的地區設定設定為相同的語言，這樣會正確顯示所有郵件。

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server 控制台

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>在某些情況下，當按一下上方導覽列中的最後一個專案時，[Lync Server 控制台] 頁面上方導覽列中的第一個專案便會消失。

**問題：**

在下列三個已知案例中，按一下 [Lync Server 控制台] 頁面上方導覽列中的最後一個專案會導致上方導覽列中的第一個專案消失：

  - 在法文版的頁面「Féderation et accès externe 上，當按一下「D'accès externe PARTENAIRES」時，會消失專案 "Stratégie fédérés XMPP"。

  - 在德文版本的「用戶端」頁面上，按一下 "Pushbenachrichtigungskonfiguration" 時，專案 "Clientversionskonfiguration" 會消失。

  - 在 [Конфигурациясети] 頁面上的俄語版本中，當按一下 "на" 時，專案 "Глобально" 便會消失。

**解決 方案：**

若要解決此問題，請在瀏覽器中重新整理 Lync Server 控制台的頁面。 頁面將會在瀏覽器中載入，並顯示上方導覽列中的所有專案。

</div>

</div>

<div>

## <a name="address-book"></a>通訊錄

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>在 [通訊錄] 中的索引在某些語言中未如預期的方式運作

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。



</div>

如果使用者的屬性包含索引欄位，而該欄位只包含無法索引的字元，則使用者不會出現在通訊錄中的搜尋中。

下列字元及地區設定無法進行索引：

  - 小寫的西瑞爾文、希臘字母和亞美尼亞文字元

  - 大寫字母的重音符號

  - 泰文

  - 寮文

  - 緬甸

  - 梵文

  - 衣索比亞文

  - 西藏文

  - 孟加拉文

  - 古吉拉特文

  - 特拉古文

  - 所有其他印度文腳本

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App、Web 排程程式和 Web 元件

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Lync Web 排程器中某些語言的語言回退、Dial-In、加入啟動器、持續聊天室管理，以及 OCTab 可能無法如預期般運作

**問題：**

在 Internet Explorer 中的網頁瀏覽器中選取中立地區設定時，請 (例如，沒有進一步規範的語言名稱，例如 "挪威 \[ no \] " ) ，而不是指定語言、腳本及地區設定 (（例如 "挪威，博克瑪律文 (挪威) \[ nb-NO \] "） ) 可能會導致 Lync web 排程器、Dial-In、加入啟動器、持續聊天室管理及 OCTab 的特定語言的非預期顯示行為。 例如，當選取下列其中一種語言時，使用者可能會看到英文頁面：

  - 挪威文

  - 葡萄牙文

  - 塞爾維亞文

**解決 方案：**

如果您想要選取具有中立地區設定的語言，請務必確定您也可以使用特定地區設定來新增語言， (搭配 script 和/或國家/地區代碼) 做為瀏覽器的語言喜好設定清單中的其他語言。

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>在某些網頁瀏覽器中使用 Lync Web 排程器、Dial-In、加入啟動器、持續聊天室管理和 OCTab 時，對亞塞拜然和烏茲別克地區設定的支援有限

<div class="">


> [!NOTE]  
> 本節中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。



</div>

**問題：**

當您使用 Internet Explorer 8 或 Internet Explorer 9，並將瀏覽器語言設定為阿塞 (拉丁) 或烏茲別克 (拉丁) 時，撥號對應程式頁面會以英文或瀏覽器中設定的慣用語言顯示。

當您使用 Firefox 或 Chrome 瀏覽器，並將瀏覽器語言設定為阿塞 (拉丁) 或烏茲別克 (拉丁) 時，Lync Web App、Lync Web 排程程式和 RGS OCTab 將會以英文或瀏覽器的慣用語言集顯示。

在 Safari 瀏覽器中，不支援烏茲別克 (拉丁) 地區設定。

**解決 方案：**

這些問題沒有解決方法。

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>在 Lync Web App 的羅馬尼亞語版本中，「加入會議」清單的下拉式箭頭遺失

**問題：**

當使用 Lync Web App 的羅馬尼亞版本的使用者執行下列步驟時，下拉式清單中不會顯示 [ **加入會議** ] 下拉式箭頭：

1.  在 [**一般**] 索引標籤上，選取 [**在這部電腦**上記錄]。

2.  選取 [ **電話** ] 索引標籤。

3.  按一下 [ **加入會議**] 的下拉式清單。
    
    使用者看不到指出其選項超過預設 **Lync Web App**的箭號，其包括：請勿在羅馬尼亞文中 **加入音訊** (，"Nu se asociaža la componenta 音訊" ) and **New number**" (文中的" Număr nou ") 。

**解決 方案：**

即使此下拉式清單的箭號並未顯示出來，使用者仍可按一下預設值，在清單中選取其他設定。

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>使用土耳其文版本的 Lync Web 排程器時，當使用「誰是簡報者」下的「我選擇」選項時，無法儲存會議。

**問題：**

在土耳其文版本的 Lync Web 排程程式中建立或編輯會議時，不支援 [誰是簡報者] 底下的 [人員我選擇] 選項。 選取此選項時，無法儲存會議。 相反地，會出現錯誤訊息，指出無法將一個或多個人員設為簡報者。

**解決 方案：**

若要解決此問題，使用者可以使用「我的公司人員」的預設選項，或任何其他選項，例如「只有召集人」或「所有人（包括公司以外的人員）」）。 召集人可以在使用者加入會議之後，將其降級或將其提升為正確的角色。

或者，瞭解其他語言的使用者可以將其瀏覽器中的語言選擇變更為其他43支援的語言，並嘗試使用「人員選擇」選項。

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>著作權

這份檔支援軟體產品的初步發行，該產品可能會在最終發行版本本之前變更，而且是 Microsoft Corporation 的機密和專有資訊。 它會依照收件者和 Microsoft 之間的保密合約條款披露。 本檔僅供提供資訊之用，但 Microsoft 對本檔中的任何明示或默示的保證都沒有任何擔保。 本檔中的資訊（包括 URL 及其他網際網路網站參考）如有變更恕不另行通知。 使用此檔帶來的全部風險，或因使用此檔所產生的結果，都由使用者自行保留。 除非另有說明，否則本文範例中所描述的公司、組織、產品、功能變數名稱、電子郵件地址、徽標、人員、地點和事件皆為虛構。 與任何真實的公司、組織、產品、功能變數名稱、電子郵件地址、標誌、人員、地點或事件都沒有任何關聯或應加以推斷。 遵守所有適用著作權法律為使用者的責任。 除著作權之下的權利外，未獲 Microsoft Corporation 明確的書面許可，本文件任何部分均不得複製、儲存或引入擷取系統、或以任何形式或藉任何方式 (電子、機械、影印、錄音、或其他) 傳輸，或做為任何用途。

Microsoft 對本文件中主題事務可能擁有專利、專利應用程式、商標、著作權或其他智慧財產權。除非在 Microsoft 的任何書面授權合約中已明確載明，否則提供本文件並未賦予貴用戶對這些專利、商標、著作權或其他智慧財產權的任何授權。

© 2012 Microsoft Corporation。 著作權所有，並保留一切權利。

Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook 和 SQL Server 是 Microsoft Corporation 在美國及（或）其他國家/地區的注冊商標或商標。

所有其他商標為其各自擁有者的商標。

</div>

</div>

<span> </span>

</div>

</div>

</div>

