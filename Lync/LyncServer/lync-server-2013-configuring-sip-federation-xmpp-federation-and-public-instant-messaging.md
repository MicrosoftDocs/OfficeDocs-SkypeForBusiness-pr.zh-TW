---
title: 設定 SIP 同盟、XMPP 同盟及公用立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f3fa4f3b78f53df101da42a2e6b7630cdfb71dd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537070"
---
# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及公用立即訊息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

同盟、公用立即訊息連線及可延伸的訊息和顯示狀態通訊協定 (XMPP) 定義不同類別的外部使用者–同盟使用者。 同盟 Lync Server 部署或 XMPP 部署的使用者可以存取有限的一組服務，而且會透過外部部署進行驗證。 遠端使用者是 Lync Server 部署的成員，而且可以存取部署所提供的所有服務。

<div>


> [!NOTE]
> AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。



</div>

公用立即訊息連線是一種特殊的同盟類型，可讓 Lync Server 用戶端使用 Lync 2013 存取已設定的公用立即訊息夥伴。 目前的公用立即訊息連線夥伴為：

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    雅虎\!

公用立即訊息連線設定可讓 Lync 使用者透過下列方式存取公用立即訊息連線使用者：

  - IM 和目前狀態

  - Lync 用戶端中公用立即訊息線上連絡人的可見度

  - 與連絡人進行 IM 交談的人員

  - 使用 Windows Live 使用者的音訊和影片通話

Lync Server 同盟定義 Lync Server 部署與其他 Office 通訊伺服器 2007 R2 或 Lync Server 部署之間的合約。 Lync Server 同盟設定可讓 Lync 使用者透過下列方式存取同盟使用者：

  - IM 和目前狀態

  - 在 Lync 用戶端中建立同盟連絡人

XMPP 同盟會根據可延伸的訊息和顯示狀態通訊協定，定義外部部署。 XMPP 設定可讓 Lync 使用者依下列方式存取允許的 XMPP 網域使用者：

  - IM 和目前狀態–僅限人員

  - 在 Lync 用戶端中建立 XMPP 同盟連絡人

<div>


> [!IMPORTANT]
> Lync Server 2013 的 XMPP 功能會經過測試，並受 Microsoft 支援，以進行與 Google 交談的立即訊息同盟。 對於任何其他 XMPP 系統，請聯繫協力廠商廠商，以確認其支援與 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>Edge Server 外部同盟、公用立即訊息連線和 XMPP 使用者部署程式


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>權限</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>決定要新增至現有 Edge 部署的選項</p></td>
<td><p>執行拓撲產生器以編輯 Edge Server 設定，以及建立及發行拓撲。 您的現有 Edge 拓撲會將中央管理存放區的變更複寫至 Edge Server。</p></td>
<td><p>Domain Admins 群組和 RTCUniversalServerAdmins 群組</p>



> [!NOTE]
> 您可以使用本機使用者群組的成員帳戶來編輯拓撲，但發行拓撲需要的帳戶是 Domain Admins 群組和 RTCUniversalServerAdmins 群組的成員帳戶。

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">在 Lync Server 2013 中建立 edge 和 Director 拓撲</a></p></td>
</tr>
<tr class="even">
<td><p>準備安裝</p></td>
<td><ol>
<li><p>確定已符合系統先決條件。</p></li>
<li><p>設定內部和外部 DNS 記錄，以支援公用立即訊息連線、Lync 同盟及 XMPP 同盟</p></li>
<li><p>在防火牆上設定埠和通訊協定，以支援您要部署的同盟類型</p></li>
<li><p>取得及安裝公用憑證。 取得憑證所需的時間，視發出憑證的憑證授權單位 (CA) 而定。 在部署中這一點是選用的步驟。 如果您此時不執行此步驟，則必須在 Edge Server 設定期間執行此步驟。 在取得憑證之前，無法啟動 Edge Server 服務</p></li>
</ol></td>
<td><p>視您的組織而定，因為這些角色通常會分割許多工作群組</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">在 Lync Server 2013 中規劃 SIP、XMPP 同盟和公用立即訊息</a></p></td>
</tr>
<tr class="odd">
<td><p>設定同盟案例的 Edge Server</p></td>
<td><ol>
<li><p>將匯出的拓撲配置檔案傳輸至每一部 Edge Server，或允許複製完成</p></li>
<li><p>Re-Run 部署嚮導，以安裝同盟的支援元件</p></li>
<li><p>設定 Edge Server</p></li>
<li><p>針對每一部 Edge Server 要求並安裝憑證</p></li>
<li><p>重新開機 Edge Server 服務</p></li>
</ol></td>
<td><p>Administrators 群組</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">在 Lync Server 2013 中設定 Lync 同盟</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">在 Lync Server 2013 中設定公用立即訊息連線</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">在 Lync Server 2013 中設定 XMPP 同盟</a></p></td>
</tr>
<tr class="even">
<td><p>設定外部使用者存取的支援。</p></td>
<td><ol>
<li><p>使用 Lync Server 控制台外部使用者存取</p></li>
<li><p>設定外部存取原則以啟用與同盟使用者或公用使用者的通訊</p></li>
<li><p>設定 SIP 同盟網域以允許或封鎖網域</p></li>
<li><p>啟用公用立即訊息連線提供者的 SIP 同盟提供者</p></li>
<li><p>設定每個 XMPP 網域的 XMPP 同盟協力廠商</p></li>
</ol></td>
<td><p>指派給 CSAdministrator 角色的 RTCUniversalServerAdmins 群組或使用者帳戶</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中設定外部使用者存取的支援</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">在 Lync Server 2013 中設定公用提供者的媒體加密</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證 Edge Server 設定</p></td>
<td><p>驗證服務器連線以及內部伺服器的設定資料複寫</p></td>
<td><p>若要驗證複寫，請 RTCUniversalServerAdmins 群組或使用者帳戶指派給使用者連線的 CSAdministrator roleFor 驗證，每種類型的同盟使用者的使用者</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">在 Lync Server 2013 中驗證 edge 部署</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 的範例 XMPP 設定– XMPP 與 Google 交談的同盟</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

