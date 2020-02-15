---
title: Lync Server 2013： 設定監看員節點以執行綜合交易
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
ms.openlocfilehash: 107803caba66c19ec852d4c077e69aec5f7cf5ca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>設定監看員節點以 Lync Server 2013 中執行的綜合交易

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-07_

在安裝 System Center 代理程式檔案之後，您必須下一步] 設定監看員節點本身。 設定監看員節點所採取的步驟將視您的監看員節點電腦位於周邊網路內或周邊網路外而異。

當您設定監看員節點時，您也必須選擇該節點要使用的驗證方法的型別。 Lync Server 2013 可讓您選擇下列其中一個兩種驗證方法： 信任的伺服器] 或 [認證驗證。 下表列出這兩個方法之間的差異：


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
<td><p>受信任的伺服器</p></td>
<td><p>使用憑證來模擬內部伺服器，並略過驗證質詢。</p>
<p>這種方法適合偏好管理單一憑證而不是每個監看員節點上的許多使用者密碼的系統管理員。</p></td>
<td><p>企業內部。</p>
<p>請注意，使用此方法時，監看員節點必須集區相同網域中受監視。 如果監看員節點和受監視的集區是在不同的網域，請改為使用認證驗證。</p></td>
</tr>
<tr class="even">
<td><p>認證驗證</p></td>
<td><p>儲存使用者名稱和密碼安全地以 Windows 認證管理員在每個監看員節點上。</p>
<p>此模式需要更多的密碼管理，但位於企業外的監看員節點的唯一選項。 這些監看員節點無法被視為受信任的驗證端點。</p></td>
<td><p>於企業外。</p>
<p>企業內部。</p></td>
</tr>
</tbody>
</table>


您也應確認您的防火牆都有輸入規則 MonitoringHost.exe 和 PowerShell.exe。 如果這些處理程序會被防火牆封鎖，則您的綜合交易，將會失敗並 504 （伺服器逾時） 時發生錯誤。

</div>

<span> </span>

</div>

</div>

</div>

