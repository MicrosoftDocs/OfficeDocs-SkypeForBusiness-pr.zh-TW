---
title: Lync Server 2013： E9 的部署檢查清單-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efe5c55386eb431c91e798ad960cc510ce33ce1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 的 E9 部署檢查清單-1-1

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

若要有效地規劃增強型9-1-1 （E9-1-1），請務必包含下列部署需求：

  - 部署 E9 的先決條件-1-1。

  - 部署 E9 所需的步驟-1-1。

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>E9 的部署必備元件-1-1

在您部署 E9-1-1 之前，您必須已部署 Lync Server 內部伺服器，包括中央管理儲存體、前端池或標準版伺服器、一或多個轉送伺服器或轉送伺服器池，以及 Lync Server 用戶端。 此外，E9 部署需要將 SIP 主幹轉至合格的 E9-1 服務提供者，或緊急位置識別號碼（ELIN）閘道到您的公用交換電話網絡（PSTN）。 Lync Server 僅支援在美國境內使用 E9-1 服務提供者。

</div>

<div>

## <a name="deployment-process"></a>部署程式

下表提供 E9-1-1 1 部署程式的概覽。 如需部署步驟的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [設定增強型 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md) ]。


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
<th>角色</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設定語音使用方式、路由和主幹設定</p></td>
<td><ol>
<li><p>建立新的 PSTN 使用記錄。 這與位置原則中用於<strong>PSTN 使用</strong>設定的名稱相同。</p></li>
<li><p>建立或指派語音路由至在上一個步驟建立的 PSTN 使用記錄，然後將閘道屬性指向 E9-1-1 SIP 幹線或 ELIN 閘道。</p></li>
<li><p>針對 SIP 幹線 E9-1 服務提供者，請設定要透過 SIP 處理 E9-1-1 呼叫的幹線，以使用<strong>set-EnablePIDFLOSupport</strong> Cmdlet 來傳送 PIDF-LO 資料。</p></li>
<li><p>您也可以選擇針對 SIP 幹線 E9-1 服務提供者，為不是由 E9-1-1 服務提供者 SIP 幹線處理的呼叫建立或指派本機 PSTN 路由。 如果無法連線至 E9-1-1 服務提供者，就會使用這個路由。 如果您的 E9-1 服務提供者支援，請將幹線設定規則指派給閘道，將911撥號字串轉換為國內/地區緊急電話回應中心（ECRC）的直接向內撥號（已發出）號碼。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">在 Lync Server 2013 中設定 E9-1-1 的語音路由</a></p></td>
</tr>
<tr class="even">
<td><p>建立位置原則並將其指派給使用者和子網</p></td>
<td><ol>
<li><p>查看全域位置原則。</p></li>
<li><p>建立具有使用者層級範圍的位置原則;或者，如果組織有一個以上的網站有不同的緊急用途，請建立具有網路層級範圍的位置原則。</p></li>
<li><p>將位置原則指派給網路網站。</p></li>
<li><p>將適當的子網新增至網路網站。</p></li>
<li><p>可選將位置原則指派給使用者原則。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin （建立位置原則除外）</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">在 Lync Server 2013 中建立位置原則</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">在 Lync Server 2013 的網路網站中新增位置原則</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">在 Lync Server 2013 中將子網與網路網站進行 E9-1-1</a></p></td>
</tr>
<tr class="odd">
<td><p>設定位置資料庫</p></td>
<td><ol>
<li><p>使用網路元素對應至位置來填入資料庫。</p></li>
<li><p>針對 ELIN 閘道，將 ELINs 新增至&lt;[&gt;公司名稱] 資料行。</p></li>
<li><p>設定連線至 E9-1 服務提供者，以驗證位址。</p></li>
<li><p>使用 E9-1 服務提供者驗證位址。</p></li>
<li><p>發佈更新後的資料庫。</p></li>
<li><p>若是 ELIN 閘道，請將 ELINs 上傳到 PSTN 載波的自動位置識別（阿裡）資料庫。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">在 Lync Server 2013 中設定位置資料庫</a></p></td>
</tr>
<tr class="even">
<td><p>設定高級功能（選用）</p></td>
<td><ol>
<li><p>設定 SNMP 應用程式的 URL。</p></li>
<li><p>設定次要位置資訊服務之位置的 URL。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">在 Lync Server 2013 中設定 SNMP 應用程式</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中設定次要位置資訊服務</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

