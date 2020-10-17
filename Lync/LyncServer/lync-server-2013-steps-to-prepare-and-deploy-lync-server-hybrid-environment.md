---
title: Lync Server 2013：準備及部署 Lync Server 混合式環境的步驟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e7acf5fa315e566094728066bbc798267f029ed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519450"
---
# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>準備及部署 Lync Server 2013 混合式環境的步驟

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-08_

下表列出使用商務用 Skype Online 和 Microsoft Office 365 為混合式部署準備環境所需的步驟。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>完成？</th>
<th>步驟</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>建立 Office 365 的租使用者帳戶並啟用 Lync Online</p></td>
<td><p>深入瞭解 Office 365 和 Lync Online （ <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>）。</p>
<p>若要確定您的環境已準備好用於 Office 365，請參閱 <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">系統需求</a>。</p>
<p>如需設定 Office 365 的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">office 365 快速入門</a> 和 <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">設定 Office 365</a>。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>新增您的網域並驗證擁有權</p></td>
<td><p>您的網域有時也稱為您的 <em>虛名網域</em>。 您必須將您的網域新增至 Office 365 組織，然後依照步驟驗證使用 Office 365 的網域。 這是確認您是網域的擁有者。</p>
<p>若要將您的網域新增至 Office 365 組織，請遵循在 [ <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">將您的網域新增至 office 365</a>] 中所述的步驟。</p>
<p>完成主題中每一個區段中的所有步驟，包括 &quot; 為您的 Office 365 服務編輯 DNS 記錄。&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>驗證環境準備</p></td>
<td><p>您可以使用 Office 365 設定助理來協助您部署 Office 365。 如需詳細資訊，請參閱<a href="https://go.microsoft.com/fwlink/p/?linkid=254985">使用設定助理來決定 Office 365 的準備</a></p>
<p>如需使用工具及部署 Office 365 的詳細資訊，請參閱《 <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">office 365 部署指南》</a>。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>準備 Active Directory 同步處理</p></td>
<td><p>Active Directory 同步處理會使您的內部部署 Active Directory 持續與 Office 365 保持同步。 這可讓您建立每個使用者帳戶和群組的同步處理版本，也可讓全域通訊清單 (GAL) 從您當地的 Microsoft Exchange Server 環境同步處理至 Microsoft Exchange Online。</p>
<div>

> [!IMPORTANT]  
> 您必須在內部部署和線上 Lync 部署之間同步處理組織內所有 Lync 使用者的 AD 帳戶，即使使用者未移至 Lync Online 也是一樣。 如果您未同步處理所有使用者，組織中內部部署與線上使用者之間的通訊可能無法如預期的方式運作。


</div>
<p>若要準備環境以進行 Active Directory 同步處理，請遵循 <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">目錄同步處理藍圖</a>中所述的步驟，包括設定單一登入。</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>建立 Active Directory Federation Services (AD FS 的憑證) </p></td>
<td><p>您將需要建立憑證，以用於與 Office 365 的身分識別同盟。 如需詳細資訊，請參閱規劃及部署 AD FS 的「同盟伺服器憑證」一節，以與單一登入主題搭配使用， <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">檢查清單：使用 AD fs 來執行和管理單一登入</a>。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>指派 AD FS 的憑證</p></td>
<td><p>在您建立用於身分識別同盟與 Office 365 的憑證之後，您必須安裝並指派這些憑證。</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>將試驗使用者移至商務用 Skype Online</p></td>
<td><p>在您完成準備及設定商務用 Skype Online 環境的步驟之後，您可以開始將試驗使用者移至 Lync Online。</p>
<p>請參閱 <a href="lync-server-2013-move-users-to-lync-online.md">在 Lync Server 2013 中將使用者移至 Lync Online</a>。</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>在混合式部署中管理使用者</p></td>
<td><p>如需如何在混合式部署中管理使用者的詳細資訊，請參閱 <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合 Lync Server 2013 部署中管理使用者</a>。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

