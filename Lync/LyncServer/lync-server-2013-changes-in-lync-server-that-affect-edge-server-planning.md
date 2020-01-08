---
title: Lync Server 2013：在 Lync Server 中會影響 Edge Server 規劃的變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>在 Lync Server 2013 中會影響 Edge Server 規劃的變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

Lync Server 2013 引入了新功能，可延伸您使用者的功能與通訊方法。 此外，Lync Server 2013 也會為現有的服務引入變更，以更好地整合及延伸貴組織所提供的服務。 以下是可能會影響您規劃和部署 Lync Server 2013 Edge Server 服務的變更摘要。

<div>

## <a name="support-for-ipv6-addressing"></a>支援 IPv6 位址

Lync Server 2013 支援所有 Edge 伺服器服務的 IPv6 位址。 如果您已透過 Windows Server 中的設定提供介面的 IPv6 位址，您可以透過拓撲建立器中的 IP 位址設定，在 Edge 伺服器配置中使用 IPv6 位址。 此外，可擴展的訊息和目前狀態通訊協定（XMPP）支援 IPv6。 不需要其他配置。 如果在拓撲中設定 IPv6，XMPP 將會使用 IPv6 （如果需要的話）。

在 Lync Server 2013 中增加支援 IPv6 的需求是針對必須發現並解析為 IPv6 位址的記錄，建立網域名稱系統記錄。 IPv6 DNS 使用定義為**AAAA**並稱為「四 A」的主機記錄。 其他記錄類型與其 IPv4 對應專案一致。

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>支援可擴展訊息和目前狀態通訊協定（XMPP）部署

Edge 伺服器會引入完全整合的 XMPP proxy （在 Edge 伺服器上部署）和 XMPP 閘道（在您的前端伺服器上部署）。 您可以將 XMPP 同盟部署為選用的元件。 您可以新增並設定 XMPP proxy 和 XMPP 閘道，讓您的 Microsoft Lync 2013 使用者新增來自 XMPP 合作夥伴的連絡人，以進行立即訊息（IM）和目前狀態。

<div>


> [!NOTE]  
> 目前，Edge 伺服器中的 XMPP 服務只會在 Lync Server 用戶端和 XMPP 的連絡人之間提供 IM 和目前狀態。 此外，XMPP 僅託管于一個網站中。



</div>

<div>


> [!IMPORTANT]  
> Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。 針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>支援將音訊/視頻驗證和伺服器滾動到伺服器驗證憑證

證書是用來產生向用戶端和 A/V 驗證服務的其他消費者（以及伺服器到伺服器驗證）頒發的權杖。 音訊/視頻驗證憑證的類型為*AudioVideoAuthentication* ，而伺服器到伺服器驗證憑證的類型是*OAuthTokenIssuer*。

針對音訊/視頻驗證，權杖是用來驗證埠配置要求，而權杖最多可緩存8小時，即權杖的預設存留期。 在 [標準作業] 下，這是一個非常可靠的方法，可為 A/V 消費者建立並散佈驗證資料。 不過，憑證的生命週期有限，且會在預先定義的日期和時間到期（根據建立日期，以及在建立憑證的認證機構所強制的原則，通常是2年適用于這種類型的憑證）。 當憑證到期時，由過期憑證所建立且由消費者快取的任何權杖都會無效。 任何使用已過期證書所建立之權杖的嘗試，都會導致媒體轉送分配失敗，而且所有目前的音訊/視頻會話都會失敗。 用戶端需要取得由有效憑證建立的新權杖，才能繼續執行正常的音訊和視頻功能。

伺服器到伺服器驗證是由要求並套用至部署中所有伺服器的全域憑證所管理。 憑證負責驗證 Lync Server 2013 中的伺服器，以及驗證 Exchange 2013 和 Microsoft SharePoint Server 2013。 如需伺服器驗證服務器驗證運作方式的詳細資訊，請參閱[在 Lync server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。 音訊/視頻驗證程式與伺服器到伺服器驗證處理常式之間的一個非常重要的差異是驗證或權杖的存留期。 針對音訊/視頻驗證，驗證會在八小時後到期。 伺服器對伺服器驗證的存留期為24小時。 您必須針對每個憑證類型進行相應的規劃。

Lync Server 2013 的新功能是在目前憑證到期前將替換音訊/視頻驗證憑證和伺服器轉移到伺服器驗證憑證的能力。 然後使用新憑證來產生新的權杖或新的驗證要求。 但保留舊憑證以驗證目前的會話與驗證。 完成這個工作是為了有效避免因標記和憑證到期而發生的幾乎所有失敗。 如需此功能的詳細資訊及如何進行設定，請參閱[使用 CsCertificate 中的 Lync Server 2013 暫存 AV 和 OAuth 憑證](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>減少對以 Cookie 為基礎的關聯性的依賴性

在舊版的 Lync Server 和 Office 通訊伺服器中，Web 服務會使用以 cookie 為基礎的相似性，以確保用戶端和 Web 服務會話狀態已維護。 Lync Server 2013 Web 服務使用內建的關聯機制，可消除 cookie 關聯的大部分需求。

<div>


> [!WARNING]  
> Microsoft Lync 2010 行動用戶端仍必須使用以 cookie 為基礎的關聯性，且需要設定以 cookie 為基礎的關聯性，除非您將所有用戶端轉移到即將到來的 Microsoft Lync 行動用戶端（尚未決定發行日期）。



</div>

如需 Lync Server 2013 中以 cookie 為基礎的關聯性的詳細資料，請參閱[Lync server 2013 中的外部使用者存取所需的元件](lync-server-2013-components-required-for-external-user-access.md)。

</div>

<div>

## <a name="autodiscover-enhancements"></a>自動探索增強功能

Lync Server 2013 中的自動探索功能可讓用戶端找出提供給通訊的其他功能。 自動探索是在 Lync Server 2010 的累積更新中開始推出：行動裝置和 Microsoft Lync 2010 行動裝置的年 11 2011 月。 自動探索功能（由 DNS 記錄名稱 LyncDiscover 和 LyncDiscoverInternal 提供）可讓用戶端找到並使用行動服務（適用于 Microsoft Lync 2010 行動用戶端）、Microsoft Lync Web App 以及 Lync Web 排程程式，以及與 Microsoft Exchange Server 和 SharePoint Server 的通訊。 自動探索是在您的基礎結構和 Lync Server 2013 伺服器的設定和部署中正常安裝。 [拓撲建立器] 和 [Lync Server 部署] 嚮導會消除 Lync Server 2010 的累積更新中所需的大部分配置工作：2011年11月。

</div>

<div>

## <a name="services-for-mobile-clients"></a>行動用戶端的服務

在 Lync Server 2010 的累積更新中所述，Lync Server 2013 中的行動服務可讓您使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行 Lync Mobile 和平板電腦裝置，以執行行動電話2011。活動（例如傳送及接收立即訊息、查看連絡人及查看目前狀態）。 此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電通知。

<div>


> [!NOTE]  
> 行動服務會使用部署在您前端伺服器上的反向 proxy 與已發佈的服務。 Edge 伺服器不需要任何變更。 您最簡單的情況是，您需要使用 [輸出 SIP/TCP/5061from] 伺服器執行 Lync Server 存取邊緣服務。



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>主管角色是選擇性的

在 Lync Server 2013 拓撲中，控制器伺服器的角色沒有變更。 它仍會寄存 web 服務、preauthenticates 傳入的使用者要求，並將外部使用者導向其主區。 透過將主管從建議的角色變更為選用的角色，Microsoft 不想要降低主管的價值。 目的是要減少伺服器數量及其他硬體需求（例如，控制器的硬體負載平衡器），而不會影響功能和功能。 因為前端伺服器可以執行與主管所提供服務不受影響的相同作業，所以如果您選擇的話，就可以部署控制器。 您可以放心地排除主管，讓前端伺服器提供相同的服務來取代控制器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

