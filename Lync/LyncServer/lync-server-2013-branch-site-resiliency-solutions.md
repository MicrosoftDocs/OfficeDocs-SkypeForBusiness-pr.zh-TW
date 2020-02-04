---
title: Lync Server 2013：分支網站恢復解決方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16261d4add87462991c877e85cc6a0ff1e7fdfd4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Lync Server 2013 中的分支網站恢復解決方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-10_

為您的組織提供分支網站復原功能有明顯的優點。 具體來說，如果您失去中央網站的連線，分支網站使用者將會繼續使用企業語音服務和語音信箱（如果您要設定語音信箱重新路由設定，請參閱[Lync Server 2013 的分支網站復原需求](lync-server-2013-branch-site-resiliency-requirements.md)）。 不過，對於使用者少於25名的網站而言，復原方案可能無法提供足夠的投資回報。

如果您決定提供分支網站復原，您有三個選項。 下表可協助您判斷貴組織的最佳選項。

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>如果您 .。。</th>
<th>我們建議您使用 .。。</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>在分支網站上的25與1000使用者之間主持，如果投資回報不支援完整部署或本機管理支援無法使用</p></td>
<td><p>Survivable 分支裝置</p>
<p>Survivable 分支裝置是一個行業標準的刀片式伺服器，其中包含在 Windows Server 2008 R2 上執行的 Lync Server 註冊機構和中繼伺服器。 Survivable 分支裝置也包含公用的交換電話網絡（PSTN）閘道。 合格的協力廠商裝置（由 Survivable 分支裝置（SBA）資格/認證計畫中的 Microsoft 合作夥伴所開發）可在 WAN 發生故障時提供連續 PSTN 連線，但此方法不會提供復原的目前狀態與會議，因為這些功能依賴于中央網站上的前端伺服器。</p>
<p>如需 Survivable 分支裝置的詳細資訊&quot;，請參閱本主題&quot;稍後的 Survivable 分支裝置詳細資料。</p>
<p><strong>注意：</strong>如果您決定還要將 SIP 主幹與您的 Survivable 分支裝置搭配使用，請與您的 Survivable 分支裝置供應商聯繫，以瞭解哪個服務提供者最適合您的組織。</p></td>
</tr>
<tr class="even">
<td><p>在您的分支網站上的1000和2000使用者之間主持、缺乏強健的 WAN 連線，且已提供訓練有素的 Lync Server 管理員</p></td>
<td><p>Survivable 分支伺服器或兩個 Survivable 分支裝置。</p>
<p>Survivable 分支伺服器是一種 Windows Server 會議，其中已有安裝 Lync Server 註冊機構和中繼伺服器軟體的硬體需求。 它必須連線至 PSTN 閘道或 SIP 幹線給電話服務提供者。</p>
<p>如需 Survivable 分支伺服器的詳細資料&quot;，請參閱本主題&quot;稍後的 Survivable 分支伺服器詳細資料。</p></td>
</tr>
<tr class="odd">
<td><p>如果您除了適用于5000使用者的語音功能之外，還需要您的目前狀態與會議功能，且已提供訓練有素的 Lync Server 系統管理員</p></td>
<td><p>使用標準版伺服器（而不是分支網站）部署成中央網站。</p>
<p>全式 Lync Server 部署可在 WAN 發生故障時，提供連續的 PSTN 連線及彈性的目前狀態與會議。</p>
<p>如需準備此方案的詳細資訊，請參閱<a href="lync-server-2013-planning-for-your-organization.md">Lync server 2013 的組織規劃</a>，<a href="lync-server-2013-determining-your-system-requirements.md">判斷 lync server 2013 的系統需求</a>，<a href="lync-server-2013-determining-your-infrastructure-requirements.md">判斷 lync server 2013 的基礎結構需求</a>，以及規劃檔的其他相關區段。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>復原拓朴

下圖顯示分支網站復原的建議拓撲。

**分支網站復原選項**

![語音分支恢復能力選項](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "語音分支恢復能力選項")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Survivable 分支裝置詳細資料

Lync Server Survivable 分支裝置包含下列元件：

  - [使用者驗證]、[註冊] 和 [呼叫路由] 的註冊機構

  - 在註冊機與 PSTN 閘道之間處理信號的中繼伺服器

  - 在 WAN 中斷事件中，將呼叫路由至 PSTN 的 PSTN 閘道作為備用傳輸

  - 本機使用者資料儲存的 SQL Server Express

Survivable 分支裝置也包含 PSTN trunks、類比埠和乙太網路介面卡。

如果分支網站與中央網站的 WAN 連線無法使用，內部分支使用者會繼續向 Survivable 分支裝置註冊機構註冊，並使用 Survivable 分支裝置連線來取得不間斷的語音服務PSTN。 從家用或其他遠端位置連線的分支網站使用者，如果無法使用分支網站的 WAN 連結，就能在中央網站上註冊註冊機構伺服器。 這些使用者會有完整的整合通訊功能，其中一個例外情況是，分支網站的入站呼叫會移至 [語音信箱]。 WAN 連線變為可用時，應將完整的功能還原至分支網站使用者。 容錯移轉至 Survivable 分支裝置，而不是服務的還原，都需要 IT 系統管理員的狀態。

Lync Server 支援最多兩個分支網站上的 Survivable 分支裝置。

<div>


> [!NOTE]  
> 駐留在 Lync Server Survivable 分支裝置上的使用者無法建立新的聊天室，或無法查看現有聊天室的聊天室卡片。



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Survivable 分支裝置部署概述

Survivable 分支裝置是由與 Microsoft 合作的原始設備製造商生產，並由增值零售商代表其部署。 只有在中央網站部署 Lync Server、分支網站的 WAN 連線已就緒，且已針對企業語音啟用分支網站使用者時，才應進行此部署。

如需這些階段的詳細資訊，請參閱部署檔中的[使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>使用者權限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>為 Survivable 分支裝置設定 Active Directory 網域服務</p></td>
<td><p><strong>在中央網站：</strong></p>
<ol>
<li><p>針對將在分支網站上安裝並啟用 Survivable 分支裝置的技術人員，建立網域使用者帳戶（或企業身分識別）。</p></li>
<li><p>在 Active Directory 網域服務中，為 Survivable 分支裝置建立電腦帳戶（並提供適用的完整功能變數名稱（FQDN））。</p></li>
<li><p>在 [拓撲建立器] 中，建立及發佈 Survivable 分支裝置。</p></li>
</ol></td>
<td><p>技術員使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。 Survivable 分支裝置必須屬於 [RTCSBAUniversalServices] 群組，當您使用 [拓撲建立器] 時，就會自動進行這個作業。</p></td>
</tr>
<tr class="even">
<td><p>安裝並啟動 Survivable 分支裝置。</p></td>
<td><p><strong>在分支網站上：</strong></p>
<ol>
<li><p>將 Survivable 分支裝置連線至乙太網路埠和 PSTN 埠。</p></li>
<li><p>啟動 Survivable 分支裝置。</p></li>
<li><p>使用在中央網站為 Survivable 分支裝置建立的網域使用者帳戶，將 Survivable 分支裝置加入網域。 將 FQDN 和 IP 位址設定為與電腦帳戶中建立的 FQDN 相符。</p></li>
<li><p>使用 OEM 使用者介面設定 Survivable 分支裝置。</p></li>
<li><p>測試 PSTN 連線性。</p></li>
</ol></td>
<td><p>技術員使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Survivable 分支伺服器詳細資料

在拓撲建立器中建立分支網站，將 Survivable 分支伺服器新增到該網站，然後在您要安裝該角色的電腦上執行 Lync Server 部署嚮導。

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

