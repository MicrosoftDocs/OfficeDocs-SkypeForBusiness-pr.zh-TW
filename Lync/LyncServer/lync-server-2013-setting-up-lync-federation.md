---
title: Lync Server 2013：設定 Lync federation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b955def7b7648f274125353673d6973afb59b7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Lync 同盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-27_

如果您已經部署一或多部 Edge Server，就可以直接新增同盟案例功能。 如果您尚未設定 Edge Server，則必須先進行設定。 如需詳細資訊，請參閱部署檔中的規劃檔及[部署 [Lync server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)] 中的 [在[lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)]。

<div>


> [!NOTE]  
> 如果您想要設定任何 XMPP 同盟、Lync 同盟或 Public Instant Messaging Connectivity 的組合，您可以同時部署它們，或者一次部署一個。如果您透過拓撲產生器和 Lync Server 管理命令介面設定選項，接著在設定一個、兩個或三個同盟類型的選項之後，於 Edge Server 上執行部署精靈，則您可以減少必要的步驟數。



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>在拓撲產生器和部署精靈中設定 Lync 同盟

1.  在前端伺服器上，開啟 [拓撲產生器]。展開 Edge 集區，然後按一下您的 Edge Server 或 Edge Server 集區。選取 [編輯內容]。

2.  在 [編輯內容] 的 [一般] 下方，選取 [啟用此 Edge 集區的同盟 (連接埠 5061)]。按一下 [確定]。

3.  按一下 [動作]，然後依序選取 [拓撲] 和 [發行]。出現發行拓撲的提示時，按 [下一步]。完成發行時，按一下 [完成]。

4.  在 Edge Server 上，開啟 [Lync Server 部署精靈]。按一下 [安裝或更新 Lync Server 系統]，然後按一下 [安裝或移除 Lync Server 元件]。按一下 [再執行一次]。

5.  在 [安裝 Lync Server 元件] 上，按 [下一步]。摘要畫面將顯示它們執行的動作。部署完成之後，按一下 [檢視記錄] 以檢視可用的記錄檔。按一下 [完成] 以完成部署。
    
    <div>
    

    > [!IMPORTANT]  
    > 您可以選取此選項，但是只能將組織中的一個 Edge 集區或 Edge Server 發行到外部，以進行同盟。所有由同盟使用者 (包括公用立即訊息 (IM) 使用者) 進行的存取都會通過相同的 Edge 集區或單一 Edge Server。例如，如果您的部署範圍包括分別部署在紐約與倫敦的一個 Edge 集區或單一 Edge Server，而您針對紐約的 Edge 集區或單一 Edge Server 啟用了同盟支援，則同盟使用者的訊號流量會通過紐約的 Edge 集區或單一 Edge Server。儘管位於倫敦的內部使用者在致電倫敦的同盟使用者時，使用了倫敦集區或 Edge Server 以傳送音訊/視訊流量，與倫敦的使用者進行通訊時也適用這種情況。

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>設定與協力廠商同盟

1.  若要設定與其他 Microsoft Lync Server 2013、Lync Server 2010、Office 通訊伺服器 2007 R2 或 Office Communicator 2007 的成功同盟，請選取下表的同盟類型及定義 DNS SRV 記錄、DNS 主機（A 或 AAAA 用於 IPv6）及設定適用于同盟類型的原則：
    
    
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
    <th>附註</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>探索到的協力廠商網域</p></td>
    <td><p>設定 _sipfederationtls 格式的 SRV 記錄。 _tcp。 &lt;外部功能變數名稱 &gt; ，其中 SRV 記錄的埠值為 TCP 5061，而<strong>提供此服務的主機</strong>是定義為 sip。 &lt;外部功能變數名稱 &gt; – Access Edge service 的 FQDN。 如需建立 SRV 記錄的詳細資訊，請參閱<a href="lync-server-2013-configure-dns-for-edge-support.md">CONFIGURE DNS for edge support In Lync Server 2013</a> 。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中啟用或停用同盟協力廠商的探索</a></p></li>
    </ul></td>
    <td><p>舊版將此類型的同盟稱為<strong>「開放式增強型同盟」</strong>。您必須針對此類型的同盟建立 SRV 記錄，以允許其他協力廠商探索您的同盟。</p></td>
    </tr>
    <tr class="even">
    <td><p>允許的協力廠商網域</p></td>
    <td><p>設定 _sipfederationtls 格式的 SRV 記錄。 _tcp。 &lt;外部功能變數名稱 &gt; ，其中 SRV 記錄的埠值為 TCP 5061，而<strong>提供此服務的主機</strong>是定義為 sip。 &lt;外部功能變數名稱 &gt; – Access Edge service 的 FQDN。 如需建立 SRV 記錄的詳細資訊，請參閱<a href="lync-server-2013-configure-dns-for-edge-support.md">CONFIGURE DNS for edge support In Lync Server 2013</a> 。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></li>
    </ul></td>
    <td><p>先前版本稱為這類同盟為<strong>增強型同盟</strong>。 您可以選擇性地針對此類型的同盟建立 SRV 記錄，以允許其他協力廠商探索您的同盟。 當然，這就是<strong>「開放式增強型同盟」</strong>或<strong>「探索到的協力廠商網域」</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p>允許的協力廠商伺服器</p></td>
    <td><p>將 SIP 功能變數名稱和協力廠商 Edge Server FQDN 設定為原則中的同盟夥伴</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">在 Lync Server 2013 中為允許的外部網域設定支援</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">在 Lync Server 2013 中為封鎖的外部網域設定支援</a></p></li>
    </ul></td>
    <td><p>此同盟類型為一對一關聯性的定義，不允許其他同盟協力廠商進行探索。每個同盟協力廠商都已明確設定。在舊版中，這稱為<strong>「直接同盟」</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>裝載提供者和公用 IM 提供者</p></td>
    <td><p>未針對此類型的同盟定義任何特定的 DNS 需求</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">建立或編輯主控的 SIP 同盟提供者 Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>此同盟類型定義您要為使用者設定的服務和裝載提供者。 一般用法包含針對像是 Windows Live Messenger、Yahoo! 和 AOL，以及主控服務提供者（如 Lync Online 和 Microsoft 365）</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>從2012年9月1日起，Microsoft Lync 公開 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
    > <LI>
    > <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
    > <LI>
    > <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  定義和設定任何必要的 DNS 主機 (適用於 IPv6 的 A 或 AAAA) 和 DNS SRV 記錄

3.  使用 Lync Server 控制台或使用 Lync Server 管理命令介面及適當的指令程式，來定義及設定任何原則。 如需 Lync Server 管理命令介面 Cmdlet 的詳細資訊，請參閱[Lync server 2013 中的同盟和外部訪問 Cmdlet](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync 會議室系統（LRS）不會顯示同盟 Lync 合作夥伴中召集人所傳送之會議的 [加入] 按鈕。 若要在 LRS 上顯示會議加入連結，傳送組織必須使用下列 Cmdlet 來啟用 TNEF：<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>請注意，這不是 LRS 特定的。 在此情況下，outlook 和 Lync 也不會顯示聯接連結，因為 MAPI 屬性並未傳輸，但是在 Outlook 案例中，使用者可以開啟會議邀請，然後按一下會議 URL。 當 TNEFEnabled 設定為 true Exchange 2013 時，不會去除 MAPI 屬性包含 OnlineMeetingExternalLink，而且會在提醒上顯示 [加入] 按鈕。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃 SIP、XMPP 同盟和公用立即訊息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[管理 Lync Server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

