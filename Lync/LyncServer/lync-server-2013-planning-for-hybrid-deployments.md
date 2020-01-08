---
title: Lync Server 2013：規劃混合式部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b528e22e24635d47755096cd4bf81d4066feb3c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>規劃 Lync Server 2013 混合式部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-05-25_

規劃混合式部署時，請考慮下列使用者與網路基礎結構的需求。

<div>

## <a name="infrastructure-requirements"></a>基礎結構需求

您必須在您的環境中設定下列設定，才能實現及部署混合式部署。

  - 已啟用商務用 Skype Online 的 Microsoft Office 365 租使用者。 請注意，您只能使用單一租使用者進行混合式設定與您的內部部署。

  - 在支援的拓朴中部署的商務用 Skype Server 或 Lync Server 的單一內部部署（基礎架構）。 請參閱拓撲需求。
    
    如需針對混合式設定 Lync Server 2013 或 Lync Server 2010 部署的相關資訊，請參閱設定[Lync server 2013 混合式部署](lync-server-2013-configuring-hybrid-deployments.md)。

  - 商務用 Skype Server 2015 系統管理工具。 如果您使用的是 Lync Server 2013 或 Lync Server 2010，您可以使用 Lync Server 2013 系統管理工具。

  - 若要支援單一登入與 Office 365，讓使用者可以使用相同的登入認證，在他們在內部部署時登入 Office，您可以使用 Azure Active Directory （AAD） Connect 的密碼同步處理功能。 您也可以使用 Active Directory Federation Services （AD FS）進行單一登入與 Office 365。
    
    如需詳細資訊，請參閱[整合內部部署身分識別與 Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754)。

  - 讓您的內部部署和線上 Active Directory 物件同步處理的單一目錄同步處理解決方案。 如需目錄同步處理的詳細資訊，請參閱[目錄整合工具](http://go.microsoft.com/fwlink/p/?linkid=530320)。

</div>

<div>

## <a name="lync-client-support"></a>Lync 用戶端支援

Lync 用戶端支援的功能有一些差異，以及內部部署和線上環境中提供的功能。 在您決定您要在組織中的哪些位置，您可以針對不同的 Lync Server 設定，查看用戶端支援。 Lync 混合式部署中的商務用 Skype Online 支援下列用戶端：

  - Lync 2010

  - Lync 2013

  - Lync Windows Store 應用程式

  - Lync Web App

  - Lync Mobile

  - Lync for Mac 2011

  - Lync 會議室系統

  - Lync Basic 2013

如需用戶端支援的詳細資訊，請參閱下列主題：

  - [Lync Online 的用戶端](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Lync Server 2013 的用戶端比較表](lync-server-2013-desktop-client-comparison-tables.md)

  - [Lync Server 2013 行動用戶端比較表](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>拓撲需求

若要在商務用 Skype Online 中設定混合式部署，您必須具備下列其中一個受支援拓撲：

  - 商務用 Skype Server 2015 部署與所有執行商務用 Skype Server 2015 的伺服器。

  - Lync Server 2013 部署與所有執行 Lync Server 2013 的伺服器。

  - Lync Server 2010 部署，其中所有執行 Lync Server 2010 的伺服器都有最新的累計更新。
    
      - 同盟邊緣伺服器與同盟 Edge 伺服器的下一個躍點伺服器必須執行 Lync Server 2010，並提供最新的累加更新。
    
      - 商務用 Skype Server 2015 或 Lync Server 2013 系統管理工具必須安裝在至少一個伺服器或管理工作站上。

  - 混合式 Lync Server 2013 和商務用 Skype Server 2015 部署，在至少有一個執行商務用 Skype Server 2015 的網站中，都有下列伺服器角色：
    
      - 至少有一個企業版池或標準版伺服器
    
      - 與 SIP 同盟相關聯的控制器池（如果有的話）
    
      - 與 SIP 同盟相關聯的邊緣池

  - 混合式 Lync Server 2010 和商務用 Skype Server 2015 部署，在至少一個執行商務用 Skype Server 2015 的網站中，都有下列伺服器角色：
    
      - 至少有一個企業版池或標準版伺服器
    
      - 與 SIP 同盟相關聯的控制器池（如果有的話）
    
      - 與網站 SIP 同盟相關聯的邊緣池

  - 混合式 Lync Server 2010 和 Lync Server 2013 部署，在至少一個執行 Lync Server 2013 的網站中，都有下列伺服器角色：
    
      - 網站中至少有一個企業版池或標準版伺服器
    
      - 與 SIP 同盟相關聯的控制器池（如果它存在於網站中）
    
      - 與網站 SIP 同盟相關聯的邊緣池

<div>


> [!IMPORTANT]  
> 所有的使用者管理，包括使用者在線上內部部署和 UNRESOLVED_TOKEN_VAL （com.microsoft.skypeforbusiness.plugin.plist）之間移動，都需要使用最新安裝的系統管理工具來完成。 [管理工具] 必須安裝在可連線存取現有內部部署和網際網路的個別伺服器上。 您必須從連線到內部部署的管理工具執行<A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">move-csuser</A> Cmdlet，才能將使用者從內部部署部署移至 UNRESOLVED_TOKEN_VAL （skype16_online）。



</div>

如需支援的拓撲的詳細資訊，請參閱[Lync server 2013 支援的拓撲](lync-server-2013-supported-topologies.md)，以及[適用于企業混合式部署的 Lync server 2013 參考資料拓撲](http://go.microsoft.com/fwlink/p/?linkid=398709)。

如需混合式部署和將 PowerShell 連線至 Lync Online 的疑難排解資訊，請參閱[Lync online： Lync PowerShell 及混合式疑難排解](http://go.microsoft.com/fwlink/p/?linkid=306718)。

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>同盟允許/封鎖清單的需求

[允許的網域] 清單包含已設定「合作夥伴邊緣」完全限定功能變數名稱（FQDN）的網域。 這些有時稱為「*允許夥伴伺服器*」或「*直接聯盟夥伴*」。 在內部部署部署中，您應該熟悉開啟同盟與封閉式同盟之間的差異，分別稱為「*合作夥伴探索*」和「*允許的合作夥伴網域清單*」。

若要成功設定混合式部署，必須符合下列需求：

  - 您的內部部署和 Office 365 租使用者的網域相符設定必須相同。 如果在內部部署部署上啟用合作夥伴探索，則必須針對您的線上租使用者設定開啟同盟。 如果未啟用合作夥伴探索，則必須針對您的線上租使用者設定關閉的同盟。

  - 內部部署部署中的 [封鎖的網域] 清單必須完全符合您線上租使用者的封鎖網域清單。

  - 內部部署部署中的 [允許的網域] 清單必須完全符合您線上租使用者的「允許」網域清單。

  - 聯盟必須針對線上租使用者啟用，且使用 Lync Online 控制台進行設定。

</div>

<div>

## <a name="dns-settings"></a>DNS 設定

針對混合式部署建立 DNS 記錄時，所有 Lync 外部 DNS 記錄都應該指向內部部署基礎結構。 如需必要 DNS 記錄的詳細資料，請參閱[Lync Server 2013 的網域名稱系統（DNS）需求](lync-server-2013-domain-name-system-dns-requirements.md)。

此外，您還需要確保下表所述的 DNS 解析度可在您的內部部署中運作：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>DNS 記錄</p></td>
<td><p>可解析的方式</p></td>
<td><p>DNS 需求</p></td>
</tr>
<tr class="even">
<td><p>_Sipfederationtls _tcp 的 DNS SRV 記錄。&lt;針對&gt;所有支援的 SIP 網域 Sipdomain.com，解析為存取邊緣外部 IP （s）</p></td>
<td><p>Edge 伺服器</p></td>
<td><p>在混合式設定中啟用聯盟通訊。 Edge 伺服器需要知道在內部部署與線上之間分割之 SIP 網域的聯盟流量。</p></td>
</tr>
<tr class="odd">
<td><p>針對 Edge Web 會議服務 FQDN 的 DNS A 記錄，例如 webcon.contoso.com 解析為網路會議 Edge 外部 IP （s）</p></td>
<td><p>已連接內部公司網路的使用者電腦</p></td>
<td><p>讓線上使用者在內部部署的託管會議中展示或查看內容。 內容包括 PowerPoint 檔案、白板、投票和共用筆記。</p></td>
</tr>
</tbody>
</table>


根據貴組織中的 DNS 設定方式，您可能需要將這些記錄新增到對應 SIP 網域的內部託管 DNS 區域中，以提供這些記錄的內部 DNS 解析。

</div>

<div>

## <a name="firewall-considerations"></a>防火牆考慮

您網路上的電腦必須能夠執行標準的網際網路 DNS 查閱。 如果這些電腦能達到標準的網際網路網站，您的網路就能滿足這個需求。

根據您的 Microsoft Online 服務資料中心的位置，您也必須設定您的網路防火牆裝置，以根據萬用字元功能變數名稱（例如，所有來自 outlook.com 的\*流量）來接受連線。 如果貴組織的防火牆不支援萬用字元名稱設定，您將必須手動判斷您想要允許的 IP 位址範圍，以及指定的埠。

請參閱[Office 365 url 和 IP 位址範圍](http://go.microsoft.com/fwlink/p/?linkid=252942)的說明主題。

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>埠與通訊協定需求

除了內部 Lync Server 2013 通訊的埠需求之外，您還必須設定下列埠。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/埠</th>
<th>程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>開啟入站</p>
<ul>
<li><p>Active Directory 同盟服務（同盟伺服器角色）</p>
<p>如需詳細資訊，請參閱<a href="http://go.microsoft.com/fwlink/p/?linkid=281899">瞭解 AD FS 角色服務</a>。</p></li>
<li><p>Active Directory 同盟服務（proxy 伺服器角色）</p></li>
<li><p>Microsoft Online 服務入口網站</p></li>
<li><p>我的公司入口網站</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync 用戶端（從內部部署 Lync Server 與 Lync Online 的通訊）</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 和443</p></td>
<td><p>開啟入站</p>
<ul>
<li><p>Microsoft Online Services 目錄同步處理工具</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>開啟邊緣伺服器的入站/出站</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>開啟資料共用會話的輸入/輸出</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>開啟音訊、影片、應用程式共用會話的輸入/輸出</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>開啟音訊及視頻會話的輸入/輸出</p></td>
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

在 Lync Server 2013 混合式部署中，您要在家中的任何使用者都必須先在內部部署中建立，才能在 Active Directory 網域服務中建立使用者帳戶。 然後，您可以將使用者移至商務用 Skype Online，這會移動使用者的連絡人清單。

當您在您的 Lync 內部部署和 Lync Online 部署與 AD FS 和 Dirsync 之間同步處理使用者帳戶時，您必須在內部部署和線上 Lync 部署之間同步處理貴組織中所有 Lync 使用者的廣告帳戶，即使使用者不會移至 Lync Online。 如果您不同步處理所有使用者，貴組織中內部部署與線上使用者之間的通訊可能無法如期運作。

<div>


> [!IMPORTANT]  
> 如果使用者是使用 Office 365 的線上入口網站建立，使用者帳戶將不會與內部部署的 Active Directory 同步處理，而且使用者將不會存在於內部部署的 Active Directory 中。 如果您已在 Lync Online 中建立使用者，並且想要設定混合式與內部部署的 Lync Server，請參閱在<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync server 2013 中將使用者從 Lync Online 移至 lync 內部部署</A>。



</div>

規劃混合式部署時，您也應該考慮下列與使用者相關的問題。

  - **使用者連絡人**   Lync Online 使用者的連絡人限制是250。 當帳戶移至 Lync Online 時，該號碼以外的任何連絡人都會從使用者的連絡人清單中移除。

  - **立即訊息和目前狀態**   使用者連絡人清單、群組和存取控制清單（acl）會與使用者帳戶一起遷移。

  - **會議資料、會議內容和排程會議**   此內容不會與使用者帳戶一起遷移。 使用者必須在帳戶遷移至 Lync Online 後重新排程會議。

</div>

<div>

## <a name="user-policies-and-features"></a>使用者原則與功能

  - 在 Lync Server 2013 混合式環境中，使用者可在內部部署或線上使用立即訊息、語音及會議，但不能同時使用這兩個功能。

  - **Lync 用戶端**   在使用者移至 Lync Online 時，可能需要新的用戶端版本。 若是 Office 通訊伺服器 2007 R2，在遷移至 Lync Online 之前，必須先將使用者移至 Lync Server 2013 池。
    
    如需用戶端支援的詳細資訊，請參閱[Lync Online 的用戶端](http://go.microsoft.com/fwlink/p/?linkid=281902)和[支援的 lync 用戶端和網路埠](http://go.microsoft.com/fwlink/p/?linkid=281901)設定。

  - **內部部署原則與設定（非使用者）**   線上和內部部署原則都需要個別的配置。 您無法設定適用于這兩者的全域原則。

</div>

</div>

<span> </span>

</div>

</div>

</div>

