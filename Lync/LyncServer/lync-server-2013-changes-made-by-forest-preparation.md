---
title: Lync Server 2013：由林準備所做的變更
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
ms.openlocfilehash: 4df16ffb24c4eb4e010e2b57f6af62d3518c05b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Lync Server 2013 中的林準備所做的變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

本節說明全域設定與物件，以及由目錄林準備步驟所建立的泛型服務和管理群組。

<div>

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全域設定與物件

如果您在 [設定] 容器中儲存全域設定（所有新 Lync Server 2013 部署的案例），目錄林準備就會使用現有的服務容器，並在 [設定\\服務] 物件下新增**RTC 服務**物件。 在 RTC 服務物件下，林準備會新增 type msRTCSIP-GlobalContainer 的**全域設定**物件。 [全域設定] 物件包含所有適用于 Lync Server 部署的設定。 如果您在系統容器中儲存全域設定，目錄林準備會在系統\\microsoft 物件下使用根網域系統容器和 RTC 服務物件底下的 Microsoft 容器。

林準備也會為執行程式的根網域新增一個新**的 msRTCSIP-網域**物件。

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 泛型服務與管理群組

林準備會根據您指定的網域建立通用群組，並新增這些群組的存取控制專案（Ace）。 此步驟會在您指定之網域的使用者容器中建立通用群組。

通用群組可讓系統管理員存取及管理全域設定及服務。 [林準備] 會新增下列類型的通用群組：

  - **系統管理群組**   這些群組會定義 Lync Server 網路的系統管理員角色。

  - **基礎結構群組**   這些群組提供存取 Lync Server 基礎結構特定區域的許可權。 它們的功能是系統管理群組的元件。 您不應該修改這些群組，或直接將使用者新增至其中。

  - **服務群組**   ：這些群組是存取各種 Lync Server 服務所需的服務帳戶。

下表說明管理群組。

### <a name="administrative-groups-created-during-forest-preparation"></a>在林準備期間建立的系統管理群組

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>系統管理群組</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>允許成員管理伺服器和池設定，包括所有伺服器角色、全域設定和使用者。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>允許成員管理使用者設定，以及將使用者從一個伺服器或一個池移到另一個伺服器或資源庫。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>允許成員讀取伺服器、池及使用者設定。</p></td>
</tr>
</tbody>
</table>


下表說明基礎結構群組。

### <a name="infrastructure-groups-created-during-forest-preparation"></a>在林準備期間建立的基礎結構群組

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>基礎結構群組</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>授予 Lync Server 全域設定物件的寫入權限。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>授予 Lync Server 全域設定物件的唯讀存取權。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>授予 Lync Server 使用者設定的唯讀存取權。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>授予 Lync Server 設定的唯讀存取權。 這個群組無法存取 [池] 層級設定，只適用于個別伺服器專用的設定。</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>授予 Lync Server 設定的唯讀存取權，並將其放在安裝期間 survivable 分支裝置的 [本機管理員] 群組中。</p></td>
</tr>
</tbody>
</table>


下表說明服務群組。

### <a name="service-groups-created-during-forest-preparation"></a>在林準備期間建立的服務群組

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>服務群組</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>包含用來執行前端伺服器和標準版伺服器的服務帳戶。 這個群組可讓伺服器讀/寫 Lync Server 全域設定和 Active Directory 使用者物件的存取權。</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>包含用來執行 A/V 會議伺服器、Web 服務、中繼伺服器、封存伺服器及監視伺服器的服務帳戶。</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>包含用來執行 Lync Server Edge 伺服器的服務帳戶。</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>包括可參與 Lync Server 中央管理儲存複製的伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>授予 Lync Server 設定的唯讀存取權，但允許安裝 survivable 分支伺服器和 survivable 分支裝置部署。</p></td>
</tr>
</tbody>
</table>


[林準備] 接著會將服務和系統管理群組新增至適當的基礎結構群組，如下所示：

  - RTCUniversalServerAdmins 已新增至 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。

  - RTCUniversalUserAdmins 會新增為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。

  - RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 會新增為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。

林準備也會建立下列角色式存取控制（RBAC）群組：

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

如需 RBAC 角色及每個角色所允許的工作的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的角色式存取控制規劃](lync-server-2013-planning-for-role-based-access-control.md)。

林準備會建立私人和公用 Ace。 它會在 Lync Server 所使用的全域設定容器上建立私用 Ace。 這個容器只能由 Lync Server 使用，且位於配置容器或根網域中的系統容器中，視您儲存全域設定的位置而定。 [林準備] 建立的公用 Ace 列在下表中。

### <a name="public-aces-created-by-forest-preparation"></a>由林準備建立的公用 Ace

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>A</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>讀取根網域系統容器（不繼承）<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>讀取配置的 DisplaySpecifiers 容器（不是繼承的）</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>未繼承的 Ace 不會在這些容器下授與子物件的存取權。 被繼承的 Ace 在這些容器下授與子物件的存取權。



</div>

在 [設定] 容器的 [設定命名] 內容底下，[林準備] 會執行下列任務：

  - 針對使用者、連絡人和 InetOrgPersons （例如，CN = user 顯示幕、cn = 409、cn = DisplaySpecifiers）的語言顯示說明符之 [adminCoNtextMenu] 和 [adminPropertyPages] 屬性，為 [ **RTC] 屬性**頁面新增專案 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 。

  - 在套用至使用者和連絡人類別的**延伸許可權**底下，新增類型**controlAccessRight**的**RTCPropertySet**物件。

  - 在適用于使用者、連絡人、OU 和 DomainDNS 類別的**延伸許可權**底下，新增類型**controlAccessRight**的**RTCUserSearchPropertySet**物件。

  - 在每個語言組織單位（OU）顯示說明符的**extraColumns**屬性（例如，Cn = OrganizationalUnit-DISPLAY、cn = 409、Cn = DisplaySpecifiers）中新增**msRTCSIP-PrimaryUserAddress** ，並複製預設顯示的**EXTRACOLUMNS**屬性值（例如 cn = 預設顯示，Cn = 409，cn = DisplaySpecifiers）。

  - 針對使用者、連絡人及 MsRTCSIP 物件（例如英文： CN = 使用者顯示，CN = 409，CN = UserEnabled），在每個語言顯示說明符的**attributeDisplayNames**屬性下，新增**msRTCSIP-PrimaryUserAddress**、 **MsRTCSIP-PrimaryHomeServer**和**InetOrgPerson DisplaySpecifiers**篩選屬性。

</div>

</div>

<span> </span>

</div>

</div>

</div>

