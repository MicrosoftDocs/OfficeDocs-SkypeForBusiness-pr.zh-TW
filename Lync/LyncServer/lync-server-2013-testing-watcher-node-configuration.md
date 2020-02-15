---
title: Lync Server 2013： 測試監看員節點組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8d0fe8500bd676ef1a9a33c9197dfeac7783c10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Lync Server 2013 中的測試監看員節點組態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-11-03_


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
<td><p>測試工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-cswatchernodeconfiguration</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

如果您使用 Microsoft System Center Operations Manager 監視 Lync Server 2013，則您可以設定 「 監看員節點 」 的選擇： 定期，並自動執行綜合交易，若要驗證為正常到 Lync Server 的電腦預期的。 監看員節點指派給集區]，並使用**CsWatcherNodeConfiguration** cmdlet 所管理。 請注意，您不需要安裝監看員節點，如果您使用 System Center Operations Manager。 您仍然可以監視您的系統，而不需使用監看員節點。 唯一的差別在於，任何您想要執行的綜合交易必須叫用手動方式而不是自動叫用 Operations Manager。

**Test-cswatchernodeconfiguration** cmdlet 可讓您確認監看員節點已正確設定，並指派給有效的 Lync Server 2013 集區。 請注意，必須在本身的監看員節點上執行**Test-cswatchernodeconfiguration** cmdlet。 此 cmdlet 無法執行對遠端電腦。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列命令會確認已採用組織中每個監看員節點組態設定。

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

下列成功的範例輸出顯示具有四個 edge server 的系統。

驗證目標集區 atl-cs-001.litwareinc.com 針對拓樸。

成功： 目標集區 atl-cs-001.litwareinc.com 存在於拓撲中。

成功： 目標集區 atl-cs-001.litwareinc.com 已安裝登錄器角色。

成功： 目標集區 atl-cs-001.litwareinc.com 是支援的版本。

成功： 5061 目標集區 atl-cs-001.litwareinc.com 的連接埠號碼正確。

檢查監看員節點設定中遺漏的集區已啟動。 如果偵測到任何錯誤，它將會列印。

檢查遺漏的集區在監看員節點組態便已完成。

檢查安裝監看員節點所建立的監看員節點登錄機碼，便會啟動。 如果偵測到任何錯誤，它將會列印。

檢查安裝監看員節點所建立的監看員節點登錄機碼，已完成。 偵測到的驗證類型是交涉。

在成功驗證測試使用者的認證 sip: user1 @ atl-cs-001.litwareinc.com 認證管理存放區中存在。

在成功驗證測試使用者的認證 sip: user2 @ atl-cs-001.litwareinc.com 認證管理存放區中存在。

檢查監看員節點設定中遺漏的集區已啟動。 如果偵測到任何錯誤，它將會列印。

警告： 集區 atl-cs-001.litwareinc.com 已註冊機構

角色安裝，但沒有測試使用者為其設定。

檢查遺漏的集區在監看員節點組態便已完成。

檢查安裝監看員節點所建立的監看員節點登錄機碼，是

啟動。 如果偵測到任何錯誤，它將會列印。

Test-cswatchernodeconfiguration： 找不到健康情況登錄機碼

軟體\\Microsoft\\即時通訊。 請確定監看員節點.msi 是

正確安裝。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-cswatchernodeconfiguration**可能會失敗：

  - 未正確地安裝監看員節點。

  - 沒有測試使用者的設定。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

