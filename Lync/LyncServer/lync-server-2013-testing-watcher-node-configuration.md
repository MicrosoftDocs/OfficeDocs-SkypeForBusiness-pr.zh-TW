---
title: Lync Server 2013：測試觀察程式節點配置
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
ms.openlocfilehash: 920fc39d3800f83a2d40a613c391b2f0c93e4dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中測試觀察程式節點配置

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
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsWatcherNodeConfiguration</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

如果您使用 Microsoft System Center Operations Manager 來監視 Lync Server 2013，就可以選擇設定「觀察程式節點」：定期及自動執行綜合交易的電腦，以驗證 Lync Server 的運作方式正確. 系統會將觀察程式節點指派給 pool，並使用**CsWatcherNodeConfiguration** Cmdlet 進行管理。 請注意，如果您使用的是系統中心作業管理員，則不需要安裝觀察程式節點。 您仍可在不使用觀察程式節點的情況下監控您的系統。 唯一的差異是，您必須手動呼叫任何您想要執行的綜合交易，而不是由 Operations Manager 自動呼叫。

**CsWatcherNodeConfiguration** Cmdlet 可讓您確認已正確設定觀察程式節點，且指派給有效的 Lync Server 2013 池。 請注意， **CsWatcherNodeConfiguration** Cmdlet 必須在 [觀察程式] 節點本身上執行。 無法針對遠端電腦執行 Cmdlet。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列命令會驗證組織中使用的每個觀察程式節點的配置設定。

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

下列成功的範例輸出顯示具有四個邊緣伺服器的系統。

對照拓朴驗證目標池 atl-cs-001.litwareinc.com。

成功：在拓撲中存在目標池 atl-cs-001.litwareinc.com。

成功：目標池 atl-cs-001.litwareinc.com 已安裝註冊機構角色。

成功：目標 pool atl-cs-001.litwareinc.com 是受支援的版本。

成功：5061目標池 atl-cs-001.litwareinc.com 的埠號碼正確無誤。

已啟動在 [觀察程式節點設定] 中檢查遺失的池。 如果偵測到任何錯誤，就會列印出來。

在觀察程式節點設定中檢查遺失的池已完成。

檢查已啟動由觀察程式節點安裝所建立的觀察程式節點登錄機碼。 如果偵測到任何錯誤，就會列印出來。

檢查由觀察程式節點安裝所建立的觀察程式節點登錄機碼已完成。 偵測到驗證類型為 [協商]。

已成功驗證測試使用者的認證 sip 是否存在： user1@ atl-cs-001.litwareinc.com 認證管理儲存區中。

已成功驗證測試使用者的認證 sip 是否存在： user2@ atl-cs-001.litwareinc.com 認證管理儲存區中。

已啟動在 [觀察程式節點設定] 中檢查遺失的池。 如果偵測到任何錯誤，就會列印出來。

警告： Pool atl-cs-001.litwareinc.com 有註冊機構

已安裝角色，但沒有為其設定的測試使用者。

在觀察程式節點設定中檢查遺失的池已完成。

檢查由觀察程式節點安裝所建立的觀察程式節點登錄機碼，是

起步. 如果偵測到任何錯誤，就會列印出來。

CsWatcherNodeConfiguration：在下列情況中找不到健康情況登錄機碼

軟體\\Microsoft\\即時通訊。 請確定 [觀察程式] 節點為 [msi]

安裝正確。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsWatcherNodeConfiguration**可能失敗的一些常見原因：

  - 未正確安裝 [觀察程式] 節點。

  - 未設定測試使用者。

</div>

<div>

## <a name="see-also"></a>請參閱


[CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[移除-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

