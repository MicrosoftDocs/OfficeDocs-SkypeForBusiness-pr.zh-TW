---
title: Lync Server 2013：備份和還原需求：資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b9f077e0f9d7c4137844b2cba352b096fdb564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Lync Server 2013 中的備份和還原需求：資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-26_

Lync Server 使用儲存在資料庫中的設定和配置資訊，以及儲存在資料庫和檔案存儲區中的資料。 本主題說明當您的組織遇到失敗或中斷時，您必須備份才能還原服務的資料，也可以識別 Lync Server 所用的資料和元件，您需要分別進行備份。

<div>

## <a name="settings-and-configuration-requirements"></a>設定和配置需求

本主題包含備份和還原 Lync Server 服務復原所需的設定和設定資訊的程式。 配置資訊位於中央管理儲存體或另一份後端資料庫或標準版伺服器上。

下表列出備份及還原所需的設定和設定資訊。

### <a name="settings-and-configuration-data"></a>設定和配置資料

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>資料類型</th>
<th>儲存位置</th>
<th>描述/備份時間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拓撲配置資訊</p></td>
<td><p>中央管理存放區（資料庫： Xds）</p></td>
<td><p>拓撲、原則和設定設定。</p>
<p>使用 [Lync Server 控制台] 或 [Cmdlet] 來修改您的設定或原則，以備份您的一般備份。</p></td>
</tr>
<tr class="even">
<td><p>位置資訊</p></td>
<td><p>中央管理存放區（資料庫： .Lis. .mdf）</p></td>
<td><p>企業語音增強9-1-1 （E9-1-1）配置資訊。 此資訊通常是靜態的。</p>
<p>使用您的一般備份進行備份。</p></td>
</tr>
<tr class="odd">
<td><p>回應群組設定資訊</p></td>
<td><p>後端伺服器或標準版伺服器（database： RgsConfig）</p></td>
<td><p>回應群組代理群組、佇列和工作流程。</p>
<p>在您新增或變更代理群組、佇列或工作流程之後，再使用一般備份進行備份。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>資料需求

以下是您需要備份的 Lync 伺服器資料清單，讓您可以在發生失敗的情況下還原 Lync Server 服務。

請注意，恢復不需要某些類型的資料。 本主題不包含備份這些類型資料的程式，包括下列各項：

  - 暫時的使用者資料，例如端點與訂閱、活動會議服務器及暫時性的會議狀態（database： RtcDyn）

  - 通訊錄資料（資料庫： Rtcab 和 Rtcab1）。 通訊錄資料庫會自動從 Active Directory 網域服務重新產生。

  - 通話駐留應用程式（database： CpsDyn）的動態資訊

  - 暫時回應群組資料，例如 agent 登入狀態及呼叫等待資訊（database： RgsDyn）

  - 持續聊天（database： MgcComp）的相容性資料庫。 如果您已啟用持續性聊天規範，只要您已將配接器設定為讀取資料庫中的資訊，並將其轉換為替代格式，就能讓持續聊天規範資料庫中的資訊成為暫時性的。 因此，持久聊天的合規性資料庫會被視為暫時性的。
    
    Lync Server 2013 持續聊天伺服器隨附 XML 配接器。 您也可以安裝接受此資料的自訂配接器，並將其移至其他來源，例如 Exchange 託管的檔案。

下表列出您需要備份及還原的資料。

### <a name="data-stored-in-databases"></a>儲存在資料庫中的資料

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>資料類型</th>
<th>儲存位置</th>
<th>描述/備份時間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>持久性使用者資料</p></td>
<td><p>後端伺服器或標準版伺服器（database： RTCXDS）</p></td>
<td><p>使用者權利、使用者連絡人清單、伺服器或池資料、排定的會議等。 此使用者資料不包含上傳到會議的內容。</p>
<p>使用您的一般備份進行備份。 這項資訊是動態的，但如果您需要還原到上一個定期備份，則不會對 Lync 伺服器造成更新的災難性影響。 如果連絡人清單對您的組織而言是重要的，您可以更頻繁地備份此資料。</p></td>
</tr>
<tr class="even">
<td><p>存檔資料</p></td>
<td><p>封存資料庫（資料庫： LcsLog）</p>
<p>如果您已啟用 Microsoft Exchange 整合選項，此資料可能會儲存在 Exchange 2013 上。 否則，此資料會保留在 Lync Server 封存資料庫中，這可能會與另一個 Lync Server 資料庫 collocated，或獨立資料庫伺服器上獨立的方式。</p></td>
<td><p>立即訊息（IM）及會議內容。</p>
<p>這種資料對於 Lync Server 並不重要，但對您的組織而言，可能是您組織的重要用途。 據此判斷您的備份排程。</p></td>
</tr>
<tr class="odd">
<td><p>監控資料</p></td>
<td><p>監視資料庫（LcsCDR .mdf 與 QoeMetrics）</p>
<p>這些資料庫可能會與另一個 Lync Server 資料庫 collocated，或獨立資料庫伺服器上獨立的資料庫。</p></td>
<td><p>通話詳細資料記錄（LcsCDR）和體驗品質（QoE）度量（QoeMetrics）。</p>
<p>通話明細記錄是動態的，對您的企業可能是至關重要的。 考慮是否需要這些記錄，以決定您的備份排程。</p>
<p>經驗品質資訊是動態的。 QoE 資料的遺失對於 Lync Server 的運作並不重要，但對您的公司可能是至關重要的。 根據這些資訊對您組織的重要程度，決定您的備份排程。</p></td>
</tr>
<tr class="even">
<td><p>持續聊天資料</p></td>
<td><p>持續聊天資料庫（mgd）。</p>
<p>這個資料庫可能是與另一個 Lync Server 資料庫 collocated，或獨立資料庫伺服器上獨立的資料庫。</p></td>
<td><p>持續聊天資料是在聊天室中張貼的實際聊天內容。 這個資料通常是業務關鍵型的。</p>
<p>您可以選擇使用 SQL Server 備份，或使用 Lync Server 中提供的<strong>Export CsPersistentChatData</strong> Cmdlet 來匯出資料庫。 若要還原資料，您可以將資料庫匯入並還原到最後一次完整備份的位置，這表示您無法將資料庫還原到失敗的位置。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>檔案儲存資料需求

在企業版部署中，Lync Server 檔存放區通常位於檔案伺服器上。 在標準版的部署中，Lync Server 檔案存放區預設位於標準版伺服器上。 通常會有一個 Lync Server 檔案存放區共用給網站。 永久聊天檔案存放區會使用與 Lync Server 檔案存放區相同的檔案共用。

檔案存放位置會識別為\\ \\伺服器\\共用名稱。 若要尋找檔案存放區的特定位置，請開啟 [拓撲建立器]，然後在 [檔案存放**區**] 節點中查看。

下表列出您需要備份及還原的檔案存放區。

### <a name="file-stores"></a>檔案存放區

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>資料類型</th>
<th>儲存位置</th>
<th>描述/備份時間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 檔存放區</p></td>
<td><p>通常是在檔案伺服器、檔案群集或標準版伺服器上</p></td>
<td><p>會議內容、會議內容中繼資料、會議合規性記錄、應用程式資料檔案、裝置更新、音訊檔案（回應群組）、通話駐留及宣告應用程式，以及張貼到持續聊天室中的檔案。</p>
<p>使用您的一般備份進行備份。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>其他備份需求

若要協助確保您在發生失敗時還原 Lync Server 服務的能力，您必須備份不屬於 Lync Server 本身的一些必要元件。 下列元件不會在本檔所述的 Lync Server 備份和還原程式中進行備份或還原：

  - **Active directory 網域服務**   ：您需要在備份 Lync Server 時，同時使用 Active directory 工具備份 AD DS。 請務必將 AD DS 與 Lync Server 保持同步，以避免當 Lync Server 預期與 AD DS 中的連絡人物件不相符時可能會發生的問題。 AD DS 儲存 Lync Server 所使用的下列設定：
    
      - 使用者 SIP URI 和其他使用者設定。
    
      - 針對回應群組和會議助理等應用程式的連絡人物件。
    
      - 指向中央管理存放區的指標。
    
      - Kerberos 驗證帳戶（選擇性電腦物件）和 Lync Server 安全性群組。
    
    如需在 Windows Server 2008 中備份及還原 AD DS 的詳細資料，請參閱「AD DS 備份與復原逐步指南」 [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)。

  - **憑證授權單位和憑證**   使用貴組織的原則來備份您的憑證授權單位（CA）及證書。 如果您使用可匯出的私密金鑰，您可以備份憑證和私密金鑰，如果您使用本檔中的程式來還原 Lync Server，就可以將其匯出。 如果您使用內部 CA，您可以在需要還原 Lync Server 時重新註冊。 請務必將私人金鑰保留在能在電腦出現故障時使用的安全位置。

  - **System Center operations manager**   如果您使用 Microsoft System center operations manager （舊稱 microsoft Operations manager）來監視 lync server 部署，您可以選擇性地備份在監視 lync server 時所建立的資料。 使用您的標準 SQL Server 備份程式來備份 System Center Operations Manager 檔案。 在恢復期間，不會還原這些檔案。

  - **公用交換電話網絡（PSTN）閘道**   設定如果您使用企業語音或 Survivable 分支裝置，則需要備份 PSTN 閘道設定。 如需備份及還原 PSTN 閘道設定的詳細資訊，請參閱您的廠商。

  - **[共存版的 lync server] 或 [office 通訊伺服器**   ] 如果您的 lync server 2013 部署 coexists 使用 lync server 2010 或舊版 Office 通訊伺服器，則無法使用本檔中的程式來備份或還原較舊的版本。 相反地，您必須使用專為舊版版本所記錄的備份和還原程式。 如需備份及還原 Lync Server 2010 的詳細資訊， [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417)請參閱。 如需備份及還原 Microsoft Office 通訊伺服器 2007 R2 的詳細資料， [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)請參閱。

  - **基礎結構資訊**   您需要備份基礎結構的相關資訊，例如防火牆設定、負載平衡設定、網際網路資訊服務（IIS）設定、網域名稱系統（DNS）記錄和 IP 位址，以及動態主機設定通訊協定（DHCP）設定。 如需有關備份這些元件的詳細資訊，請諮詢其各自的供應商。

  - **Microsoft exchange 與 exchange 整合訊息（UM）**   備份及還原 microsoft exchange 與 exchange UM，如 microsoft exchange 檔中所述。 如需備份及還原 Exchange Server 2013 的詳細資訊， [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)請參閱。 如需備份及還原 Exchange Server 2010 的詳細資訊， [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)請參閱。
    
    請注意，Lync Server 2013 引入了將使用者連絡人清單、高清晰度使用者相片和歸檔資料儲存在 Exchange 2013 中的功能。 請參閱下列清單，以瞭解如何備份這些類型的資料：
    
      - **高清晰度相片**是作為 Exchange Server 備份的一部分進行備份。
    
      - [Lync Server 2013] 中引入了 [**整合連絡人存放區**]。 「整合連絡人存放區」可讓使用者在 Exchange 2013 中保留所有連絡人資訊。
        
        您應該確定針對使用者的使用者連絡人是儲存在整合式連絡人存放區中，還是儲存在 Lync 後端伺服器上，才能讓備份保持在最新狀態。 下列案例說明將使用者連絡人遷移至 [整合連絡人] 存放區的位置，可能會導致備份和還原程式發生問題。
        
        **案例1：** 使用者連絡人會遷移至 [整合] 連絡人存放區，然後從遷移使用者連絡人之前所進行的 Lync Server 備份執行還原。 在這種情況下，使用者會將過時的連絡人狀態保持在一天，直到 Lync Server 遷移任務開始將使用者連絡人遷移到 Exchange。 （請注意，因為使用者連絡人先前已遷移至 [整合連絡人] 存放區，則會使用 Exchange 連絡人資訊）。 在這種情況下，不需要系統管理員干預。
        
        **案例2：** 使用者連絡人先前儲存在 [整合連絡人] 存放區中，但接著是 [回退]。 當使用者連絡人儲存在「整合連絡人存放區」時，就會從 Lync Server 備份執行還原。 在這種情況下，用戶端`Error: Incorrect Exchange Version`或 Lyss 伺服器記錄中的錯誤訊息可能會指出這是問題。 使用者將能夠直接從 Exchange 存取 Lync 2013 中的連絡人清單，但用戶端的狀態不會與 Lync Server 狀態相符。 若要修正此問題，管理員將需要針對受影響的使用者執行**CsUCSRollback** Cmdlet。
    
      - **存檔資料**可以儲存在 Exchange 2013 中。 這種資料對於 Lync Server 並不重要，但對您的組織而言，可能是您組織的重要用途。 如果封存資料是儲存在 Exchange 中，對您的組織而言是重要的，請依照 Exchange 備份和還原程式。 請注意，儲存在 Exchange 中的歸檔資料不能移回 Lync Server。 此外，也無法將已儲存在 Lync 封存資料庫中的資料移到 Exchange。

</div>

</div>

<span> </span>

</div>

</div>

</div>

