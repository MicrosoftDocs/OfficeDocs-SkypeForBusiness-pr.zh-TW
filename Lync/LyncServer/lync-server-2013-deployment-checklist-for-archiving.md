---
title: Lync Server 2013： 封存的部署檢查清單
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
ms.openlocfilehash: 2df74bda74f1b9af01e1c4e73fa2f21b7119363f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lync Server 2013 中的封存的部署檢查表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-18_

封存會自動安裝在每部前端伺服器在 Lync Server 2013 部署中，但您仍需要設定它，然後您可以使用它。 請依本節摘要之設定所需的步驟部署封存。

<div>

## <a name="deployment-sequence"></a>部署順序

如何根據所選擇的存放區選項設定封存：

  - 如果您在部署中的所有使用者使用 Microsoft Exchange 整合，您不需要設定您的使用者的 Lync Server 2013 封存原則。 相反地，設定 Exchange 就地保留原則以支援封存的使用者使用他們放入原有範圍暫止的信箱位於 Exchange 2013。 如需設定這些原則的詳細資訊，請參閱 < Exchange 2013 產品的說明文件。

  - 如果您不在您的部署中使用的所有使用者的 Microsoft Exchange 整合，您需要新增 Lync Server 封存資料庫 （SQL Server 資料庫） 至您的拓撲，然後發行，以及設定原則和設定您的使用者，然後您才可以封存這些使用者的資料。 您可在部署初始拓撲的同時，或者在部署至少一個前端集區或 Standard Edition Server 之後，進行部署封存資料庫。 本文件描述如何透過將封存資料庫新增至現有部署來進行部署。

如果您在一個前端集區或 Standard Edition Server 啟用封存，則應在部署中針對所有其他前端集區和 Standard Edition Server 一併啟用。這是因為，需要將通訊封存的使用者可受邀至由其他集區所主控的群組 IM 交談或會議。如果封存未在主控交談或會議的所在集區啟用，可能無法封存完整的工作階段。在此情況下，包含已啟用封存之使用者的 IM 仍可進行封存，但不包含會議內容檔案以及會議加入或離開事件。

<div>


> [!IMPORTANT]  
> 如果封存極為重要，您的組織基於規範考量，務必部署封存、 設定原則與其他選項，在適當的層級，以及啟用的所有適當的使用者，才能讓這些使用者在 Lync Server 2013。



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
<li><p>若要使用 Microsoft Exchange 整合 （針對部分或所有使用者的封存存放區中使用 Exchange 2013），您需要現有的 Exchange 2013 部署。</p></li>
<li><p>若針對部分或所有使用者使用個別封存資料庫 (使用 SQL Server 資料庫) 封存存放區，伺服器上的 SQL Server 將會儲存封存資料。</p></li>
</ul>
<div>

> [!NOTE]  
> 封存會在 Enterprise Pool 前端伺服器與 Standard Edition Server 上執行。安裝這些伺服器除必條件外，沒有額外的硬體或軟體需求。


</div></td>
<td><p>身為本機系統管理員群組成員的網域使用者。</p></td>
<td><p>支援文件中<a href="lync-server-2013-supported-hardware.md">的 Lync Server 2013 支援硬體</a>。</p>
<p>支援文件中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的伺服器軟體和基礎結構支援</a>。</p>
<p>規劃文件中<a href="lync-server-2013-technical-requirements-for-archiving.md">的 technical requirements for Lync Server 2013 中的封存</a>。</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">設定系統與基礎結構的 Lync Server 2013 中的封存</a>中部署文件。</p>
<p>支援文件中的<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server 與 SharePoint 整合支援 Lync Server 2013 中</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>建立適當的內部拓撲以支援封存 （只有當不使用 Microsoft Exchange 整合您的部署中的所有使用者）</strong></p></td>
<td><p>執行拓撲產生器來將 Lync Server 2013 封存資料庫 （SQL Server 資料庫） 新增至拓撲，並再發行拓撲。</p></td>
<td><p>若要將拓撲定義以納入封存資料庫，帳戶須為本機使用者群組成員。</p>
<p>若要發行拓撲，這是 domain admins 群組和 RTCUniversalServerAdmins 群組的成員，且用於 Lync Server 2013 檔案存放區 （以便拓撲產生器可以設定必要的 Dacl） 的檔案共用具有完整控制權限 （讀取/寫入/修改） 的帳戶。</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">新增封存資料庫到現有的 Lync Server 2013 部署</a>中部署文件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>設定伺服器對伺服器驗證 （只有在使用 Microsoft Exchange 整合）</strong></p></td>
<td><p>設定伺服器，以啟用 Lync Server 2013 和 Exchange 2013 之間的驗證。 建議您執行<strong>測試 CsExchangeStorageConnectivity testuser_sipUri – 資料夾暫放</strong>若要驗證 Exchange 封存儲存連線才能啟用封存。</p></td>
<td><p>具有適當權限可在伺服器上管理憑證的帳戶。</p></td>
<td><p>部署文件或作業文件中的<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>設定封存原則及組態</strong></p></td>
<td><p>設定封存，包括是否要使用 Microsoft Exchange 整合、 全域原則及任何網站與使用者原則 （如果不使用 Microsoft Exchange 整合的所有資料存放區），以及特定封存選項，例如重要模式及資料匯出和清除。</p>
<p>如果使用 Microsoft Exchange 整合，視需要設定 Exchange 就地保留原則。</p></td>
<td><p>RTCUniversalServerAdmins 群組 (僅限 Windows PowerShell) 或將使用者指派為 CSArchivingAdministrator 或 CSAdministrator 角色。</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving Lync Server 2013 中</a>部署文件中。</p>
<p>Exchange 產品文件 （如果使用 Microsoft Exchange 整合）。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>部署 Lync Server 和 Microsoft Exchange 在不同樹系

如果未在 Lync Server 相同的樹系中部署 Microsoft Exchange Server，您必須確定下列 Exchange Active Directory 屬性已同步處理至 Lync Server 部署所在之樹系：

1.  msExchUserHoldPolicies

2.  proxyAddresses

此為多重值屬性。在同步處理此屬性之時，您必須將數值合併，不要予以取代，以便確保現有數值不會遺失。

</div>

</div>

<span> </span>

</div>

</div>

</div>

