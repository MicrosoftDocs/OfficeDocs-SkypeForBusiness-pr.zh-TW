---
title: Lync Server 2013 簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Lync Server 2013 簡介

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

Lync Server 2013 及其用戶端軟體（例如 Lync 2013）可讓您的使用者以新的方式連線並保持連線，無論其物理位置為何。 Lync 和 Lync Server 會將人們在單一用戶端介面中通訊的不同方式整合在一起，並以單一管理基礎結構的方式來管理。

此表格和下列各節說明 Lync Server 針對您的使用者提供的主要功能集或*工作負荷*。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>負載</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM 和目前狀態</p></td>
<td><p>[立即訊息（IM）] 與「目前狀態」可協助您的使用者以更有效率的方式與其他人找到並溝通。</p>
<p>IM 會提供包含交談記錄的立即訊息平臺，並支援與公用 IM 網路（例如 MSN/Windows Live、Yahoo！、AOL 和 Google 交談）使用者的公用 IM 連線。</p>
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
<p>目前狀態會建立並顯示使用者的個人可用性，以及透過使用通用狀態（例如 [<strong>可用</strong>] 或 [<strong>忙碌</strong>]），以及更詳細的狀態（例如，<strong>立即返回</strong>和 [<strong>請勿打擾</strong>]）來進行溝通。 這個豐富的目前狀態資訊可讓其他使用者立即進行有效的通訊選項。</p></td>
</tr>
<tr class="even">
<td><p>會議</p></td>
<td><p>Lync 伺服器支援針對排程與臨時會議進行 IM 會議、音訊會議、網路會議、視訊會議及應用程式共用等支援。 單一用戶端支援所有這些會議類型。 Lync Server 也支援電話撥入式會議，讓公開交換電話網絡（PSTN）電話的使用者可以參與會議的音訊部分。</p>
<p>會議可以即時地以無縫方式變更和放大。 例如，單一會議可以在幾個使用者之間立即訊息的方式開始，並透過桌面共用和較大的觀眾立即、輕鬆且不中斷交談流程來上報音訊會議。</p></td>
</tr>
<tr class="odd">
<td><p>企業語音</p></td>
<td><p><em>企業語音</em>是 Lync Server 中的 [透過網際網路通訊協定（VoIP）] 提供的語音。 它會提供語音選項來加強或取代傳統的專用分支 exchange （PBX）系統。 除了 IP PBX 的完整電話功能之外，企業語音已整合為豐富的目前狀態、IM、共同作業和會議。 您可以直接支援通話應答、保留、繼續、傳輸、轉寄和轉移等功能，而個人化速度撥號金鑰會由連絡人清單取代，自動 intercom 會以 IM 取代。</p>
<p>企業語音支援透過呼叫許可控制（CAC）、分支辦公室留存以及資料復原的延伸選項，提供高可用性。</p></td>
</tr>
<tr class="even">
<td><p>支援遠端使用者</p></td>
<td><p>您可以透過部署稱為 [ <em>Edge 伺服器</em>] 的伺服器，為這些遠端使用者提供連線，以提供完整的 Lync 伺服器功能供您組織防火牆以外的使用者使用。 這些遠端使用者可以使用安裝了 Lync 2013、手機或網頁介面的個人電腦，連線至會議。</p>
<p>部署 Edge 伺服器也能讓您與合作夥伴或供應商組織<em>聯盟</em>。 同盟關聯可讓您的使用者將聯盟使用者放在連絡人清單、exchange 目前狀態資訊與這些使用者的立即訊息，並邀請他們加入語音通話、視頻通話及會議。</p></td>
</tr>
<tr class="odd">
<td><p>行動用戶端支援</p></td>
<td><p>此外，使用 Lync Server 行動服務，您的使用者可以在使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置時存取 Lync 功能，並以傳送和接收立即訊息、查看連絡人的方式執行這類活動。並查看目前狀態。 此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電。 對於不支援在背景中執行之應用程式的行動裝置，也支援推播通知。</p></td>
</tr>
<tr class="even">
<td><p>與其他產品整合</p></td>
<td><p>Lync Server 與數個其他產品整合，為您的使用者和系統管理員帶來額外的好處。</p>
<p>會議工具已整合至 Outlook，讓召集人可以一次性排程會議或啟動臨時會議，並讓出席者輕鬆加入會議。</p>
<p>目前狀態資訊已整合至 Outlook 和 SharePoint 中。</p>
<p>Exchange 整合通訊（UM）提供數個整合功能。 使用者可以查看在 Lync Server 中是否有新的語音信箱。 他們可以按一下 Outlook 訊息中的 [播放] 按鈕來聽到音訊語音信箱，或在通知訊息中查看語音信箱。</p>
<p>此外，使用 Exchange 2013 執行 Lync Server 2013 時，您可以透過兩個產品的用戶端存取多個新功能（例如，這是 Exchange 2013 資料庫中的連絡人），以及高解析度的相片。</p></td>
</tr>
<tr class="odd">
<td><p>簡單的部署</p></td>
<td><p>為了協助您規劃及部署伺服器和用戶端，Lync Server 提供拓撲建立器。</p>
<p>[拓撲建立器] 是 Lync Server 的安裝元件。 您可以使用 [拓撲建立器] 來建立、調整及發佈您規劃的拓撲。 它也會在您開始伺服器安裝之前驗證您的拓撲。 當您在個別伺服器上安裝 Lync Server 時，安裝程式會以拓撲中的指示方式來部署伺服器。</p></td>
</tr>
<tr class="even">
<td><p>簡單的管理</p></td>
<td><p>在您部署 Lync Server 之後，它會提供下列功能強大且精簡的管理工具：</p>
<ul>
<li><p>中央設定管理，可讓您集中管理變更，並將這些變更快速複製到整個部署。</p></li>
<li><p>Lync Server 控制台，為系統管理員提供的 web 圖形使用者介面。 透過這個以 web 為基礎的 UI，Lync Server 系統管理員可以從公司網路的任何地方管理其系統，而不需要在電腦上安裝專用管理軟體。</p></li>
<li><p>Lync Server 管理命令介面命令列管理工具，以 Windows PowerShell 命令列介面為基礎。 它提供豐富的命令集來管理產品的所有方面，並讓 Lync Server 系統管理員使用熟悉的工具自動化重複的工作。</p></li>
</ul></td>
</tr>
</tbody>
</table>


雖然 IM 和目前狀態功能會在每個 Lync Server 部署中自動安裝，但您可以選擇是否要部署會議、企業語音及遠端使用者存取，以根據貴組織的需求來調整您的部署。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的 IM 和目前狀態](lync-server-2013-im-and-presence.md)

  - [Lync Server 2013 中的會議](lync-server-2013-conferencing.md)

  - [Lync Server 2013 中的企業語音](lync-server-2013-enterprise-voice.md)

  - [使用 Lync Server 2013 的延展性](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

