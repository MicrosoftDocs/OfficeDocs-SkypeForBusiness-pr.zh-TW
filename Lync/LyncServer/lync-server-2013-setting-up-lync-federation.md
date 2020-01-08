---
title: Lync Server 2013：設定 Lync 同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6dc0a2aeb39c86db54d21a2c4be5ff6c5be599
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Lync 同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-27_

如果您已經部署了 Edge 伺服器或伺服器，新增同盟案例功能就會是直向。 如果您沒有設定邊緣伺服器，您必須先執行此動作。 如需詳細資訊，請參閱：在[Lync server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)在 [部署] 檔中的 [規劃檔] 和 [在[lync Server 2013 中部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)]。

<div>


> [!NOTE]  
> 如果您想要設定 XMPP 同盟、Lync 同盟或公用立即訊息連線的任何組合，您可以同時部署它們或一次一個。 如果您是透過拓撲產生器和 Lync Server 管理命令介面設定選項，請在 Edge 伺服器上執行部署嚮導，然後再針對其中一個、兩個或全部三個同盟類型設定選項之後，您就可以減少所需的步驟數。



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>在拓撲建立器和 [部署嚮導] 中設定 Lync 同盟

1.  在前端伺服器上，開啟 [拓撲建立器]。 展開 [邊緣池]，然後以滑鼠右鍵按一下 Edge 伺服器或 Edge 伺服器池。 選取 [編輯屬性]。

2.  在 [編輯屬性] 底下的 [一般] 底下，選取 [針對此 Edge 池啟用同盟（埠5061）]。 按一下 [確定]。

3.  按一下 [動作]，選取 [拓撲]，選取 [發佈]。 發佈拓撲時出現提示時，請按 [下一步]。 發佈完成後，請按一下 [完成]。

4.  在邊緣伺服器上，開啟 Lync Server 部署嚮導。 按一下 [安裝或更新 Lync Server 系統]，然後按一下 [設定] 或 [移除 Lync Server 元件]。 再次按一下 [執行]。

5.  在安裝程式 Lync Server 元件上，按一下 [下一步]。 [摘要] 畫面會在執行時顯示動作。 完成部署之後，按一下 [查看記錄] 以查看可用的記錄檔。 按一下 [完成] 以完成部署。
    
    <div>
    

    > [!IMPORTANT]  
    > 您可以選取這個選項，但貴組織中只有一個邊界池或邊緣伺服器可以在外部針對同盟進行發佈。 同盟使用者的所有存取權，包括公用立即訊息（IM）使用者，請流覽相同的邊緣池或單層伺服器。 例如，如果您的部署包含在紐約部署的邊緣池或單層伺服器，且在倫敦部署，且您在紐約的邊緣池或單一邊緣伺服器上啟用同盟支援，則聯盟使用者的信號流量將會透過紐約進行。[邊緣] 池或 [單一邊緣] 伺服器。 儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>設定與合作夥伴的同盟

1.  若要設定成功的同盟與另一個 Microsoft Lync Server 2013、Lync Server 2010、Office 通訊伺服器 2007 R2 或 Office Communicator 2007，請從下表中選取同盟類型，並定義 DNS SRV 記錄、DNS 主機（A 或 AAAA）。IPv6）並設定適用于同盟類型的原則：
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>同盟類型</th>
    <th>DNS 記錄</th>
    <th>原則定義</th>
    <th>筆記</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>已發現合作夥伴網域</p></td>
    <td><p>設定 _sipfederationtls 格式的 SRV 記錄。 _tcp。&lt;外部功能變數名稱，&gt;其中 SRV 記錄的埠值是 TCP 5061，而<strong>提供此服務的主機</strong>定義為 sip。 &lt;外部功能變數名稱&gt; -您的存取邊緣服務的 FQDN。 如需建立 SRV 記錄的詳細資料，請參閱<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定 edge 支援 DNS</a></p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中啟用或停用探索同盟協力廠商</a></p></li>
    </ul></td>
    <td><p>先前版本會參照此同盟類型，即<strong>開啟增強型同盟</strong>。 此類型的同盟需要建立 SRV 記錄，並允許其他夥伴探索您的同盟。</p></td>
    </tr>
    <tr class="even">
    <td><p>允許的合作夥伴網域</p></td>
    <td><p>設定 _sipfederationtls 格式的 SRV 記錄。 _tcp。&lt;外部功能變數名稱，&gt;其中 SRV 記錄的埠值是 TCP 5061，而<strong>提供此服務的主機</strong>定義為 sip。 &lt;外部功能變數名稱&gt; -您的存取邊緣服務的 FQDN。 如需建立 SRV 記錄的詳細資料，請參閱<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中設定 edge 支援 DNS</a></p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></li>
    </ul></td>
    <td><p>先前版本稱為此同盟類型為 [<strong>增強聯盟</strong>]。 對於這種類型的同盟而言，SRV 記錄的建立是選用的，而且是允許其他夥伴探索您的同盟。 當然，這是<strong>開啟的增強聯盟</strong>，或已<strong>發現的合作夥伴網域</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>允許的合作夥伴伺服器</p></td>
    <td><p>在原則中將 SIP 功能變數名稱與夥伴邊緣伺服器 FQDN 設定為同盟夥伴</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">在 Lync Server 2013 中針對允許的外部網域設定支援</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">在 Lync Server 2013 中為封鎖的外部網域設定支援</a></p></li>
    </ul></td>
    <td><p>此同盟類型是單一關聯的定義，不允許發現其他同盟夥伴。 每個同盟夥伴都是明確設定的。 在舊版中，這稱為<strong>直接同盟</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>主機服務提供者和公用 IM 提供者</p></td>
    <td><p>此類型同盟沒有定義任何特定的 DNS 需求</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">建立或編輯主控的 SIP 同盟提供者 Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>此同盟類型定義您想要為使用者設定的服務與主機服務提供者。 典型用途包括公用 IM 提供者的設定，例如 Windows Live Messenger、Yahoo！ 與 AOL，以及主機服務提供者（例如 Lync Online 和 Office 365）</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
    > <LI>
    > <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
    > <LI>
    > <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  定義並設定任何必要的 DNS 主機（A 或 AAAA IPv6）和 DNS SRV 記錄

3.  使用 Lync Server [控制台] 或使用 Lync Server 管理命令介面和適當的 Cmdlet 來定義及設定任何原則。 如需 Lync Server 管理命令介面 Cmdlet 的詳細資料，請參閱[Lync server 2013 中的同盟與外部存取 Cmdlet](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync 會議室系統（LRS）不會針對聯盟 Lync 合作夥伴中的召集人所傳送的會議顯示 [加入] 按鈕。 若要在 LRS 上顯示會議加入連結，傳送組織必須使用下列 Cmdlet 來啟用 TNEF：<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>請注意，這不是 LRS 的特定功能。 在這種情況下，outlook 和 Lync 也不會顯示聯結連結，因為 MAPI 屬性不會傳輸，但在 Outlook 案例中，使用者可以開啟會議邀請，然後按一下會議 URL。 當 TNEFEnabled 設定為 true 時，Exchange 2013 不會去除 MAPI 屬性（包括 OnlineMeetingExternalLink），而且會在提醒上顯示 [加入] 按鈕。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[管理 Lync Server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

