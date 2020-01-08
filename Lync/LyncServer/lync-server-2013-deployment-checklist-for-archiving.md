---
title: Lync Server 2013：封存的部署檢查單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中封存的部署檢查單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

存檔會自動安裝在 Lync Server 2013 部署中的每個前端伺服器上，但您仍需先設定，然後才能使用。 進行設定所需的步驟，如本節所總結，將歸檔部署組成。

<div>

## <a name="deployment-sequence"></a>部署順序

設定存檔的方式取決於您選擇的儲存空間選項：

  - 如果您針對部署中的所有使用者使用 Microsoft Exchange 整合，就不需要為使用者設定 Lync Server 2013 的歸檔原則。 相反地，請設定您的 Exchange 就地保留原則，以支援駐留在 Exchange 2013 的使用者的封存，並將其信箱放在適當的位置。 如需有關設定這些原則的詳細資訊，請參閱 Exchange 2013 產品檔。

  - 如果您不是針對您部署中的所有使用者使用 Microsoft Exchange 整合，您必須先在拓撲中新增 Lync Server 封存資料庫（SQL Server 資料庫），然後發佈它，以及為使用者設定原則和設定，才能存檔這些使用者的資料。 您可以在部署初始拓撲或部署至少一個前端池或標準版伺服器之後，部署存檔資料庫。 本檔說明如何將存檔資料庫新增至現有的部署。

如果您在一個前端池或標準版伺服器中啟用封存，您應該針對部署中的所有其他前端池和標準版伺服器啟用該功能。 這是因為需要封存其通訊的使用者可以受邀加入群組 IM 交談或託管于不同的池中的會議。 如果在託管或會議所在的池中未啟用 [封存]，則可能不會封存整個會話。 在這些情況下，擁有封存的使用者的 Im 仍可歸檔，但不適用於會議內容檔案，以及會議加入或離開活動。

<div>


> [!IMPORTANT]  
> 如果您組織中的存檔是符合合規性的理由，請務必在適當的層級部署封存、設定原則及其他選項，並針對所有適當的使用者啟用封存，然後再針對 Lync Server 2013 啟用這些使用者。



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>存檔部署程式

下表概要說明在現有拓撲中部署存檔所需的步驟。


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
<th>角色和群組成員資格</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安裝必備的硬體和軟體</strong></p></td>
<td><ul>
<li><p>若要使用 Microsoft Exchange 整合（使用 Exchange 2013 來封存部分或所有使用者的儲存空間），您需要現有的 Exchange 2013 部署。</p></li>
<li><p>若要使用個別的存檔資料庫（使用 SQL Server 資料庫）來儲存部分或所有使用者的儲存空間，請在伺服器上將儲存封存資料的 SQL Server。</p></li>
</ul>
<div>

> [!NOTE]  
> 封存是在企業版池和標準版伺服器的前端伺服器上執行。 除了安裝這些伺服器所需的其他硬體或軟體需求之外，它還沒有其他硬體或軟體需求。


</div></td>
<td><p>屬於本機管理員群組成員的網域使用者。</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">支援檔中 Lync Server 2013 支援的硬體</a>。</p>
<p>支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a>。</p>
<p>規劃檔中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中的存檔技術需求</a>。</p>
<p>在部署檔中<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">設定在 Lync Server 2013 中封存的系統和基礎結構</a>。</p>
<p>支援檔中的<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 Exchange Server 和 SharePoint 整合支援</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>建立適當的內部拓朴，以支援封存（僅適用于您部署中的所有使用者都不使用 Microsoft Exchange 整合）</strong></p></td>
<td><p>執行拓撲建立器，將 Lync Server 2013 封存資料庫（SQL Server 資料庫）新增到拓撲結構，然後發佈拓撲。</p></td>
<td><p>若要定義拓撲以納入封存資料庫，該帳戶是 [本機使用者] 群組的成員。</p>
<p>若要發佈拓朴，該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員，且在檔案共用上擁有 [完全控制] 許可權（讀取/寫入/修改），以用於 Lync Server 2013 檔案存放區（讓拓撲建立員可以設定所需的 Dacl）。</p></td>
<td><p>在部署檔中<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">將存檔資料庫新增至現有的 Lync Server 2013 部署</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>設定伺服器對伺服器驗證（僅在使用 Microsoft Exchange 整合時）</strong></p></td>
<td><p>設定伺服器以啟用 Lync Server 2013 與 Exchange 2013 之間的驗證。 我們建議您執行<strong>測試 CsExchangeStorageConnectivity testuser_sipUri –資料夾 Dumpster</strong> ，以驗證 Exchange 封存儲存連接，才能啟用封存。</p></td>
<td><p>具有適當許可權的帳戶，可在伺服器上管理證書。</p></td>
<td><p>在部署檔或操作檔中<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">管理 Lync server 2013 中的伺服器到伺服器驗證（OAuth）與合作夥伴應用程式</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>設定封存原則和配置</strong></p></td>
<td><p>設定封存，包括是否使用 Microsoft Exchange 整合、全域原則及任何網站和使用者原則（不使用 Microsoft Exchange 整合進行所有資料儲存），以及特定的歸檔選項（例如，重要模式與資料）匯出和清除。</p>
<p>如果您使用的是 Microsoft Exchange 整合，請視需要設定 Exchange 就地保留原則。</p></td>
<td><p>RTCUniversalServerAdmins 群組（僅限 Windows PowerShell）或將使用者指派給 CSArchivingAdministrator 或 CSAdministrator 角色。</p></td>
<td><p>在部署檔中設定<a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 中的封存支援</a>。</p>
<p>Exchange 產品檔（如果您使用的是 Microsoft Exchange 整合）。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>在不同的林中部署 Lync Server 和 Microsoft Exchange

如果 Microsoft Exchange Server 未部署在 Lync Server 所在的林中，您必須確認下列 Exchange Active Directory 屬性已同步處理到部署 Lync Server 的林：

1.  msExchUserHoldPolicies

2.  proxyAddresses

這是多重值屬性。 同步處理此屬性時，您必須合併值，而不要將其取代，以確保現有值不會遺失。

</div>

</div>

<span> </span>

</div>

</div>

</div>

