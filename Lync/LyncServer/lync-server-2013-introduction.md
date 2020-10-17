---
title: Lync Server 2013 簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2878f47fcace98bbd9e156f24c2b87e85faf728
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525230"
---
# <a name="introduction-to-lync-server-2013"></a>Lync Server 2013 簡介

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

Lync Server 2013 及其用戶端軟體（如 Lync 2013）可讓您的使用者以新的方式連線並保持連線，不論其物理位置為何。 Lync 和 Lync Server 會集中在單一用戶端介面中通訊的不同方式，以整合平臺的方式部署，並透過單一管理基礎結構進行管理。

此表格及下列各節說明 Lync Server 為您的使用者提供的主要功能組或 *工作負載*。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>工作負載</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM 與顯示狀態</p></td>
<td><p>立即訊息 (IM) 與顯示狀態，可協助您的使用者有效且有效地尋找及與彼此進行通訊。</p>
<p>IM 可提供「立即訊息平臺」與「交談記錄」，並支援與公用 IM 網路的使用者進行公用 IM 連線，例如 MSN/Windows Live、Yahoo！、AOL 和 Google 交談。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>


</div>
<p><strong>目前</strong>狀態會建立並顯示使用者的個人可用性和意願，以透過使用的常見狀態（如正確或<strong>忙碌</strong>）進行通訊，以及更詳細的狀態，如正確，也就<strong>是</strong>「<strong>請勿打擾</strong>」。 這種豐富的目前狀態資訊可讓其他使用者立即進行有效的通訊選擇。</p></td>
</tr>
<tr class="even">
<td><p>會議</p></td>
<td><p>Lync Server 包含對排程和即時會議的 IM 會議、音訊會議、web 會議、影片會議和應用程式共用的支援。 所有這些會議類型都支援單一用戶端。 Lync Server 也支援電話撥入式會議，讓公用交換電話網路 (PSTN) 電話的使用者可以參與會議的音訊部分。</p>
<p>會議可以即時無縫地變更與成長。 例如，單一會議可以在少數使用者之間開始立即訊息，並透過桌面共用和較大的物件立即、輕鬆且不中斷交談流程的方式升級至音訊會議。</p></td>
</tr>
<tr class="odd">
<td><p>設定使用者</p></td>
<td><p><em>Enterprise voice</em> 是 Lync Server 中) 提供的語音 Over 網際網路通訊協定 (VoIP。 它會提供語音選項，以加強或取代傳統專用交換機 exchange (PBX) 系統。 除了 IP PBX 的完整電話語音功能之外，企業語音已與豐富的目前狀態、IM、共同作業和會議整合。 可直接支援通話答案、保留、繼續、轉接、轉寄和轉移等功能，而個人化速度撥號機碼會取代為連絡人清單，而自動 intercom 會取代為 IM。</p>
<p>Enterprise Voice 支援通過通話許可控制的高可用性 (CAC) 、分支機搆留存能力，以及資料恢復的延伸選項。</p></td>
</tr>
<tr class="even">
<td><p>遠端使用者的支援</p></td>
<td><p>您可以透過部署稱為 <em>Edge</em> server 的伺服器，為這些遠端使用者提供連線，為目前組織防火牆外部的使用者提供完整的 Lync Server 功能。 這些遠端使用者可以使用已安裝 Lync 2013 的個人電腦、電話或 web 介面，連線至會議。</p>
<p>部署 Edge Server 也可讓您與合作夥伴或廠商組織 <em>聯盟</em> 。 同盟關聯可讓您的使用者將同盟使用者放在其連絡人清單、exchange 目前狀態資訊和立即訊息與這些使用者，並邀請他們撥打語音通話、影片通話和會議。</p></td>
</tr>
<tr class="odd">
<td><p>行動用戶端支援</p></td>
<td><p>此外，借助 Lync Server 行動服務，您的使用者可以在使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置時存取 Lync 功能，並執行類似傳送和接收立即訊息、查看連絡人及查看顯示狀態等活動。 此外，行動裝置還可支援某些 Enterprise Voice 功能，例如按一下加入會議、從公司撥號、單一號碼搜尋、語音信箱及未接來電。 對於不支援在後臺執行之應用程式的行動裝置，也支援推播通知。</p></td>
</tr>
<tr class="even">
<td><p>與其他產品整合</p></td>
<td><p>Lync Server 會與其他數種產品整合，為您的使用者和系統管理員提供額外的好處。</p>
<p>會議工具已整合至 Outlook，讓召集人可以透過單一按一下來排程會議或啟動即時會議，並使出席者輕鬆加入。</p>
<p>目前狀態資訊已整合至 Outlook 和 SharePoint。</p>
<p>Exchange 整合通訊 (UM) 提供數種整合功能。 使用者可以查看是否有 Lync Server 中的新語音信箱。 他們可以按一下 Outlook 訊息中的 [播放] 按鈕，收聽音訊語音信箱，或在通知訊息中查看語音信箱。</p>
<p>此外，使用 Exchange 2013 來執行 Lync Server 2013，可啟用多種新功能，例如整合連絡人存放區，可供兩種產品的用戶端存取，以及儲存在 Exchange 2013 資料庫中之連絡人的高解析度相片。</p></td>
</tr>
<tr class="odd">
<td><p>簡易部署</p></td>
<td><p>為了協助您規劃及部署伺服器及用戶端，Lync Server 會提供拓撲產生器。</p>
<p>拓撲產生器是 Lync Server 的安裝元件。 您可以使用拓撲產生器來建立、調整和發行您規劃的拓撲。 在您開始伺服器安裝之前，它也會驗證您的拓撲。 當您在個別伺服器上安裝 Lync Server 時，安裝程式會以拓撲中的導向方式來部署伺服器。</p></td>
</tr>
<tr class="even">
<td><p>簡易管理</p></td>
<td><p>在您部署 Lync Server 之後，它會提供下列功能強大且簡化的管理工具：</p>
<ul>
<li><p>中央設定管理，可讓您集中管理變更，並將變更快速複寫至整個部署。</p></li>
<li><p>Lync Server 控制台，是系統管理員的 web 型圖形使用者介面。 透過這種以 web 為基礎的 UI，Lync Server 系統管理員可以從公司網路的任何地方管理其系統，而不需要在其電腦上安裝專門的管理軟體。</p></li>
<li><p>Lync Server 管理命令介面命令列管理工具，以 Windows PowerShell 命令列介面為基礎。 它會提供豐富的命令集，以管理產品的各個層面，並讓 Lync Server 系統管理員可以使用熟悉的工具來自動化重複的工作。</p></li>
</ul></td>
</tr>
</tbody>
</table>


當 IM 及顯示狀態功能會自動安裝在每個 Lync Server 部署中時，您可以選擇是否要部署會議、Enterprise Voice 及遠端使用者存取，以根據組織的需求來定義您的部署。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的 IM 和目前狀態](lync-server-2013-im-and-presence.md)

  - [Lync Server 2013 中的會議](lync-server-2013-conferencing.md)

  - [Lync Server 2013 中的 Enterprise Voice](lync-server-2013-enterprise-voice.md)

  - [可擴充性搭配 Lync Server 2013](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

