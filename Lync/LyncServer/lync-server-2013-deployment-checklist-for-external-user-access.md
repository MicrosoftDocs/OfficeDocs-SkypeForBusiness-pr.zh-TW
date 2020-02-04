---
title: Lync Server 2013：外部使用者存取的部署檢查表
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
ms.openlocfilehash: 6ad2ad90ab43402babdd10478e1d86cac2a38ddf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中外部使用者存取的部署檢查表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

您必須先部署 Microsoft Lync Server 2013 內部伺服器（包括前端池或標準版伺服器），才能部署周邊網路並實現外部使用者的支援。 如果您打算在內部網路中部署選用的控制器，您也應該在部署邊緣伺服器之前先進行部署。 如需主管部署程式的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)。

Microsoft Lync Server 2013 包含協助規劃及部署內部伺服器與邊緣伺服器的工具。 拓撲完成後，將產生的拓撲定義發佈到您的生產環境。 若要這樣做，您必須是 [**網域管理員**] 群組和 [ **RTCUniversalServerAdmins** ] 群組的成員。

  - **規劃工具**   Office 通訊伺服器 2007 R2 包含規劃工具和 Edge 規劃工具，您可以用來協助引導拓撲設計。 在 Lync Server 2010 中，這兩個工具已結合成單一規劃工具，其中有其他功能，例如收集已規劃的使用者數目、語音需求、外部使用者存取類型，以及同盟選項。 此外，您也可以規劃基礎結構的網路參數，例如 IP 位址、負載平衡器類型及其他周邊網路考慮。

  - **拓撲**   建立程式 Lync Server 2013 拓撲建立器可協助您定義拓撲與元件。 若要部署執行 Lync Server 2013 的伺服器，拓撲建立器是必要的。 [拓撲建立器] 會將結果發佈到中央管理儲存區，用來設定貴組織中所有執行 Lync Server 2013 的伺服器。 您無法在伺服器上安裝 Lync Server 2013，不需要使用拓撲建立器。

如果您是在規劃流程中設計邊緣拓撲，包括執行拓撲建立器以定義邊緣拓撲，您可以使用這些結果來啟動 Edge 伺服器部署。 如果您之前沒有完成建立邊緣拓撲，或者想要變更您先前指定的資訊，您必須先完成執行拓撲建立器，然後再繼續進行其他部署步驟。 如需如何建立拓撲的詳細資料，請參閱[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

如需規劃工具與拓撲建立器的詳細資料，請參閱規劃檔中的[Lync Server 2013 規劃程式](lync-server-2013-beginning-the-planning-process.md)。

下表提供 Edge 伺服器部署程式的概覽。 若要查看部署外部使用者存取之前必須做出的規劃決定，請參閱[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

<div>


> [!WARNING]  
> 下表中的資訊將重點放在新的部署上。 如果您已在 Lync Server 2010、Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007環境中部署 Edge 伺服器，請參閱<A href="migration.md">遷移</A>以取得遷移至 Lync Server 2013 的詳細資料。 Office 通訊伺服器 2007 R2 之前的任何版本都不支援 [遷移]，包括 Office 通訊伺服器2007、[即時通訊伺服器 2005]，以及 [即時通訊伺服器] 2003。



</div>

為了加強邊緣伺服器的效能與安全性，以及協助部署，請在部署周邊網路和 Edge 伺服器時，套用下列最佳做法：

  - 只有在貴組織內部已測試並驗證 Lync Server 2013 的操作後，才會部署 Edge 伺服器。

  - 我們建議您將 Edge 伺服器部署在工作組中，而非網域中。 如此一來簡化安裝，並將 Active Directory 網域服務（AD DS）從周邊網路中保留。 在周邊網路中尋找 AD DS 可能會帶來巨大的安全性風險。

  - 支援將 Edge 伺服器加入完全位於周邊網路的網域，但不建議這樣做。 在內部網域中，邊緣伺服器違反受信任的網路界限，且網際網路最小信任、周邊網路比網際網路更受信任，且內部網路最受信任。 作為網域成員的邊緣伺服器會自動成為最受信任網路的一部分，但位於較不信任的網路（週邊）中。

<div>

## <a name="deployment-process-for-edge-servers"></a>Edge 伺服器的部署程式


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>許可權</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建立適當的邊緣拓撲，並判斷適當的元件。</p></td>
<td><ul>
<li><p>執行拓撲建立器以設定 Edge 伺服器設定，並建立和發佈拓撲，然後使用 Lync Server 管理命令介面匯出拓撲設定檔。</p></li>
</ul></td>
<td><p>[<strong>網域管理員</strong>] 群組和 [ <strong>RTCUniversalServerAdmins</strong> ] 或 [ <strong>CsAdmins</strong> ] 群組</p>
<div>

> [!NOTE]  
> 您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但發佈拓朴需要<STRONG>網域系統管理員</STRONG>群組和 [ <STRONG>RTCUniversalServerAdmins</STRONG> ] 群組成員的帳戶。


</div></td>
<td><p>在部署檔的<a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 中建立邊緣與控制器拓撲</a></p></td>
</tr>
<tr class="even">
<td><p>準備進行設定。</p></td>
<td><ol>
<li><p>確保已滿足系統先決條件。</p></li>
<li><p>針對每個 Edge 伺服器上的內部和公開的網路介面，設定 IP 位址（IPv4 和 IPv6，如果是使用）。</p></li>
<li><p>設定內部和外部 DNS 記錄（IPv4 和 IPv6 的主機 A 和 AAAA），包括在電腦上設定要部署為邊緣伺服器的 DNS 尾碼。</p></li>
<li><p>可選建立及安裝公用憑證。 取得憑證所需的時間取決於憑證授權單位（CA）所頒發的憑證。 如果您目前不執行此步驟，您必須在 Edge 伺服器安裝期間執行此步驟。 在取得並安裝證書之前，無法啟動 Edge 伺服器服務。</p></li>
<li><p>如果您的部署是要支援與 Windows Live、AOL 或 Yahoo！的通訊，請為公用 IM 連線提供支援 使用者.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>


</div></li>
<li><p>針對 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 合作夥伴的 XMPP 及同盟支援提供支援，如果您的部署將使用這些</p></li>
<li><p>設定防火牆。</p></li>
</ol></td>
<td><p>視您的組織而定</p></td>
<td><p>在部署檔中<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">針對 Lync Server 2013 的周邊網路安裝伺服器的準備</a></p></td>
</tr>
<tr class="odd">
<td><p>設定反向 proxy。</p></td>
<td><ul>
<li><p>在周邊網路中設定反向 proxy （例如，針對 Microsoft Forefront 威脅管理閘道2010或 Microsoft Internet 安全性及加速（ISA） Server），取得必要的公用憑證，並將反向 proxy 伺服器上的 web 發佈規則。</p>
<p>如果您已規劃行動，且正在部署前端池或標準版伺服器上的行動服務，請準備行動服務的反向 proxy。</p></li>
</ul></td>
<td><p><strong>管理員</strong>群組或反向 Proxy 管理員</p></td>
<td><p>在部署檔中<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">設定 Lync Server 2013 的反向 proxy 伺服器</a></p></td>
</tr>
<tr class="even">
<td><p>設定導演（選用）。</p></td>
<td><ul>
<li><p>可選在內部網路中安裝並設定一或多個控制器。</p></li>
</ul></td>
<td><p>[<strong>管理員</strong>] 群組</p></td>
<td><p>在部署檔的<a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 中設定導演</a></p></td>
</tr>
<tr class="odd">
<td><p>設定邊緣伺服器。</p></td>
<td><ol>
<li><p>安裝必備軟體。</p></li>
<li><p>將匯出的拓撲設定檔案傳輸到每個邊緣伺服器。</p></li>
<li><p>在每個邊緣伺服器上安裝 Lync Server 2013 軟體。</p></li>
<li><p>設定邊緣伺服器。</p></li>
<li><p>針對每個 Edge 伺服器要求並安裝證書。</p></li>
<li><p>啟動 Edge 伺服器服務。</p></li>
</ol></td>
<td><p>[<strong>管理員</strong>] 群組</p></td>
<td><p>在部署檔的<a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013 中設定 Edge 伺服器</a></p></td>
</tr>
<tr class="even">
<td><p>設定外部使用者存取的部署。</p></td>
<td><ol>
<li><p>使用 Lync Server [控制台] 來設定下列各項的支援（如果適用）：</p>
<ul>
<li><p>媒體轉送</p></li>
<li><p>同盟路由</p></li>
<li><p>遠端使用者存取</p></li>
<li><p>使用 Lync Server、Office 通訊伺服器與即時通訊伺服器的同盟</p></li>
<li><p>公用 IM 連線</p></li>
<li><p>XMPP 同盟</p></li>
<li><p>匿名使用者</p></li>
</ul></li>
<li><p>針對遠端使用者存取、同盟、公用 IM 連線、XMPP 與匿名使用者支援（如果適用的話），設定使用者帳戶。</p></li>
</ol></td>
<td><p>指派給<strong>CSAdministrator</strong>角色的<strong>RTCUniversalServerAdmins</strong>群組或使用者帳戶</p></td>
<td><p>在部署檔中設定<a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 中的外部使用者存取支援</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證 Edge 伺服器設定。</p></td>
<td><ol>
<li><p>驗證服務器連線並從內部伺服器複製配置資料。</p></li>
<li><p>針對您的部署，確認外部使用者可以連線，包括遠端使用者、聯盟網域中的使用者、公用 IM 使用者以及匿名使用者。</p></li>
<li><p>使用 Lync Server 遠端連線分析程式驗證設定和通訊<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></p></li>
<li><p>疑難排解配置和通訊問題</p></li>
</ol></td>
<td><p>針對已指派給<strong>CSAdministrator</strong>角色的複製、 <strong>RTCUniversalServerAdmins</strong>群組或使用者帳戶進行驗證</p>
<p>針對使用者連線驗證，您支援的每個外部使用者存取類型的使用者</p>
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

