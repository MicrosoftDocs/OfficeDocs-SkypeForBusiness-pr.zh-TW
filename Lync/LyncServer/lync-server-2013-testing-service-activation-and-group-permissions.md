---
title: Lync Server 2013：測試服務啟用和群組許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e29cafcfac7a74e43617841a174653f6072c5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530520"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中測試服務啟用和群組許可權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>每日</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsTopology Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsTopology Cmdlet 可讓您驗證 Lync Server 2013 在全域範圍內是否運作正常。 根據預設，指令程式會檢查整個 Lync 伺服器基礎結構，確認所需的服務正在執行，且已針對這些服務及在安裝 Lync Server 時所建立的通用安全性群組設定適當的許可權。

除了驗證 Lync Server 安裝的有效性之外，Test-CsTopology 也可讓您檢查特定服務的有效性。 例如，下列命令會檢查集區 atl-cs-001.litwareinc.com 上 A/V 會議伺服器的狀態：

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>執行測試

根據預設，Test-CsTopology 會在螢幕上顯示非常少的輸出。 相反地，指令程式傳回的資訊會寫入至 HTML 檔案。 Report 參數可讓您指定 Test-CsTopology 所產生之 HTML 檔案的檔案路徑和檔案名。 如果不包含報表參數，HTML 檔案將會自動儲存至您的使用者資料夾，並指定如下名稱： ce84964a-c4da-4622-ad34-c54ff3ed361f.html。

下列範例命令會執行 Test-CsTopology，並將輸出儲存至名為 C： Logs 的 \\ 檔案 \\ComputerTest.html：

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

如需詳細資訊，請參閱 [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

與大多數的測試 Cmdlet 不同的是，Test-CsTopology 會傳回成功或失敗報告。 部分，這是因為在每次執行 Cmdlet 時，都必須執行大量驗證檢查。 相反地，會將資料儲存到 HTML 報表，然後再使用 Internet Explorer 來查看。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsTopology 可能失敗的常見原因：

  - 測試電腦上的複寫可能不是最新的。 您可以執行 Get-CsManagementStoreReplicationStatus Cmdlet，檢查電腦目前的複寫狀態。
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    若複寫狀態不是最新狀態，您可以使用類似下列的命令，手動強制進行複寫：
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - 可能必須啟用拓撲。 如果您變更 Lync Server 拓撲 (可能會影響本機電腦的變更) ，則必須啟用新的拓撲。 您可以隨時執行下列命令來啟用拓撲：
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

