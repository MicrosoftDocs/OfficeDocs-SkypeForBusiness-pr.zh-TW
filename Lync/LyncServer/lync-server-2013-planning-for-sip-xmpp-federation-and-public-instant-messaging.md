---
title: 規劃 SIP、XMPP 同盟及公用立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 994a1395363c28976c8bbfe325edae99e97cdc48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-28_

您可以將 Edge 伺服器設定為允許您的內部與外部使用者存取合作夥伴組織或服務的連絡人。 同盟（因為這些合作夥伴協定是已知的）可將下列任何或所有專案提供給您組織中的連絡人，或是合作夥伴同盟中的連絡人：

  - 立即訊息與顯示狀態

  - 共同作業與會議，例如網路會議

  - 音訊會議、視訊會議或兩者

在某些情況下，通訊（例如立即訊息（IM），以及在 Microsoft Lync Server 2013 與可擴展的訊息和目前狀態通訊協定（XMPP）連絡人之間的狀態，只支援對等使用者以及同盟中的連絡人partner. 在其他情況下（例如 Lync 伺服器），Lync server 2010 to Lync Server 2013 同盟，可邀請多個參與者加入交談。

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Lync Server 和 Office 通訊伺服器同盟

Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間的同盟支援對等與多方通訊。 對等交談可以上報給多個參與方交談，以便進行即席會議。 [會議-網路會議] 或 [音訊/視覺會議]-可安排在您的組織內加入連絡人，以及與您聯盟的合作夥伴中的連絡人。

同盟會先出現在 Microsoft Office Live 迅 Server 2005 中，並且支援一種類型的同盟（直接聯盟）。 直接同盟需要您知道同盟夥伴的會話初始通訊協定（SIP）網域以及合作夥伴邊緣伺服器的完整功能變數名稱（FQDN）。 即時通訊伺服器2005（含 SP1）引進了其他聯合體類型，聯盟夥伴必須發佈所有需要的網域名稱系統（DNS） SRV 記錄，才能找出其 Edge 伺服器。 該版本的術語為：

  - *開啟加強聯盟*：接受任何 SIP 功能變數名稱，並使用 DNS SRV 來尋找合作夥伴邊緣伺服器

  - *增強聯盟*：將合作夥伴的 SIP 功能變數名稱設定為貴組織的同盟夥伴，並使用 DNS SRV 尋找合作夥伴邊緣伺服器

  - *直接聯盟*：將合作夥伴的 SIP 功能變數名稱和 FQDN 設定為合作夥伴的邊緣伺服器

  - *伺服器允許清單*：接受任何網域，請使用 DNS SRV 來尋找主機服務提供者或公用立即訊息（IM）連線提供者的邊緣伺服器

Microsoft Office 通訊伺服器2007引進了同盟類型的更新命名，以更好地定義每個同盟類型實際完成的專案：

  - 開啟的加強聯盟稱為「已*探索夥伴網域*」

  - 增強聯盟成為「*允許的夥伴網域*」

  - 直接同盟成為「*允許的合作夥伴伺服器*」

  - 伺服器允許清單已成為*託管提供者*和*公用 IM 提供者*

Microsoft Lync Server 2010 會根據 Microsoft Lync Online 2010 和 Microsoft Office 365，以較窄的方式定義主機服務提供者，同時也使其遵守允許的合作夥伴網域同盟類型所定義的同一個允許清單。

在 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間啟用同盟，就會使用 Edge 伺服器和反向代理伺服器來強制執行您定義的規則及允許的夥伴網域。 從規劃的角度來看，與其他 Lync 伺服器進行聯盟，Office 通訊伺服器需要下列各項：

  - 在拓撲建立器中啟用同盟。 如需詳細資訊，請參閱[在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及公用立即訊息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)的部署主題。

  - 判斷您的聯盟網域探索需求：
    
      - <span></span>  
        如需手動設定聯盟，您必須具備合作夥伴的邊緣伺服器和功能變數名稱的完整功能變數名稱（FQDN），或是在 Lync Server 控制台、**同盟及外部存取**、 **SIP 聯盟網域**中輸入的線上功能變數名稱。 建立**新**原則，或**編輯**現有的原則，以允許或封鎖 FQDN 的網域。
        
        <div>
        

        > [!WARNING]
        > 如果合作夥伴變更其 Edge 伺服器的 IP 位址，則聯盟夥伴的邊緣伺服器的手動設定就很容易失敗。

        
        </div>
        
        <div>
        

        > [!NOTE]
        > 針對<STRONG>新的 SIP 聯盟網域</STRONG>，您必須提供 Microsoft Lync Online、microsoft Office 365 的<STRONG>功能變數名稱（或 FQDN）</STRONG> 。 針對 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器，您也必須提供<STRONG>存取邊緣服務（FQDN）</STRONG>

        
        </div>
    
      - <span></span>  
        針對已探索的合作夥伴同盟，合作夥伴可以在其中探索您的 Edge 伺服器，您可以在外部 DNS \_sipfederationtls 中建立 SRV 記錄。\_tcp.contoso.com –哪些指向邊緣伺服器的埠5061和主機（A）記錄
        
        <div>
        

        > [!IMPORTANT]
        > 如果您在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 裝置上支援 Microsoft Lync Mobile 用戶端，且使用推播通知服務或推播通知服務，您必須規劃 _sipfederationtls _tcp。 &lt;您擁有&gt; Lync 行動用戶端之每個 SIP 網域的 SIP 網域 SRV 記錄。 Android 和 Nokia Symbian Lync Mobile 不使用推播通知，也不受此需求。

        
        </div>

  - 設定外部使用者存取原則以支援聯盟網域

  - 開啟 [會話初始化通訊協定] （SIP）、[web 會議] 和 [音訊/視覺] 的防火牆埠，以適應您要啟用的同盟或連絡人。 如需詳細資訊，請參閱：[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

下列資訊將協助您針對使用 Microsoft Lync Server 2013 和 Lync Server 2010 的同盟定義憑證、埠/通訊協定及 DNS 需求。

如果您已規劃或部署 Microsoft Lync Server 2013 Edge 伺服器，則規劃憑證、防火牆和埠/通訊協定需求以及 DNS 需求通常是一個直接的轉寄程式。 因為同盟是使用現有邊緣伺服器的其他功能，所以 Edge 伺服器規劃和部署通常都能滿足規劃需求。 您應該使用下清單格來判斷符合您的需求，並據此變更埠/通訊協定及 DNS。

<div>


> [!IMPORTANT]
> 如果您有一個 Edge 伺服器池，且正在與 Lync Server 2013 或 Lync Server 2010 合作夥伴進行聯盟，則您可以在邊緣伺服器的內部和外部方端上使用 DNS 負載平衡或硬體負載平衡器。 如果您是使用 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 進行聯盟，則硬體負載平衡將在 Edge 伺服器的事件中提供容錯移轉支援。 Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 不是 DNS 負載平衡感知。 夥伴邊緣伺服器會與您在池中回應的第一個邊緣伺服器進行通訊。 如果該 Edge 伺服器發生故障，通訊就不會自動進行容錯移轉。



</div>

證書需求通常是透過針對您所選的邊緣伺服器或彙集邊緣伺服器方案的憑證規劃來達到。

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>公用立即訊息連線

公用立即訊息連線是一種聯盟類別，並設定為允許您的內部和外部 Lync Server 2013 使用者從下列任何專案新增連絡人：

  - 信使連絡人

  - Yahoo\! 聯絡

  - 美洲線上（AOL）連絡人

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（PIC USL）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期（確切日期仍會決定，但不會早于6月2013）。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟所需的每個使用者、每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，不會更新的底層合約。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 Skype 同盟將會新增到此清單，讓 Lync 使用者能夠透過 IM 和語音來取得成百上千的人員。</P></LI></UL>



</div>

此同盟類別需要下列規劃考慮：

  - 除了立即訊息之外，Windows Live Messenger 使用者也可以與 Lync Server 2013 使用者進行對等音訊/視覺通訊。 您的邊緣伺服器必須符合特定的埠和通訊協定需求。 如需詳細資訊，請參閱[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

  - Yahoo [立即訊息] 沒有任何獨特的需求，除了在提供同盟的一般邊緣伺服器規劃和部署中通常所使用的情況。

  - 美洲線上要求指派給存取邊緣服務的 Edge 伺服器憑證具有用戶端增強型金鑰用法（EKU）。

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>可擴展訊息和目前狀態通訊協定（XMPP）同盟

舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和目前狀態通訊協定（XMPP）閘道，可將其部署為個別的伺服器角色，以允許與 XMPP 部署進行聯盟。 在 Microsoft Lync Server 2013 中，您可以將 XMPP 功能部署為功能。 XMPP 功能是由兩個部分所安裝：在 Edge 伺服器上執行的 XMPP proxy，以及在前端伺服器上執行的 XMPP 閘道。

XMPP 的部署與設定在[Lync Server 2013 中的 [部署外部使用者存取權](lync-server-2013-deploying-external-user-access.md)] 中，您打算在防火牆上定義埠和通訊協定規則、設定憑證的設定，以及新增 DNS 記錄，以規劃支援組織中的 XMPP。 本節中的下列主題摘要說明為您的部署順利規劃 XMPP 同盟時所需的資訊。

<div>


> [!IMPORTANT]
> Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。 針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。



</div>

<div>


> [!IMPORTANT]
> 託管在 survivable 分支裝置上的使用者不支援 XMPP 同盟。 這適用于查看目前狀態資訊和交換 IM 訊息。



</div>

</div>

<div id="sectionSection3" class="section">

下列主題包含針對支援的同盟情況類型定義憑證、防火牆埠及 DNS 專案的指導方針。

  - <span></span>  
    [認證摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [埠摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [DNS 摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定控制同盟使用者存取的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[針對 Lync Server 2013 判定 DNS 需求](lync-server-2013-determine-dns-requirements.md)  


[在 Lync Server 2013 中管理組織的 Access Edge 設定](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[在 Lync Server 2013 中管理組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[在 Lync Server 2013 中管理組織的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

