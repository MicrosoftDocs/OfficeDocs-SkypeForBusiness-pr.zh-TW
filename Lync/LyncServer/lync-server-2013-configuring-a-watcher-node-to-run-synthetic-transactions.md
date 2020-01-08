---
title: Lync Server 2013：設定觀察程式節點以執行綜合交易
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec42f5b0f3839ee0efac84f08344aa1718120b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>將觀察程式節點設定為在 Lync Server 2013 中執行綜合交易

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

安裝系統中心代理盤案之後，您必須接著設定 [觀察程式] 節點本身。 您針對配置觀察程式節點所採取的步驟，會根據您的觀察者節點電腦是否位於周邊網路內或周邊網路外部而有所不同。

當您設定 [觀察程式] 節點時，您也必須選擇該節點要採用的驗證方法類型。 Lync Server 2013 可讓您選擇其中一種驗證方法： [信任伺服器] 或 [認證驗證]。 下列兩種方法間的差異如下表所示：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuration</th>
<th>描述</th>
<th>支援的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>受信任的伺服器</p></td>
<td><p>使用憑證來類比內部伺服器並略過驗證難題。</p>
<p>這對想要在每個觀察程式節點上管理單一憑證而不是多個使用者密碼的管理員很有用。</p></td>
<td><p>在企業內。</p>
<p>請注意，使用此方法時，觀察程式節點必須與受監視的池位於同一個網域中。 如果觀察程式節點和受監視的池都在不同的網域中，請改用認證驗證。</p></td>
</tr>
<tr class="even">
<td><p>認證驗證</p></td>
<td><p>在每個觀察程式節點上安全地儲存在 Windows 認證管理器中的使用者名稱和密碼。</p>
<p>這個模式需要更多的密碼管理，但是位於企業外部的 [觀察程式] 節點唯一的選項。 這些觀察程式節點無法被視為受信任的端點以進行驗證。</p></td>
<td><p>在企業外部。</p>
<p>在企業內。</p></td>
</tr>
</tbody>
</table>


您也應該確認您的防火牆對 MonitoringHost 和 ngen.exe 都有入站規則。 如果防火牆封鎖這些程式，則您的綜合交易將會失敗，並出現504（伺服器超時）錯誤。

</div>

<span> </span>

</div>

</div>

</div>

