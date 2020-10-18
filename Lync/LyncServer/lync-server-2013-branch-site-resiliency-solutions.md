---
title: Lync Server 2013：分支網站恢復解決方案
description: Lync Server 2013：分支網站恢復解決方案。
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
ms.openlocfilehash: 796ed22344f02bca16571ff5f156c6bb80b1fcfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572959"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Lync Server 2013 中的分支網站恢復解決方案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-10_

為您的組織提供分支網站恢復能力的好處是顯而易見的。 具體而言，如果您失去中央網站的連線，分支網站使用者將繼續擁有 Enterprise Voice service 和 Voice mail (（如果您設定語音信箱重新路由設定）。如需詳細資訊，請參閱 [Lync Server 2013) 的分支網站恢復需求](lync-server-2013-branch-site-resiliency-requirements.md) 。 但對於使用者人數低於 25 位的網站而言，恢復能力解決方案所提供的投資報酬率可能不夠。

如果您決定要提供分支網站恢復能力，您有三個選項。下表可協助您判斷最適合您的組織之選項。

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>如果您...</th>
<th>建議您使用...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>在您的分支網站上主控 25 到 1000 名使用者，且投資報酬率不足以支應完整部署，或是不具本機管理支援</p></td>
<td><p>Survivable Branch Appliance</p>
<p>Survivable 分支裝置是業界標準的刀片伺服器，具有在 Windows Server 2008 R2 上執行的 Lync Server 註冊機構和轉送伺服器。 Survivable Branch 裝置也包含公用交換電話網路 (PSTN) 閘道。 合格的第三方裝置 (由參與 Survivable Branch Appliance (SBA) 資格/認證方案的 Microsoft 協力廠商所開發) 在 WAN 失效時仍可提供持續的 PSTN 連線，但這個方法無法提供可恢復的顯示狀態與會議功能，因為這些功能依存於中央網站上的前端伺服器。</p>
<p>如需 Survivable 分支裝置的詳細資訊，請參閱 &quot; &quot; 本主題稍後的 Survivable Branch 裝置詳細資料。</p>
<p><strong>附注：</strong> 如果您決定同時將 SIP 主幹與 Survivable 分支裝置搭配使用，請與您的 Survivable 分支裝置廠商聯繫，以瞭解哪一種服務提供者最適合您的組織。</p></td>
</tr>
<tr class="even">
<td><p>在分支網站上的1000和2000使用者間主機、缺乏彈性的 WAN 連線，且已訓練有素的 Lync Server 系統管理員可用</p></td>
<td><p>Survivable 分支伺服器或兩個 Survivable 分支裝置。</p>
<p>Survivable 分支伺服器是 Windows Server 會議指定的硬體需求，其上已安裝 Lync Server 註冊機構和轉送伺服器軟體。 該伺服器必須將 PSTN 閘道或 SIP 主幹連線至電話服務提供者。</p>
<p>如需 Survivable 分支伺服器的詳細資訊，請參閱 &quot; &quot; 本主題稍後的 Survivable Branch Server details。</p></td>
</tr>
<tr class="odd">
<td><p>如果您除了語音功能之外，還需要最多5000名使用者的目前狀態與會議功能，且有訓練有素的 Lync Server 系統管理員可用</p></td>
<td><p>以 Standard Edition Server 部署為中央網站，而非分支網站。</p>
<p>在發生 WAN 失敗時，完整的 Lync 伺服器部署會提供連續的 PSTN 連線和彈性顯示功能和會議。</p>
<p>如需準備此方案的詳細資訊，請參閱 <a href="lync-server-2013-planning-for-your-organization.md">組織規劃 Lync server 2013</a>， <a href="lync-server-2013-determining-your-system-requirements.md">判斷 lync server 2013 的系統需求</a>， <a href="lync-server-2013-determining-your-infrastructure-requirements.md">判斷 lync server 2013 的基礎結構需求</a>，以及規劃檔的其他相關章節。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>恢復能力拓撲

下圖顯示分支網站恢復能力所適用的建議拓撲。

**分支網站恢復能力選項**

![語音分支恢復選項](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "語音分支恢復選項")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance 詳細資料

Lync Server Survivable Branch 裝置包含下列元件：

  - 使用者驗證、登錄與通話路由所需的登錄器

  - 用以處理登錄器與 PSTN 閘道間往來訊號的中繼伺服器

  - 在 WAN 中斷時，用以將通話路由至 PSTN 作為後援傳輸的 PSTN 閘道

  - 供本機使用者存放資料的 SQL Server Express

Survivable 分支裝置也包含 PSTN 主幹、類比埠和乙太網路介面卡。

如果分支網站與中央網站之間的 WAN 連線無法使用，則內部分支使用者仍會向 Survivable Branch 裝置註冊機構註冊，並使用 Survivable Branch 裝置連接至 PSTN，以取得不間斷的語音服務。 當分支網站的 WAN 連結無法使用時，從家中或其他遠端位置連線的分支網站使用者將可使用中央網站上的登錄器伺服器進行登錄。 這些使用者將可擁有完整的整合通訊功能，但有一例外，傳入分支網站的來電會轉接至語音信箱。 當 WAN 連線恢復時，分支網站使用者即應可重獲完整的功能。 容錯移轉至 Survivable Branch 裝置或服務的還原，都不需要有 IT 系統管理員的狀態。

Lync Server 在分支網站上支援最多兩個 Survivable 分支裝置。

<div>


> [!NOTE]  
> 在 Lync Server Survivable Branch 裝置上的使用者無法建立新聊天室或查看現有聊天室的會議室卡片。



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Survivable Branch Appliance 部署概觀

Survivable 分支裝置是由原始設備製造商生產，與 Microsoft 合作，並由增值零售商自行部署。 只有在中央網站部署 Lync Server 之後，才會發生此部署，分支網站的 WAN 連線會就地存在，且會為企業語音啟用分支網站使用者。

如需這些階段的詳細資訊，請參閱部署檔中的 [部署 Survivable Branch 裝置或含 Lync Server 2013 的伺服器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>使用者權限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>為 Survivable Branch 裝置設定 Active Directory 網域服務</p></td>
<td><p><strong>在中央網站上：</strong></p>
<ol>
<li><p>在分支網站上，為將安裝及啟動 Survivable 分支裝置的技術人員建立網域使用者帳戶 (或企業身分識別) 。</p></li>
<li><p>使用 Active Directory 網域服務中 Survivable Branch 裝置的適用的完整功能變數名稱 (FQDN) # A3，建立電腦帳戶 (。</p></li>
<li><p>在 [拓撲產生器] 中，建立併發布 Survivable Branch 裝置。</p></li>
</ol></td>
<td><p>技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。 Survivable 分支裝置必須屬於 RTCSBAUniversalServices 群組，這會在您使用拓撲產生器時自動進行。</p></td>
</tr>
<tr class="even">
<td><p>安裝和啟動 Survivable 分支裝置。</p></td>
<td><p><strong>在分支網站上：</strong></p>
<ol>
<li><p>將 Survivable 分支裝置連接至乙太網路埠和 PSTN 埠。</p></li>
<li><p>啟動 Survivable 分支裝置。</p></li>
<li><p>使用在中央網站為 Survivable Branch 裝置建立的網域使用者帳戶，將 Survivable 分支裝置加入網域。 設定 FQDN 與 IP 位址，使其符合在電腦帳戶中建立的 FQDN。</p></li>
<li><p>使用 OEM 使用者介面設定 Survivable 分支裝置。</p></li>
<li><p>測試 PSTN 連線。</p></li>
</ol></td>
<td><p>技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Survivable Branch Server 詳細資料

在 [拓撲產生器] 中，建立分支網站，將 Survivable 分支伺服器新增至該網站，然後在您要安裝該角色的電腦上執行 Lync Server 部署嚮導。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

