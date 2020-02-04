---
title: Lync Server 2013：瞭解自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9d885654f9222ce3d3e9fb7b03e9b388f0ca0a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>瞭解 Lync Server 2013 中的自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-06-03_

Lync Server 2013 自動探索服務是最初在 Microsoft Lync Server 2010 中引入的一項功能，可做為 Lync Server 2010 的累積更新：11月2011。 除了修正程式之外，此累積更新提供 Lync Mobile 和 Lync 2013 用戶端的支援。

在 Lync Server 2013 中，自動探索服務是外部和內部行動用戶端作業的一部分，而且自動探索也會延伸至新的用戶端，例如最近推出的 Windows 8 版 Lync Windows Store 應用程式。 Lync 2013 桌面用戶端也會使用自動探索功能。 在 Lync Server 中，系統會透過所需的網域名稱系統（DNS）記錄 lyncdiscover 識別自動探索 **。\<網域\> **與**lyncdiscoverinternal。\<網域\>**。 此外，更新版本的 Lync 2010 和 Lync 2013 桌面用戶端喜歡自動探索網功能變數名稱稱系統（DNS） SRV 記錄（只有在 lyncdiscover 時才使用 DNS SRV 記錄）。\<[\>網域] 或 [lyncdiscoverinternal]。\<網域\>沒有回應或無法解決。 適用于 Windows 8 和 Lync Mobile 的 Lync Windows Store 應用程式會獨佔使用自動探索，不會參照傳統的 DNS SRV 記錄。

在 Lync Server 2013 中，會展開 [自動探索]，以便與用戶端提供哪些元素、功能和通訊方法供用戶端使用。 資訊是透過從用戶端傳送的要求來傳遞，而 Lync Server web 服務則會以明確定義的回應來回應，讓用戶端可以使用哪些專案，以及如何以自動探索的格式來聯繫這些功能。回應檔。

瞭解自動探索回應檔的最佳方式，包括 web 服務透過這份檔將功能傳達給用戶端的方式，是在 Lync web 服務自動探索回應檔的一般回應中 dissect 及定義每一行。

<div class="">


> [!NOTE]  
> 在後續的詳細資料中，使用者已透過回應驗證要求驗證至主伺服器。



</div>

<div class="">


> [!NOTE]  
> Lync 自動探索 Web 服務是在<STRONG>Microsoft 開發人員網路</STRONG>（MSDN）文件庫的 [<STRONG>開啟規格</STRONG>] 區段中的 [ <STRONG>microsoft Office 通訊協定</STRONG>] 中定義。 如需詳細資訊，請參閱完整的規格檔：「Lync 自動探索 Web 服務通訊<A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>協定」，網址為：。 如需有關驗證的詳細資訊，請參閱「OC 驗證 Web <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>服務通訊協定」。



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Lync Server Web 服務自動探索回應

傳送自動探索要求時所傳回的回應，對於內部或外部用戶端而言是相同的。 某些位置的可感知參數可能會變更。 如果收到用戶端要求，但實際的池不是您所取得的那一個，則會針對該使用者設定使用者的主文件庫。 如果同事的使用者帳戶位於不同的文檔池中，但是從同一個 office 登入，則回應會稍有不同。 回應會指出該使用者的正確前端伺服器或頂層端池。

自動探索回應檔的範例：

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a>自動探索回應檔詳細資料

自動探索回應檔可以是兩種格式的其中之一。 預設格式是 JavaScript 物件符號（JSON）。 另一種格式是可擴展標記語言（XML）檔。 此範例會使用 XML。 要求和回應是可預測的，因為檔的定義架構決定了格式。 檔中描述所使用之架構的行是要求或回應中的第一行：

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

**AccessLocation = "External"** 的定義代表來自外部使用者的要求。

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

目前未使用 SipServerInternalAccess 和 SipServerExternalAccess。 這些專案會保留供日後使用。

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess 和 SipClientExternalAccess 說明內部或外部用戶端將用來存取已定義 SIP 伺服器的完整功能變數名稱和埠。 Lync 桌面用戶端和 Lync Windows Store 應用程式會根據其位置（內部或外部），使用這些專案來尋找控制器或前端伺服器。

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

`Autodiscover`參照包含自動探索服務的服務進入點。 Token 屬性包含服務的名稱，href 是定義可找到服務之用戶端的 URL。 外部網路上的`External/Autodiscover`用戶端使用。 自動探索服務會安裝為部署程式的一部分。 `Internal/Autodiscover`目前不使用，且已保留供日後使用。

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

`AuthBroker`參照包含內部和外部驗證 broker 服務的服務進入點，在此案例中為 [sip.]。 Token 屬性包含服務的名稱，href 是定義可找到服務之用戶端的 URL。 內部網路上使用`Internal/AuthBroker`的用戶端。 外部網路上的`External/AuthBroker`用戶端使用。 AuthBroker 服務已安裝為內部 Lync Server 2013 部署 web 服務部署程式的一部分。

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

`WebScheduler`權杖會參照用戶端存取 Lync Server 會議的網路排程的 url。 目前只`External/WebScheduler`使用。 WebScheduler 已安裝為您內部 Lync Server 2013 部署 web 服務部署程式的一部分。

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`而且`External/Mcx`是行動服務的位置，在 Lync Server 2010 的累加更新中引入：2011年11月。 Lync 2010 Mobile 會繼續在所有支援的裝置上使用這些參考。 Mcx 服務已安裝為內部 Lync Server 2013 部署 web 服務部署程式的一部分。

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**、 **External/Ucwa**和**Ucwa**提供一種方式讓用戶端存取整合通訊 Web 應用程式程式設計介面（Ucwa API 或只是 Ucwa）。 `Internal/Ucwa`而且`External/Ucwa`虛擬目錄是保留給未來功能增強的存取點，不會使用。 `Ucwa`虛擬目錄用於 Microsoft Lync Mobile （在所有支援的裝置上推出 Lync Server 2013）。 UCWA 服務已安裝為內部 Lync Server 2013 部署 web 服務部署程式的一部分。

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`、**外部/XFrame**和**XFRAME**提供對 UCWA 伺服器應用程式的存取權。 XFrame 已安裝為您內部 Lync Server 2013 部署 web 服務部署程式的一部分。

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

`Self`標記是指發出要求之用戶端（使用者回應類型）專用的資訊。 發出此要求的用戶端是外部的，而這個自動探索參照是對自動探索服務的使用者部分。

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[外部使用者為 Lync Server 2013 存取元件的系統需求](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[規劃 Lync Server 2013 中的自動探索](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

