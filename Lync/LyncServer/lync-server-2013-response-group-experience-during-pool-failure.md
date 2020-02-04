---
title: Lync Server 2013 集區失敗期間的回應群組經驗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad00afac363642106019269e86111f61eaca504e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Lync Server 2013 中集區失敗期間的回應群組經驗

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

本節將詳細說明回應群組活動如何在下列階段受到影響：

  - 在主要的池中發生停機，但尚未啟動容錯移轉。

  - 服務已容錯移轉至備份池。

  - 服務傳回主要池失敗。

<div>

## <a name="user-experience-when-outage-occurs"></a>發生停機時的使用者體驗

當池或網站發生停機，但系統管理員尚未啟動容錯移轉時，系統會處理回應群組活動，如下表所述。

<div>


> [!NOTE]  
> 在災害復原期間，視主要池回應群組是否已匯入到備份池中而定，呼叫的行為會有所不同。 在下表中，已匯入的回應群組的參照代表在災害復原模式中，主要的池回應群組已匯入到備份池中。



</div>

### <a name="outage-occurs"></a>發生中斷

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>撥號類型或使用者動作</th>
<th>在中斷期間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>連線至代理程式的通話</p></td>
<td><ul>
<li><p>定期通話仍保持連線。</p></li>
<li><p>匿名呼叫已中斷連線。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>尚未連線至代理程式的 [進行中] 通話</p></td>
<td><p>通話中斷連線。</p></td>
</tr>
<tr class="odd">
<td><p>新的通話</p></td>
<td><ul>
<li><p>通話中斷連線。</p></li>
<li><p>如果已匯入回應群組，則呼叫會連線至 [備份] 池，但主機駐留在主要池中的代理無法到達。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>代表回應群組的代理程式通話</p></td>
<td><p>在此階段停用功能。</p></td>
</tr>
<tr class="odd">
<td><p>[代理程式登入] 和 [代理程式資訊]</p></td>
<td><ul>
<li><p>主要池擁有的代理群組可以在代理程式主控台上查看，但代理程式無法登入。</p></li>
<li><p>備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</p></li>
<li><p>[匯入的代理程式群組] 不會顯示在代理程式主控台上。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>回應群組設定</p></td>
<td><ul>
<li><p>根據主要池後端資料庫的可用性，您可以查看主要池所擁有的回應群組，但不能加以修改。</p></li>
<li><p>備份池所擁有的回應群組可以查看及修改。</p></li>
<li><p>無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>容錯移轉期間的使用者體驗

當系統管理員將容錯移轉喚醒至備份池時，會在容錯移轉期間和之後處理回應群組活動，如下表所述。 第一欄會說明可能發生的活動類型。 中間欄會說明如何在短時間內處理每個活動，以進行容錯移轉至備份池。 最後一欄說明在容錯移轉程式完成後，以及針對主要池進行備份池之後，該活動在該期間的處理方式。

<div>


> [!NOTE]  
> 在災害復原期間，視主要池回應群組是否已匯入到備份池中而定，呼叫的行為會有所不同。 在下表中，已匯入的回應群組的參照代表在災害復原模式中，主要的池回應群組已匯入到備份池中。



</div>

### <a name="failover-is-initiated"></a>已啟動容錯移轉

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>撥號類型或使用者動作</th>
<th>在容錯移轉期間</th>
<th>容錯移轉完成後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>連線至代理程式的通話</p></td>
<td><ul>
<li><p>定期通話仍保持連線。</p></li>
<li><p>匿名呼叫已中斷連線。</p></li>
</ul></td>
<td><ul>
<li><p>定期通話仍保持連線。</p></li>
<li><p>若是已匯入的回應群組，已到達備份池的匿名呼叫仍會保持連線。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>尚未連線至代理程式的 [進行中] 通話</p></td>
<td><p>通話中斷連線。</p></td>
<td><ul>
<li><p>如果無法匯入回應群組，就不會有任何通話處於此狀態。</p></li>
<li><p>若是已匯入的回應群組，已到達備份池的通話仍會保持連線。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>新的通話</p></td>
<td><ul>
<li><p>通話中斷連線。</p></li>
<li><p>針對匯入的回應群組，呼叫會連線至備份池，但無法取得駐留在主要池中的代理程式。</p></li>
</ul></td>
<td><ul>
<li><p>如果無法匯入回應群組，通話會中斷連線。</p></li>
<li><p>在匯入的回應群組中，呼叫會連線至 [備份] 池。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>代表回應群組的代理程式通話</p></td>
<td><p>在此階段停用功能</p></td>
<td><ul>
<li><p>如果無法匯入回應群組，通話就會失敗。</p></li>
<li><p>如果是匯入的回應群組，通話就會成功。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>[代理程式登入] 和 [代理程式資訊]</p></td>
<td><ul>
<li><p>主要池擁有的代理群組可以在代理程式主控台上查看，但代理程式無法登入。</p></li>
<li><p>備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</p></li>
<li><p>匯入的代理程式群組會顯示在代理程式主控台上，且代理程式可以登入。</p></li>
</ul></td>
<td><ul>
<li><p>主要池擁有的代理群組可以在代理程式主控台上查看，但代理程式無法登入。</p></li>
<li><p>備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</p></li>
<li><p>匯入的代理程式群組會顯示在代理程式主控台上，且代理程式可以登入。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>回應群組設定</p></td>
<td><ul>
<li><p>根據主要池後端資料庫的可用性，您可以查看主要池所擁有的回應群組，但不能加以修改。</p></li>
<li><p>備份池所擁有的回應群組可以查看及修改。</p></li>
<li><p>無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</p></li>
</ul></td>
<td><ul>
<li><p>根據後端資料庫的可用性，您可以查看主要池所擁有的回應群組，但不能加以修改。</p></li>
<li><p>備份池所擁有的回應群組可以查看及修改。</p></li>
<li><p>無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>在回切期間的使用者體驗

當管理員將回切移至主要池時，系統會在回切期間和之後處理回應群組活動，如下表所述。

<div>


> [!NOTE]  
> 在災害復原期間，視主要池回應群組是否已匯入到備份池中而定，呼叫的行為會有所不同。 在下表中，已匯入的回應群組的參照代表在災害復原模式中，主要的池回應群組已匯入到備份池中。



</div>

### <a name="call-handling-in-failback"></a>回切中的呼叫處理

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>撥號類型或使用者動作</th>
<th>在回切期間</th>
<th>在回切完成後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>連線至代理程式的通話</p></td>
<td><ul>
<li><p>定期通話仍保持連線。</p></li>
<li><p>如果無法匯入回應群組，就不會有任何匿名通話處於此狀態。</p></li>
<li><p>在匯入的回應群組中，匿名通話仍保持連線。</p></li>
</ul></td>
<td><ul>
<li><p>定期通話仍保持連線。</p></li>
<li><p>如果無法匯入回應群組，就不會有任何匿名通話處於此狀態。</p></li>
<li><p>在匯入的回應群組中，匿名通話仍保持連線。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>尚未連線至代理程式的 [進行中] 通話</p></td>
<td><ul>
<li><p>如果無法匯入回應群組，就不會有任何通話處於此狀態。</p></li>
<li><p>在匯入的回應群組中，通話會中斷連線。</p></li>
</ul></td>
<td><ul>
<li><p>如果無法匯入回應群組，就不會有任何通話處於此狀態。</p></li>
<li><p>在匯入的回應群組中，通話會中斷連線。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>新的通話</p></td>
<td><p>呼叫會連接到主要池，但駐留在主要池中的代理程式無法到達。</p></td>
<td><p>呼叫會連接到主要池。</p></td>
</tr>
<tr class="even">
<td><p>代表回應群組的代理程式通話</p></td>
<td><p>在此階段停用功能。</p></td>
<td><p>通話成功。</p></td>
</tr>
<tr class="odd">
<td><p>[代理程式登入] 和 [代理程式資訊]</p></td>
<td><ul>
<li><p>主要池擁有的代理群組可以在代理程式主控台上查看，但代理程式無法登入。</p></li>
<li><p>備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</p></li>
<li><p>匯入的代理程式群組會顯示在代理程式主控台上，且代理程式可以登入。</p></li>
</ul></td>
<td><ul>
<li><p>主要池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</p></li>
<li><p>備份池所擁有的代理群組可以在代理程式主控台上查看，而且代理程式可以登入。</p></li>
<li><p>[匯入的代理程式群組] 不會顯示在代理程式主控台上。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>回應群組設定</p></td>
<td><ul>
<li><p>根據主要池後端資料庫的可用性，您可以查看主要池所擁有的回應群組，但不能加以修改。</p></li>
<li><p>備份池所擁有的回應群組可以查看及修改。</p></li>
<li><p>無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</p></li>
</ul></td>
<td><ul>
<li><p>主要池擁有的回應群組可以查看和修改。</p></li>
<li><p>備份池所擁有的回應群組可以查看及修改。</p></li>
<li><p>無法透過 Lync Server [控制台] 或 [回應群組設定] 工具來查看匯入的回應群組，但可以使用 Lync Server 管理命令介面 Cmdlet 進行設定。</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

