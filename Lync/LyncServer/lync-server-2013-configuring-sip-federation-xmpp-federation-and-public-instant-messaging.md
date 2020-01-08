---
title: 設定 SIP 同盟、XMPP 同盟及 Public Instant Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及 Public Instant Messaging

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

[同盟]、[公用立即訊息連線] 和 [可擴展訊息] 和 [目前狀態通訊協定] （XMPP）定義不同類別的外部使用者-聯盟使用者。 同盟 Lync Server 部署或 XMPP 部署的使用者可以存取一組有限的服務，並由外部部署進行驗證。 遠端使用者是您 Lync Server 部署的成員，且擁有您的部署所提供的所有服務的存取權。

<div>


> [!NOTE]
> AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。



</div>

公用立即訊息連線是一種特殊的同盟類型，可讓 Lync Server 用戶端使用 Lync 2013 存取已設定的公用立即訊息合作夥伴。 目前的公用立即訊息連線性合作夥伴為：

  - <span></span>  
    美洲線上

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

公用立即訊息連線設定可讓 Lync 使用者透過以下方式存取公用立即訊息連線使用者：

  - IM 和目前狀態

  - Lync 用戶端中公用立即訊息線上連絡人的可見度

  - 某人與連絡人進行 IM 交談

  - 與 Windows Live 使用者進行音訊與視頻通話

Lync Server 同盟會定義您的 Lync Server 部署與其他 Office 通訊伺服器 2007 R2 或 Lync Server 部署之間的協定。 Lync Server 同盟設定可讓 Lync 使用者透過以下方式存取聯盟使用者：

  - IM 和目前狀態

  - 在 Lync 用戶端中建立同盟連絡人

XMPP 同盟會根據可擴展的訊息和目前狀態通訊協定來定義外部部署。 XMPP 設定可讓 Lync 使用者透過以下方式存取允許 XMPP 網域使用者：

  - IM 和目前狀態-僅限人員的人員

  - 在 Lync 用戶端中建立 XMPP 同盟連絡人

<div>


> [!IMPORTANT]
> Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。 針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Edge 伺服器外部同盟、公用立即訊息連線與 XMPP 使用者部署程式


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>許可權</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>決定要新增到現有邊緣部署的選項</p></td>
<td><p>執行拓撲建立器以編輯邊緣伺服器設定，並建立和發佈拓撲。 您現有的邊緣拓朴會將變更從中央管理儲存體複製到 Edge 伺服器。</p></td>
<td><p>[網域管理員] 群組和 [RTCUniversalServerAdmins] 群組</p>



> [!NOTE]
> 您可以使用屬於 [本機使用者] 群組成員的帳戶來編輯拓朴，但發佈拓朴需要網域系統管理員群組和 [RTCUniversalServerAdmins] 群組成員的帳戶。

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">在 Lync Server 2013 中建置 Edge 和 Director 拓撲</a></p></td>
</tr>
<tr class="even">
<td><p>準備設定</p></td>
<td><ol>
<li><p>確保已滿足系統先決條件。</p></li>
<li><p>設定內部和外部 DNS 記錄，以支援公用立即訊息連線、Lync 同盟與 XMPP 同盟</p></li>
<li><p>在防火牆上設定埠和通訊協定，以支援您要部署的同盟類型</p></li>
<li><p>取得並安裝公用憑證。 取得憑證所需的時間取決於憑證授權單位（CA）所頒發的憑證。 此步驟在部署時是選用的。 如果您目前不執行此步驟，您必須在邊緣伺服器設定期間進行。 在取得證書前，無法啟動 Edge 伺服器服務</p></li>
</ol></td>
<td><p>視您的組織而定，因為這些角色通常會分割在許多工作群組中</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息</a></p></td>
</tr>
<tr class="odd">
<td><p>針對同盟案例設定邊緣伺服器</p></td>
<td><ol>
<li><p>將匯出的拓撲設定檔案傳輸到每個邊緣伺服器，或允許複製完成</p></li>
<li><p>重新執行部署嚮導來安裝同盟的支援元件</p></li>
<li><p>設定邊緣伺服器</p></li>
<li><p>針對每個 Edge 伺服器要求並安裝證書</p></li>
<li><p>重新開機 Edge 伺服器服務</p></li>
</ol></td>
<td><p>[管理員] 群組</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">在 Lync Server 2013 中設定 Lync 同盟</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">在 Lync Server 2013 中設定 Public Instant Messaging Connectivity</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">在 Lync Server 2013 中設定 XMPP 同盟</a></p></td>
</tr>
<tr class="even">
<td><p>設定外部使用者存取的支援。</p></td>
<td><ol>
<li><p>使用 Lync Server [控制台] 外部使用者存取</p></li>
<li><p>設定外部存取原則以啟用與聯盟使用者或公用使用者的通訊</p></li>
<li><p>將 SIP 聯盟網域設定為允許或封鎖網域</p></li>
<li><p>針對公用立即訊息連線提供者啟用 SIP 聯盟提供者</p></li>
<li><p>針對每個 XMPP 網域設定 XMPP 聯盟合作夥伴</p></li>
</ol></td>
<td><p>指派給 CSAdministrator 角色的 RTCUniversalServerAdmins 群組或使用者帳戶</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中設定外部使用者存取支援</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">在 Lync Server 2013 中設定公用提供者的媒體加密</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證 Edge 伺服器設定</p></td>
<td><p>驗證服務器連線並從內部伺服器複製配置資料</p></td>
<td><p>針對複製、RTCUniversalServerAdmins 群組或使用者帳戶指派給 CSAdministrator roleFor 驗證使用者連線性的使用者，每一種類型的聯盟使用者</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">在 Lync Server 2013 中驗證 Edge 部署</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

