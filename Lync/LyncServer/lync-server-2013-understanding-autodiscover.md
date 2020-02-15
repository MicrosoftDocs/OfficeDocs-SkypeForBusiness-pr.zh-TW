---
title: Lync Server 2013： 了解自動探索
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
ms.openlocfilehash: f57dd0158f4a9b6c798d1b968353e5f84b55d46e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>了解在 Lync Server 2013 中的自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-06-03_

Lync Server 2013 自動探索服務是一種功能，原本 Microsoft Lync Server 2010 中引進一部分的 Lync Server 2010 累計更新： 2011 年 11 月。 修正程式，除了這個累計更新會傳遞 Lync Mobile 和 Lync 2013 用戶端的支援。

在 Lync Server 2013 中，自動探索服務的外部及內部行動用戶端，作業不可或缺的一部分，自動探索也會延伸至新的用戶端，例如 Windows 8 的最近引進 Lync Windows 市集應用程式。 Lync 2013 桌面用戶端也會使用自動探索。 自動探索會辨識在 Lync 伺服器所需的網域名稱系統 (DNS) 記錄**lyncdiscover。\<網域\>** 和**lyncdiscoverinternal。\<網域\>**。 此外，較新版本的 Lync 2010 和 Lync 2013 桌面用戶端的偏好自動探索網域名稱系統 (DNS) SRV 記錄，使用 DNS SRV 記錄，只有當透過 lyncdiscover。\<網域\>或 lyncdiscoverinternal。\<網域\>沒有回應或無法解決。 適用於 Windows 8 和 Lync Mobile Lync Windows 市集應用程式以獨佔模式使用自動探索，而且不會參照傳統 DNS SRV 記錄。

在 Lync Server 2013 中，自動探索會擴充為用戶端的項目、 功能及通訊方法，可使用的用戶端進行通訊。 資訊傳達透過用戶端上，從傳送要求，並命名項目定義明確回應 Lync Server web 服務回應可供用戶端，以及如何連絡這些功能的格式為自動探索回應文件。

若要了解自動探索回應文件，包括 web 服務的用戶端中，透過此文件的功能的通訊方式的最佳方式是仔細分析，並在 [從 Lync web 服務自動探索回應的文件的一般回應中定義每一行。

<div class="">


> [!NOTE]  
> 在巨集中接續的詳細資訊，使用者已經至主伺服器驗證所回應驗證要求。



</div>

<div class="">


> [!NOTE]  
> <STRONG>開放規格</STRONG>] 區段中的<STRONG>Microsoft Developer Network</STRONG> (MSDN) 程式庫中的<STRONG>Microsoft Office 通訊協定</STRONG>中定義 Lync 自動探索 Web 服務。 如需詳細資訊，請參閱完整規格文件中，「 Lync 自動探索 Web 服務通訊協定，「: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>。 如需驗證的詳細資訊，請參閱 「 OC 驗證 Web 服務通訊協定" <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>。



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Lync Server Web 服務自動探索回應

傳回傳送自動探索要求時的回應是相同的內部或外部的用戶端。 位置 – 知道一些參數可能會變更。 如果收到用戶端要求時，但實際的集區是已連絡以外，使用者的主集區會設定為該使用者。 使用者帳戶是另一個集區，但從相同的 office，登入同事會取得稍有不同的回應。 回應指出正確的前端伺服器或前端集區，為該使用者。

自動探索回應文件的範例：

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

## <a name="autodiscover-response-document-details"></a>自動探索回應文件詳細資料

自動探索回應文件可以是下列兩種格式。 預設的格式是 JavaScript Object Notation (JSON)。 其他格式為 「 可延伸標記語言 (XML) 的文件。 本範例會使用 XML。 要求和回應都可預測，因為文件有定義的結構描述會決定格式。 說明使用的結構描述的文件中的一行是要求或回應中的第一行：

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

定義**AccessLocation = 「 外部 」** 指出要求已從外部使用者進行。

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess 和 SipServerExternalAccess 目前未使用。 這些項目會保留供日後使用。

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess 和 SipClientExternalAccess 說明的完整的網域名稱和內部或外部用戶端用來存取已定義的 SIP 伺服器的連接埠。 Lync 桌面用戶端和 Lync Windows 市集應用程式會使用這些項目，根據其位置 （內部或外部），可尋找 Director 或前端伺服器。

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

`Autodiscover`參考包含了自動探索服務的服務進入點。 語彙基元屬性包含名稱的服務，且 href 定義為用戶端的 URL 可以找到此服務。 在外部網路使用的用戶端`External/Autodiscover`。 自動探索服務會安裝做為部署程序的一部分。 `Internal/Autodiscover`目前不使用，並保留供日後使用。

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

`AuthBroker`參考包含了服務項目指向的內部和外部驗證代理人服務] 中，在此情況下，sip.svc。 語彙基元屬性包含名稱的服務，且 href 定義為用戶端的 URL 可以找到此服務。 使用內部網路上的用戶端`Internal/AuthBroker`。 在外部網路使用的用戶端`External/AuthBroker`。 AuthBroker 服務會安裝您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

`WebScheduler`語彙基元所參考的用戶端存取 web 型排程 Lync Server 會議的 Url。 目前，只有`External/WebScheduler`使用。 WebScheduler 安裝成您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`及`External/Mcx`是行動性服務，在 Lync Server 2010 的累計更新中引入的位置： 2011 年 11 月。 這些參考將會繼續可供所有支援的裝置上的 Lync 2010 Mobile。 Mcx 服務會安裝您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**內部 /ucwa**、**外部 /ucwa**和**ucwa 的參考**可提供用戶端存取整合通訊 Web 應用程式發展介面 （UCWA API 或只是 UCWA） 方法。 `Internal/Ucwa`及`External/Ucwa`虛擬目錄會保留供未來功能增強功能的存取點，並不會使用。 `Ucwa`虛擬目錄適用於 Microsoft Lync Mobile （搭配 Lync Server 2013 引進） 的所有支援的裝置。 UCWA 服務會安裝您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`**外部/XFrame**和**XFrame**提供 UCWA 型伺服器應用程式的存取。 XFrame 安裝成您的內部 Lync Server 2013 部署 web 服務的部署程序的一部分。

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

`Self`權杖是指提出要求的用戶端 （使用者的回應類型） 的特定資訊。 進行這項要求用戶端的外部，且此自動探索參照到自動探索服務的使用者部份。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 的外部使用者存取元件的系統需求](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[規劃 Lync Server 2013 中的自動探索](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

