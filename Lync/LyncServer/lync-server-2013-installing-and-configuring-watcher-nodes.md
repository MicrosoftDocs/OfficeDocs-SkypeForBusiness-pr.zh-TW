---
title: Lync Server 2013：安裝及設定監視程式節點
description: Lync Server 2013：安裝及設定監視程式節點。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87bf43e1651fabfa0137d09234d663cc905e947b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573999"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>在 Lync Server 2013 中安裝及設定觀察程式節點

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

*觀察程式節點* 是定期執行 Lync Server 綜合交易的電腦。 *綜合交易* 是 Windows PowerShell Cmdlet，用來驗證重要的使用者案例，例如登入系統的功能，或 exchange 立即訊息的功能會如預期般運作。 對於 Lync Server 2013，System Center Operations Manager 可以執行下表所示的綜合交易。 表中顯示三種不同綜合交易類型：

  - **預設值**。 這些是監看員節點預設會執行的綜合交易。 建立新的監看員節點時，可以選擇指定節點會執行的綜合交易。  (**New-CsWatcherNodeConfiguration** 指令程式所使用之測試參數的目的。 ) 如果在建立監看員節點時未使用 [測試] 參數，它會自動執行所有預設的綜合交易，而且不會執行任何非預設的綜合交易。 舉例而言，這表示監看員節點會設定執行 Test-CsAddressBookService 測試，但是不會設定執行 Test-CsExumConnectivity 測試。

  - **非預設值**。 如名稱所指，非預設綜合交易為監看員節點依預設不會執行的測試。 不過，可以啟用監看員節點來執行任何非預設綜合交易。 您可以在建立監看員節點時 (透過使用 **New-CsWatcherNodeConfiguration** Cmdlet)，或在建立後的任何時點進行啟用。 許多非預設綜合交易需要額外的設定步驟。 如需詳細資訊，請參閱 [Lync Server 2013 中的綜合交易的特殊安裝指示](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)。

  - **擴充**。 延伸測試為非預設綜合交易的特別類型。 與其他綜合交易不同的是，延伸測試在每個行程中可以執行多次。 在驗證如集區的多重公用電話交換網路 (PSTN) 語音路由時，這就非常有用。 只要在監看員節點中新增延伸測試的多個執行個體，即可設定。

如需將其他綜合交易新增至監看員節點程式的詳細資訊，請參閱 [管理 Lync Server 2013 中的](lync-server-2013-managing-watcher-nodes.md)監看員節點。 您可以使用 Lync Server 管理命令介面，從監看員節點中移除綜合交易。

監看員節點可用的綜合交易包括下列：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet 名稱 (測試名稱)</th>
<th>描述</th>
<th>綜合交易類型</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>確認使用者可以查詢不在其連絡人清單中的使用者。</p></td>
<td><p>預設</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>確認使用者可以透過 HTTP 查詢不在其連絡人清單中的使用者。</p></td>
<td><p>預設</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>確認使用者可以傳送對等立即訊息。</p></td>
<td><p>預設</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV) </p></td>
<td><p>確認使用者可以撥出對等音訊通話 (僅訊號)。</p></td>
<td><p>預設</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>確認使用者可以檢視其他使用者的目前狀態。</p></td>
<td><p>預設</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>確認使用者可以登入 Lync。</p></td>
<td><p>預設</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>不會搭配 Lync Server 2013 的內部部署版本使用</p></td>
<td><p>延伸</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>確認使用者可以對企業外人員 (PSTN 號碼) 撥出及接聽通話。</p></td>
<td><p>非預設、延伸</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference) </p></td>
<td><p>確認使用者可以建立並參與音訊/視訊會議。</p></td>
<td><p>預設</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity) </p></td>
<td><p>確認 A/V Edge Server 可以接受對等通話及電話會議的連線。</p></td>
<td><p>非預設</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference) </p></td>
<td><p>確認使用者可以參與資料共同作業會議 (包含如白板及投票等活動的線上會議)。</p></td>
<td><p>非預設</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity) </p></td>
<td><p>確認使用者可以連線至 Exchange 整合通訊 (UM) 。</p></td>
<td><p>非預設</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM) </p></td>
<td><p>確認使用者可以在會議中傳送立即訊息，並參與有三位或更多位人員的立即訊息交談。</p></td>
<td><p>預設</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM – TestJoinLauncher (JoinLauncher) </p></td>
<td><p>確認使用者可以透過網址連結建立並加入排程會議。</p></td>
<td><p>非預設</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM) </p></td>
<td><p>確認行動裝置使用者可以註冊並傳送立即訊息。</p></td>
<td><p>非預設</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage) </p></td>
<td><p>確認使用者可以使用 Persistent Chat service 來交換郵件。</p></td>
<td><p>非預設</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore) </p></td>
<td><p>確認可以透過整合連絡人存放區來存取使用者的連絡人。 整合連絡人存放區提供一種方法，讓使用者維護一組可使用 Lync 2013、Outlook 和/或 Outlook Web Access 存取的連絡人。</p></td>
<td><p>非預設</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM) </p></td>
<td><p>確認立即訊息可以跨 XMPP (Extensible Messaging and Presence Protocol) 閘道傳送。</p></td>
<td><p>非預設</p></td>
</tr>
</tbody>
</table>


您不需要安裝觀察程式節點，即可使用 System Center Operations Manager。 如果您未安裝這些節點，您仍然可以在發生問題時，從 Lync Server 2013 元件取得即時提醒。  (元件和 User Management Pack 不會使用觀察器節點。 ) 不過，如果您想要使用作用中的監控管理元件來監視端對端案例，則必須要有觀察程式節點。

<div>


> [!NOTE]  
> 系統管理員也不需要使用或安裝 Operations Manager，就可以手動執行綜合交易。 如需各種 Test-Cs Cmdlet 的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 Cmdlet 索引</A>。



</div>

視部署大小而定，綜合交易可能會使用大量電腦記憶體及處理器時間。 因此，建議您使用專用電腦作為監看員節點。 例如，您不應將前端伺服器設定為充當監看員節點。 觀察程式節點應該符合下列硬體規格：

<div>


> [!NOTE]  
> 舊版 Microsoft Lync Server 2010 監看員節點無法在具有 Lync Server 2013 觀察者節點的同一部電腦上組合。 這是因為 Lync Server 2010 和 Lync Server 2013 的核心系統檔無法安裝在同一部電腦上。<BR>不過，Lync Server 2013 觀察程式節點可以同時監視 Lync Server 2013 和 Lync Server 2010。 兩個產品版本都支援預設綜合交易。



</div>

Lync Server 2013 觀察程式節點可能會部署在企業內部或外部，以協助確認：

  - <span></span>  
    企業內使用者對集區的連線。

  - <span></span>  
    於企業外工作的遠端使用者透過周邊網路的連線。

  - <span></span>  
    對分公司設備的連線。

  - <span></span>  
    企業內和周邊網路中的 Lync Server 2010 的連線能力。

對於簡化管理，企業內外有不同的驗證選項。 如需詳細資訊，請參閱設定 [監視節點以在 Lync Server 2013 中執行綜合交易](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)。

若要將電腦設定為監視節點，您必須在安裝 System Center Operations Manager 並匯入 Lync Server 2013 管理套件之後，完成下列步驟。

在您安裝 Lync Server 2013 核心檔案與 System Center agent 檔案之前，您也應該確定觀察程式節點電腦符合安裝 Lync Server 2013 的所有必要條件。 此外，監看員節點電腦還應該安裝下列項目：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>基本需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>下列其中之一：</p>
<ul>
<li><p>64位處理器、四核心2.33GHz 或更高版本</p></li>
<li><p>64位2路處理器、雙核2.33GHz 或更高版本</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>記憶體</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>網路作業系統</p></td>
<td><ul>
<li><p>1個網路介面卡 1 Gbps</p></li>
<li><p>Windows Server 2008 R2、Windows Server 2012 或</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - .NET Framework 4.5 的完整版本。

  - Windows Identity Foundation。

  - Windows PowerShell 3.0。

一旦符合所有這些必要條件，就可以執行下列動作來設定監看員節點：

  - 在監看員節點電腦上安裝 Lync Server 2013 核心檔案。

  - 在監看員節點電腦上安裝 System Center Operations Manager 代理程式。

  - 執行 Watchernode.msi 可執行檔。

  - 使用 **CsWatcherNodeConfiguration** Cmdlet 設定監看員節點要使用的測試使用者。

</div>

<span> </span>

</div>

</div>

</div>

