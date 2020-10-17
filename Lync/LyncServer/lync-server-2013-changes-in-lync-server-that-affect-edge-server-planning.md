---
title: Lync Server 2013： Lync Server 中影響 Edge Server 規劃的變更
description: Lync Server 2013： Lync Server 中影響 Edge Server 規劃的變更。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660a281d858cf92a48d5eaed6d5caf3141b3817
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543749"
---
# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Lync Server 2013 中影響 Edge Server 規劃的變更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

Lync Server 2013 引進新功能，可擴充使用者的功能和通訊方法。 另外，Lync Server 2013 也會引入現有服務的變更，以更好地整合及擴充組織可使用的服務。 下列摘要會影響您規劃和部署 Lync Server 2013 Edge Server 服務的變更。

<div>

## <a name="support-for-ipv6-addressing"></a>支援 IPv6 定址

Lync Server 2013 支援所有 Edge Server 服務的 IPv6 位址。 如果您已在 Windows Server 中透過設定提供介面的 IPv6 位址，您可以透過 [拓撲產生器] 中的 IP 位址設定，使用 Edge Server 設定中的 IPv6 位址。 此外，可延伸的訊息和顯示狀態通訊協定 (XMPP) 支援 IPv6。 不需要其他設定。 如果在拓撲中設定 IPv6，XMPP 將會使用 IPv6 (必要的) 。

在 Lync Server 2013 中新增支援 IPv6，是為了必須探索並解析為 IPv6 位址的記錄建立網域名稱系統記錄。 IPv6 DNS 使用定義為 **AAAA** 並稱為「四 A」的主機記錄。 其他記錄類型則與 IPv4 記錄類型一致。

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>支援 Extensible Messaging and Presence Protocol (XMPP) 部署

Edge Server 會引入完整整合的 XMPP proxy (部署于 Edge Server 上) 以及 (部署在前端伺服器) 上的 XMPP 閘道。 您可部署 XMPP 同盟作為選用元件。 透過新增及設定 XMPP proxy 和 XMPP 閘道，您可以讓 Microsoft Lync 2013 使用者從 XMPP 的協力廠商夥伴新增連絡人，以進行立即訊息 (IM) 和顯示狀態。

<div>


> [!NOTE]  
> 目前，Edge Server 中的 XMPP 服務只會在 Lync Server 用戶端和以 XMPP 為基礎的連絡人之間提供 IM 及目前狀態。 此外，XMPP 僅裝載在單一網站。



</div>

<div>


> [!IMPORTANT]  
> Lync Server 2013 的 XMPP 功能會經過測試，並受 Microsoft 支援，以進行與 Google 交談的立即訊息同盟。 對於任何其他 XMPP 系統，請聯繫協力廠商廠商，以確認其支援與 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>支援輪流 Audio/Video 驗證及伺服器對伺服器驗證憑證

憑證是用於產生權杖，以核發給 A/V 驗證服務的用戶端與其他取用者，以及用於伺服器對伺服器驗證。Audio/Video 驗證憑證為 *AudioVideoAuthentication* 類型，而伺服器對伺服器驗證憑證為 *OAuthTokenIssuer* 類型。

對於 Audio/Video 驗證，權杖是用於驗證連接埠配置要求，並快取最高可達 8 小時 (權杖的預設存留期)。在一般作業情況下，這是建立並散發驗證資料給 A/V 取用者非常可靠的方法。然而，憑證存留期有限，並且會在預先定義的日期與時間過期 (以建立日期以及建立憑證的憑證授權單位實施的原則為準，此類型的憑證通常為 2 年)。當憑證過期時，由過期憑證建立並由取用者快取的任何權杖，都會失效。只要使用過期憑證建立的權杖都會造成「媒體轉送」配置失敗，而且任何進行中的音訊/視訊工作階段也會失敗。用戶端需要取得由有效憑證建立的新權杖，才能恢復正常的音訊和視訊功能。

伺服器對伺服器驗證由全域憑證管理，並適用於部署中的所有伺服器。 憑證負責在 Lync Server 2013 中驗證服務器，並對 Exchange 2013 和 Microsoft SharePoint Server 2013 進行驗證。 如需伺服器對伺服器驗證運作方式的詳細資訊，請參閱 [管理 Lync server 2013 中的伺服器對伺服器驗證 (OAuth) 和夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。 Audio/Video 驗證程序和伺服器對伺服器驗證程序之間一個非常重要的差別是，驗證的存留期 (或權杖)。 對於 Audio/Video 驗證，驗證在 8 小時後過期。 伺服器對伺服器驗證則有 24 小時的存留期。 您必須針對每個憑證類型加以規劃。

Lync Server 2013 的新增功能是在目前憑證到期之前，將取代 Audio/Video 驗證憑證和伺服器暫存至伺服器驗證憑證的功能。 然後使用新的憑證來產生新的權杖或新的驗證要求。 但保留舊憑證以驗證目前的會話和驗證驗證。 完成此工作的方式是有效地避免由於權杖和憑證到期而幾乎所有的失敗。 如需此功能及其設定方式的詳細資訊，請參閱 [Lync Server 2013 中的「暫存 AV」和 OAuth 憑證。 Set-CsCertificate 中使用-擲入](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>降低對 Cookie 為主親和性的依賴

在舊版的 Lync Server 和 Office 通訊伺服器中，Web 服務會使用 cookie 型相似性，以確保已維護用戶端和 Web 服務會話狀態。 Lync Server 2013 Web 服務使用內建的仿射性機制，可消除 cookie 基礎上的大部分需求。

<div>


> [!WARNING]  
> Microsoft Lync 2010 行動用戶端仍必須使用 cookie 型相似性，而且在您將所有用戶端遷移至即將推出的 Microsoft Lync Mobile 客戶)  (端之前，必須設定 cookie 的相似性



</div>

如需 Lync Server 2013 中以 cookie 為基礎之相似性的詳細資訊，請參閱 [Lync server 2013 中的外部使用者存取所需的元件](lync-server-2013-components-required-for-external-user-access.md)。

</div>

<div>

## <a name="autodiscover-enhancements"></a>自動探索增強功能

Lync Server 2013 中的自動探索功能可讓用戶端尋找其他可用於通訊的功能。 「自動探索」是第一次在 Lync Server 2010 的累計更新中引進2011：行動性和 Microsoft Lync 2010 Mobile 的累計更新。 「DNS 記錄名稱 LyncDiscover 及) LyncDiscoverInternal」所知道的自動探索功能 (，可讓用戶端尋找及使用行動服務 (為 Microsoft Lync 2010 行動用戶端) 、Microsoft Lync Web App 和 Lync Web 排程，以及與 Microsoft Exchange Server 和 SharePoint 伺服器的通訊。 自動探索是安裝及部署基礎結構和 Lync Server 2013 伺服器的正常部分。 拓撲產生器和 Lync Server 部署嚮導可避免 Lync Server 2010：11月2011累計更新所需的大部分設定工作。

</div>

<div>

## <a name="services-for-mobile-clients"></a>適用於行動用戶端的服務

在 Lync Server 2010 的累計更新中引進：11月2011，Lync Server 2013 中的行動性服務可使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行 Lync Mobile 和平板電腦裝置的行動電話，以執行如傳送和接收立即訊息、查看連絡人及查看狀態的活動。 此外，行動裝置也支援某些企業語音功能，例如按一下以加入會議、呼叫透過工作、單一號碼到達、語音信箱及未接來電通知。

<div>


> [!NOTE]  
> 行動性服務使用前端伺服器中部署的反向 Proxy 和發佈的服務。 Edge Server 不需要進行任何變更。 您至少需要有輸出 SIP/TCP/5061from 執行 Lync Server Access Edge service 的伺服器。



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>Director 角色為選用

Lync Server 2013 拓撲中 Director 伺服器的角色尚未變更。 它仍舊裝載 Web 服務、預先驗證連入使用者要求，以及將外部使用者導向至其主集區。 將 Director 從建議的角色變更為選用的角色，Microsoft 不想要降低 Director 的價值。 目的是要減少伺服器數目及其他硬體需求 (例如，Director) 的硬體負載平衡器，而不會損等功能。 由於前端伺服器可以執行與不會影響提供之服務的 Director 相同的工作，因此您可以選擇部署 Director。 您可以放心地排除 Director，前端伺服器將會提供相同服務以取代 Director。

</div>

</div>

<span> </span>

</div>

</div>

</div>

