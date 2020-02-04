---
title: Lync Server 2013：安裝及設定觀察程式節點
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
ms.openlocfilehash: 89465227e351da3c69116201efe5ee4eab89eca4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>在 Lync Server 2013 中安裝及設定觀察程式節點

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

[觀察程式]*節點*是定期執行 Lync Server 綜合交易的電腦。 *綜合交易*是 Windows PowerShell Cmdlet，可驗證重要的最終使用者案例，例如登入系統的能力，或 exchange 立即訊息的功能，如預期的那樣運作。 在 Lync Server 2013 中，System Center Operations Manager 可以執行下表所示的綜合交易。 資料表中有三種不同的綜合交易類型：

  - **預設值**。 這些是觀察程式節點預設會執行的綜合交易。 當您建立新的 [觀察程式] 節點時，您可以選擇指定該節點要執行的綜合交易。 （這是**新的 CsWatcherNodeConfiguration** Cmdlet 所使用的測試參數的用途）。如果您在建立觀察程式節點時不使用測試參數，就會自動執行所有預設的綜合交易，且不會執行任何非預設的綜合交易。 這表示，系統會將觀察程式節點設定為執行測試 CsAddressBookService 測試，但不會將其設定為執行測試 CsExumConnectivity 測試。

  - **非預設值**。 正如名稱所示，非預設的綜合交易是測試觀察程式節點預設不會執行。 不過，可以啟用觀察程式節點來執行任何非預設的綜合交易。 您可以在建立觀察程式節點（使用**新的 CsWatcherNodeConfiguration** Cmdlet），或在此後的任何時間執行此動作。 許多非預設的綜合交易需要額外的設定步驟。 如需詳細資訊，請參閱[Lync Server 2013 中的綜合交易的特殊設定指示](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)。

  - **延伸**。 [延伸測試] 是一種特殊類型的非預設綜合交易。 與其他綜合交易不同，延長式測試可以在每一階段執行多次。 在驗證諸如多個公用交換電話網絡（PSTN）語音路由的資源時，這個功能非常有用。 只要將延伸測試的多個實例新增至觀察程式節點，即可進行設定。

如需將其他綜合交易新增至觀察程式節點的程式詳細資訊，請參閱[在 Lync Server 2013 中管理觀察程式節點](lync-server-2013-managing-watcher-nodes.md)。 您可以使用 Lync Server 管理命令介面來移除來自觀察程式節點的綜合交易。

可供觀察程式節點使用的綜合交易，包括下列各項：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet 名稱（測試名稱）</th>
<th>說明</th>
<th>綜合交易類型</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService （ABS）</p></td>
<td><p>確認使用者可以查詢不在連絡人清單中的使用者。</p></td>
<td><p>設置</p></td>
</tr>
<tr class="even">
<td><p>CsAddressBookWebQuery （ABWQ）</p></td>
<td><p>確認使用者可以透過 HTTP 找不在連絡人清單中的使用者。</p></td>
<td><p>設置</p></td>
</tr>
<tr class="odd">
<td><p>Test CsIM （IM）</p></td>
<td><p>確認使用者可以傳送對等立即訊息。</p></td>
<td><p>設置</p></td>
</tr>
<tr class="even">
<td><p>CsP2PAV （P2PAV）</p></td>
<td><p>確認使用者可以進行對等音訊通話（僅限通知）。</p></td>
<td><p>設置</p></td>
</tr>
<tr class="odd">
<td><p>CsPresence （目前狀態）</p></td>
<td><p>確認使用者能夠查看其他使用者的目前狀態。</p></td>
<td><p>設置</p></td>
</tr>
<tr class="even">
<td><p>Test CsRegistration （註冊）</p></td>
<td><p>確認使用者可以登入 Lync。</p></td>
<td><p>設置</p></td>
</tr>
<tr class="odd">
<td><p>CsAudioConferencingProvider （ACP）</p></td>
<td><p>不會用於 Lync Server 2013 的內部部署版本</p></td>
<td><p>延伸</p></td>
</tr>
<tr class="even">
<td><p>CsPstnPeerToPeerCall （PSTN）</p></td>
<td><p>確認使用者可以與企業外部的人員（PSTN 號碼）撥打電話和接聽來電。</p></td>
<td><p>非預設，延伸</p></td>
</tr>
<tr class="odd">
<td><p>CsAVConference （AvConference）</p></td>
<td><p>確認使用者可以建立並參與音訊/視訊會議。</p></td>
<td><p>設置</p></td>
</tr>
<tr class="even">
<td><p>CsAVEdgeConnectivity （AVEdgeConnectivity）</p></td>
<td><p>確認 A/V 邊緣伺服器能夠接受對等通話和電話會議的連線。</p></td>
<td><p>非預設值</p></td>
</tr>
<tr class="odd">
<td><p>CsDataConference （DataConference）</p></td>
<td><p>確認使用者可以參與資料共同作業會議，包括白板和投票等活動的線上會議。</p></td>
<td><p>非預設值</p></td>
</tr>
<tr class="even">
<td><p>CsExumConnectivity （ExumConnectivity）</p></td>
<td><p>確認使用者可以連線到 Exchange 整合通訊（UM）。</p></td>
<td><p>非預設值</p></td>
</tr>
<tr class="odd">
<td><p>CsGroupIM （GroupIM）</p></td>
<td><p>確認使用者可以在會議中傳送立即訊息，並與三人或多位人員一起參與立即訊息交談。</p></td>
<td><p>設置</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM – TestJoinLauncher （JoinLauncher）</p></td>
<td><p>確認使用者可以透過網址連結來建立及加入排程會議。</p></td>
<td><p>非預設值</p></td>
</tr>
<tr class="odd">
<td><p>CsMCXP2PIM （MCXP2PIM）</p></td>
<td><p>確認行動裝置使用者可以註冊並傳送立即訊息。</p></td>
<td><p>非預設值</p></td>
</tr>
<tr class="even">
<td><p>CsPersistentChatMessage （PersistentChatMessage）</p></td>
<td><p>確認使用者可以使用持續聊天服務來交換郵件。</p></td>
<td><p>非預設值</p></td>
</tr>
<tr class="odd">
<td><p>CsUnifiedContactStore （UnifiedContactStore）</p></td>
<td><p>確認使用者的連絡人可以透過整合連絡人存放區存取。 「整合連絡人存放區」提供一種方式，讓使用者可以使用 Lync 2013、Outlook 和/或 Outlook Web Access 來維護一組可存取的連絡人。</p></td>
<td><p>非預設值</p></td>
</tr>
<tr class="even">
<td><p>CsXmppIM （XmppIM）</p></td>
<td><p>確認立即訊息可透過 XMPP （可擴展訊息和目前狀態通訊協定）閘道傳送。</p></td>
<td><p>非預設值</p></td>
</tr>
</tbody>
</table>


您不需要安裝觀察程式節點，就能使用 System Center Operations Manager。 如果您沒有安裝這些節點，您仍然可以在問題發生時，從 Lync Server 2013 元件取得即時通知。 （元件和使用者管理套件不使用觀察程式節點）。不過，如果您想要使用主動監視管理套件監視端對端案例，則需要觀察程式節點。

<div>


> [!NOTE]  
> 系統管理員也可以手動執行綜合交易，而不需要使用或安裝，Operations Manager。 如需各種 Test-Cs Cmdlet 的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 Cmdlet 索引</A>。



</div>

根據您的部署規模而定，綜合交易可能會使用大量的電腦記憶體和處理器時間。 基於這個原因，我們建議您使用專用電腦做為觀察程式節點。 例如，您不應該將前端伺服器設定為充當觀察程式節點。 觀察程式節點應該符合下列硬體規格：

<div>


> [!NOTE]  
> 舊版 Microsoft Lync Server 2010 觀察程式節點無法與 Lync Server 2013 觀察程式節點在同一部電腦上 collocated。 這是因為 Lync Server 2010 和 Lync Server 2013 的核心系統檔案無法安裝在同一部電腦上。<BR>不過，Lync Server 2013 觀察程式節點可以同時監視 Lync Server 2013 和 Lync Server 2010。 這兩個產品版本都支援預設的綜合交易記錄。



</div>

Lync Server 2013 觀察程式節點可以在企業內部或外部部署，以協助驗證：

  - <span></span>  
    企業內部使用者的 [池連線]。

  - <span></span>  
    針對在企業外部工作的遠端使用者，透過周邊網路進行連線。

  - <span></span>  
    連接至分支機搆裝置。

  - <span></span>  
    企業和周邊網路中的 Lync Server 2010 的連線能力。

企業內部和外部都提供不同的驗證選項，可協助簡化管理。 如需詳細資訊，請參閱[將觀察程式節點設定為在 Lync Server 2013 中執行綜合交易](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)。

若要將電腦設定為充當觀察者節點，您必須在安裝 System Center Operations Manager 並匯入 Lync Server 2013 管理套件後完成下列步驟。

在您安裝 Lync Server 2013 core 檔案和 System Center 代理程式檔案之前，您也應該確定觀察程式節點電腦符合安裝 Lync Server 2013 的所有先決條件。 此外，觀察程式節點電腦也應該安裝下列專案：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>最低需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>下列其中一項：</p>
<ul>
<li><p>64-位處理器、四核、2.33 GHz 或更新版本</p></li>
<li><p>64位雙路處理器、雙核、2.33 GHz 或更新版本</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>儲存體</p></td>
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

  - Windows 身分識別基礎。

  - Windows PowerShell 3.0。

只要符合所有這些先決條件，您就可以透過下列方式設定觀察程式節點：

  - 在觀察程式節點電腦上安裝 Lync Server 2013 core 檔案。

  - 在觀察程式節點電腦上安裝 System Center Operations Manager 代理程式。

  - 執行 Watchernode 的可執行檔。

  - 使用**CsWatcherNodeConfiguration** Cmdlet 來設定要由觀察程式節點使用的測試使用者。

</div>

<span> </span>

</div>

</div>

</div>

