---
title: Lync Server 2013：測試 .LIS 伺服器設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e5baed37e4c72da8b8348dab9702b5d22fbbc5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中測試 IIS 伺服器設定

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsLisConfiguration Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsLisConfiguration Cmdlet 會驗證您是否可以與 IIS 網站服務取得聯繫。 如果可以取得 web 服務，則無論是否找到任何特定位置，都會認為測試是成功的。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsLisConfguration Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。 若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。 例如：

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。 當您呼叫 Test CsLisConfiguration 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果 .LIS 的設定正確，您將會收到與此類似的輸出，結果屬性標示為**成功：**

TargetUri :https://atl-cs-001.litwareinc.com:443/locationinformation/

liservice （.svc）

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.1616913

出錯

自檢

如果指定的使用者無法登入或登出，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：

TargetUri :

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：11004，要求的名稱有效，但沒有要求的資料

已找到類型

自檢

Test-CsLisConfiguration：在拓撲中找不到相符的群集。

例如，前一個輸出包含「在拓撲中找不到相符的群集」的筆記。 這通常表示邊緣伺服器的問題：使用 Edge 伺服器來連線至服務提供者並驗證位址的 IIS 類型。

如果測試 CsLisConfiguration 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsLisConfiguration 會傳回其嘗試的每個動作的逐步帳戶。 例如：

呼叫位置資訊服務。

服務路徑 =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

ChassisId =

PortId =

PortIdSubType = 未定義的類型

版

例外 ' 位置資訊 Web 服務要求失敗，回應碼 Item400。」 在工作流程 SyntheticTrsnactions STLisConfigurationWorkflow 執行期間發生。

如果您仔細檢查先前的輸出，您會發現 Cmdlet 在嘗試呼叫位置資訊服務之後失敗。 該呼叫中使用的其中一個參數就是：

BssId = 5

這個值不是基本服務組識別元（BssID）的有效值。 相反地，BssID 應如下所示：

12-34-56-78-90-ab

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsLisConfiguration 可能失敗的一些常見原因：

  - 提供不正確的參數值。 如上一個範例所示，必須正確設定選用的參數，否則測試將會失敗。 重新執行不含選用參數的命令，並查看是否成功。

</div>

</div>

<span> </span>

</div>

</div>

</div>

