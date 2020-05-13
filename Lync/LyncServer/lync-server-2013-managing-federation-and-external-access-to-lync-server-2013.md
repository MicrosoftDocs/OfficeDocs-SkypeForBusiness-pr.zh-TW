---
title: Lync Server 2013：管理 Lync Server 2013 的同盟與外部存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 155ee98a7386368d90fd549d920cdfe77c05cb6e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>管理 Lync Server 2013 的同盟與外部存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

支援外部使用者的首要步驟，是部署 Edge Server 或 Edge 集區。 如需部署 Edge Server 的詳細資訊，請參閱部署檔中的部署[Lync Server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)。

在安裝和設定 Lync Server 2013 的內部部署之後，您組織中的內部使用者可以與在您的 Active Directory 網域服務（AD DS）中具有 SIP 帳戶的其他內部使用者共同作業。 共同作業可包含傳送和接收立即訊息，以及會議中目前狀態與參加情況的更新。 您可以啟用和設定外部使用者存取，以控制是否支援的外部使用者能夠與內部 Lync Server 使用者共同作業。 外部使用者可能包含您部署的遠端使用者、同盟使用者 (包括公用立即訊息 (IM) 服務提供者的支援使用者)、XMPP 同盟與會議的匿名參與者。

如果您的部署包含安裝 Lync Server 2013 Edge Server 或 Edge 集區，則可能的通訊類型的範圍會大大擴充，具有許多選項可供外部使用者存取、與其他 SIP 同盟網域的成員進行通訊、SIP 同盟提供者，以及 XMPP 同盟使用者。 在設定 Edge Server 或 Edge 集區之後，請啟用您要提供的外部使用者存取類型，並設定原則以控制外部存取。 在 Lync Server 2013 中，您可以根據任務需求，使用 Lync Server 控制台、Lync Server 管理命令介面或兩者來啟用及設定外部使用者存取和原則。 如需這些管理工具的詳細資訊，請參閱 operations 檔中的[lync server 2013](lync-server-2013-lync-server-administrative-tools.md)系統管理工具、 [Lync Server 2013 管理命令](lync-server-2013-lync-server-management-shell.md)介面，並安裝 Operations 檔中的[lync server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

<div>


> [!IMPORTANT]  
> 當您設計外部使用者存取的組態和原則時，必須知道原則的優先順序以及原則的套用方式。 套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。 Lync Server 原則優先順序是：使用者原則（影響最大）會覆寫網站原則，然後網站原則會覆寫全域原則（影響最小）。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。



</div>

根據預設，沒有原則是設定為支援外部使用者存取 (包括遠端使用者存取、同盟網域使用者存取)，即使您已為組織啟用外部使用者存取也一樣。若要控制外部使用者存取的使用，您必須設定一個或多個原則，並在每個原則指定支援的外部使用者存取類型。這包括下列外部存取原則：

  - **全域原則**   全域原則是在您部署 Edge Server 時建立。 根據預設，全域原則中不會啟用任何外部使用者存取選項。 若要在全域層級支援外部使用者存取，您可以設定全域原則來支援一或多個類型的外部使用者存取選項。 全域原則適用於組織中的所有使用者，但是網站原則和使用者原則會覆寫全域原則。 如果您刪除全域原則，不會將它移除。 而是會將它重設為預設值。

  - **網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者對特定網站存取的支援。 網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。 例如，如果您在全域原則中啟用了遠端使用者存取，您可以指定網站原則以對特定網站停用遠端使用者存取。 根據預設，網站原則會套用至該網站的所有使用者，但您可以指派使用者原則給個別使用者，以覆寫網站原則設定。

  - **使用者原則**   您可以建立並設定一或多個使用者原則，以限制遠端使用者對特定網站存取的支援。 使用者原則中的設定會覆寫全域與網站原則，但僅限於該使用者原則指派的特定使用者。 例如，如果您在全域原則和網站原則中啟用了遠端使用者存取，您可以指定使用者原則以停用遠端使用者存取，然後將該使用者原則指派給特定使用者。 如果您建立使用者原則，必須將其套用至一或多個使用者，該原則才能生效。

若要決定需要建立或編輯哪些組態設定及原則，請參閱下列決策要點：

**您是否要允許您網域的內部及外部使用者能夠使用立即訊息、Web 會議及音訊/視訊來共同作業？**

在 lync server 2013 中設定[原則以控制遠端使用者存取](lync-server-2013-configure-policies-to-control-remote-user-access.md)，以及[啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以詳細設定設定中的相關設定。

**您是否要允許匿名使用者加入您部署中使用者所主控的會議，以及收到該會議的邀請？**

在 [[指派會議原則以支援 Lync server 2013 中的匿名使用者](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)] 中，設定相關的設定，並在 lync server [2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)，以及[lync server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)中的詳細資訊。

**您是否要允許使用者與 SIP 同盟網域連絡人進行通訊？**

設定各主題的詳細資訊，請在 lync server [2013 中設定控制同盟使用者存取的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)、[啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[在 lync server 2013 中管理組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**若您已啟用與 SIP 同盟網域的通訊，您是否還要啟用與 XMPP 同盟協力廠商連絡人的通訊？**

設定如需在[Lync server 2013 中設定原則以控制 XMPP 同盟使用者存取](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)，以及[管理 lync server 2013 中的 XMPP](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)同盟協力廠商，請設定詳細資訊。

**若您已啟用與 SIP 同盟網域的通訊，您是否要啟用 SIP 同盟自動探索？**

設定在[Lync Server 2013 中啟用或停用同盟](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)協力廠商探索主題的詳細資訊。

**若您已啟用與 SIP 同盟網域的通訊，您是否還要啟用傳送免責聲明給同盟連絡人，以通知他們您使用了封裝功能，且可能會封裝通訊內容？**

設定如需在[Lync Server 2013 中啟用或停](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)用傳送封存免責聲明至同盟合作夥伴的詳細資訊，請設定相關設定。

**您是否要允許使用者與使用公用提供者通訊的 SIP 同盟提供者（例如 Windows Live Messenger、AOL 和 Yahoo）進行通訊 \! ？**

設定相關設定，請在 Lync server[中設定控制公用使用者存取的原則](lync-server-2013-configure-policies-to-control-public-user-access.md)在 lync server 2013 中，[啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[在 lync server 2013 中建立或編輯公用 SIP 同盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公開 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>



</div>

**您是否要允許使用者與執行 Microsoft 365、Microsoft Lync Online 及 Microsoft Lync Online 2010 之主控供應商的 SIP 同盟提供者通訊？**

設定如需詳細資訊，請在[lync server 2013 中建立或編輯公用 SIP 同盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)、[啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[建立或編輯主控的 Sip 同盟提供者 Lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**您是否將部署設定在分割 (也稱為混合) 網域中，且該網域的某些使用者在內部部署中具有自己的主伺服器，而其他使用者則是透過線上環境中的主伺服器加以設定？**

設定各主題的詳細資訊在[Lync server 2013 中設定用來控制同盟使用者存取的原則](lync-server-2013-configure-policies-to-control-federated-user-access.md)、[啟用或停用 lync server 2013 中的同盟和公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[建立或編輯主控的 SIP 同盟提供者 lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

若您偏好以表格列出需求：


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>同盟和外部存取（透過）同盟或外部存取類型（向內）中的 Tab 鍵</th>
<th>外部存取原則</th>
<th>Access Edge 設定</th>
<th>SIP 同盟網域</th>
<th>SIP 同盟提供者</th>
<th>XMPP 同盟協力廠商</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>遠端使用者</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中設定控制遠端使用者存取的原則</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中啟用或停用遠端使用者存取</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP 同盟連絡人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中啟用或停用同盟協力廠商的探索</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">在 Lync Server 2013 中管理組織的 SIP 同盟網域</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP 同盟連絡人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">在 Lync Server 2013 中管理 XMPP 同盟協力廠商</a></p></td>
</tr>
<tr class="even">
<td><p>分割網域 / 混合使用者</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">建立或編輯主控的 SIP 同盟提供者 Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>公用 IM 服務連絡人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中設定原則以控制公用使用者存取</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>匿名使用者對會議的存取權</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">在 Lync Server 2013 中指派會議原則以支援匿名使用者</a></p>
<div>

> [!NOTE]  
> 您也必須考慮下列設定設定：在 [會議原則] 下<A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">建立或修改 lync server 2013 的會議原則</A>，以及<A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 的會議原則設定參考</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


您可以設定外部使用者存取設定，包括任何您要用以控制外部使用者存取的原則，即使您並未啟用組織的外部使用者存取亦然。但只有在您啟用組織的外部使用者存取後，您所設定的原則與其他設定才會生效。當外部使用者存取停用，或未設定外部使用者存取原則加以支援時，外部使用者將無法與您組織的使用者通訊。

您的 Edge 部署會根據您設定 Edge 支援的方式，來驗證外部使用者 (但匿名使用者除外，匿名使用者是由當您建立會議並邀請參與者時，所傳送給匿名參與者的會議 ID 及密碼金鑰加以驗證) 的類型及控制存取。若要控制通訊，您可以設定一或多項原則並設定其他設定，以定義您部署內外之使用者彼此通訊的方式。這些原則及設定包括外部使用者存取的預設全域原則，以及您可以建立並設定以針對特定網站或使用者啟用一或多種外部使用者存取類型的網站與使用者原則。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中管理外部存取原則](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [在 Lync Server 2013 中管理組織的 Access Edge 設定](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [在 Lync Server 2013 中管理組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [在 Lync Server 2013 中管理組織的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [在 Lync Server 2013 中管理 XMPP 同盟協力廠商](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [在 Lync Server 2013 中為 Lync Online 客戶設定同盟支援](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

