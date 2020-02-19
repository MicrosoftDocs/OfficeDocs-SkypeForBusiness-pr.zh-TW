---
title: 'Lync Server 2013: E9-1-1 的部署檢查清單'
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
ms.openlocfilehash: 38e2cffcaa54df8d9a7bc3715d609ac4bc7d7b8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>E9-1-1 Lync Server 2013 中的部署檢查表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

若要有效規劃的增強型 9-1-1 (E9-1-1)，請務必包含下列部署需求：

  - 部署 E9-1-1 的先決條件。

  - 部署 E9-1-1 所需的步驟。

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 的部署先決條件

部署 E9-1-1 之前，您必須已部署 Lync Server 內部伺服器，包括中央管理存放區、 前端集區或 Standard Edition server、 一或多個中繼伺服器或中繼伺服器集區] 中，與 Lync Server 用戶端。 此外，E9-1-1 部署需要合格的 E9-1-1 服務提供者的 SIP 主幹或公用交換的電話網路 (PSTN) 緊急位置識別號碼 (ELIN) 閘道。 Lync Server 支援使用 E9-1-1 服務提供者，僅在美國境內內部。

</div>

<div>

## <a name="deployment-process"></a>部署程序

下表提供 E9-1-1 部署程序的概觀。 如需部署步驟的詳細資訊，請參閱部署文件中的[設定增強型 9-1-1 Lync Server 2013 中](lync-server-2013-configure-enhanced-9-1-1.md)。


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
<td><p>設定語音使用方式、 路由和主幹組態</p></td>
<td><ol>
<li><p>建立新的 PSTN 使用方式記錄。 這是相同的名稱，用於位置原則中的<strong>PSTN 使用方式</strong>設定。</p></li>
<li><p>建立或指派語音路由給在上一個步驟中建立的 PSTN 使用方式記錄，然後閘道屬性指向 [E9-1-1 SIP 主幹或 ELIN 閘道。</p></li>
<li><p>SIP 主幹 E9-1-1 服務提供者，設定主幹來透過 SIP 傳遞 PIDF-LO 資料使用<strong>Set-cstrunkconfiguration – EnablePIDFLOSupport</strong> cmdlet 將會處理 E9-1-1 通話。</p></li>
<li><p>（選用） 的 SIP 主幹 E9-1-1 服務提供者，建立或指派本機 PSTN 路由不由 E9-1-1 服務提供者的 SIP 主幹處理的通話。 如果與 E9-1-1 服務提供者的連線無法使用，則會使用此路由。 如果您的 E9-1-1 服務提供者支援，將主幹組態規則指派給將 911 撥號字串轉譯成的國家/區域緊急通話回應中心 (ECRC) 直接向內撥號 (DID) 號碼的閘道。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Lync Server 2013 中設定 E9-1-1 語音路由</a></p></td>
</tr>
<tr class="even">
<td><p>建立位置原則，並將它們指派給使用者和子網路</p></td>
<td><ol>
<li><p>檢閱全域位置原則。</p></li>
<li><p>使用者層級範圍; 建立位置原則或者，如果組織有多個具有不同緊急使用方式的網站，建立位置原則具有網路層級範圍。</p></li>
<li><p>將位置原則指派給網路網站。</p></li>
<li><p>將適當的子網路新增至網站。</p></li>
<li><p>（選用）將位置原則指派給使用者原則。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin （建立位置原則除外）</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">在 Lync Server 2013 中建立位置原則</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">將位置原則新增至 Lync Server 2013 中的網路網站</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">關聯子網路與 E9-1-1 Lync Server 2013 中的網站</a></p></td>
</tr>
<tr class="odd">
<td><p>設定位置資料庫</p></td>
<td><ol>
<li><p>填入網路元素與位置的對應資料庫。</p></li>
<li><p>對於 ELIN 閘道，請新增 Elin 至&lt;CompanyName&gt;資料行。</p></li>
<li><p>設定 E9-1-1 服務提供者的連線驗證地址。</p></li>
<li><p>驗證與 E9-1-1 服務提供者的地址。</p></li>
<li><p>發佈更新過的資料庫。</p></li>
<li><p>為 ELIN 閘道，將 Elin 上傳至您 PSTN 業者的自動位置識別 (ALI) 資料庫。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">在 Lync Server 2013 中設定位置資料庫</a></p></td>
</tr>
<tr class="even">
<td><p>設定進階功能 （選用）</p></td>
<td><ol>
<li><p>設定 SNMP 應用程式的 URL。</p></li>
<li><p>設定次要位置資訊服務的位置的 URL。</p></li>
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

