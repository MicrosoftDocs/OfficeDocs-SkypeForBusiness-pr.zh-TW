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
ms.openlocfilehash: b63e29608dd8c3a0187b17c03e6ba9373b31f08f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527760"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a>瞭解 Lync Server 2013 中的自動探索

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-06-03_

Lync Server 2013 自動探索服務是一項功能，最初是在 Lync Server 2010： 11 2011 月的累計更新中所引進的 Microsoft Lync Server 2010 中。 除了修正之外，此累積更新可提供 Lync Mobile 和 Lync 2013 用戶端的支援。

在 Lync Server 2013 中，自動探索服務是外部和內部行動用戶端作業的一部分，而自動探索也會延伸至新的用戶端，例如最近引進的適用于 Windows 8 的 Lync Windows Store 應用程式。 Lync 2013 桌面用戶端也會使用自動探索。 使用必要的網域名稱系統 (DNS) 記錄 lyncdiscover，可在 Lync Server 中識別自動探索 **。 \<domain\> ** 和**lyncdiscoverinternal。 \<domain\> ** 此外，更新版本的 Lync 2010 和 Lync 2013 桌面用戶端更喜歡透過網域名稱系統自動探索 (DNS) SRV 記錄，只會在 lyncdiscover 時使用 DNS SRV 記錄。\<domain\> 或 lyncdiscoverinternal。\<domain\> 未回應或未解決。 適用于 Windows 8 和 Lync Mobile 的 Lync Windows 應用商店應用程式會以獨佔方式使用自動探索，不會參照傳統的 DNS SRV 記錄。

在 Lync Server 2013 中，自動探索已展開，可與用戶端通訊，以與用戶端使用哪些元素、功能和通訊方式。 透過用戶端傳送的要求來傳遞資訊，且 Lync Server web 服務會以明確定義的回應來回應，該回應會以名稱明確定義的回應，以命名用戶端可使用的內容，以及如何與自動探索回應檔的格式聯繫這些功能。

瞭解自動探索回應檔的最佳方式，包含 web 服務透過此檔對用戶端進行通訊的方式，是要在 Lync web 服務自動探索回應檔的一般回應中 dissect 及定義每一行。

<div class="">


> [!NOTE]  
> 在後續的詳細資料中，使用者已透過回應驗證要求來驗證主伺服器。



</div>

<div class="">


> [!NOTE]  
> Lync 自動探索 Web 服務是在 microsoft <STRONG>Developer Network</STRONG> (MSDN) 程式庫的 [<STRONG>開啟規格</STRONG>] 區段中的 [ <STRONG>microsoft Office 通訊協定</STRONG>] 中定義的。 如需詳細資訊，請參閱：的完整規格檔「Lync 自動探索 Web 服務通訊協定」 <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> 。 如需驗證的詳細資訊，請參閱 at 中的「OC 驗證 Web 服務通訊協定」 <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> 。



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Lync Server Web 服務自動探索回應

傳送自動探索要求給內部或外部用戶端時所傳回的回應。 有些位置識別的參數可能會變更。 如果接收到用戶端要求，但是實際的集區不是已連接的集區，則會為該使用者設定使用者的主集區。 如果同事的使用者帳戶位於不同的集區，但從相同的 office 登入，將會稍有不同的回應。 回應會指出正確的前端伺服器或該使用者的前端集區。

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

自動探索回應檔可以是兩種格式的其中一種。 預設格式為 JavaScript 物件標記法 (JSON) 。 另一種格式是可擴展標記語言 (XML) 檔。 此範例會使用 XML。 要求和回應是可預測的，因為檔具有決定格式的定義架構。 檔中描述所用架構的行是要求或回應中的第一行：

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

**AccessLocation = "External"** 的定義表示來自外部使用者的要求。

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

目前未使用 SipServerInternalAccess 和 SipServerExternalAccess。 這些專案會保留以供日後使用。

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess 和 SipClientExternalAccess 描述內部或外部用戶端用來存取定義的 SIP 伺服器的完整功能變數名稱和埠。 Lync 桌面用戶端和 Lync Windows Store 應用程式會根據其位置 (內部或外部) 來使用這些專案，以找出 Director 或前端伺服器。

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

`Autodiscover`參考資料包含自動探索服務的服務進入點。 Token 屬性包含服務的名稱，而 href 是定義可找到服務之用戶端的 URL。 外部網路上的用戶端使用 `External/Autodiscover` 。 自動探索服務會安裝為部署程式的一部分。 `Internal/Autodiscover` 目前未使用，且保留供日後使用。

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

`AuthBroker`參考資料包含內部及外部驗證代理程式服務的服務進入點，在此情況下為 sip .svc。 Token 屬性包含服務的名稱，而 href 是定義可找到服務之用戶端的 URL。 內部網路上使用的用戶端 `Internal/AuthBroker` 。 外部網路上的用戶端使用 `External/AuthBroker` 。 AuthBroker 服務會安裝為內部 Lync Server 2013 部署 web 服務之部署程式的一部分。

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

`WebScheduler`權杖會參考用戶端存取的 URLs，以供 Lync Server 會議以 web 為基礎的排程。 目前只 `External/WebScheduler` 會使用。 WebScheduler 安裝為內部 Lync Server 2013 部署 web 服務部署程式的一部分。

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx` 而且， `External/Mcx` 也就是 Lync Server 2010 的累計更新所引進的行動服務位置：11月2011。 在所有支援的裝置上，Lync 2010 Mobile 會繼續使用這些參考。 Mcx 服務會安裝為內部 Lync Server 2013 部署 web 服務之部署程式的一部分。

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**、 **External/Ucwa** 和 **Ucwa** 提供一種方法，讓用戶端存取整合通訊 Web 應用程式程式設計介面 (Ucwa API 或僅僅是 Ucwa) 。 `Internal/Ucwa` 和 `External/Ucwa` 虛擬目錄是保留以供未來功能增強使用的訪問點，不會使用。 `Ucwa`虛擬目錄用於 Microsoft Lync Mobile (引進于所有支援的裝置上的 Lync Server 2013) 。 UCWA 服務會安裝為內部 Lync Server 2013 部署 web 服務之部署程式的一部分。

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`、 **External/XFrame** 及 **XFrame** 提供 UCWA 型伺服器應用程式的存取權。 XFrame 已安裝為內部 Lync Server 2013 部署 web 服務之部署程式的一部分。

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

`Self`權杖是指用戶端 (使用者回應類型) 進行要求的特定資訊。 進行此要求的用戶端為外部用戶端，此自動探索參考是自動探索服務的使用者部分。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 之外部使用者存取元件的系統需求](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[在 Lync Server 2013 中規劃自動探索](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

