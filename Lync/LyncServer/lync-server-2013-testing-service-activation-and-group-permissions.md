---
title: Lync Server 2013：測試服務啟用與群組許可權
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
ms.openlocfilehash: ef22928f9506c4ec67acd3de6bad80274f8c0f12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中測試服務啟用與群組許可權

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
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsTopology Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsTopology Cmdlet 可讓您驗證 Lync Server 2013 在全域範圍中是否正常運作。 根據預設，此 Cmdlet 會檢查您的整個 Lync 伺服器基礎結構，確認所需的服務正在執行，且已針對這些服務以及在安裝 Lync Server 時所建立的通用安全性群組設定適當的許可權.

除了驗證 Lync Server 安裝的有效性，測試 CsTopology 也可讓您檢查特定服務的有效性。 例如，這個命令會檢查 [pool atl-cs-001.litwareinc.com] 上的 A/V 會議伺服器狀態：

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>執行測試

根據預設，測試 CsTopology 會在畫面上顯示極小的輸出。 相反地，由 Cmdlet 傳回的資訊會寫入 HTML 檔案。 Report 參數可讓您指定由 Test CsTopology 所產生之 HTML 檔案的檔案路徑和檔案名。 如果您不包含報表參數，HTML 檔案將會自動儲存到 [使用者] 資料夾，並指定如下的名稱： ce84964a-c4da-4622-ad34-c54ff3ed361f .html。

下列範例命令會執行 Test-CsTopology，並將輸出儲存到名為 C：\\Logs\\ComputerTest 的檔案中：

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

如需詳細資訊，請參閱[Test CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

與大部分的測試 Cmdlet 不同，測試 CsTopology 會傳回成功或失敗的報告。 部分原因是，這是因為 Cmdlet 在每次執行時都必須發出大量驗證檢查。 相反地，資料會儲存至 HTML 報表，然後才能使用 Internet Explorer 來查看。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsTopology 可能失敗的一些常見原因：

  - 測試電腦上的複製可能不是最新的。 您可以執行 CsManagementStoreReplicationStatus Cmdlet 來檢查電腦的目前複製狀態：
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    如果複製狀態不是最新的，您可以使用類似以下的命令，手動強制進行複製：
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - 可能必須啟用拓撲。 如果您變更 Lync Server 拓撲（可能會影響本機電腦的變更），則您必須啟用新的拓撲。 您可以在任何時候執行此命令來啟用拓撲：
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

