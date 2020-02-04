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
ms.openlocfilehash: 9dadc455389d95c91996b75928def8f03b06c64e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>管理 Lync Server 2013 的同盟與外部存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

部署 Edge 伺服器或 Edge 池是支援外部使用者的第一個步驟。 如需有關部署邊緣伺服器的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [部署外部使用者存取](lync-server-2013-deploying-external-user-access.md)]。

安裝並設定 Lync Server 2013 的內部部署之後，貴組織內的內部使用者就可以與在 Active Directory 網域服務（AD DS）中擁有 SIP 帳戶的其他內部使用者共同作業。 共同作業可以包括傳送及接收立即訊息，以及更新目前狀態及參與會議（也稱為「會議」）。 您可以啟用並設定外部使用者存取權，以控制支援的外部使用者是否可與內部 Lync 伺服器使用者共同作業。 外部使用者可以包含您部署的遠端使用者、同盟使用者（包括公用立即訊息（IM）服務提供者）、XMPP 同盟及會議中的匿名參與者。

如果您的部署包括安裝 Lync Server 2013 Edge 伺服器或邊緣池，可能的通訊類型的範圍會大大擴大，有幾個選項可供外部使用者存取、與其他 SIP 聯盟網域的成員進行通訊。SIP 聯盟提供者，並 XMPP 聯盟使用者。 在設定 Edge 伺服器或 Edge 池之後，您可以啟用您想要提供的外部使用者存取類型，並設定控制外部存取的原則。 在 Lync Server 2013 中，您可以使用 Lync Server [控制台]、[Lync Server 管理命令介面] 或這兩者（根據任務需求）來啟用及設定外部使用者存取與原則。 如需這些管理工具的詳細資訊，請參閱 Operations 檔中的[Lync server 2013 系統管理工具](lync-server-2013-lync-server-administrative-tools.md)、 [Lync Server 2013 管理 Shell](lync-server-2013-lync-server-management-shell.md)中的操作檔，以及[安裝 Lync server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)（在作業檔中）。

<div>


> [!IMPORTANT]  
> 當您設計外部使用者存取的設定與原則時，您必須瞭解原則的優先順序，以及原則的套用方式。 在一個策略層級套用的 Lync Server 原則設定，可以覆寫在其他原則層級套用的設定。 Lync 伺服器策略優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。



</div>

根據預設，不會將任何原則設定為支援外部使用者存取，包括遠端使用者存取、同盟使用者存取，即使您已為組織啟用外部使用者存取支援。 若要控制外部使用者存取的使用方式，您必須設定一或多個原則，以指定每個原則支援的外部使用者存取類型。 這包括下列外部存取原則：

  - **全域原則**   當您部署邊緣伺服器時，就會建立全域原則。 根據預設，全域原則中不會啟用任何外部使用者存取選項。 若要支援全域層級的外部使用者存取，您可以將全域原則設定為支援一或多種類型的外部使用者存取選項。 全域原則會套用至貴組織中的所有使用者，但網站原則和使用者原則會覆寫全域原則。 如果您刪除全域原則，就不會將它移除。 相反地，您可以將其重設為預設設定。

  - **網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者存取特定網站的支援。 網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。 例如，如果您在全域原則中啟用遠端使用者存取，您可以指定可停用特定網站之遠端使用者存取權的網站原則。 根據預設，網站原則會套用至該網站的所有使用者，但您可以將使用者原則指派給使用者，以覆寫網站原則設定。

  - **使用者原則**   您可以建立及設定一或多個使用者原則，以限制對特定使用者的遠端使用者存取權的支援。 使用者原則中的設定會覆寫全域和網站原則，但只適用于指派使用者原則的特定使用者。 例如，如果您在全域原則和網站原則中啟用遠端使用者存取，您可以指定可停用遠端使用者存取的使用者原則，然後將該使用者原則指派給特定的使用者。 如果您建立使用者原則，您必須先將其套用至一或多個使用者，才會生效。

若要判斷您需要建立或編輯哪些設定設定以及哪些原則，請參閱下列決策點：

**您想要讓您網域的內部和外部使用者能夠使用立即訊息、Web 會議和音訊/影片進行共同作業嗎？**

在 lync [server 2013 中設定控制遠端使用者存取權的原則](lync-server-2013-configure-policies-to-control-remote-user-access.md)，並在[lync Server 2013 中啟用或停用同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以設定相關設定的詳細資訊

**您想要允許匿名使用者出席並邀請您部署中的使用者所託管的會議嗎？**

設定相關設定，如主題中的 [[指派會議原則以支援 Lync server 2013 中的匿名使用者](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)]、[在 lync server [2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)] 和 [ [lync server 2013 的會議原則設定] 參考](lync-server-2013-conferencing-policy-settings-reference.md)資訊

**您想要允許使用者與 SIP 聯盟網域連絡人通訊嗎？**

在 lync server 2013 中設定[策略來控制聯盟使用者存取](lync-server-2013-configure-policies-to-control-federated-user-access.md)、[啟用或停用 lync server 2013 中的同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[在 lync server 2013 中管理貴組織的 SIP 聯盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)，即可設定設定的詳細資訊。

**如果您已啟用與 SIP 同盟網域的通訊，您想要啟用與 XMPP 聯盟夥伴連絡人的通訊嗎？**

在 lync [server 2013 中設定控制 XMPP 聯盟使用者存取的原則](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)，並在[lync Server 2013 中管理 XMPP 聯盟夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)，以設定主題中的詳細資訊。

**如果您已啟用與 SIP 聯盟網域的通訊，您是否要啟用 SIP 同盟自動探索？**

設定在[Lync Server 2013 中啟用或停用同盟合作夥伴的探索](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)主題中的詳細資訊。

**如果您已啟用與 SIP 同盟網域的通訊，您是否要啟用將免責聲明傳送給同盟連絡人，通知他們您使用的是封存，而且該通訊可能已封存？**

在[Lync Server 2013 的 [聯盟夥伴] 中啟用或停](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)用將封存免責聲明傳送至同盟合作夥伴，以進行設定。

**您是否要允許使用者與 SIP 聯盟提供者通訊，以便與公用提供者通訊（例如 Windows Live Messenger、AOL 和 Yahoo\!）？**

在 lync server 2013 中設定[策略來控制公用使用者存取](lync-server-2013-configure-policies-to-control-public-user-access.md)的相關設定，請在 lync server[2013 中啟用或停用同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[在 lync server 2013 中建立或編輯公用 SIP 聯盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>



</div>

**您是否要允許使用者與 SIP 同盟提供者通訊，這些提供者是執行 Microsoft Office 365、Microsoft Lync Online 和 Microsoft Lync Online 2010 的託管提供者？**

在 lync server [2013 中建立或編輯公用 SIP 聯盟提供者](lync-server-2013-create-or-edit-public-sip-federated-providers.md)的相關設定，請在 lync server [2013 中啟用或停用同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[建立或編輯託管 SIP 聯合提供者 Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**您的部署是在分割（也稱為混合式）網域中設定，有些使用者在內部部署中擁有其主伺服器，而其他使用者則是在線上環境中使用家用伺服器進行設定？**

在 lync server 2013 中設定[策略來控制聯盟使用者存取](lync-server-2013-configure-policies-to-control-federated-user-access.md)、[啟用或停用 lync server 2013 中的同盟與公用 IM](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[建立或編輯託管 SIP 同盟提供者 Lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)的相關設定，如下列主題所述。

如果您想要的表格會列出需求：


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
<th>同盟與外部存取（跨）同盟或外部存取類型（向下）中的索引標籤</th>
<th>外部存取原則</th>
<th>存取邊緣配置</th>
<th>SIP 聯盟網域</th>
<th>SIP 同盟提供者</th>
<th>XMPP 聯盟合作夥伴</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>遠端使用者</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中設定原則以控制遠端使用者存取</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中啟用或停用遠端使用者存取</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP 同盟連絡人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中設定控制同盟使用者存取的原則</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中啟用或停用探索同盟協力廠商</a></p>
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
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">在 Lync Server 2013 中管理 XMPP 同盟夥伴</a></p></td>
</tr>
<tr class="even">
<td><p>分割網域/混合式使用者</p></td>
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
<td><p>匿名使用者對會議與會議的存取權</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">在 Lync Server 2013 中指派會議原則以支援匿名使用者</a></p>
<div>

> [!NOTE]  
> 您也必須在 [會議原則] 下考慮下列設定設定：<A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">在 lync server 2013 中建立或修改會議原則</A>，以及<A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 的會議原則設定參考</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


您可以設定外部使用者存取設定，包括任何您想要用來控制外部使用者存取權的原則，即使您的組織未啟用外部使用者存取權也一樣。 不過，您設定的原則和其他設定只有在您的組織啟用外部使用者存取後才會生效。 外部使用者在停用外部使用者存取權，或未設定外部使用者存取原則支援時，無法與貴組織的使用者進行通訊。

Edge 部署會驗證外部使用者的類型（匿名使用者除外，其由會議 ID 驗證，以及當您建立會議與邀請參與者時傳送給匿名參與者的密碼）。根據您設定 edge 支援的方式來存取。 若要控制通訊，您可以設定一或多個原則，並設定定義您的部署內部和外部的使用者之間相互通訊方式的設定。 [原則與設定] 包含外部使用者存取的預設全域原則，除了您可以建立並設定以啟用一或多種類型的外部使用者存取特定網站或使用者的網站和使用者原則之外。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中管理外部使用存取原則](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [在 Lync Server 2013 中管理組織的 Access Edge 設定](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [在 Lync Server 2013 中管理組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [在 Lync Server 2013 中管理組織的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [在 Lync Server 2013 中管理 XMPP 同盟夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [在 Lync Server 2013 中設定 Lync Online 客戶的同盟支援](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

