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
ms.openlocfilehash: 8431e16e976f0ad189205f0c42c04d50e6936e90
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527040"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Lync Server 2013 中的備份和還原需求：資料

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-26_

Lync Server 會使用儲存在資料庫中的設定和設定資訊，以及儲存在資料庫和檔案存放區中的資料。 本主題說明當您的組織遇到故障或中斷時，需要備份以還原服務的資料，也會識別您需要個別備份之 Lync Server 所使用的資料和元件。

<div>

## <a name="settings-and-configuration-requirements"></a>設定和設定需求

本主題包含備份及還原 Lync Server 服務的修復所需設定和設定資訊的程式。 設定資訊位於中央管理存放區，或在其他後端資料庫或 Standard Edition server 上。

下表列出備份與還原所需的設定和設定資訊。

### <a name="settings-and-configuration-data"></a>設定和設定資料

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
<th>Description/備份時間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>拓撲設定資訊</p></td>
<td><p>中央管理存放區 (資料庫： Xds) </p></td>
<td><p>拓撲、原則及設定設定。</p>
<p>使用 Lync Server 控制台或 Cmdlet 修改您的設定或原則，以備份一般備份。</p></td>
</tr>
<tr class="even">
<td><p>位置資訊</p></td>
<td><p>中央管理存放區 (資料庫： .Lis) </p></td>
<td><p>Enterprise Voice 增強型 9-1-1 (E9-1-1) 設定資訊。 這種資訊通常是靜態的。</p>
<p>以定期備份備份。</p></td>
</tr>
<tr class="odd">
<td><p>回應群組設定資訊</p></td>
<td><p>後端伺服器或 Standard Edition Server (資料庫： RgsConfig.mdf) </p></td>
<td><p>回應群組代理程式群組、佇列和工作流程。</p>
<p>在您新增或變更代理人群組、佇列或工作流程之後，再備份一般備份。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>資料需求

以下是您需要備份之 Lync Server 資料的清單，讓您在失敗的情況您可以還原 Lync Server 服務。

請注意，修復不需要某些類型的資料。 本主題不包含備份這些類型資料的程式，包括下列各項：

  - 暫態使用者資料，例如端點和訂閱、使用中會議服務器及暫時性會議狀態 (資料庫： RtcDyn.mdf) 

  - 通訊錄資料 (資料庫： Rtcab 及 Rtcab1.mdf) 。 通訊錄資料庫會自動從 Active Directory 網域服務重新產生。

  - 通話駐留應用程式 (資料庫的動態資訊： CpsDyn.mdf) 

  - 暫時性的回應群組資料，例如 agent 登入狀態及通話等候資訊 (資料庫： RgsDyn.mdf) 

  - Persistent Chat (資料庫： MgcComp) 的規範資料庫。 如果您已啟用持續性聊天規範，只要您已設定配接器來讀取資料庫中的資訊，並將其轉換成替代格式，則 Persistent Chat 規範資料庫中的資訊就是暫時性的。 因此，持久聊天的規範資料庫被視為暫時性。
    
    Lync Server 2013 Persistent Chat Server 隨附有 XML 介面卡。 您也可以安裝採用此資料的自訂配接器，並將其移至其他來源（例如 Exchange 主控的封存）。

下表列出備份與還原所需的資料。

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
<th>Description/備份時間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Persistent 使用者資料</p></td>
<td><p>後端伺服器或 Standard Edition Server (資料庫： RTCXDS) </p></td>
<td><p>使用者權限、使用者連絡人清單、伺服器或集區資料、排程的會議等等。 此使用者資料不包含上傳至會議的內容。</p>
<p>以定期備份備份。 這項資訊是動態的，但是如果您需要還原至您的最後一次定期備份，則不會有更新失敗的 Lync Server。 如果連絡人清單對您的組織來說很重要，您可以更經常備份此資料。</p></td>
</tr>
<tr class="even">
<td><p>封存資料</p></td>
<td><p>封存資料庫 (資料庫： LcsLog.mdf) </p>
<p>如果您已啟用 Microsoft Exchange 整合選項，則此資料可能會儲存在 Exchange 2013。 否則，此資料會保留在 Lync Server 封存資料庫中，該資料庫可能會組合其他 Lync Server 資料庫，或獨立資料庫伺服器上獨立。</p></td>
<td><p>立即訊息 (IM) 和會議內容。</p>
<p>這種資料對 Lync Server 並非很重要，但對於您的組織而言，它對您的組織來說可能是很重要的。 據以判斷備份排程。</p></td>
</tr>
<tr class="odd">
<td><p>監控資料</p></td>
<td><p>監視資料庫 (LcsCDR.mdf 及 QoeMetrics.mdf) </p>
<p>這些資料庫可能會與其他 Lync Server 資料庫組合，或獨立于個別資料庫伺服器上獨立。</p></td>
<td><p>詳細通話記錄 (LcsCDR.mdf) 和經驗品質 (QoE) 度量 (QoeMetrics.mdf) 。</p>
<p>詳細通話記錄是動態的，可能對您的業務很重要。 考慮是否出於法規原因而需要這些記錄來決定備份排程。</p>
<p>經驗品質資訊是動態的。 QoE 資料遺失對 Lync Server 的運作而言並不重要，但對您的企業而言可能很重要。 根據組織的重要資訊，判斷備份排程。</p></td>
</tr>
<tr class="even">
<td><p>Persistent Chat 資料</p></td>
<td><p>Persistent Chat database (managed) 。</p>
<p>這個資料庫可能會組合其他 Lync Server 資料庫，或獨立于不同的資料庫伺服器上。</p></td>
<td><p>Persistent Chat Data 是在聊天室中張貼的實際聊天內容。 這種資料通常是商務重要的。</p>
<p>您可以選擇使用 SQL Server 備份，或是使用 Lync Server 中提供的 <strong>Export-CsPersistentChatData</strong> Cmdlet 來匯出資料庫。 若要復原資料，您可以匯入資料庫並將其還原至最後一次完整備份的點，這表示您無法將資料庫還原至失敗點。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>檔案存放區資料需求

在 Enterprise Edition 部署中，Lync Server 檔存放區通常位於檔案伺服器上。 在 Standard Edition 部署中，Lync Server 檔存放區在 Standard Edition Server 上是預設所在的。 一般來說，網站有一個共用的 Lync Server 檔存放區。 Persistent Chat file store 使用與 Lync Server 檔案存放區相同的檔案共用。

檔案存放區位置識別為 \\ \\ 伺服器 \\ 共用名稱稱。 若要尋找檔案存放區的特定位置，請開啟拓撲產生器，然後在 [檔案存放 **區** ] 節點中查看。

下表列出備份與還原所需的檔案存放區。

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
<th>Description/備份時間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 檔存放區</p></td>
<td><p>通常是在檔案伺服器、檔叢集或 Standard Edition server 上</p></td>
<td><p>會議內容、會議內容中繼資料、會議相容性記錄檔、應用程式資料檔案、裝置更新的更新檔案、回應群組的音訊檔、通話駐留及宣告應用程式，以及張貼在 Persistent 聊天室中的檔案。</p>
<p>以定期備份備份。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>其他備份需求

為了協助確保您還原 Lync Server 服務的能力，在發生失敗時，您必須備份並非 Lync Server 本身一部分的某些必要元件。 這份檔中所述的 Lync Server 備份與還原程式的一部分，不會備份或還原下列元件：

  - **Active Directory 網域服務**    當您備份 Lync Server 時，您需要使用 Active Directory 工具備份 AD DS。 請務必將 AD DS 與 Lync Server 保持同步，以避免當 Lync Server 預期的連絡人物件與 AD DS 中的連絡人物件不符時可能發生的問題。 AD DS 會儲存 Lync Server 所使用的下列設定：
    
      - 使用者 SIP URI 及其他使用者設定。
    
      - 回應群組和會議助理等應用程式的連絡人物件。
    
      - 中央管理存放區的指標。
    
      - Kerberos 驗證帳戶 (選用的電腦物件) 和 Lync Server 安全性群組。
    
    如需在 Windows Server 2008 中備份及還原 AD DS 的詳細資訊，請參閱《 AD DS 備份和復原逐步指南》 [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) 。

  - **憑證授權單位單位和憑證**    使用組織的原則 (CA) 和憑證備份憑證授權單位單位。 如果您使用可匯出的私密金鑰，您可以備份憑證和私密金鑰，然後在使用本檔中的程式來還原 Lync Server 時，將其匯出。 如果您使用內部 CA，當您需要還原 Lync Server 時，您可以重新註冊。 請務必將私密金鑰保留在安全的位置，以便在電腦失敗時使用。

  - **System Center Operations Manager**    如果您使用 Microsoft System Center Operations Manager (過去的 Microsoft Operations Manager) 若要監視 Lync Server 部署，您可以選擇性地備份它在監視 Lync Server 時所建立的資料。 使用您的標準 SQL Server 備份程式來備份 System Center Operations Manager 檔案。 復原期間不會還原這些檔案。

  - **公用交換電話網路 (PSTN) 閘道**     設定如果您使用 Enterprise Voice 或 Survivable 分支裝置，則必須備份 PSTN 閘道設定。 如需備份及還原 PSTN 閘道設定的詳細資訊，請參閱廠商。

  - **Lync server 或 Office 通訊伺服器**     的共存版本如果您的 Lync Server 2013 部署 coexists 使用 Lync Server 2010 或舊版的 Office 通訊伺服器，您就無法使用本檔中的程式來備份或還原舊版本。 相反地，您必須使用專為舊版所記錄的備份與還原程式。 如需備份及還原 Lync Server 2010 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) 。 如需備份及還原 Microsoft Office 通訊伺服器 2007 R2 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) 。

  - **基礎結構資訊**    您必須備份基礎結構的相關資訊，例如防火牆設定、負載平衡設定、Internet Information Services (IIS) 設定、網域名稱系統 (DNS) 記錄和 IP 位址，以及動態主機設定通訊協定 (DHCP) 設定。 如需備份這些元件的詳細資訊，請與其各自的廠商核實。

  - **Microsoft exchange 和 Exchange 整合通訊 (UM) **    如 Microsoft Exchange 檔中所述，備份及還原 Microsoft Exchange 和 Exchange UM。 如需備份及還原 Exchange Server 2013 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) 。 如需備份及還原 Exchange Server 2010 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) 。
    
    請注意，Lync Server 2013 引進使用者連絡人清單、高清晰使用者相片，以及封存資料儲存在 Exchange 2013 中的功能。 請參閱下列清單，查看如何備份這些類型的資料：
    
      - **高清晰度相片** 會備份為 Exchange Server 備份的一部分。
    
      - 在 Lync Server 2013 中引入**整合連絡人存放區**。 整合連絡人存放區可讓使用者在 Exchange 2013 中保留所有的連絡人資訊。
        
        您應確定針對使用者的使用者連絡人是儲存在「整合連絡人存放區」或 Lync 後端伺服器上，來決定備份是否是最新的。 下列案例說明將使用者連絡人遷移至整合連絡人存放區的位置，可能會造成備份及還原程式的問題。
        
        **案例1：** 使用者連絡人會遷移至整合連絡人存放區，而且會從遷移使用者連絡人之前所進行的 Lync Server 備份執行還原。 在此案例中，使用者會在一天內狀態為過期的連絡人，直到 Lync Server 遷移任務開始將使用者連絡人遷移至 Exchange。  (請注意，因為使用者的連絡人先前已遷移至整合連絡人存放區，所以會) 使用 Exchange 連絡人資訊。 此案例不需要系統管理員介入。
        
        **案例2：** 使用者連絡人先前已儲存在統一連絡人存放區中，但會進行還原。 當使用者連絡人儲存在統一連絡人存放區中時，會從 Lync Server 備份執行還原。 在此情況下， `Error: Incorrect Exchange Version` 用戶端或 Lyss server 記錄中的錯誤訊息可能表示這是問題。 使用者將可以直接從 Exchange 存取 Lync 2013 中的連絡人清單，但用戶端的狀態將不會符合 Lync Server 狀態。 若要修正此問題，系統管理員必須對受影響的使用者執行 **CsUCSRollback** Cmdlet。
    
      - 封存**資料**可以儲存在 Exchange 2013。 這種資料對 Lync Server 並非很重要，但對於您的組織而言，它對您的組織來說可能是很重要的。 如果封存資料儲存在 Exchange 中，且對您的組織很重要，請遵循 Exchange 備份及還原程式。 請注意，儲存在 Exchange 中的封存資料無法移回 Lync Server。 此外，無法將已儲存在 Lync 封存資料庫中的資料移至 Exchange。

</div>

</div>

<span> </span>

</div>

</div>

</div>

