---
title: Lync Server 2013：自動探索服務需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea9d9be05561d200696a5ad0256c0d5424cf9b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Lync Server 2013 的自動探索服務需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

Microsoft Lync Server 2013 自動探索服務會在主管和前端池伺服器上執行，並在 DNS 中發佈時，可供執行 Lync Mobile 的行動裝置使用，以找出行動服務。 在執行 Lync Mobile 的行動裝置上，您可以充分利用自動探索，您必須在執行自動探索服務的任何主管和前端伺服器上修改證書消費者備用名稱清單。 此外，可能還需要針對反向代理伺服器上的外部 web 服務發佈規則，在證書上修改消費者備用名稱清單。

如需董事、前端伺服器及反向 proxy 所需的主題替換名稱專案的詳細資料，請參閱規劃行動[中的 Lync Server 2013 行動技術需求](lync-server-2013-technical-requirements-for-mobility.md)。

在反向 proxy 上使用 subject 備用名稱清單的決策是依據您是否要在埠80或埠443上發佈自動探索服務而定：

  - **已在埠 80**   上發佈如果自動探索服務的初始查詢是在埠80上進行，則不需要進行憑證變更。 這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後在內部將埠8080重新導向到控制器或前端伺服器。 如需詳細資訊，請參閱本主題稍後的「使用埠80的初始自動探索進程」一節。

  - **已在埠 443**   上發佈：外部 web 服務發佈規則所使用的憑證上的使用方式備用名稱清單必須包含*lyncdiscover。\<針對\> *貴組織內的每個 SIP 網域 sipdomain 專案。

使用內部憑證授權單位重新頒發憑證通常是一個簡單的程式，但適用于在 web 服務發佈規則上使用的公用憑證，新增多個消費者替換名稱專案可能會變得很昂貴。 若要解決此問題，我們支援經由埠80的初始自動探索連線，然後再重新導向控制器或前端伺服器上的埠8080。

例如，假設執行 Lync Mobile 的行動用戶端已設定為使用自動探索功能，在初始要求中使用「自動探索」功能來登入 Lync Server 2013。

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>使用埠80的行動裝置初始自動探索進程

1.  執行 Lync Mobile 的行動裝置會使用 DNS （記錄存在）查閱 lyncdiscover.contoso.com。

2.  外部 DNS 會將外部 web 服務的 IP 位址傳回用戶端。

3.  執行 Lync Mobile 的行動裝置會http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com將要求傳送到反向 proxy

4.  Web 發佈規則會將埠80的要求從外部橋接到內部的埠8080，然後將其路由到控制器或前端伺服器。
    
    因為要求是 HTTP 而不是 HTTPS，所以外部 web 服務發佈規則的憑證不需要任何修改，即可支援自動探索服務。

5.  自動探索服務會傳回外部 web 服務 Url （以 HTTPS 格式）。

6.  執行 Lync Mobile 的行動裝置可以重新連線到埠443上的反向 proxy，並重新4443導向至在使用者的家用版池中執行的行動服務。
    
    由於 HTTPS 查詢是針對外部 web 服務 URL 與自動探索服務 URL，因此它會成功，因為憑證已包含外部 web 服務完整功能變數名稱（Fqdn）的消費者備用名稱專案。
    
    在這種情況下，不需要有任何憑證變更即可支援行動。
    
    <div>
    

    > [!NOTE]  
    > 如果目標網頁伺服器的憑證沒有 lyncdiscover.contoso.com 的對應值做為 subject 替換名稱清單值：<BR>a.&nbsp;&nbsp;&nbsp;Web 服務器會以「伺服器 Hello」而不是憑證來回應。<BR>b.&nbsp;&nbsp;&nbsp;執行 Lync mobile 的行動裝置會立即終止會話。<BR>如果目標網頁伺服器的憑證包含 lyncdiscover.contoso.com 做為 subject 替換名稱清單值：<BR>a.&nbsp;&nbsp;&nbsp;Web 服務器會以「伺服器 hello」和憑證來回應。<BR>b.&nbsp;&nbsp;&nbsp;執行 Lync mobile 的行動裝置會驗證憑證並完成握手。

    
    </div>

若要在您的反向 proxy 伺服器上使用埠80來支援自動探索服務的初始連線，您可以建立與此範例類似 Forefront 威脅管理閘道2010反向 proxy web 發佈規則的 HTTP 發佈規則：

1.  建立新的 web 發佈規則（例如， **Lync Server 自動探索（HTTP）**）。

2.  在 [**公用名稱**] 中，輸入 lyncdiscover.contoso.com。

3.  在 [**橋接**] 索引標籤上，只選取將埠80中的要求橋接到埠8080的選項。

4.  在 [**驗證**] 索引標籤上，選取 [**無驗證**]，而且**用戶端無法直接驗證**。

5.  [提交變更]，然後將規則移至 Lync 規則清單的頂端（首先是處理順序）。

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>分割網域部署的行動性

共用的 SIP 位址空間（又稱為*分割網域*）或是*混合式部署*，是在內部部署和線上環境中部署使用者的配置。 您想要的結果是，無論其主伺服器位於何處（內部部署或線上），都能讓使用者登入並重新導向到其主伺服器位置。 若要完成這項作業，請使用 Microsoft Lync Server 2013 的自動探索功能，將線上使用者重新導向至線上拓撲。 您可以透過使用 Lync Server 管理命令介面和 Cmdlet **CsHostingProvider**和**Set-CsHostingProvider**來設定自動探索統一資源定位器（URL）來完成這項工作。

您將需要收集並錄製下列已部署的屬性：

  - 從 Lync Server 管理命令介面輸入
    
        Get-CsHostingProvider

  - 在結果中，尋找具有屬性**ProxyFQDN**的線上提供者。 例如，sipfed.online.lync.com

  - 記錄 ProxyFQDN 的值

  - 在內部部署的 Lync Server 控制台中啟用同盟，允許與線上提供者同盟

  - 針對線上提供者啟用同盟。 根據預設，所有的線上使用者都會啟用網域同盟，而且可以與所有網域通訊

  - 如果您要定義封鎖和允許的網域，請判斷您將明確允許或明確封鎖的網域

  - 針對線上同盟，您必須規劃防火牆例外狀況、憑證和 DNS 主機（A 或 AAAA （如果使用 IPv6）記錄）。 此外，您必須設定同盟原則。 如需詳細資訊，請參閱[規劃 Lync Server 2013 和 Office 通訊伺服器同盟](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

