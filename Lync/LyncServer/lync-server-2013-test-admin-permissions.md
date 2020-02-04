---
title: Lync Server 2013：測試系統管理員許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4543501d668b61bbb90073c80c4e85373341d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a>Lync Server 2013 中的測試管理員許可權

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-18_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>初次進行 Lync Server 部署之後。 如有許可權相關問題，請視需要進行。</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsOUPermission Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

當您安裝 Lync Server 2013 1 時，安裝程式所執行的工作會為 RTCUniversalUserAdmins 群組提供管理使用者、電腦、連絡人、應用程式連絡人及 InetOrg 人員所需的 Active Directory 許可權。 如果您已在 Active Directory 設定中停用許可權繼承，將無法指派這些許可權。 因此，RTCUniversalUserAdmins 群組的成員將無法管理 Lync Server 實體。 只有網域系統管理員可以使用這些管理許可權。

CsOUPermission Cmdlet 會驗證管理使用者、電腦及其他物件所需的許可權是否已在 Active Directory 容器上設定。 如果未設定這些許可權，您可以執行[授與 CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) Cmdlet 來解決這個問題。

請注意，授與 CsOUPermission 只能將許可權指派給 RTCUniversalUserAdmins 群組的成員。 您無法使用此 Cmdlet 來授與任何使用者或群組的許可權。 如果您想要讓不同的使用者或群組擁有使用者管理許可權，您應該將該使用者（或群組）新增至 [RTCUniversalUserAdmins] 群組。

如需有關 OU 許可權的詳細資訊，請參閱在[Lync Server 2013 中，電腦、使用者或 InetOrgPerson 容器上的許可權繼承已停用](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要確認管理許可權是在容器上設定，請執行 Test CsOUPermission Cmdlet，後面接著該容器的辨識名稱，以及您要驗證的許可權類型。 例如，這個命令會檢查是否在 OU ou = 雷蒙德、dc = litwareinc、dc = com 中設定使用者許可權：

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

若要使用單一命令驗證多個許可權，請用引號括住每個許可權類型，然後使用逗號分隔這些類型。 例如，下列一個命令會驗證使用者、電腦和連絡人許可權：

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

如需詳細資訊，請參閱[Test CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) Cmdlet 的說明主題。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果已設定必要的許可權，則 CsOUPermission 會傳回單字回應：

滿足

如果沒有設定所需的許可權，則 CsOUPermission 會傳回值 False。 您可能需要搜尋時間來尋找這個值。 它通常會內嵌在幾個伴隨的警告中。 例如：

警告：存取控制專案（ACE） atl-cs-001\\RTCUniversalUserReadOnlyGroup;允許ReadProperty;ContainerInherit;子類bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4

警告：物件 "OU = 北美" （Ace）上的 access 控制項專案（Ace），DC = atl-\\cs-001 dc = LITWAREINC，dc = com "尚未就緒。

虛假

警告：「Test CsOUPermission」處理已完成，但出現警告。 此執行期間錄製了 "2" 個警告。

警告：您\\可以在「C：使用者\\系統管理員\\AppData\\本機\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de .html」中找到詳細的結果。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果測試 CsOUPermission 失敗，通常表示指定的許可權尚未指派給 RTCUniversalUserAdmins 群組。 您可以使用 Grant CsOUPermission Cmdlet 來解決這個問題，並指派所需的許可權。 例如，這個命令會將使用者、連絡人及 inetOrgPersons 的 OU 許可權提供給 RTCUniversalUserAdmins 群組：

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

如需詳細資訊，請參閱 Grant CsOUPermission Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

