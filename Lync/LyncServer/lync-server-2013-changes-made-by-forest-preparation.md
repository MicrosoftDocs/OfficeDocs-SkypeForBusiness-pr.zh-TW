---
title: Lync Server 2013：樹系準備所進行的變更
description: Lync Server 2013：由樹系準備所進行的變更。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c9bc40539c285e03610b2fc97166842473997fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543649"
---
# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Lync Server 2013 中的樹系準備所進行的變更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

本節將說明樹系準備步驟所建立的全域設定與物件，以及萬用服務和管理群組。

<div>

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全域設定和物件

如果您將全域設定儲存在設定容器中 () 所有新的 Lync Server 2013 部署的案例，樹系準備會使用現有的服務容器，並在設定服務物件底下新增 **RTC 服務** 物件 \\ 。 在 RTC 服務物件下，樹系準備會新增 msRTCSIP-GlobalContainer 類型的**Global Settings**物件。 全域設定物件會包含套用至 Lync Server 部署的所有設定。 如果您在系統容器中儲存全域設定，樹系準備會使用根網域系統容器底下的 Microsoft 容器，以及系統 Microsoft 物件底下的 RTC 服務物件 \\ 。

樹系準備也會針對執行程序的根網域，新增 **msRTCSIP-Domain** 物件。

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 萬用服務和管理群組

樹系準備也會根據您指定的網域建立萬用群組，並為這些群組新增存取控制項目 (ACE)。這個步驟會在您指定之網域的使用者容器中，建立萬用群組。

萬用群組允許管理員存取以及管理全域設定和服務。樹系準備會新增下列類型的萬用群組：

  - 系統**管理群組**    這些群組會定義 Lync Server 網路的系統管理員角色。

  - **基礎結構群組**    這些群組提供訪問 Lync Server 基礎結構特定區域的許可權。 它們可做為系統管理群組元件的功能來運作。 您不應該修改這些群組或將使用者直接新增至這些群組中。

  - **服務群組**    這些群組是存取各種 Lync Server 服務所需的服務帳戶。

下表說明系統管理群組。

### <a name="administrative-groups-created-during-forest-preparation"></a>樹系準備時建立的系統管理群組

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>系統管理群組</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>允許成員管理伺服器和集區設定，包括所有伺服器角色、全域設定以及使用者。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>可讓成員管理使用者設定，也可以將使用者從一個伺服器或集區移到另一個伺服器或集區。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>可讓成員讀取伺服器、集區和使用者設定。</p></td>
</tr>
</tbody>
</table>


下表說明基礎結構群組。

### <a name="infrastructure-groups-created-during-forest-preparation"></a>樹系準備時建立的基礎結構群組

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>基礎結構群組</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>授與 Lync Server 之全域設定物件的寫入權限。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>授與 Lync Server 之全域設定物件的唯讀存取權。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>授與 Lync Server 使用者設定的唯讀許可權。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>授與 Lync Server 設定的唯讀許可權。 這個群組沒有集區層級設定的存取權，只能存取個別伺服器特有的設定。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>授與 Lync Server 設定的唯讀許可權，並將其放置在安裝期間 survivable 分支裝置的本機系統管理員群組中。</p></td>
</tr>
</tbody>
</table>


下表說明服務群組。

### <a name="service-groups-created-during-forest-preparation"></a>樹系準備時建立的服務群組

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>服務群組</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>包含用於執行前端伺服器和 Standard Edition 伺服器的服務帳戶。 此群組可讓伺服器讀取/寫入 Lync Server 全域設定和 Active Directory 使用者物件的存取權。</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>包括用來執行 A/V 會議伺服器、Web 服務、轉送伺服器、封存伺服器及監控伺服器的服務帳戶。</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>包括用來執行 Lync Server Edge server 的服務帳戶。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>包括可參與 Lync Server 中央管理存放區複寫的伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>授與 Lync Server 設定的唯讀存取權，但允許設定 survivable branch server 和 survivable branch 裝置部署的安裝。</p></td>
</tr>
</tbody>
</table>


接著，樹系準備會將服務和管理群組新增到適當的基礎結構群組，如下所示：

  - 新增 RTCUniversalServerAdmins 到 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。

  - 新增 RTCUniversalUserAdmins 做為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。

  - 新增 RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 做為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。

樹系準備也會建立下列角色型存取控制 (RBAC) 群組：

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

如需有關 RBAC 角色和每個角色所允許之工作的詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的角色型存取控制](lync-server-2013-planning-for-role-based-access-control.md) 。

樹系準備會同時建立私人與公用 ACE。 它會在 Lync Server 所使用的全域設定容器上建立專用 Ace。 這個容器只會由 Lync Server 使用，而且可以位於設定容器或根域的系統容器中，視您儲存全域設定的位置而定。 樹系準備所建立的公用 ACE 列於下表。

### <a name="public-aces-created-by-forest-preparation"></a>樹系準備建立的公用 ACE。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ace</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>讀取根網域系統容器 (非繼承的)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>讀取設定的 DisplaySpecifiers 容器 (非繼承的)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>未繼承的 Ace 不會將存取權授與這些容器底下的子物件。 繼承的 Ace 會將存取權授與這些容器底下的子物件。



</div>

樹系準備會在組態命名內容下的設定容器上執行下列工作：

  - 在使用者、連絡人和 InetOrgPerson 之語言顯示規範的 adminContextMenu 和 adminPropertyPages 屬性下方，為 **RTC property** 頁面新增 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 項目 (例如 CN=user-Display、CN=409、CN=DisplaySpecifiers)。

  - 在套用到 User 和 Contact 類別的 **Extended-Rights** 下方，新增 **controlAccessRight** 類型的 **RTCPropertySet** 物件。

  - 在套用到 User、Contact、OU 與 DomainDNS 類別的 **Extended-Rights** 下方，新增 **controlAccessRight** 類型的 **RTCUserSearchPropertySet** 物件。

  - 在每一個語言組織單位 (OU) 顯示規範 (例如，CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) 的 **extraColumns** 屬性下新增 **msRTCSIP-PrimaryUserAddress**，並複製預設顯示 (例如，CN=default-Display、CN=409、CN=DisplaySpecifiers) 的 **extraColumns** 屬性值。

  - 在 Users、Contacts 與 InetOrgPerson 物件的每一個語言顯示規範的 **attributeDisplayNames** 屬性下，新增 **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer** 與 **msRTCSIP-UserEnabled** 篩選屬性 (以英文為例：CN=user-Display、CN=409、CN=DisplaySpecifiers)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

