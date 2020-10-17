---
title: 規劃 Lync Server 和 Office 通訊伺服器同盟
description: 規劃 Lync Server 和 Office 通訊伺服器同盟。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d7385b8fde27446fb0648802544a8840a0f6276
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552369"
---
# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>規劃 Lync Server 2013 和 Office 通訊伺服器同盟

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-13_

Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間的同盟可支援對等與多方通訊。 對等交談可以呈報給多方交談，以允許點對點會議。 會議– Web 會議或音訊/視頻/視覺會議–可以排定在組織內的連絡人，以及您同盟的夥伴中的連絡人。

同盟會先出現在 Microsoft Office Live 通訊伺服器2005中，並支援一種同盟、直接同盟。 直接同盟需要您知道同盟協力廠商的會話初始通訊協定 (SIP) 網域和夥伴的 Edge Server 的完整功能變數名稱 (FQDN) 。 Live 通訊伺服器2005與 SP1 引進其他的同盟類型，所有必要的網域名稱系統都 (DNS) 可供同盟協力廠商用來找到其 Edge Server 的 SRV 記錄。 該版本的術語如下：

  - *開啟增強型同盟*：接受任何 SIP 功能變數名稱，並使用 DNS SRV 尋找合作夥伴 Edge Server

  - *增強型同盟*：將合作者的 SIP 功能變數名稱設定為組織的同盟夥伴，並使用 DNS SRV 尋找合作夥伴 Edge Server

  - *直接同盟*：設定夥伴的 SIP 功能變數名稱和 FQDN 至夥伴的 Edge Server

  - *伺服器允許清單*：接受任何網域，使用 DNS SRV 尋找主機服務或公用立即訊息 (IM) 連線提供者的 Edge Server

Microsoft Office 通訊伺服器2007引進同盟類型的更新命名，以更好地定義每個同盟類型實際完成的專案：

  - 開啟增強型同盟成為所謂的已 *探索夥伴網域*

  - 增強型同盟成為所謂的 *允許夥伴網域*

  - 直接同盟成為所謂的 *允許夥伴伺服器*

  - 伺服器允許清單被稱為「*裝載提供者*」和「*公用 IM 提供者*」

Microsoft Lync Server 2010 會依照 Microsoft Lync Online 2010 和 Microsoft Office 365 引進主機提供者較窄的定義，也就是遵守允許的協力廠商域同盟類型所定義的相同允許清單。

在 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器之間啟用同盟，即可使用 Edge server 和反向 proxy 來強制執行所定義的規則及允許的夥伴網域。 從規劃的觀點來看，與其他 Lync Server 同盟，Office 通訊伺服器需要下列各項：

  - 在拓撲產生器中啟用同盟。 如需詳細資訊，請參閱部署主題設定 [SIP 同盟、XMPP 同盟和 public 立即訊息 In Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)。

  - 決定同盟網域探索的需求：
    
      - <span></span>  
        若要手動設定同盟，您必須具有夥伴之 Edge Server 和功能變數名稱（或線上功能變數名稱）的功能變數名稱 (FQDN) ，該名稱會在 Lync Server 控制台、 **同盟及外部存取**、 **SIP 同盟網域**中輸入。 建立 **新** 原則或 **編輯** 現有原則，以允許或封鎖 FQDN 的網域。
        
        <div>
        

        > [!WARNING]
        > 當夥伴變更其 Edge Server 的 IP 位址時，同盟協力廠商的 Edge Server 的手動設定便很容易失敗。

        
        </div>
        
        <div>
        

        > [!NOTE]
        > 若為 <STRONG>新的 SIP 同盟網域</STRONG>，您必須提供 <STRONG>功能變數名稱 (或 FQDN) </STRONG> ，以供 Microsoft Lync Online 和 microsoft 365 或 Office 365。 針對 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器，您也必須提供 <STRONG>Access Edge service (FQDN) </STRONG>

        
        </div>
    
      - <span></span>  
        在已探索的夥伴同盟中，協力廠商可以探索您的 Edge Server，您可以在外部 DNS sipfederationtls 中建立 SRV 記錄 \_ 。 \_tcp.contoso.com –哪些指向埠5061，而主機 (Edge Server 的) 記錄
        
        <div>
        

        > [!IMPORTANT]
        > 如果您要在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 裝置上支援 Microsoft Lync 行動用戶端，且使用推播通知服務或推播通知服務，您必須規劃 _sipfederationtls _tcp。 &lt;&gt;您擁有 Lync Mobile 用戶端之每個 sip 網域的 SIP 網域 SRV 記錄。 Android 和 Nokia Symbian Lync Mobile 不會使用推播通知，也不會受到此項需求的制約。

        
        </div>

  - 設定外部使用者存取原則以支援同盟網域

  - 針對會話初始通訊協定開啟防火牆埠 (SIP) 、web 會議與音訊/視覺效果，以容納您要啟用的同盟或連絡人。 如需詳細資訊，請參閱： [判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

下列資訊可協助您為與 Microsoft Lync Server 2013 和 Lync Server 2010 的同盟定義憑證、埠/通訊協定和 DNS 需求。

若您已規劃或部署 Microsoft Lync Server 2013 Edge server，則規劃憑證、防火牆及埠/通訊協定需求和 DNS 需求通常是直接的向前處理。 因為同盟是另一個使用現有 Edge Server 的功能，所以 Edge Server 規劃及部署一般會滿足規劃需求。 您應該使用下表來判斷是否符合您的需求，並對埠/通訊協定和 DNS 作出適當的變更。

<div>


> [!IMPORTANT]
> 如果您有一部 Edge server 集區，且與 Lync Server 2013 或 Lync Server 2010 合作夥伴同盟，您可以在 Edge server 的內部及外部方端上使用 DNS 負載平衡或硬體負載平衡器。 如果您與 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2 同盟，硬體負載平衡會在 Edge Server 的事件中提供容錯移轉支援。 Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 不是 DNS 負載平衡感知。 夥伴 Edge Server 會與集區中的第一個 Edge Server 進行通訊，以進行回應。 如果該 Edge Server 失敗，通訊不會自動容錯移轉。



</div>

憑證需求通常是透過規劃您所選 Edge Server 或集區 Edge Server 計畫的憑證所獲得。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的憑證摘要-SIP、XMPP 同盟和公用立即訊息](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Lync Server 2013 中的埠摘要-SIP、XMPP 同盟和公用立即訊息](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Lync Server 2013 中的 DNS 摘要-SIP、XMPP 同盟和公用立即訊息](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

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

