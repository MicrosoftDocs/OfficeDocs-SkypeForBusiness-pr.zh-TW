---
title: Lync Server 2013： Lync Server 的 Active Directory 網域服務
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
ms.openlocfilehash: 00038dce85a7461be37456d9dee263a71f60c113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Lync Server 2013 的 Active Directory 網域服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-13_

Active Directory 網域服務可做為 Windows Server 2003、Windows Server 2008、Windows Server 2012 及 Windows Server 2012 R2 網路的目錄服務。 Active Directory 網域服務也充當建立 Microsoft Lync Server 2013 安全性基礎結構的基礎。 本節的目的是說明 Lync Server 2013 如何使用 Active Directory 網域服務，為 IM、Web 會議、媒體及語音建立信任的環境。 如需有關 Active Directory 網域服務之 Lync 伺服器擴充功能的詳細資料，以及準備您的環境使用 Active Directory 網域服務，請參閱部署檔中的[準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。 如需 Windows Server 網路中之 Active Directory 網域服務角色的詳細資料，請參閱您所使用之作業系統版本的文件。

Lync Server 2013 使用 Active Directory 網域服務來儲存：

  - 在樹系中執行 Lync Server 2013 的所有伺服器都需要的全域設定。

  - 識別樹系中所有執行 Lync Server 2013 之伺服器的角色的服務資訊。

  - 一些使用者設定。

<div>

## <a name="active-directory-infrastructure"></a>Active Directory 基礎結構

Active Directory 的基礎結構需求如下：

  - 網域控制站的作業系統需求

  - 網域和樹系功能等級需求

  - 通用類別目錄網域需求

如需詳細資訊，請參閱部署檔中的[Lync Server 2013 的 Active Directory 基礎結構需求](lync-server-2013-active-directory-infrastructure-requirements.md)。

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Active Directory 網域服務準備工作

<div>


> [!NOTE]  
> 建議您將通用設定部署到設定容器，而不要部署到系統容器。 這樣不會增強安全性，但可以為某些 Active Directory 網域服務拓撲增進延展性。 如果您是從 Microsoft Office 通訊伺服器2007進行遷移，但已使用系統容器，但計畫使用設定容器，您必須先將設定移至系統容器，再進行任何升級準備。 若要將系統容器設定遷移至設定容器，請參閱 Office 通訊伺服器2007全域設定遷移工具，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A> 。



</div>

部署 Lync Server 2013 時，第一步是準備 Active Directory 網域服務。 準備 Lync Server 2013 的 Active Directory 網域服務包含下列三個步驟：

  - **準備架構**。 這項工作會延伸 Active Directory 網域服務中的架構，以包含 Lync Server 2013 特有的類別和屬性。 如需準備架構的詳細資訊，請參閱部署檔中的在[Lync Server 2013 中執行 Active Directory 架構準備工作](lync-server-2013-running-schema-preparation.md)。 如需詳細資訊，請參閱[從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)。

  - **準備樹**系。 這項工作會在樹系根網域中建立通用設定和物件，以及控管這些設定和物件存取權的萬用服務和系統管理群組。 如需準備樹系的詳細資訊，請參閱部署檔中的對[Lync Server 2013 執行樹系準備工作](lync-server-2013-running-forest-preparation.md)。

  - **準備網域**。 這項工作會將必要的存取控制項目 (ACE) 新增至萬用群組，而這些群組會授與權限來裝載和管理網域內的使用者。 在您想要部署執行 Lync Server 2013 之伺服器的所有網域，以及 Lync Server 使用者所在的任何網域，都必須完成此工作。 如需有關準備網域的詳細資訊，請參閱部署檔中的[執行 Lync Server 2013 的網域準備工作](lync-server-2013-running-domain-preparation.md)。

有關準備 Active Directory 的完整程式，以及執行每個步驟所需的權利和許可權，請參閱部署檔中的[Lync Server 2013 的 Active Directory 基礎結構需求](lync-server-2013-active-directory-infrastructure-requirements.md)。

</div>

<div>

## <a name="universal-groups"></a>萬用群組

在準備樹系的過程中，Lync Server 2013 會在 Active Directory 網域服務中建立各種通用群組，而這些群組具有存取及管理全域設定和服務的許可權。 這些萬用群組包括：

  - **系統管理群組**。 這些群組會定義 Lync Server 網路的基本系統管理員角色。 樹系準備過程中，會將這些系統管理員群組新增至 Lync Server 基礎結構群組。

  - **服務群組**。 這些群組是存取 Lync Server 所提供之各種服務所需的服務帳戶。

  - **基礎結構群組**。 這些群組提供訪問 Lync Server 基礎結構特定區域的許可權。 其功能就如系統管理群組的元件，因此您不應修改這些群組或直接將使用者新增到其中。 在樹系準備過程中，會將特定服務和管理群組新增至適當的基礎結構群組。

如需在準備 Lync Server 的 AD 時所建立之特定通用群組的詳細資訊，以及新增至基礎結構群組的服務和管理群組，請參閱部署檔中的[Lync Server 2013 中的樹系準備所進行的變更](lync-server-2013-changes-made-by-forest-preparation.md)。

<div>


> [!NOTE]  
> Lync Server 2013 支援 Windows Server 2012 中執行 Lync Server 2013 之伺服器的通用群組，以及網域控制站的 Windows Server 2003 作業系統。 萬用群組的成員可以包含網域樹或樹系中任何網域的其他群組和帳戶，而且可以將網域樹或樹系中任何網域的權限指派給它。 通用群組支援（結合系統管理員委派）可簡化 Lync Server 部署的管理。 例如，不需要為了讓系統管理員能夠同時管理兩個網域，而將某個網域加入另一個網域。



</div>

</div>

<div>

## <a name="role-based-access-control"></a>角色型存取控制

除了建立泛型服務和管理群組，以及將服務和系統管理群組新增至適當的通用群組以外，樹系準備也會建立 Role-Based 的存取控制 (RBAC) 群組。 如需「樹系準備」所建立之特定 RBAC 群組的詳細資訊，請參閱部署檔中的[Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md)中的「樹系準備」所做的變更。 如需 RBAC 群組的詳細資訊，請參閱[以角色為基礎的存取控制 (Lync Server 2013 的 RBAC) ](lync-server-2013-role-based-access-control-rbac.md)。

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>存取控制項目 (ACE) 及繼承

樹系準備會同時建立私人與公用 ACE，並針對其建立的萬用群組新增 ACE。 它會在 Lync Server 所使用的全域設定容器上建立特定的專用 Ace。 這個容器只會由 Lync Server 使用，而且可以位於設定容器或根域的系統容器中，視您儲存全域設定的位置而定。

網域準備步驟會將必要的存取控制項目 (ACE) 新增至萬用群組，而這些群組會授與權限來裝載和管理網域內的使用者。網域準備作業會在網域根目錄和三個內建容器上建立 ACE：使用者、電腦和網域控制站。

如需由樹系準備和網域準備所建立及新增之公用 Ace 的詳細資訊，請參閱在「lync server 2013」中的[樹系準備工作中所做的變更](lync-server-2013-changes-made-by-forest-preparation.md)，以及部署檔中的[lync server 2013](lync-server-2013-changes-made-by-domain-preparation.md)中所做的變更。

組織經常會鎖定 Active Directory 網域服務 (AD DS)，以減低安全性風險。 不過，鎖定的 Active Directory 環境可以限制 Lync Server 2013 所需的許可權。 其中包括從容器和 OU 移除 ACE，以及停用 User、Contact、InetOrgPerson 或 Computer 物件的權限繼承。 在鎖定的 Active Directory 環境中，必須在需要權限的容器和 OU 上手動設定權限。 如需詳細資訊，請參閱部署檔中的在[Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

</div>

<div>

## <a name="server-information"></a>伺服器資訊

在啟用期間，Lync Server 2013 會將伺服器資訊發佈至 Active Directory 網域服務中的三個下列位置：

  - 與安裝 Lync Server 2013 之實體電腦對應之每個 Active Directory 電腦物件上的服務連線點 (SCP) 。

  - **msRTCSIP-Pools** 類別容器中建立的伺服器物件。

  - 拓撲產生器中指定的受信任伺服器。

</div>

<div>

## <a name="service-connection-points"></a>服務連線點

Active Directory 網域服務中的每個 Lync Server 2013 物件都有一個名為 RTC 服務的 SCP，該 SCP 又包含一些屬性，用以識別每一部電腦並指定其所提供的服務。 其中較重要的 SCP 屬性包括 *serviceDNSName*、*serviceDNSNameType*、*serviceClassname* 和 *serviceBindingInformation*。 協力廠商資產管理應用程式可以透過查詢 SCP 屬性，在部署中擷取伺服器資訊。

</div>

<div>

## <a name="active-directory-server-objects"></a>Active Directory 伺服器物件

每個 Lync Server 2013 伺服器角色都有對應的 Active Directory 物件，其屬性可定義該角色所提供的服務。 此外，啟用 Standard Edition server 或建立 Enterprise Edition 集區時，Lync Server 2013 會在**msRTCSIP-Pools**容器中建立新的**msRTCSIP 集**區物件。 **msRTCSIP-Pool** 類別會指定集區的完整網域名稱 (FQDN)，以及集區前端和後端元件之間的關聯性。 Standard Edition 伺服器會視為邏輯集區，其前端和後端會配置在同一部電腦上。

</div>

<div>

## <a name="trusted-servers"></a>受信任伺服器

在 Lync Server 2013 中，受信任的伺服器是執行拓撲產生器和發行拓撲時所指定的伺服器。 發行的拓撲 (包括所有伺服器資訊) 會儲存在中央管理存放區中。 只有定義在中央管理存放區中的伺服器會受信任。 在 Lync Server 2013 中，信任的伺服器是符合下列條件的伺服器：

  - 伺服器的 FQDN 出現在儲存於中央管理存放區的拓撲中。

  - 伺服器顯示來自受信任 CA 的有效憑證。 如需詳細資訊，請參閱[Lync Server 2013 的憑證基礎結構需求](lync-server-2013-certificate-infrastructure-requirements.md)。

如果不符合這些條件，則伺服器就不受信任，其連線也會遭拒。這項雙重需求能避免惡意伺服器嘗試佔用有效伺服器 FQDN 的可能 (即使不太可能) 攻擊。

此外，若要啟用 Microsoft Office 通訊伺服器 2007 R2 和 Microsoft Office 通訊伺服器2007部署，以與 Lync Server 2013 伺服器通訊，Lync Server 2013 會在樹系準備期間建立容器，以存放舊版版本的信任伺服器清單。 下表說明為與舊版部署相容而建立的容器。

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>為與舊版相容的受信任伺服器清單及其 Active Directory 容器

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
<td><p>Standard Edition 伺服器和 Enterprise 集區前端伺服器</p></td>
<td><p>RTC 服務/通用設定</p></td>
</tr>
<tr class="even">
<td><p>會議伺服器</p></td>
<td><p>RTC 服務/信任的 MCU</p></td>
</tr>
<tr class="odd">
<td><p>Web 元件伺服器</p></td>
<td><p>RTC 服務/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>中繼伺服器及 Communicator Web Access Server、應用程式伺服器、含 QoE 的登錄器、A/V 會議服務 (還有協力廠商 SIP 伺服器)</p></td>
<td><p>RTC 服務/信任的服務</p></td>
</tr>
<tr class="odd">
<td><p>Proxy 伺服器</p></td>
<td><p>Lync Server 2013 不支援 proxy 伺服器的回溯相容性</p></td>
</tr>
</tbody>
</table>


若要支援先前版本的信任伺服器，您必須執行最佳作法分析工具。 如需執行最佳做法分析程式的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

