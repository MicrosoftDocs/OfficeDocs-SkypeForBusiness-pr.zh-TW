---
title: Lync Server 2013：適用于 Lync Server 的 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac4b4da954fd792559d2160ce457aec91cb0ac6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Lync Server 2013 的 Active Directory 網域服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-13_

Active Directory 網域服務的功能是 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 網路的目錄服務。 Active Directory 網域服務也會充當建立 Microsoft Lync Server 2013 安全基礎結構的基礎。 本節的目的是說明 Lync Server 2013 如何使用 Active Directory 網域服務來建立 IM、網路會議、媒體及語音的可信環境。 如需有關 Active Directory 網域服務的 Lync Server extensions 的詳細資料，以及如何為 Active Directory 網域服務準備您的環境，請參閱在部署檔中[為 Lync server 2013 準備 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。 如需有關 Windows Server 網路中 Active Directory 網域服務角色的詳細資訊，請參閱您所使用之作業系統版本的相關檔。

Lync Server 2013 使用 Active Directory 網域服務來儲存：

  - 在樹林中執行 Lync Server 2013 的所有伺服器都需要的全域設定。

  - 服務資訊，可識別在樹林中執行 Lync Server 2013 的所有伺服器角色。

  - 部分使用者設定。

<div>

## <a name="active-directory-infrastructure"></a>Active Directory 基礎結構

Active Directory 的基礎結構需求包括下列各項：

  - 網網域控制站的作業系統需求

  - 網域和林功能層級需求

  - 全域編目網域需求

如需詳細資訊，請參閱部署檔中[Lync Server 2013 的 Active Directory 基礎結構需求](lync-server-2013-active-directory-infrastructure-requirements.md)。

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Active Directory 網域服務準備

<div>


> [!NOTE]  
> 我們建議您將全域設定部署到配置容器，而不是系統容器。 這不會增強安全性，但可能會針對某些 Active Directory 網域服務拓撲提供伸縮性改善。 如果您是從 Microsoft Office 通訊伺服器2007遷移，且已使用系統容器，但想要使用配置容器，您必須先移動系統容器中的設定，然後才能進行任何升級準備。 若要將您的系統容器設定遷移至 [設定] 容器，請參閱 Office 通訊伺服器 2007 <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>全域設定遷移工具，網址為。



</div>

部署 Lync Server 2013 時，第一個步驟是準備 Active Directory 網域服務。 為 Lync Server 2013 準備 Active Directory 網域服務的步驟包括下列三個步驟：

  - [**準備架構**]。 此任務會將 Active Directory 網域服務中的架構擴大，以包含 Lync Server 2013 專用的類別和屬性。 如需準備架構的詳細資料，請參閱在部署檔中執行[Lync Server 2013 中的 Active Directory 架構準備](lync-server-2013-running-schema-preparation.md)。 如需詳細資訊，請參閱[從 Office 通訊伺服器 2007 R2 遷移到 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)。

  - **準備林**。 這個工作會建立目錄林根網域中的全域設定和物件，以及控制存取這些設定和物件的泛型服務和系統管理群組。 如需準備林的詳細資料，請參閱在部署檔中[執行 Lync Server 2013 的林準備](lync-server-2013-running-forest-preparation.md)。

  - **準備網域**。 這個工作會將必要的存取控制專案（Ace）新增到通用群組，以授與管理網域中的使用者的許可權。 在您想要部署執行 Lync Server 2013 的伺服器以及 Lync Server 使用者所駐留的任何網域時，必須在所有網域中完成這項工作。 如需有關準備網域的詳細資訊，請參閱在部署檔中[執行 Lync Server 2013 的網域準備](lync-server-2013-running-domain-preparation.md)。

如需有關準備 Active Directory 的完整程式，以及執行每個步驟所需的許可權和許可權，請參閱部署檔中[Lync Server 2013 的 Active Directory 基礎結構需求](lync-server-2013-active-directory-infrastructure-requirements.md)。

</div>

<div>

## <a name="universal-groups"></a>通用群組

在準備林期間，Lync Server 2013 會在 Active Directory 網域服務中建立可存取及管理全域設定及服務許可權的各種通用群組。 這些通用群組包括：

  - [系統**管理群組**]。 這些群組會定義 Lync Server 網路的基本系統管理員角色。 在林準備期間，這些系統管理員群組會新增至 Lync Server 基礎結構群組。

  - **服務群組**。 這些群組是用來存取 Lync Server 所提供的各種服務所需的服務帳戶。

  - **基礎結構群組**。 這些群組提供存取 Lync Server 基礎結構特定區域的許可權。 它們的功能是系統管理群組的元件，您不應該直接修改它們或直接將使用者新增至其中。 在林準備期間，系統會將特定的服務與管理群組新增至適當的基礎結構群組中。

如需在準備 Lync Server 的 AD 時所建立的特定通用群組，以及新增至基礎結構群組的服務和管理群組，請參閱在部署檔中的[Lync Server 2013 中所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)。

<div>


> [!NOTE]  
> Lync Server 2013 支援執行 Lync Server 2013 之伺服器的 Windows Server 2012 中的通用群組，以及適用于網網域控制站的 Windows Server 2003 作業系統。 通用群組的成員可以包含網域樹狀結構或林中任何網域的其他群組和帳戶，而且可以在網域樹狀結構或樹林中的任何網域中指派許可權。 通用群組支援，與系統管理員委派結合，簡化 Lync Server 部署的管理。 例如，您不需要將一個網域新增至另一個網域，就能讓系統管理員同時管理兩者。



</div>

</div>

<div>

## <a name="role-based-access-control"></a>以角色為基礎的存取控制

除了建立泛型服務與管理群組，以及將服務和系統管理群組新增至適當的通用群組之外，林準備也會建立以角色為基礎的存取控制（RBAC）群組。 如需林準備所建立之特定 RBAC 群組的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的林準備所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)。 如需 RBAC 群組的詳細資訊，請參閱[Lync Server 2013 的角色式存取控制（RBAC）](lync-server-2013-role-based-access-control-rbac.md)。

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>存取控制專案（Ace）與繼承

林準備會建立私人和公用 Ace，並為它所建立的通用群組新增 Ace。 它會在 Lync Server 所使用的全域設定容器上建立特定的專用 Ace。 這個容器只能由 Lync Server 使用，且位於配置容器或根網域中的系統容器中，視您儲存全域設定的位置而定。

[網域準備] 步驟會將必要的存取控制專案（Ace）新增至通用群組，以便在網域中授與主機及管理使用者的許可權。 [網域準備] 會在網域根目錄和三個內建容器中建立 Ace：使用者、電腦及網網域控制站。

如需由林準備及網域準備所建立和新增的公用 Ace 的詳細資料，請參閱[Lync server 2013 中的林準備所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)，以及部署檔中[由 lync server 2013 中的網域準備](lync-server-2013-changes-made-by-domain-preparation.md)所做的變更。

組織通常會鎖定 Active Directory 網域服務（AD DS），協助減輕安全性風險。 不過，鎖定的 Active Directory 環境可以限制 Lync Server 2013 所需的許可權。 這可能包括從容器和 Ou 中移除 Ace，以及在使用者、連絡人、InetOrgPerson 或電腦物件上停用許可權繼承。 在鎖定的 Active Directory 環境中，許可權必須在需要它們的容器和 Ou 上手動設定。 如需詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [準備已鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)]。

</div>

<div>

## <a name="server-information"></a>伺服器資訊

在啟用期間，Lync Server 2013 會將伺服器資訊發佈到 Active Directory 網域服務中的三個下列位置：

  - 與安裝 Lync Server 2013 之物理電腦對應的每個 Active Directory 電腦物件上的服務連接點（SCP）。

  - 在**MsRTCSIP 池**類別的容器中建立的伺服器物件。

  - 在拓撲建立器中指定的信任伺服器。

</div>

<div>

## <a name="service-connection-points"></a>服務連接點

Active Directory 網域服務中的每個 Lync Server 2013 物件都有一個名為「RTC 服務」的 SCP，該伺服器又包含幾個屬性來識別每個電腦並指定它所提供的服務。 *ServiceDNSName*、 *serviceDNSNameType*、 *serviceClassname*和*serviceBindingInformation*等更重要的 SCP 屬性。 協力廠商資產管理應用程式可透過查詢這些與其他 SCP 屬性來在整個部署中檢索伺服器資訊。

</div>

<div>

## <a name="active-directory-server-objects"></a>Active Directory Server 物件

每個 Lync Server 2013 伺服器角色都有對應的 Active Directory 物件，其屬性會定義該角色所提供的服務。 此外，當您啟用標準版伺服器或建立企業版文件庫時，Lync Server 2013 會在**MsRTCSIP pool**容器中建立新的**msRTCSIP 池**物件。 **MsRTCSIP 池**類別指定了池子的完整功能變數名稱（FQDN），以及該池前端與後端元件之間的關聯。 （標準版伺服器會被視為在單一電腦上 collocated 其前端和後端的邏輯池）。

</div>

<div>

## <a name="trusted-servers"></a>受信任的伺服器

在 Lync Server 2013 中，[受信任的伺服器] 是您執行拓撲建立器併發布拓撲時指定的伺服器。 已發佈的拓撲（包括所有伺服器資訊）都儲存在中央管理儲存區中。 只有在中央管理存儲區中定義的伺服器才是受信任的。 在 Lync Server 2013 中，受信任的伺服器是符合下列準則的一種：

  - 伺服器的 FQDN 會出現在儲存在中央管理存放區的拓撲中。

  - 伺服器會從信任的 CA 中出示有效的憑證。 如需詳細資訊，請參閱[Lync Server 2013 的憑證基礎結構需求](lync-server-2013-certificate-infrastructure-requirements.md)。

如果缺少其中一個準則，則伺服器不受信任，且無法與它連線。 這種雙重需求可以避免可能的情況下，惡意伺服器企圖利用有效伺服器的 FQDN 來取得的攻擊。

此外，若要啟用 Microsoft Office 通訊伺服器 2007 R2 和 Microsoft Office 通訊伺服器2007部署，以使用 Lync Server 2013 伺服器進行通訊，Lync Server 2013 會在目錄林準備期間建立容器，以保留清單早期版本的受信任伺服器。 下表說明為啟用與舊版部署相容性而建立的容器。

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>受信任的伺服器清單及其 Active Directory 容器，以與舊版版本相容

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>受信任的伺服器清單</th>
<th>Active Directory 容器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>標準版伺服器與企業版池前端伺服器</p></td>
<td><p>RTC 服務/全域設定</p></td>
</tr>
<tr class="even">
<td><p>會議服務器</p></td>
<td><p>RTC 服務/信任的 MCUs</p></td>
</tr>
<tr class="odd">
<td><p>網頁元件伺服器</p></td>
<td><p>RTC 服務/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>中繼伺服器與 Communicator Web Access 伺服器、應用程式伺服器、QoE 的註冊機構、A/V 會議服務（也是協力廠商 SIP 伺服器）</p></td>
<td><p>RTC 服務/受信任的服務</p></td>
</tr>
<tr class="odd">
<td><p>Proxy 伺服器</p></td>
<td><p>Lync Server 2013 不支援 proxy 伺服器的向後相容性</p></td>
</tr>
</tbody>
</table>


若要支援舊版版本的信任伺服器，您必須執行最佳做法分析程式工具。 如需執行最佳做法分析程式的詳細資訊[http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)，請參閱。

</div>

</div>

<span> </span>

</div>

</div>

</div>

