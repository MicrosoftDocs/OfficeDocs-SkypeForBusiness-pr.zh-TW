---
title: Lync Server 2013：測試監視器節點設定
description: Lync Server 2013：測試監視器節點設定。
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
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546839"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中測試監視器節點設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-03_


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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsWatcherNodeConfiguration</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

如果您使用 Microsoft System Center Operations Manager 來監視 Lync Server 2013，您可以選擇設定「觀察程式節點」：定期及自動執行綜合交易的電腦，以驗證 Lync Server 是否如預期般運作。 觀察程式節點會指派給集區，並使用 **CsWatcherNodeConfiguration** Cmdlet 進行管理。 請注意，如果您使用 System Center Operations Manager，便不需要安裝觀察程式節點。 您仍可監控系統，而不需要使用監視程式節點。 唯一不同之處在于，您要執行的任何綜合交易都必須手動呼叫，而不是由 Operations Manager 自動呼叫。

**Test-CsWatcherNodeConfiguration** Cmdlet 可讓您確認是否已正確設定或指派給有效的 Lync Server 2013 集區的監看員節點。 請注意，必須在監看員節點本身上執行 **Test-CsWatcherNodeConfiguration** Cmdlet。 無法對遠端電腦執行 Cmdlet。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列命令會驗證組織中所使用之每個監看員節點的設定設定。

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

下列成功的範例輸出會顯示具有四部 edge 伺服器的系統。

對照拓撲驗證目標集區 atl-cs-001.litwareinc.com。

成功：目標集區 atl-cs-001.litwareinc.com 存在於拓撲中。

成功：目標集區 atl-cs-001.litwareinc.com 已安裝註冊機構角色。

成功：目標集區 atl-cs-001.litwareinc.com 為支援的版本。

成功：5061目標集區 atl-cs-001.litwareinc.com 的埠號碼是正確的。

已啟動在觀察者節點設定中檢查遺失的集區。 如果偵測到任何錯誤，就會將它列印出來。

在觀察者節點設定中檢查遺失的集區已完成。

已啟動透過檢查監視節點安裝所建立的監看員節點登錄機碼。 如果偵測到任何錯誤，就會將它列印出來。

檢查監視節點安裝所建立的監看員節點登錄機碼已完成。 偵測到驗證類型為 [協商]。

已成功驗證測試使用者的身分憑證 sip 是否存在： user1@ atl-cs-001.litwareinc.com in 認證管理存放區。

已成功驗證測試使用者的身分憑證 sip 是否存在： user2@ atl-cs-001.litwareinc.com in 認證管理存放區。

已啟動在觀察者節點設定中檢查遺失的集區。 如果偵測到任何錯誤，就會將它列印出來。

警告：集區 atl-cs-001.litwareinc.com 有註冊機構

已安裝角色，但沒有為其設定的測試使用者。

在觀察者節點設定中檢查遺失的集區已完成。

檢查監視節點安裝所建立的監看員節點登錄機碼，是

開始。 如果偵測到任何錯誤，就會將它列印出來。

Test-CsWatcherNodeConfiguration：在中找不到健康情況登錄機碼

軟體 \\ Microsoft \\ 即時通訊。 確定 [監看員] 節點 .msi 是

正確安裝。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsWatcherNodeConfiguration** 可能失敗的常見原因：

  - 未正確安裝觀察器節點。

  - 未設定測試使用者。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[Remove-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

