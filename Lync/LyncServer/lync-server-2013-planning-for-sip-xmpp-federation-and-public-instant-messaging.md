---
title: 規劃 SIP、XMPP 同盟和公用立即訊息
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
ms.openlocfilehash: 4148cd97ec118a223e7e8b1b1e8c3825f51dbad6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>在 Lync Server 2013 中規劃 SIP、XMPP 同盟和公用立即訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-28_

您可以設定 Edge Server，以允許您的內部和外部使用者存取夥伴組織或服務上的連絡人。 這些合作夥伴合約稱為「同盟」，可提供貴組織的連絡人對合作夥伴同盟，或者合作夥伴同盟的連絡人對貴組織，下列任一或所有的功能：

  - 立即訊息和目前狀態

  - 共同作業和會議，例如：Web 會議

  - 音訊會議、視訊會議，或兩者

在某些情況下，通訊（如立即訊息（IM）和目前狀態通訊協定（XMPP）連絡人）2013之間的通訊是對等的，僅支援您和同盟合作夥伴的連絡人。 在其他情況下，例如 Lync Server、Lync Server 2010 to Lync Server 2013 同盟，可邀請多位參與者加入交談。

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Lync Server 和 Office 通訊伺服器同盟

Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間的同盟可支援對等與多方通訊。 對等交談可以呈報給多方交談，以允許點對點會議。 會議– Web 會議或音訊/視頻/視覺會議–可以排定在組織內的連絡人，以及您同盟的夥伴中的連絡人。

同盟會先出現在 Microsoft Office Live 通訊伺服器2005中，並支援一種同盟、直接同盟。 直接同盟需要您知道同盟協力廠商的會話初始通訊協定（SIP）網域，以及夥伴的 Edge Server 的完整功能變數名稱（FQDN）。 Live 通訊伺服器2005與 SP1 引進其他的同盟類型，同盟協力廠商所需要的網域名稱系統（DNS） SRV 記錄，以找出其 Edge Server。 該版本的術語如下：

  - *開啟增強型同盟*：接受任何 SIP 功能變數名稱，並使用 DNS SRV 尋找合作夥伴 Edge Server

  - *增強型同盟*：將合作者的 SIP 功能變數名稱設定為組織的同盟夥伴，並使用 DNS SRV 尋找合作夥伴 Edge Server

  - *直接同盟*：設定夥伴的 SIP 功能變數名稱和 FQDN 至夥伴的 Edge Server

  - *伺服器允許清單*：接受任何網域，使用 DNS SRV 尋找主機服務提供者或公用立即訊息（IM）連線提供者的 Edge Server

Microsoft Office 通訊伺服器2007引進同盟類型的更新命名，以更好地定義每個同盟類型實際完成的專案：

  - 開啟增強型同盟成為所謂的已*探索夥伴網域*

  - 增強型同盟成為所謂的*允許夥伴網域*

  - 直接同盟成為所謂的*允許夥伴伺服器*

  - 伺服器允許清單被稱為「*裝載提供者*」和「*公用 IM 提供者*」

Microsoft Lync Server 2010 會依照 Microsoft Lync Online 2010 和 Microsoft Office 365 引進主機提供者較窄的定義，也就是遵守允許的協力廠商域同盟類型所定義的相同允許清單。

在 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間啟用同盟，即可使用 Edge server 和反向 proxy 來強制執行所定義的規則及允許的夥伴網域。 從規劃的觀點來看，與其他 Lync Server 同盟，Office 通訊伺服器需要下列各項：

  - 在拓撲產生器中啟用同盟。 如需詳細資訊，請參閱部署主題設定[SIP 同盟、XMPP 同盟和 public 立即訊息 In Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)。

  - 決定同盟網域探索的需求：
    
      - <span></span>  
        若要手動設定同盟，您必須具有夥伴之 Edge Server 和功能變數名稱的完整功能變數名稱（FQDN），或在 Lync Server 控制台、**同盟和外部存取**（ **SIP 同盟網域**）中輸入的線上功能變數名稱。 建立**新**原則或**編輯**現有原則，以允許或封鎖 FQDN 的網域。
        
        <div>
        

        > [!WARNING]
        > 當夥伴變更其 Edge Server 的 IP 位址時，同盟協力廠商的 Edge Server 的手動設定便很容易失敗。

        
        </div>
        
        <div>
        

        > [!NOTE]
        > 針對<STRONG>新的 SIP 同盟網域</STRONG>，您必須提供 Microsoft Lync Online 和 microsoft 365 或 Office 365 的<STRONG>功能變數名稱（或 FQDN）</STRONG> 。 針對 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器，您也必須提供<STRONG>Access Edge service （FQDN）</STRONG>

        
        </div>
    
      - <span></span>  
        在已探索的夥伴同盟中，協力廠商可以探索您的 Edge Server，您可以在外部 DNS sipfederationtls 中建立 SRV 記錄 \_ 。 \_tcp.contoso.com –哪些指向您 Edge Server 的埠5061和主機（A）記錄
        
        <div>
        

        > [!IMPORTANT]
        > 如果您要在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 裝置上支援 Microsoft Lync 行動用戶端，且使用推播通知服務或推播通知服務，您必須規劃 _sipfederationtls。 _tcp。 &lt;&gt;您擁有 Lync Mobile 用戶端之每個 sip 網域的 SIP 網域 SRV 記錄。 Android 和 Nokia Symbian Lync Mobile 不會使用推播通知，也不會受到此項需求的制約。

        
        </div>

  - 設定外部使用者存取原則以支援同盟網域

  - 開啟防火牆埠的會話初始通訊協定（SIP）、web 會議與音訊/視覺效果，以容納您要啟用的同盟或連絡人。 如需詳細資訊，請參閱：[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

下列資訊可協助您為與 Microsoft Lync Server 2013 和 Lync Server 2010 的同盟定義憑證、埠/通訊協定和 DNS 需求。

若您已規劃或部署 Microsoft Lync Server 2013 Edge server，則規劃憑證、防火牆及埠/通訊協定需求和 DNS 需求通常是直接的向前處理。 因為同盟是另一個使用現有 Edge Server 的功能，所以 Edge Server 規劃及部署一般會滿足規劃需求。 您應該使用下表來判斷是否符合您的需求，並對埠/通訊協定和 DNS 作出適當的變更。

<div>


> [!IMPORTANT]
> 如果您有一部 Edge server 集區，且與 Lync Server 2013 或 Lync Server 2010 合作夥伴同盟，您可以在 Edge server 的內部及外部方端上使用 DNS 負載平衡或硬體負載平衡器。 如果您與 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 同盟，硬體負載平衡會在 Edge Server 的事件中提供容錯移轉支援。 Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 不是 DNS 負載平衡感知。 夥伴 Edge Server 會與集區中的第一個 Edge Server 進行通訊，以進行回應。 如果該 Edge Server 失敗，通訊不會自動容錯移轉。



</div>

憑證需求通常是透過規劃您所選 Edge Server 或集區 Edge Server 計畫的憑證所獲得。

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>公用立即訊息連線能力

公用立即訊息連線是同盟的類別，設定為允許您的內部及外部 Lync Server 2013 使用者從下列任何專案新增連絡人：

  - 信使連絡人

  - 雅虎\! 接觸

  - 美洲線上（AOL）連絡人

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（PIC USL）已無法再供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期（確切的日期仍會決定，但不會早于6月2013）。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的每一使用者、每月訂閱授權。 信使。 Microsoft 提供此服務的能力已因 Yahoo！的支援而產生，不會更新的基準合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以透過 IM 和語音來抵達數百個人的人員。</P></LI></UL>



</div>

這個同盟類別需要下列規劃考慮：

  - Windows Live Messenger 使用者除了立即訊息之外，還可以與 Lync Server 2013 使用者進行對等音訊/視覺通訊。 您的 Edge Server 必須符合特定埠和通訊協定的需求。 如需詳細資訊，請參閱[決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

  - 在規劃及部署提供同盟之典型 Edge Server 的情況下，Yahoo 立即訊息沒有獨特的需求。

  - 北美洲線上要求指派給 Access Edge service 的 Edge Server 憑證具有用戶端增強金鑰使用方式（EKU）。

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>可延伸的訊息和顯示狀態通訊協定（XMPP）同盟

舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和顯示狀態通訊協定（XMPP）閘道，可將其部署成個別的伺服器角色，以允許與 XMPP 部署同盟。 在 Microsoft Lync Server 2013 中，可以將 XMPP 功能部署為功能。 XMPP 功能是以兩個部分安裝：在 Edge Server 上執行的 XMPP proxy，以及在前端伺服器上執行的 XMPP 閘道。

XMPP 的部署和設定涵蓋在[Lync Server 2013 的部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)中，您可以在防火牆上定義埠和通訊協定規則、憑證的設定，以及新增 DNS 記錄，以支援組織中的 XMPP。 本節中的下列主題摘要說明為您的部署成功規劃 XMPP 同盟時所需的資訊。

<div>


> [!IMPORTANT]
> Lync Server 2013 的 XMPP 功能會經過測試，並受 Microsoft 支援，以進行與 Google 交談的立即訊息同盟。 對於任何其他 XMPP 系統，請聯繫協力廠商廠商，以確認其支援與 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。



</div>

<div>


> [!IMPORTANT]
> 在 survivable branch 裝置上的使用者不支援 XMPP 同盟。 這適用于查看顯示狀態資訊和交換 IM 郵件。



</div>

</div>

<div id="sectionSection3" class="section">

在下列主題中，會包含針對支援的同盟案例類型定義憑證、防火牆埠和 DNS 專案的指導方針。

  - <span></span>  
    [Lync Server 2013 中的憑證摘要-SIP、XMPP 同盟和公用立即訊息](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Lync Server 2013 中的埠摘要-SIP、XMPP 同盟和公用立即訊息](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Lync Server 2013 中的 DNS 摘要-SIP、XMPP 同盟和公用立即訊息](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定控制同盟使用者存取的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
[決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)  


[在 Lync Server 2013 中管理組織的 Access Edge 設定](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[在 Lync Server 2013 中管理組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[在 Lync Server 2013 中管理組織的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

