---
title: Lync Server 2013：規劃混合式部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2595d1d1e73b3078050682acc8154c227a9d2aef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522060"
---
# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>規劃 Lync Server 2013 混合式部署

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-05-25_

在規劃混合式部署時，應考慮下列使用者和網路基礎結構的需求。

<div>

## <a name="infrastructure-requirements"></a>基礎結構需求

您必須在您的環境中設定下列設定，才能實施及部署混合部署。

  - 啟用啟用商務用 Skype Online 的 Microsoft 365 或 Office 365 組織。 請注意，您可以只對內部部署部署使用單一租使用者進行混合設定。

  - 單一內部部署 (基礎結構) ，可在支援的拓撲中部署商務用 Skype Server 或 Lync Server。 請參閱拓撲的需求。
    
    如需設定 Lync Server 2013 或 Lync Server 2010 部署以進行混合的詳細資訊，請參閱設定 [Lync server 2013 混合式部署](lync-server-2013-configuring-hybrid-deployments.md)。

  - 商務用 Skype Server 2015 系統管理工具。 如果您使用的是 Lync Server 2013 或 Lync Server 2010，您可以使用 Lync Server 2013 系統管理工具。

  - 若要支援使用 Microsoft 365 或 Office 365 進行單一登入，讓使用者可以使用相同的登入認證，以在內部部署時登入 Office，您可以使用 Azure Active Directory (AAD) Connect 的密碼同步功能。 您也可以使用 Active Directory Federation Services (AD FS) ，以用於 Microsoft 365 或 Office 365 的單一登入。
    
    如需詳細資訊，請參閱[將內部部署識別與 Azure Active Directory 整合](https://go.microsoft.com/fwlink/p/?linkid=619754)。

  - 單一目錄同步處理解決方案，可讓您的內部部署和線上 Active Directory 物件同步處理。 如需目錄同步處理的詳細資訊，請參閱 [目錄整合工具](https://go.microsoft.com/fwlink/p/?linkid=530320)。

</div>

<div>

## <a name="lync-client-support"></a>Lync 用戶端支援

Lync 用戶端支援的功能有一些差異，以及內部部署和線上環境中可用的功能。 在您決定要在組織中家用使用者的位置之前，您可以針對 Lync Server 的各種設定來查看用戶端支援。 下列用戶端支援 Lync 混合式部署中的商務用 Skype Online：

  - Lync 2010

  - Lync 2013

  - Lync Windows Store 應用程式

  - Lync Web App

  - Lync Mobile

  - Lync for Mac 2011

  - Lync Room System

  - Lync Basic 2013

如需用戶端支援的詳細資訊，請參閱下列主題：

  - [Lync Online 用戶端](https://go.microsoft.com/fwlink/?linkid=281902)

  - [Lync Server 2013 的用戶端比較表](lync-server-2013-desktop-client-comparison-tables.md)

  - [Lync Server 2013 的行動用戶端比較表](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>拓撲需求

若要使用商務用 Skype Online 設定混合部署，您必須具備下列其中一種支援的拓撲：

  - 商務用 Skype Server 2015 部署，包含所有執行商務用 Skype Server 2015 的伺服器。

  - Lync Server 2013 部署，包含所有執行 Lync Server 2013 的伺服器。

  - Lync Server 2010 部署，其中包含所有執行 Lync Server 2010 的伺服器及最新的累計更新。
    
      - 同盟 edge server 與下一個躍點伺服器的同盟 Edge server 必須執行 Lync Server 2010 及最新的累計更新。
    
      - 商務用 Skype Server 2015 或 Lync Server 2013 系統管理工具必須至少安裝在一部伺服器或管理工作站上。

  - 在至少一個執行商務用 Skype Server 2015 的網站中，具有下列伺服器角色的混合 Lync Server 2013 和商務用 Skype Server 2015 部署：
    
      - 至少一個 Enterprise 集區或 Standard Edition server
    
      - 與 SIP 同盟關聯的 Director 集區（如果有的話）
    
      - 與 SIP 同盟相關聯的 Edge 集區

  - 在至少一個執行商務用 Skype Server 2015 的網站中，混合的 Lync Server 2010 和商務用 Skype Server 2015 部署（包含下列伺服器角色）
    
      - 至少一個 Enterprise 集區或 Standard Edition server
    
      - 與 SIP 同盟關聯的 Director 集區（如果有的話）
    
      - 與網站的 SIP 同盟相關聯的 Edge 集區

  - 在至少一個執行 Lync Server 2013 的網站中，混合式 Lync Server 2010 和 Lync Server 2013 部署具有下列伺服器角色：
    
      - 網站中至少有一個 Enterprise 集區或 Standard Edition server
    
      - 與 SIP 同盟關聯的 Director 集區（如果它存在於網站中）
    
      - 與網站的 SIP 同盟相關聯的 Edge 集區

<div>


> [!IMPORTANT]  
> 所有的使用者管理（包括使用者在內部部署和 UNRESOLVED_TOKEN_VAL (skypeforbusiness) Online 之間移動）都必須使用最新安裝的系統管理工具版本執行。 系統管理工具必須安裝在另一部伺服器上，且該伺服器具有現有內部部署部署和網際網路的 connect 存取權。 將內部部署的使用者移至 UNRESOLVED_TOKEN_VAL (skype16_online) 的 <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> Cmdlet 必須從連接至內部部署的系統管理工具執行。



</div>

如需支援的拓撲的詳細資訊，請參閱 [Lync server 2013 中支援的拓撲](lync-server-2013-supported-topologies.md)，以及 [適用于企業混合式部署的 Lync Server 2013 參考拓撲](https://go.microsoft.com/fwlink/p/?linkid=398709)。

如需有關混合部署的疑難排解資訊，並將 PowerShell 連接至 Lync Online，請參閱 [Lync online： lync PowerShell 和混合式疑難排解](https://go.microsoft.com/fwlink/p/?linkid=306718)。

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>同盟允許/封鎖清單的需求

允許的網域清單包括已設定協力廠商 Edge 完全限定功能變數名稱 (FQDN) 的網域。 這兩種情況有時候稱為「 *允許的夥伴伺服器* 」或「 *直接同盟夥伴*」。 您應熟悉開放式同盟和封閉式同盟之間的差異，在內部部署中分別稱為「協力廠商 *探索* 」和「允許的協力廠商」 *網域清單*」。

若要成功設定混合式部署，必須符合下列需求：

  - 您的內部部署和您的 Microsoft 365 或 Office 365 組織必須設定符合網域的功能。 如果已在內部部署上啟用夥伴探索，則必須為您的線上租使用者設定開啟同盟。 若未啟用夥伴探索，則必須為您的線上租使用者設定關閉的同盟。

  - 內部部署部署中的封鎖網域清單必須完全符合您線上租使用者的封鎖網域清單。

  - 內部部署部署中的允許網域清單必須完全符合您線上租使用者的允許網域清單。

  - 您必須為使用 Lync Online 控制台所設定的線上租使用者啟用外部通訊的同盟。

</div>

<div>

## <a name="dns-settings"></a>DNS 設定

在建立混合部署的 DNS 記錄時，所有 Lync 外部 DNS 記錄都應該指向內部部署基礎結構。 如需必要 DNS 記錄的詳細資訊，請參閱 [網域名稱系統 (Lync Server 2013 的 DNS) 需求](lync-server-2013-domain-name-system-dns-requirements.md)。

此外，您必須確定下表中所述的 DNS 解析度可在您的內部部署中運作：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>DNS 記錄</p></td>
<td><p>可解析的</p></td>
<td><p>DNS 需求</p></td>
</tr>
<tr class="even">
<td><p>_Sipfederationtls 的 DNS SRV 記錄。 _tcp c0/>sipdomain.com 以 &gt; 取得所有支援的 SIP 網域解析至存取 Edge 外部 IP (s) </p></td>
<td><p>Edge server (s) </p></td>
<td><p>在混合式設定中啟用同盟通訊。 Edge Server 需要知道如何路由傳送內部部署和線上間的 SIP 網域的同盟流量。</p></td>
</tr>
<tr class="odd">
<td><p>DNS A 記錄 (s) Edge Web 會議服務 FQDN，例如 webcon.contoso.com 解析為 Web 會議 Edge 外部 IP (s) </p></td>
<td><p>連線使用者電腦的內部公司網路</p></td>
<td><p>讓線上使用者可以在內部部署主控會議中呈現或查看內容。 內容包括 PowerPoint 檔案、白板、投票和共用附注。</p></td>
</tr>
</tbody>
</table>


根據組織中設定 DNS 的方式，您可能需要將這些記錄新增至對應 SIP 網域的內部主控 DNS 區域， (s) 以提供對這些記錄的內部 DNS 解析。

</div>

<div>

## <a name="firewall-considerations"></a>防火牆的考量

網路上的電腦必須能夠執行標準網際網路 DNS 查閱。 若這些電腦可以搜尋標準網際網路網站，表示您的網路符合此需求。

根據您的 Microsoft 線上服務資料中心的位置，您也必須設定網路防火牆裝置，以接受以萬用字元功能變數名稱為基礎的連線 (例如，所有來自 \* outlook.com) 的流量。 如果您組織的防火牆不支援萬用字元名稱設定，您必須手動判斷您要允許的 IP 位址範圍和指定的埠。

請參閱 Help 主題 [Office 365 URLs 和 IP 位址範圍](https://go.microsoft.com/fwlink/p/?linkid=252942)。

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>埠和通訊協定需求

除了內部 Lync Server 2013 通訊的埠需求之外，您還必須設定下列埠。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/埠</th>
<th>應用程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>開放輸入</p>
<ul>
<li><p>Active Directory Federation Services (同盟伺服器角色)</p>
<p>如需詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">瞭解 AD FS 角色服務</a>。</p></li>
<li><p>Active Directory Federation Services (Proxy 伺服器角色)</p></li>
<li><p>Microsoft Online Services 入口網站</p></li>
<li><p>我的公司入口網站</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync 用戶端 (從內部部署 Lync Server 的 Lync Online 通訊) </p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 和443</p></td>
<td><p>開放輸入</p>
<ul>
<li><p>Microsoft Online Services 目錄同步作業工具</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>開啟 Edge Server 上的輸入/輸出</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>開啟資料共用會話的輸入/輸出</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>開啟輸入/輸出音訊、影片、應用程式共用會話</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>開啟音訊和影片的輸入/輸出</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>開啟音訊及視頻會話的輸出</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>使用者帳戶和資料

在 Lync Server 2013 混合式部署中，您想要在 Lync Online 中建立的任何使用者，必須先在內部部署中建立，以便在 Active Directory 網域服務中建立使用者帳戶。 然後，您可以將使用者移至商務用 Skype Online，這會移動使用者的連絡人清單。

當您使用 AD FS 和 Dirsync 在您的 Lync 內部部署和 Lync Online 部署之間同步處理使用者帳戶時，即使使用者未移至 Lync Online，您還是必須同步處理組織內部部署和線上 Lync 部署間所有 Lync 使用者的 AD 帳戶。 如果您未同步處理所有使用者，組織中內部部署與線上使用者之間的通訊可能無法如預期的方式運作。

<div>


> [!IMPORTANT]  
> 如果使用者是使用 Microsoft 365 系統管理中心的線上入口網站建立，使用者帳戶將不會與內部部署 Active Directory 同步處理，而且使用者將不會存在於內部部署 Active Directory 中。 如果您已在 Lync Online 中建立使用者，而且想要使用內部部署的 Lync 伺服器設定混合，請參閱在 <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013 中將使用者從 Lync Online 移至 lync 內部部署</A>。



</div>

在規劃混合式部署時，您也應考慮下列使用者相關的問題。

  - **使用者連絡人**    Lync Online 使用者的連絡人限制為250。 當帳戶移至 Lync Online 時，任何超出該號碼的連絡人都會從使用者的連絡人清單中移除。

  - **立即訊息與顯示狀態**    使用者連絡人清單、群組和存取控制清單 (ACLs) 會以使用者帳戶一起遷移。

  - **會議資料、會議內容及排程的會議**    此內容不會與使用者帳戶一起遷移。 使用者在將其帳戶遷移至 Lync Online 後，必須重新排定會議。

</div>

<div>

## <a name="user-policies-and-features"></a>使用者原則及功能

  - 在 Lync Server 2013 混合式環境中，使用者可以在內部部署或線上上啟用立即訊息、語音和會議，但不能同時啟用兩者。

  - **Lync 用戶端**    當某些使用者移至 Lync Online 時，可能需要新的用戶端版本。 若為 Office 通訊伺服器 2007 R2，使用者必須先移至 Lync Server 2013 集區，再遷移至 Lync Online。
    
    如需用戶端支援的詳細資訊，請參閱 [用戶端的 Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) 和 [支援的 lync 用戶端和網路埠](https://go.microsoft.com/fwlink/p/?linkid=281901)設定。

  - **內部部署原則和設定 (非使用者) **    線上和內部部署原則需要不同的設定。 您無法設定適用于這兩者的全域原則。

</div>

</div>

<span> </span>

</div>

</div>

</div>
