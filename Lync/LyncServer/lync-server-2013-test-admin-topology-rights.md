---
title: Lync Server 2013：測試管理員拓撲許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3681a3328f0e1e659377947919bbfc782f1fea7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Lync Server 2013 中的測試管理員拓朴許可權

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-08_


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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsSetupPermission Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

根據預設，只有網域系統管理員可以啟用 Lync Server 拓撲，並對 Lync Server 基礎結構進行較大的變更。 只要您的網域系統管理員和您的 Lync 伺服器管理員都是相同的，就不會發生問題。在許多組織中，Lync Server 系統管理員不會在整個網域中保留系統管理許可權。 根據預設，這表示這些系統管理員（定義為 RTCUniversalServerAdmins 群組的成員）無法進行 Lync Server 拓撲變更。 若要賦予 RTCUniversalServerAdmins 群組的成員對拓撲進行變更的權利，您必須使用[Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) Cmdlet 來指派所需的 Active Directory 許可權。

CsSetupPermission Cmdlet 會確認安裝 Lync Server 或其某個元件所需的許可權已在指定的 Active Directory 容器上設定。 如果沒有指派許可權，您可以執行授與 CsSetupPermission Cmdlet，將 RTCUniversalServerAdmins 群組的成員授與安裝和啟用 Lync Server 的權利。

<div>


> [!NOTE]  
> 如需由授與 CsSetupPermission 指派之許可權的詳細清單，請參閱博客文章<A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">授與授與授與授與授與 CsOUPermission</A>。



</div>

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要判斷是否已指派 Active Directory 容器的設定許可權，請呼叫 CsSetupPermission Cmdlet。 指定要檢查之容器的辨識名稱。 例如，這個命令會驗證容器 ou = CsServers、dc = litwareinc、dc = com 的設定許可權：

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

如需詳細資訊，請參閱[Test CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的說明主題。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果測試 CsSetupPermission 決定已在 Active Directory 容器上設定所需的許可權，則 Cmdlet 會傳回值 True：

滿足

如果沒有設定許可權，測試 CsSetupPermission 會傳回值 False。 請注意，這個值通常會括在許多警告訊息中。 例如：

警告：存取控制專案（ACE） atl-cs-001\\RTCUniversalServerAdmins;允許ExtendedRight;所有所有1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

警告：物件「CN = 電腦、DC = litwareinc、DC = com」上的存取控制專案（Ace）尚未就緒。

虛假

警告：「Test CsSetupPermission」處理已完成，但出現警告。 此執行期間錄製了 "2" 個警告。

警告：您\\可以在「C：使用者\\系統管理員\\AppData\\本機\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118 .html」中找到詳細的結果。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

雖然不常見的例外狀況，但如果測試 CsSetupPermission 失敗，通常表示沒有為指定的 Active Directory 容器指派設定許可權。 您可以使用 Grant CsSetupPermission Cmdlet 來指派這些許可權。 例如，這個命令會在網域 litwareinc.com 中授與電腦容器的設定許可權：

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

如需詳細資訊，請參閱[Test CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

