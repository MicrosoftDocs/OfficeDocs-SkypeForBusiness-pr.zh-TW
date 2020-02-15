---
title: Lync Server 2013： 分支網站恢復解決方案
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
ms.openlocfilehash: 019da9259cae95d019f954f275ed36a5f79174e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Lync Server 2013 中的分支網站恢復解決方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-12-10_

為您的組織提供分支網站恢復能力的好處是顯而易見的。 具體而言，如果您遺失連線至中央網站，分支網站使用者將繼續擁有企業語音服務和語音信箱 (如果您設定語音信箱重新路由設定; 如需詳細資訊，請參閱[Lync Server 2013 的分支網站恢復能力需求](lync-server-2013-branch-site-resiliency-requirements.md))。 但對於使用者人數低於 25 位的網站而言，恢復能力解決方案所提供的投資報酬率可能不夠。

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
<p>Survivable Branch Appliance 是 Lync Server 登錄器的業界標準] 刀鋒視窗中伺服器和 Windows Server 2008 R2 上執行的中繼伺服器。 Survivable Branch Appliance 也包含公用交換的電話網路 (PSTN) 閘道。 合格的第三方裝置 (由參與 Survivable Branch Appliance (SBA) 資格/認證方案的 Microsoft 協力廠商所開發) 在 WAN 失效時仍可提供持續的 PSTN 連線，但這個方法無法提供可恢復的顯示狀態與會議功能，因為這些功能依存於中央網站上的前端伺服器。</p>
<p>如需 Survivable Branch Appliance 的詳細資訊，請參閱&quot;Survivable Branch Appliance 詳細資料，&quot;本主題稍後。</p>
<p><strong>附註：</strong>如果您決定也使用 SIP 主幹與您 Survivable Branch Appliance，請連絡您的 Survivable Branch Appliance 廠商連絡，以了解哪些服務提供者最適合您的組織。</p></td>
</tr>
<tr class="even">
<td><p>主控 1000年到 2000年分支網站的使用者之間、 缺少可恢復的 WAN 連線，以及擁有經過訓練的 Lync Server 系統管理員</p></td>
<td><p>Survivable Branch 伺服器或兩個 Survivable Branch Appliance。</p>
<p>Survivable Branch 伺服器是具有 Lync 伺服器登錄器和中繼伺服器軟體在其上安裝 Windows Server 符合指定的硬體需求。 該伺服器必須將 PSTN 閘道或 SIP 主幹連線至電話服務提供者。</p>
<p>如需 Survivable Branch 伺服器的詳細資訊，請參閱&quot;Survivable Branch Server 詳細資料，&quot;本主題稍後。</p></td>
</tr>
<tr class="odd">
<td><p>如果您需要的目前狀態和會議功能除了語音功能達 5000 名使用者，並有經過訓練的 Lync Server 系統管理員</p></td>
<td><p>以 Standard Edition Server 部署為中央網站，而非分支網站。</p>
<p>完整規模 Lync Server 部署提供持續的 PSTN 連線可恢復的目前狀態和 WAN 故障時的會議。</p>
<p>如需準備針對此解決方案的詳細資訊，請參閱<a href="lync-server-2013-planning-for-your-organization.md">組織規劃 Lync Server 2013</a>、<a href="lync-server-2013-determining-your-system-requirements.md">判斷 Lync Server 2013 系統需求</a>、<a href="lync-server-2013-determining-your-infrastructure-requirements.md">決定 Lync Server 2013 的基礎結構需求</a>，以及規劃文件的其他相關章節。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>恢復能力拓撲

下圖顯示分支網站恢復能力所適用的建議拓撲。

**分支網站恢復能力選項**

![語音分支恢復能力選項](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "語音分支恢復能力選項")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance 詳細資料

Lync Server Survivable Branch Appliance 包含下列元件：

  - 使用者驗證、登錄與通話路由所需的登錄器

  - 用以處理登錄器與 PSTN 閘道間往來訊號的中繼伺服器

  - 在 WAN 中斷時，用以將通話路由至 PSTN 作為後援傳輸的 PSTN 閘道

  - 供本機使用者存放資料的 SQL Server Express

Survivable Branch Appliance 也包含 PSTN 主幹、 類比連接埠與乙太網路介面卡。

如果分支網站的 WAN 連線至中央網站變成無法使用，內部的分支使用者繼續 Survivable Branch Appliance 註冊機構註冊並使用 Survivable Branch Appliance 的連線，以取得不會中斷的語音服務至 PSTN。 當分支網站的 WAN 連結無法使用時，從家中或其他遠端位置連線的分支網站使用者將可使用中央網站上的登錄器伺服器進行登錄。 這些使用者將可擁有完整的整合通訊功能，但有一例外，傳入分支網站的來電會轉接至語音信箱。 當 WAN 連線恢復時，分支網站使用者即應可重獲完整的功能。 不在容錯移轉至 Survivable Branch Appliance 或服務的還原要求 IT 系統管理員的目前狀態。

Lync Server 支援最多兩個 Survivable Branch Appliance 分支網站。

<div>


> [!NOTE]  
> 位於 Lync Server Survivable Branch Appliance 的使用者將無法建立新聊天室或檢視現有的會議室會議室卡片。



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Survivable Branch Appliance 部署概觀

Survivable Branch Appliance 是生產原始設備製造商，以與 Microsoft 合作關係，及在其代理上部署的加值零售商。 在中央網站已部署 Lync Server、 分支站台的 WAN 連線已經準備就緒，及分支網站使用者啟用 Enterprise Voice 之後，才應執行此部署。

如需這些階段的詳細資訊，請參閱部署文件中的[部署 Survivable Branch Appliance 或 survivable branch Server 與 Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 。


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
<td><p>設定 Survivable Branch Appliance 的 Active Directory 網域服務</p></td>
<td><p><strong>在中央網站上：</strong></p>
<ol>
<li><p>將會安裝並啟動 Survivable Branch Appliance 分支網站的技術人員建立網域使用者帳戶 （或企業身分識別）。</p></li>
<li><p>建立 Active Directory 網域服務中的 Survivable Branch Appliance 的電腦帳戶 （適用於完整的網域名稱 (FQDN)）。</p></li>
<li><p>在拓撲產生器中，建立及發佈 Survivable Branch Appliance。</p></li>
</ol></td>
<td><p>技術人員的使用者帳戶必須是 RTCUniversalSBATechnicians 的成員。 Survivable Branch Appliance 必須屬於 [RTCSBAUniversalServices 群組中，當您使用拓撲產生器自動發生。</p></td>
</tr>
<tr class="even">
<td><p>安裝並啟動 Survivable Branch Appliance。</p></td>
<td><p><strong>在分支網站上：</strong></p>
<ol>
<li><p>連線至乙太網路連接埠與 PSTN 連接埠的 Survivable Branch Appliance。</p></li>
<li><p>啟動 Survivable Branch Appliance。</p></li>
<li><p>將 Survivable Branch Appliance 加入至使用 Survivable Branch appliance 在中央網站建立的網域使用者帳戶的網域。 設定 FQDN 與 IP 位址，使其符合在電腦帳戶中建立的 FQDN。</p></li>
<li><p>設定 Survivable Branch Appliance 使用 OEM 使用者介面。</p></li>
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

在拓撲產生器建立分支網站，該網站中，新增 Survivable Branch 伺服器並執行 Lync Server 部署精靈在電腦上您要安裝角色。

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

