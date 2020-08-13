---
title: Lync Server 2013：測試系統管理員拓撲許可權
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
ms.openlocfilehash: 050ba83b4598fc5ed8ed3d40d0b1aa02ba9356b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>在 Lync Server 2013 中測試系統管理員拓撲許可權

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
<td><p>初始 Lync Server 部署之後。 在發生許可權相關的問題時，視需要進行。</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsSetupPermission Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

根據預設，只有網域管理員可以啟用 Lync Server 拓撲，並對 Lync Server 基礎結構進行大型變更。 只要您的網域管理員和您的 Lync 伺服器管理員是同一個，這就不是問題。在許多組織中，Lync Server 系統管理員不會保留整個網域的系統管理許可權。 根據預設，這表示這些管理員 (定義為 RTCUniversalServerAdmins 群組的成員) 無法進行 Lync Server 拓撲變更。 若要授與 RTCUniversalServerAdmins 群組的成員進行拓撲變更，您必須使用[Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) Cmdlet 指派必要的 Active Directory 許可權。

Test-CsSetupPermission Cmdlet 會驗證安裝 Lync Server 或其其中一個元件所需的必要許可權是否已在指定的 Active Directory 容器上進行設定。 若未指派許可權，您可以執行 Grant-CsSetupPermission 指令指令，讓 RTCUniversalServerAdmins 群組的成員能安裝及啟用 Lync Server。

<div>


> [!NOTE]  
> 如需 Grant-CsSetupPermission 所指派許可權的詳細清單，請參閱博客文章<A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission 和 Grant-CsOUPermission</A>。



</div>

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要判斷是否為 Active Directory 容器指派安裝程式許可權，請致電 Test-CsSetupPermission Cmdlet。 指定要檢查之容器的辨別名稱。 例如，此命令會驗證容器 ou = CsServers，dc = litwareinc，dc = com 的設定許可權：

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

如需詳細資訊，請參閱[Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 Test-CsSetupPermission 判斷已經在 Active Directory 容器上設定必要的許可權，則 Cmdlet 會傳回值 True：

對

如果未設定許可權，Test-CsSetupPermission 會傳回值 False。 請注意，此值通常會包含在許多警告訊息中。 例如：

警告： Access control entry (ACE) atl-cs-001 \\ RTCUniversalServerAdmins;供ExtendedRight;全全1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

警告：物件 "CN = 電腦，DC = litwareinc，DC=com" 的存取控制專案 (Ace) 尚未就緒。

錯

警告： "Test-CsSetupPermission" 處理已完成，但有警告。 在此執行期間，記錄了 "2" 個警告。

警告：在 "C： \\ Users \\ Admin \\ AppData \\ Local \\ Temp \\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html" 上可以找到詳細的結果。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

雖然很少例外，但如果 Test-CsSetupPermission 失敗通常表示未指派指定之 Active Directory 容器的設定許可權。 您可以使用 Grant-CsSetupPermission Cmdlet 指派這些許可權。 例如，此命令會授與網域 litwareinc.com 中電腦容器的設定許可權：

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

如需詳細資訊，請參閱[Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

