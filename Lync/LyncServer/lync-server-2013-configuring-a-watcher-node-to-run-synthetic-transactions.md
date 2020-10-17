---
title: Lync Server 2013：設定監視節點以執行綜合交易
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9514099b3981dafdbb34911d0cedd249221c5621
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499100"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>在 Lync Server 2013 中設定監視節點以執行綜合交易

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

安裝 System Center agent 檔案之後，您必須接著設定觀察程式節點本身。 您用來設定監看員節點的步驟會隨著您的監看員節點電腦位於周邊網路或周邊網路以外的情況而有所不同。

當您設定監視節點時，您也必須選擇該節點要使用的驗證方法類型。 Lync Server 2013 可讓您選擇兩種驗證方法之一：「信任的伺服器」或「憑證驗證」。 下表概述這兩種方法之間的差異：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>組態</th>
<th>描述</th>
<th>支援的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>受信任伺服器</p></td>
<td><p>使用憑證來模擬內部伺服器並略過驗證挑戰。</p>
<p>這對喜歡管理單一憑證，而不是在每個監看員節點上使用許多使用者密碼的系統管理員非常有用。</p></td>
<td><p>在企業內。</p>
<p>請注意，使用此方法時，監看員節點必須與受監控的集區位於相同的網域中。 如果觀察程式節點與受監視的集區位於不同的網域，請改用認證驗證。</p></td>
</tr>
<tr class="even">
<td><p>憑證驗證</p></td>
<td><p>在每個監看員節點上安全地將使用者名稱和密碼儲存在 Windows 認證管理員中。</p>
<p>這種模式需要較多的密碼管理，但對於位於企業以外的觀察器節點而言，這是唯一的選擇。 這些觀察器節點不能視為可信任的端點以進行驗證。</p></td>
<td><p>在企業外。</p>
<p>在企業內。</p></td>
</tr>
</tbody>
</table>


您也應該確認您的防火牆同時具有 MonitoringHost.exe 和 PowerShell.exe 的輸入規則。 如果這些程式被防火牆封鎖，則綜合交易會失敗，並顯示 504 (伺服器超時) 錯誤。

</div>

<span> </span>

</div>

</div>

</div>

