---
title: Lync Server 2013：測試 .LIS 伺服器設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50b2908b3f2403cc59f4cb7ce26f176d366ce2e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中測試 .LIS 伺服器設定

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsLisConfiguration Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsLisConfiguration Cmdlet 會驗證您是否可以聯繫 .LIS web 服務。 如果可以聯繫 web 服務，則不論是否可以找到任何特定位置，都可以將測試視為成功。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsLisConfguration Cmdlet 可使用預先設定的測試帳戶執行 (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何已啟用 Lync Server 的使用者帳戶。 若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN。 例如：

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。 接著，當您呼叫 Test-CsLisConfiguration 時，必須包含該認證物件和指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定 .LIS，您會收到類似下列的輸出，並將 Result 屬性標示為 [**成功]：**

TargetUri：https://atl-cs-001.litwareinc.com:443/locationinformation/

liservice

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.1616913

錯誤：

診斷：

如果指定的使用者無法登入或登出，結果將會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：

TargetUri：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：11004，要求的名稱是有效的，但沒有要求的資料

找到類型

診斷：

Test-CsLisConfiguration：在拓撲中找不到相符的集群。

例如，上一個輸出包含「沒有搭配拓撲中找到的對應叢集」的附注。 這通常表示 Edge Server 發生問題： .LIS 使用 Edge Server 來連線至服務提供者及驗證位址。

如果 Test-CsLisConfiguration 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 參數時，Test-CsLisConfiguration 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。 例如：

呼叫位置資訊服務。

服務路徑 =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

ChassisId =

PortId =

PortIdSubType = 未定義的類型

Mac

例外 ' 位置資訊 Web 服務要求失敗，回應碼 Item400。 ' 在工作流程 SyntheticTrsnactions 中發生 STLisConfigurationWorkflow 執行。

如果您仔細檢查先前的輸出，您會發現 Cmdlet 在嘗試呼叫位置資訊服務後失敗。 該呼叫中使用的其中一個參數是：

BssId = 5

這不是基本服務組識別碼的有效值 (BssID) 。 相反地，BssID 應如下所示：

12-34-56-78-90-ab

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsLisConfiguration 可能失敗的常見原因：

  - 提供的參數值不正確。 如先前的範例所示，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

</div>

</div>

<span> </span>

</div>

</div>

</div>

