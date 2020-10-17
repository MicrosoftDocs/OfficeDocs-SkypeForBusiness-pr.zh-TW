---
title: Lync Server 2013：外部使用者存取的部署檢查表
description: Lync Server 2013：外部使用者存取的部署檢查清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a31534d1dcf3ba4dd0bb222de682d247c9683f94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568322"
---
# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中外部使用者存取的部署檢查清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

在您部署周邊網路並為外部使用者執行支援之前，您必須已部署 Microsoft Lync Server 2013 內部伺服器，包括前端集區或 Standard Edition Server。 如果您打算在內部網路中部署選用的 Director，您也應該在部署 Edge Server 之前加以部署。 如需 Director 部署程式的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md) 。

Microsoft Lync Server 2013 包含一些工具，可協助您規劃及部署內部伺服器和 Edge Server。 拓撲完成之後，將產生的拓撲定義發行至生產環境。 若要進行這項作業，您必須是 **Domain Admins** 群組及 **RTCUniversalServerAdmins** 群組的成員。

  - **規劃工具**    Office 通訊伺服器 2007 R2 包含規劃工具和 Edge 計畫工具，可讓您用來協助指導拓撲設計。 在 Lync Server 2010 中，這兩個工具合併成單一計畫工具，具有其他功能，例如收集已規劃的使用者計數、語音需求、外部使用者存取類型及同盟選項。 此外，還可以規劃基礎結構的網路參數，例如 IP 位址、負載平衡器類型，以及其他周邊網路考量。

  - **拓撲產生器**    Lync Server 2013 拓撲產生器可協助您定義拓撲和元件。 拓撲產生器對部署執行 Lync Server 2013 的伺服器而言是必要的。 拓撲產生器會將結果發佈至中央管理存放區，以用於設定組織中所有執行 Lync Server 2013 的伺服器。 您無法在不使用拓撲產生器的伺服器上安裝 Lync Server 2013。

如果您在規劃程式期間設計了 edge 拓撲，包括執行拓撲產生器以定義 edge 拓撲，則可以使用這些結果來開始 Edge Server 部署。 如果您先前未完成建立 edge 拓撲，或想變更您先前所指定的資訊，必須先完成執行拓撲產生器，再繼續進行其他部署步驟。 如需如何建立拓撲的詳細資訊，請參閱 [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

如需規劃工具和拓撲產生器的詳細資訊，請參閱規劃檔中的 [開始進行 Lync Server 2013 的規劃程式](lync-server-2013-beginning-the-planning-process.md) 。

下表提供 Edge Server 部署程序的概觀。 若要查看部署外部使用者存取之前必須進行的規劃決策，請參閱 [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

<div>


> [!WARNING]  
> 下表的資訊以全新部署為主。 如果您已在 Lync Server 2010、Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007環境中部署 Edge Server，請參閱 <A href="migration.md">遷移</A> 以瞭解遷移至 Lync Server 2013 的詳細資料。 Office 通訊伺服器 2007 R2 之前的任何版本都不支援遷移，包括 Office 通訊伺服器2007、即時通訊伺服器2005和即時通訊伺服器2003。



</div>

為了提升 Edge Server 效能與安全性，以及協助部署順利進行，請在部署周邊網路和 Edge Server 時套用下列最佳作法：

  - 只有在組織內已測試並驗證 Lync Server 2013 的作業之後，才部署 Edge server。

  - 建議您在工作群組 (而不是網域) 中部署 Edge Server。這麼做可簡化安裝程序，同時將 Active Directory 網域服務 (AD DS) 置於周邊網路之外。將 AD DS 設置在周邊網路中，可能帶來重大的安全風險。

  - 可支援將 Edge Server 加入完全位於周邊網路中的網域，但不建議使用。 Edge Server 作為內部網域的一部分違反了信任網路界限 (其中網際網路最不受信任，周邊網路比網際網路更受信任，而內部網路最受信任)。Edge Server 作為網域的成員會自動成為最受信任網路的一部分，卻位於較不受信任的網路中 (周邊網路)。

<div>

## <a name="deployment-process-for-edge-servers"></a>Edge Server 部署程序


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>權限</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建立適當的 Edge 拓撲，並決定適當的元件。</p></td>
<td><ul>
<li><p>執行拓撲產生器以設定 Edge Server 設定，以及建立及發行拓撲，然後使用 Lync Server 管理命令介面來匯出拓撲設定檔。</p></li>
</ul></td>
<td><p><strong>Domain Admins</strong> 群組和 <strong>RTCUniversalServerAdmins</strong> 或 <strong>CsAdmins</strong> 群組</p>
<div>

> [!NOTE]  
> 您可以使用本機使用者群組的成員帳戶來定義拓撲，但發行拓撲需要以 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組的成員帳戶進行。


</div></td>
<td><p>在部署檔中的<a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 中建立 edge 和 Director 拓撲</a></p></td>
</tr>
<tr class="even">
<td><p>準備進行安裝。</p></td>
<td><ol>
<li><p>確定已符合系統先決條件。</p></li>
<li><p>在每部 Edge Server 上，設定內部與公開網路介面的 IP 位址 (IPv4 和 IPv6，如果使用的話)。</p></li>
<li><p>設定內部與外部 DNS 記錄 (IPv4 和 IPv6 的主機 A 和 AAAA)，包括在要部署為 Edge Server 的電腦上設定 DNS 尾碼。</p></li>
<li><p>(選用) 建立並安裝公用憑證。取得憑證所需的時間，視發出憑證的憑證授權單位 (CA) 而定。如果您此時不執行這個步驟，也必須在 Edge Server 安裝期間執行。未取得並安裝憑證前，Edge Server Service 無法啟動。</p></li>
<li><p>佈建公用 IM 連線的支援 (如果您的部署是要支援與 Windows Live、AOL 或 Yahoo! 使用者的通訊)。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>


</div></li>
<li><p>若您的部署會使用這些服務，請提供 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 合作夥伴的 XMPP 和同盟支援的支援</p></li>
<li><p>設定防火牆。</p></li>
</ol></td>
<td><p>視組織而定</p></td>
<td><p>在部署檔中<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">準備安裝 Lync Server 2013 的周邊網路伺服器</a></p></td>
</tr>
<tr class="odd">
<td><p>設定反向 Proxy。</p></td>
<td><ul>
<li><p>設定反向 proxy (例如，針對 Microsoft Forefront 威脅管理閘道2010或 Microsoft Internet Security and 加速 (ISA) Server Service Pack 1) 在周邊網路中，取得必要的公用憑證，並在反向 proxy 伺服器上設定網頁發行規則。</p>
<p>如果已為行動性做規劃，並且要在前端集區或 Standard Edition Server 上部署行動性服務，請準備好行動性服務的反向 Proxy。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> 群組或反向 Proxy 管理員</p></td>
<td><p>在部署檔中<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">設定 Lync Server 2013 的反向 proxy 伺服器</a></p></td>
</tr>
<tr class="even">
<td><p>安裝 Director (選用)。</p></td>
<td><ul>
<li><p>(選用) 在內部網路安裝並設定一個或多個 Director。</p></li>
</ul></td>
<td><p><strong>Administrators</strong> 群組</p></td>
<td><p>部署檔中的<a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 設定 Director</a></p></td>
</tr>
<tr class="odd">
<td><p>設定 Edge Server。</p></td>
<td><ol>
<li><p>安裝必要軟體。</p></li>
<li><p>將匯出的拓撲組態檔傳輸給每部 Edge Server。</p></li>
<li><p>在每一部 Edge Server 上安裝 Lync Server 2013 軟體。</p></li>
<li><p>設定 Edge Server。</p></li>
<li><p>為每一部 Edge Server 要求並安裝憑證。</p></li>
<li><p>啟動 Edge Server 服務。</p></li>
</ol></td>
<td><p><strong>Administrators</strong> 群組</p></td>
<td><p>部署檔中的<a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013 設定 Edge</a> server</p></td>
</tr>
<tr class="even">
<td><p>設定部署以進行外部使用者存取。</p></td>
<td><ol>
<li><p>使用 Lync Server 控制台，設定下列每個 (的支援（如適用）) ：</p>
<ul>
<li><p>媒體中繼</p></li>
<li><p>同盟路由</p></li>
<li><p>遠端使用者存取</p></li>
<li><p>與 Lync Server、Office 通訊伺服器和即時通訊伺服器的同盟</p></li>
<li><p>公共 IM 連線</p></li>
<li><p>XMPP 同盟</p></li>
<li><p>匿名使用者</p></li>
</ul></li>
<li><p>設定使用者帳戶以進行遠端使用者存取、同盟、公用 IM 連線、XMPP 和匿名使用者支援 (若適用)</p></li>
</ol></td>
<td><p>指派給 <strong>CSAdministrator</strong> 角色的 <strong>RTCUniversalServerAdmins</strong> 群組或使用者帳戶</p></td>
<td><p>在部署檔中設定<a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 中外部使用者存取的支援</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證您的 Edge Server 設定。</p></td>
<td><ol>
<li><p>驗證伺服器連線以及內部伺服器組態資料的複寫是否正確。</p></li>
<li><p>驗證外部使用者 (包括遠端使用者、同盟網域的使用者、公用 IM 使用者和匿名使用者，視您的部署而定) 是否能連線。</p></li>
<li><p>使用 Lync Server Remote Connectivity Analyzer 驗證設定和通訊 <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>疑難排解設定及通訊問題</p></li>
</ol></td>
<td><p>若為驗證複寫，為指派給 <strong>CSAdministrator</strong> 角色的 <strong>RTCUniversalServerAdmins</strong> 群組或使用者帳戶</p>
<p>若為驗證使用者連線，則為您支援之每種外部使用者存取類型的使用者</p>
<p>遠端使用者</p></td>
<td><p>在部署檔中<a href="lync-server-2013-verifying-your-edge-deployment.md">驗證 Lync Server 2013 中的 edge 部署</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

