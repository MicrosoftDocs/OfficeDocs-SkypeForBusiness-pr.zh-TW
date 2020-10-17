---
title: Lync Server 2013：測試 Lync Server 服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74a24818094d7de0edc4627f987464df048315f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519010"
---
# <a name="testing-lync-server-services-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Lync Server 服務

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsComputer Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsComputer 驗證本機電腦上執行的所有 Lync Server 2013 服務的狀態。  (Test-CsComputer 只能在本機執行，所以無法從 Windows PowerShell 的遠端實例執行。 ) 指令程式也會檢查是否已在電腦上開啟適當的防火牆埠，並決定當您安裝 Lync Server 2013 時所建立的 Active Directory 群組是否已新增至對應的本地群組。 例如，Test-CsComputer 會驗證是否已將 Active Directory 群組 RTCUniversalUserAdmins 新增至 Administrators 群組。

如需詳細資訊，請參閱 [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

Test-CsComputer Cmdlet 只能在本機電腦上執行，所以您無法從 Windows PowerShell 的遠端實例呼叫 Test-CsComputer。 根據預設，Test-CsComputer 會在螢幕上顯示非常少的輸出，而不是將 Cmdlet 所傳回的資訊寫入 HTML 檔案。 因此，建議您在每次執行 Test-CsComputer 時，加入 Verbose 參數和 Report 參數。 在執行 Cmdlet 時，Verbose 參數會在螢幕上稍有增加的輸出。 Report 參數可讓您指定 Test-CsComputer 所產生之 HTML 檔案的檔案路徑和檔案名。 如果不包含報表參數，HTML 檔案將會自動儲存至您的使用者資料夾，並指定如下名稱： ce84964a-c4da-4622-ad34-c54ff3ed361f.html。

下列範例命令會執行 Test-CsComputer，並將輸出儲存至名為 C： Logs 的 \\ 檔案 \\ComputerTest.html：

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

如需詳細資訊，請參閱 [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

因為執行的驗證檢查數目，所以 Test-CsComputer 不會傳回簡單的 **是，測試成功** 或 **否，測試失敗**。 相反地，您必須使用 Internet Explorer 來查看所產生的 HTML 檔案，以判斷每項測試的成功或失敗。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsComputer 可能失敗的常見原因：

  - 測試電腦可能未啟用，無法搭配 Lync Server 使用。 如果電腦上的 Lync Server 服務或伺服器角色已變更，且未執行 Enable-CsComputer Cmdlet，便會發生這種情況。 若要解決此問題，請執行下列命令：
    
        Enable-CsComputer

  - 測試電腦上的複寫可能不是最新的。 您可以執行 Get-CsManagementStoreReplicationStatus Cmdlet，檢查電腦目前的複寫狀態。
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    若複寫狀態不是最新的，您可以使用類似下列的命令，手動強制進行複寫：
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - 可能必須啟用拓撲。 如果您變更 Lync Server 拓撲 (可能會影響本機電腦的變更) ，則必須啟用新的拓撲。 您可以隨時執行下列命令來啟用拓撲：
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

