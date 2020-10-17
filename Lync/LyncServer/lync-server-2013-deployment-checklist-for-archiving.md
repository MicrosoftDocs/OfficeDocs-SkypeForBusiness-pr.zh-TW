---
title: Lync Server 2013：封存的部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccec3917e892d1ba6c3e1841773c77e8c2d015d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514524"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中封存的部署檢查清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

您的 Lync Server 2013 部署中的每一部前端伺服器都會自動安裝封存，但您仍然必須先加以設定，才能使用。 請依本節摘要之設定所需的步驟部署封存。

<div>

## <a name="deployment-sequence"></a>部署順序

如何根據所選擇的存放區選項設定封存：

  - 如果您部署中的所有使用者都使用 Microsoft Exchange 整合，您就不需要為使用者設定 Lync Server 2013 封存原則。 相反地，設定您的 Exchange In-Place 保留原則，以支援駐留在 Exchange 2013 上的使用者，並將其信箱置於 In-Place 保留狀態。 如需設定這些原則的詳細資訊，請參閱 Exchange 2013 產品檔。

  - 如果您部署中的所有使用者都不使用 Microsoft Exchange 整合，您必須將 Lync Server 封存)  (資料庫新增至您的拓撲，然後發佈它，並為使用者設定原則及設定，才能封存這些使用者的資料。 您可在部署初始拓撲的同時，或者在部署至少一個前端集區或 Standard Edition Server 之後，進行部署封存資料庫。 本文件描述如何透過將封存資料庫新增至現有部署來進行部署。

如果您在一個前端集區或 Standard Edition Server 啟用封存，則應在部署中針對所有其他前端集區和 Standard Edition Server 一併啟用。這是因為，需要將通訊封存的使用者可受邀至由其他集區所主控的群組 IM 交談或會議。如果封存未在主控交談或會議的所在集區啟用，可能無法封存完整的工作階段。在此情況下，包含已啟用封存之使用者的 IM 仍可進行封存，但不包含會議內容檔案以及會議加入或離開事件。

<div>


> [!IMPORTANT]  
> 如果您的組織中的封存非常重要，請務必在適當的層級部署封存、設定原則及其他選項，並為所有適當的使用者啟用封存，然後才為 Lync Server 2013 啟用這些使用者。



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>封存部署程序

下表提供在現有拓撲中部署封存之所需步驟的概觀。


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
<th>角色和群組成員資格</th>
<th>文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安裝必備硬體和軟體</strong></p></td>
<td><ul>
<li><p>若要使用 Microsoft Exchange 整合 (針對部分或所有使用者使用 Exchange 2013 封存儲存體) ，您需要有現有的 Exchange 2013 部署。</p></li>
<li><p>若針對部分或所有使用者使用個別封存資料庫 (使用 SQL Server 資料庫) 封存存放區，伺服器上的 SQL Server 將會儲存封存資料。</p></li>
</ul>
<div>

> [!NOTE]  
> 封存會在 Enterprise Pool 前端伺服器與 Standard Edition Server 上執行。安裝這些伺服器除必條件外，沒有額外的硬體或軟體需求。


</div></td>
<td><p>身為本機系統管理員群組成員的網域使用者。</p></td>
<td><p>支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a>。</p>
<p>支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a>。</p>
<p>規劃檔中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013</a>中封存的技術需求。</p>
<p>在部署檔中，<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">設定在 Lync Server 2013 中封存的系統和基礎結構</a>。</p>
<p>支援檔中的<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server 和 SharePoint 的 Lync server 2013 整合支援</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>只有在您部署中的所有使用者都不使用 Microsoft Exchange 整合時，才建立適當的內部拓撲以支援封存 () </strong></p></td>
<td><p>執行拓撲產生器，將 Lync Server 2013 封存資料庫新增 (SQL Server 資料庫) 至拓撲，然後發行拓撲。</p></td>
<td><p>若要將拓撲定義以納入封存資料庫，帳戶須為本機使用者群組成員。</p>
<p>若要發行拓撲，則為 domain admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，且具有「完全控制」 (許可權的檔案共用上的「讀取/寫入/修改」) ，以用於 Lync Server 2013 file store (，拓撲產生器可以設定必要的 Dacl) 。</p></td>
<td><p>在部署檔中<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">將封存資料庫新增至現有的 Lync Server 2013 部署</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>僅在使用 Microsoft Exchange 整合時設定伺服器對伺服器驗證 () </strong></p></td>
<td><p>設定伺服器以啟用 Lync Server 2013 和 Exchange 2013 之間的驗證。 建議您在啟用封存之前，執行 <strong>CsExchangeStorageConnectivity testuser_sipUri – Folder 暫放</strong> 以驗證 Exchange 封存儲存連線。</p></td>
<td><p>具有適當權限可在伺服器上管理憑證的帳戶。</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">管理伺服器對伺服器驗證 (OAuth 部署檔或作業檔中的 Lync server 2013) 和夥伴應用程式</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>設定封存原則及組態</strong></p></td>
<td><p>設定封存，包括是否使用 Microsoft Exchange 整合、全域原則及任何網站與使用者原則 (未使用 Microsoft Exchange 整合的所有資料儲存區) ，以及特定封存選項（例如重要模式和資料匯出及清除）。</p>
<p>如果使用 Microsoft Exchange 整合，請視需要設定 Exchange In-Place 保留原則。</p></td>
<td><p>RTCUniversalServerAdmins 群組 (僅限 Windows PowerShell) 或將使用者指派為 CSArchivingAdministrator 或 CSAdministrator 角色。</p></td>
<td><p>部署檔中的在<a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013</a>中設定封存支援。</p>
<p>Exchange 產品檔 (如果使用 Microsoft Exchange 整合) 。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>在不同的樹系中部署 Lync Server 和 Microsoft Exchange

如果 Microsoft Exchange Server 並非與 Lync Server 部署在相同樹系中，您必須確定下列 Exchange Active Directory 屬性已同步處理至部署 Lync Server 的樹系：

1.  msExchUserHoldPolicies

2.  proxyAddresses

此為多重值屬性。在同步處理此屬性之時，您必須將數值合併，不要予以取代，以便確保現有數值不會遺失。

</div>

</div>

<span> </span>

</div>

</div>

</div>

