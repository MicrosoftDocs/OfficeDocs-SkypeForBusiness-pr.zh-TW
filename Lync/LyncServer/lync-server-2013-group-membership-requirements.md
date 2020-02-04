---
title: Lync Server 2013：群組成員資格需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ad8c7f6eab93f3bdcd7b73d4ae05bd3b2e25ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Lync Server 2013 的群組成員資格需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

下表摘要列出人員應該歸屬的群組，以便成功安裝、管理和疑難排解 Lync Server 2013。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013 可執行檔</th>
<th>需要群組成員資格</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe：</strong>啟動 Lync Server 2013 系統管理工具安裝的可執行檔。</p></td>
<td><p>執行可執行檔之電腦上的本機管理員群組成員。 [網域使用者] 群組的成員，以讀取 Active Directory 網域服務中的資訊。 之所以需要此許可權等級，是因為在本機電腦上自動安裝必要的 MSI 套件時，必須具備允許讀取和寫入受保護的本機電腦資源（例如程式檔案目錄）和受保護的許可權的許可權。[本機電腦] 配置單元之類的註冊表。</p>
<div>

> [!TIP]  
> 您也可以將設定許可權委派給您不想在網域管理員群組中授與其成員資格的使用者或群組。 如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中的授權設定許可權</A>。


</div></td>
</tr>
<tr class="even">
<td><p><strong>.Deploy</strong> （由 setup.exe）所呼叫的是，部署 .exe 負責部署伺服器角色的軟體元件。</p></td>
<td><p>執行可執行檔之電腦上的本機管理員群組成員。 [網域使用者] 群組的成員，以朗讀 AD DS 中的資訊。 之所以需要此許可權等級，是因為在本機電腦上自動安裝必要的 MSI 套件時，必須具備允許讀取和寫入受保護的本機電腦資源（例如程式檔案目錄）和受保護的許可權的許可權。[本機電腦] 配置單元之類的註冊表。 RtcUniversalReadOnlyAdmins 群組中的成員資格是讀取中央管理儲存區所必需的。</p>
<div>

> [!NOTE]  
> 如果您執行的是 Windows Vista 作業系統或 Windows 7 作業系統，系統會提示您 [使用者帳戶控制] （UAC）繼續安裝。 如果您是使用標準使用者帳戶登入，您將需要擁有本機管理員群組成員的使用者在系統提示有安裝軟體許可權的帳戶時提供認證。


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Cscript.exe （</strong>由 setup.exe 呼叫）是由 setup.exe 負責部署和設定伺服器角色。</p></td>
<td><p>執行可執行檔之電腦上的本機管理員群組成員。 RTCUniversalServerAdmins 群組的成員，以執行引導程式。 [網域使用者] 群組的成員，以朗讀 AD DS 中的資訊。 之所以需要此許可權等級，是因為在本機電腦上自動安裝必要的 MSI 套件時，必須具備允許讀取和寫入受保護的本機電腦資源（例如程式檔案目錄）和受保護的許可權的許可權。[本機電腦] 配置單元之類的註冊表。</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> –由嚮導驅動的使用者介面，用以建立、查看、調整和驗證 Lync Server 2013 拓撲。</p></td>
<td><p>執行可執行檔之電腦上的本機管理員群組成員，以查看拓撲。 [RTCUniversalServerAdmins] 群組的成員，以變更配置設定。 RTCUniversalServerAdmins 群組和網域系統管理員群組的成員，或 RTCUniversalServerAdmins 群組的成員（只有在群組已獲委派設定許可權），才能發佈拓撲。 如需委派設定許可權以允許 RTCUniversalServerAdmins 群組的成員發佈拓撲的詳細資料，而不是網域管理員群組的成員，請參閱在部署檔中的<a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中的授權設定許可權</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> –用於管理 Lync Server 2013 的 Web 型圖形使用者介面。</p></td>
<td><p>指派特定系統管理工作的另一個角色式存取控制（RBAC）角色之 CsAdministrator 群組或成員的成員。 Lync Server 2013 的 [控制台] 會執行 Lync Server 2013 管理命令介面 Cmdlet，以實現設定變更。 如需預先定義的角色和 Cmdlet 成員的清單，請參閱規劃檔中的<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</a>。</p></td>
</tr>
<tr class="even">
<td><p>已<strong>載入 Lync server 2013 模組的 PowerShell</strong> （具有專用來管理 lync Server 2013 之 Cmdlet 的命令列管理工具）。</p></td>
<td><p>已指派特定 Cmdlet 之 CsAdministrator 群組或另一個 RBAC 角色成員的成員。 如需預先定義的角色和 Cmdlet 成員的清單，請參閱規劃檔中的<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</a>。</p>
<p>或者，下列一或多個群組的成員，視 Cmdlet 而定：</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

