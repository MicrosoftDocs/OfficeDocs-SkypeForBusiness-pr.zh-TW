---
title: Lync Server 2013： E9-1-1 的部署檢查清單
description: Lync Server 2013： E9-1-1 的部署檢查清單。
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
ms.openlocfilehash: 0c93762e2acef5e065249ced17bfa0eab2f159e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568349"
---
# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 中的 E9-1-1 的部署檢查清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

若要有效規劃增強型 9-1-1 (E9-1-1) ，請務必包含下列部署需求：

  - 部署 E9-1-1 的必要條件。

  - 部署 E9-1-1 所需的步驟。

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 的部署必要條件

在您部署 E9-1-1 之前，您必須已部署 Lync Server 內部伺服器，包括中央管理存放區、前端集區或 Standard Edition Server、一或多部轉送伺服器或轉送伺服器集區，以及 Lync Server 用戶端。 此外，E9-1-1 部署需要 SIP 主幹給合格的 E9-1-1 服務提供者或緊急位置識別號碼 (ELIN) 閘道至您公用交換電話網路 (PSTN) 。 Lync Server 僅支援在美國內使用 E9-1-1 服務提供者。

</div>

<div>

## <a name="deployment-process"></a>部署程式

下表提供 E9-1-1 部署程式的概述。 如需部署步驟的詳細資訊，請參閱部署檔中的 [Configure The Lync Server 2013 中的 Configure 增強 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md) 。


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
<th>角色</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設定語音使用方式、路由和主幹設定</p></td>
<td><ol>
<li><p>建立新的 PSTN 使用方式記錄。 這與位置原則中用於 <strong>PSTN 使用狀況</strong> 設定的名稱相同。</p></li>
<li><p>建立或指派語音路由至上一個步驟中建立的 PSTN 使用方式記錄，然後將閘道屬性指向 E9-1-1 SIP 主幹或 ELIN 閘道。</p></li>
<li><p>若為 SIP 主幹 E9-1-1 服務提供者，請設定主幹以透過 SIP 處理 E9-1-1 呼叫以透過使用 <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> Cmdlet 來傳遞 PIDF-LO 資料。</p></li>
<li><p>（選用）對於 SIP 主幹 E9-1-1 服務提供者，針對未由 E9-1-1 服務提供者的 SIP 主幹處理的呼叫建立或指派本機 PSTN 路由。 如果與 E9-1-1 服務提供者的連線無法使用，則會使用此路由。 如果您的 E9-1-1 服務提供者支援，請將主幹設定規則指派給將911撥號字串轉譯成直接向內撥號 (已) 國家/地區緊急通話回應中心 (ECRC) 的號碼。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">在 Lync Server 2013 中設定 E9-1-1 語音路由</a></p></td>
</tr>
<tr class="even">
<td><p>建立位置原則並將其指派給使用者和子網</p></td>
<td><ol>
<li><p>複查全域位置原則。</p></li>
<li><p>建立具有使用者層級範圍的位置原則;或者，如果組織有多個具有不同緊急用途的網站，請使用網路層級範圍建立一個位置原則。</p></li>
<li><p>將位置原則指派給網路網站。</p></li>
<li><p>將適當的子網新增至網路網站。</p></li>
<li><p> (選用) 指派位置原則給使用者原則。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (除了建立位置原則) </p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">在 Lync Server 2013 中建立位置原則</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">在 Lync Server 2013 中將位置原則新增至網路網站</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">將子網與 E9-1-1 在 Lync Server 2013 中的網站產生關聯</a></p></td>
</tr>
<tr class="odd">
<td><p>設定位置資料庫</p></td>
<td><ol>
<li><p>以網元對應至位置，填入資料庫。</p></li>
<li><p>針對 ELIN 閘道，將 Elin 新增至 [ &lt; CompanyName] &gt; 欄中。</p></li>
<li><p>設定 E9-1-1 服務提供者的連線以驗證位址。</p></li>
<li><p>使用 E9-1-1 服務提供者驗證位址。</p></li>
<li><p>發佈更新的資料庫。</p></li>
<li><p>針對 ELIN 閘道，將 Elin 上傳至您的 PSTN 載體的自動位置識別 (阿裡) 資料庫。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">在 Lync Server 2013 中設定位置資料庫</a></p></td>
</tr>
<tr class="even">
<td><p>設定高級功能 (選用) </p></td>
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

