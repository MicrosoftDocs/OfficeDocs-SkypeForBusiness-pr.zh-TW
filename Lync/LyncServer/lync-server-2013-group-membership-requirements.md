---
title: Lync Server 2013：群組成員資格需求
description: Lync Server 2013：群組成員資格需求。
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
ms.openlocfilehash: 3f18fb6fbc782ecd41b7a782965f2cd6a82f6fd5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554459"
---
# <a name="group-membership-requirements-for-lync-server-2013"></a>Lync Server 2013 的群組成員資格需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

下表摘要說明人員應該歸屬的群組，以便成功安裝、管理和疑難排解 Lync Server 2013。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013 可執行檔</th>
<th>需要的群組成員資格</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe</strong> –啟動 Lync Server 2013 系統管理工具安裝的可執行檔。</p></td>
<td><p>電腦上執行可執行檔的 Local Administrators 群組成員。 [網域使用者] 群組的成員，以讀取 Active Directory 網域服務中的資訊。 此層級權限是必要權限，因為在本機電腦上自動安裝必要的 MSI 套件時，需要允許在受保護的本機電腦資源 (例如 Program Files 目錄) 以及受保護登錄 (例如 Local Machine Hive) 上讀取和寫入的權限。</p>
<div>

> [!TIP]  
> 您也可以委派安裝權限給您不想授予 Domain Admins 群組成員資格的使用者或群組。 如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-granting-setup-permissions.md">授予 Lync Server 2013 的安裝許可權</A> 。


</div></td>
</tr>
<tr class="even">
<td><p><strong>Deploy.exe</strong> – 由 setup.exe 呼叫，deploy.exe 負責部署伺服器角色的軟體元件。</p></td>
<td><p>電腦上執行可執行檔的 Local Administrators 群組成員。 讀取 AD DS 中資訊的 Domain Users 群組成員。 此層級權限是必要權限，因為在本機電腦上自動安裝必要的 MSI 套件時，需要允許在受保護的本機電腦資源 (例如 Program Files 目錄) 以及受保護登錄 (例如 Local Machine Hive) 上讀取和寫入的權限。 需要有 RtcUniversalReadOnlyAdmins 群組的成員資格，才可讀取中央管理存放區。</p>
<div>

> [!NOTE]  
> 如果您正在執行 Windows Vista 作業系統或 Windows 7 作業系統，系統會提示使用者帳戶控制 (UAC) 進行安裝。 如果您是用標準使用者帳戶登入，則在出現具有安裝軟體權限的帳戶提示時，您會需要身為 Local Administrators 群組成員的某個人提供憑證。


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Bootstrapper.exe</strong> – 由 setup.exe 呼叫，bootstrapper.exe 負責部署和設定伺服器角色。</p></td>
<td><p>電腦上執行可執行檔的 Local Administrators 群組成員。執行 Bootstrapper.exe 的 RTCUniversalServerAdmins 群組成員。讀取 AD DS 中資訊的 Domain Users 群組成員。此層級權限是必要權限，因為在本機電腦上自動安裝必要的 MSI 套件時，需要允許在受保護的本機電腦資源 (例如 Program Files 目錄) 以及受保護登錄 (例如 Local Machine Hive) 上讀取和寫入的權限。</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> –以嚮導為導向的使用者介面，用來建立、查看、調整和驗證 Lync Server 2013 拓撲。</p></td>
<td><p>電腦上執行可執行檔以檢視拓撲的 Local Administrators 群組成員。 變更組態設定的 RTCUniversalServerAdmins 群組成員。 發行拓撲的 RTCUniversalServerAdmins 群組和 Domain Admins 群組成員，或 RTCUniversalServerAdmins 群組成員 (僅限於群組被授予委派安裝權限時)。 如需委派設定許可權以允許 RTCUniversalServerAdmins 群組成員發佈拓撲的詳細資訊，而不是 Domain Admins 群組的成員，請參閱部署檔中的授與 <a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013 中的設定許可權</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AdminUIHost</strong> –以 Web 為基礎的圖形使用者介面，用以管理 Lync Server 2013。</p></td>
<td><p>CsAdministrator 群組成員，或指派了特定系統管理工作的其他角色型存取控制 (RBAC) 角色成員。 Lync Server 2013 控制台會執行 Lync Server 2013 管理命令介面 Cmdlet，以實現設定變更。 如需可執行檔預先定義角色和 Cmdlet 成員的清單，請參閱規劃檔中的 <a href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</a> 。</p></td>
</tr>
<tr class="even">
<td><p>已<strong>載入 Lync server 2013 模組的PowerShell.exe</strong> –具有 lync server 2013 管理專用 Cmdlet 的命令列系統管理工具。</p></td>
<td><p>CsAdministrator 群組成員，或指派特定 Cmdlet 的其他 RBAC 角色成員。 如需可執行檔預先定義角色和 Cmdlet 成員的清單，請參閱規劃檔中的 <a href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</a> 。</p>
<p>或者，下列一或多個群組成員 (視 Cmdlet 而定)：</p>
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

