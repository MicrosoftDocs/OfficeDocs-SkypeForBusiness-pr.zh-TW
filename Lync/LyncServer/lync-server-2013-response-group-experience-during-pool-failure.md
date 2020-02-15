---
title: 集區失敗期間的 Lync Server 2013 回應群組經驗
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
ms.openlocfilehash: 0e7867af15eb5e8824562eb03244280cfbc84f7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Lync Server 2013 中遇到集區失敗期間的回應群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-30_

本節詳細說明回應群組活動在下列階段所受到的影響：

  - 主要集區中發生中斷，但尚未起始容錯移轉。

  - 服務已容錯移轉至備用集區。

  - 服務已容錯回復至主要集區。

<div>

## <a name="user-experience-when-outage-occurs"></a>發生中斷時的使用者體驗

當集區或網站發生中斷，但系統管理員尚未起始容錯移轉時，回應群組活動的處理方式如下表所述。

<div>


> [!NOTE]  
> 在災害復原期間，通話行為會視主要集區回應群組是否已在復原期間匯入備份集區而有所不同。在下表中，匯入的回應群組參考代表主要集區回應群組已在災害復原模式期間匯入備份集區。



</div>

### <a name="outage-occurs"></a>發生中斷

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通話類型或使用者動作</th>
<th>中斷期間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>連線至代理人的通話</p></td>
<td><ul>
<li><p>一般通話保持連線。</p></li>
<li><p>匿名通話中斷連線。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>進行中的通話尚未連線至代理</p></td>
<td><p>通話中斷連線。</p></td>
</tr>
<tr class="odd">
<td><p>新通話</p></td>
<td><ul>
<li><p>通話中斷連線。</p></li>
<li><p>如果已匯入回應群組，通話會連線至備份集區，但是無法與位於主要集區的代理人連線。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>代表回應群組的代理人通話</p></td>
<td><p>功能在此階段停用。</p></td>
</tr>
<tr class="odd">
<td><p>代理人登入與代理人資訊</p></td>
<td><ul>
<li><p>由主要集區擁有的代理群組可在代理主控台上檢視，但代理無法登入。</p></li>
<li><p>備用集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</p></li>
<li><p>匯入的代理人群組未顯示在代理人主控台上。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>回應群組設定</p></td>
<td><ul>
<li><p>主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</p></li>
<li><p>備份集區所擁有的回應群組可以檢視及修改。</p></li>
<li><p>匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>容錯移轉期間的使用者體驗

當系統管理員叫用容錯移轉至備份集區時，回應群組活動會在容錯移轉期間和之後處理，如下表所述。第一欄說明可能發生的活動類型。中間一欄說明各活動在容錯移轉至備份集區的短時間內的處理方式。最後一欄說明在容錯移轉程序完成之後以及備份集區代替主要集區時，這段期間活動的處理方式。

<div>


> [!NOTE]  
> 在災害復原期間，通話行為會視主要集區回應群組是否已在復原期間匯入備份集區而有所不同。在下表中，匯入的回應群組參考代表主要集區回應群組已在災害復原模式期間匯入備份集區。



</div>

### <a name="failover-is-initiated"></a>已起始容錯移轉

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>通話類型或使用者動作</th>
<th>容錯移轉期間</th>
<th>容錯移轉完成之後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>連線至代理人的通話</p></td>
<td><ul>
<li><p>一般通話保持連線。</p></li>
<li><p>匿名通話中斷連線。</p></li>
</ul></td>
<td><ul>
<li><p>一般通話保持連線。</p></li>
<li><p>對於匯入的回應群組，已連至備份集區的匿名通話會保持連線。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>進行中的通話尚未連線至代理</p></td>
<td><p>通話中斷連線。</p></td>
<td><ul>
<li><p>如果沒有匯入回應群組，這個階段就沒有通話。</p></li>
<li><p>對於匯入的回應群組，已連至備份集區的通話會保持連線。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>新通話</p></td>
<td><ul>
<li><p>通話中斷連線。</p></li>
<li><p>對於匯入的回應群組，通話會連線至備份集區，但是無法與位於主要集區的代理人連線。</p></li>
</ul></td>
<td><ul>
<li><p>如果沒有匯入回應群組，通話會中斷連線。</p></li>
<li><p>對於匯入的回應群組，通話會連線至備份集區。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>代表回應群組的代理人通話</p></td>
<td><p>功能在此階段停用</p></td>
<td><ul>
<li><p>如果沒有匯入回應群組，通話會失敗。</p></li>
<li><p>對於匯入的回應群組，通話成功。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>代理登入與代理資訊</p></td>
<td><ul>
<li><p>由主要集區擁有的代理群組可在代理主控台上檢視，但代理無法登入。</p></li>
<li><p>備用集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</p></li>
<li><p>匯入的代理人群組顯示在代理人主控台上，且代理人可以登入。</p></li>
</ul></td>
<td><ul>
<li><p>主要集區所擁有的代理人群組可在代理人主控台上檢視，但代理人無法登入。</p></li>
<li><p>備用集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</p></li>
<li><p>匯入的代理人群組顯示在代理人主控台上，且代理人可以登入。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>回應群組設定</p></td>
<td><ul>
<li><p>主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</p></li>
<li><p>備份集區所擁有的回應群組可以檢視及修改。</p></li>
<li><p>匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</p></li>
</ul></td>
<td><ul>
<li><p>主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</p></li>
<li><p>備份集區所擁有的回應群組可以檢視及修改。</p></li>
<li><p>匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>容錯回復期間的使用者體驗

當系統管理員叫用容錯回復至主要集區時，回應群組活動會在容錯回復期間和之後處理，如下表所述。

<div>


> [!NOTE]  
> 在災害復原期間，通話行為會視主要集區回應群組是否已在復原期間匯入備份集區而有所不同。在下表中，匯入的回應群組參考代表主要集區回應群組已在災害復原模式期間匯入備份集區。



</div>

### <a name="call-handling-in-failback"></a>容錯回復時的通話處理

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>通話類型或使用者動作</th>
<th>容錯回復期間</th>
<th>容錯回復完成之後</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>連線至代理人的通話</p></td>
<td><ul>
<li><p>一般通話保持連線。</p></li>
<li><p>如果沒有匯入回應群組，就沒有匿名通話處於此狀態。</p></li>
<li><p>對於匯入的回應群組，匿名通話會保持連線。</p></li>
</ul></td>
<td><ul>
<li><p>一般通話保持連線。</p></li>
<li><p>如果沒有匯入回應群組，就沒有匿名通話處於此狀態。</p></li>
<li><p>對於匯入的回應群組，匿名通話會保持連線。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>進行中的通話尚未連線至代理人</p></td>
<td><ul>
<li><p>如果沒有匯入回應群組，就沒有通話處於此狀態。</p></li>
<li><p>對於匯入的回應群組，通話將會中斷連線。</p></li>
</ul></td>
<td><ul>
<li><p>如果沒有匯入回應群組，就沒有通話處於此狀態。</p></li>
<li><p>對於匯入的回應群組，通話將會中斷連線。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>新通話</p></td>
<td><p>通話會連線至主要集區，但是無法與位於主要集區的代理人連線。</p></td>
<td><p>通話連線至主要集區。</p></td>
</tr>
<tr class="even">
<td><p>代表回應群組的代理人通話</p></td>
<td><p>功能在此階段停用。</p></td>
<td><p>通話成功。</p></td>
</tr>
<tr class="odd">
<td><p>代理人登入與代理人資訊</p></td>
<td><ul>
<li><p>由主要集區擁有的代理群組可在代理主控台上檢視，但代理無法登入。</p></li>
<li><p>備用集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</p></li>
<li><p>匯入的代理人群組顯示在代理人主控台上，且代理人可以登入。</p></li>
</ul></td>
<td><ul>
<li><p>主要集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</p></li>
<li><p>備份集區所擁有的代理人群組可在代理人主控台上檢視，且代理人可以登入。</p></li>
<li><p>匯入的代理人群組未顯示在代理人主控台上。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>回應群組設定</p></td>
<td><ul>
<li><p>主要集區所擁有的回應群組可以檢視，視主要集區後端資料庫的可用性而定，但無法修改。</p></li>
<li><p>備份集區所擁有的回應群組可以檢視及修改。</p></li>
<li><p>匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</p></li>
</ul></td>
<td><ul>
<li><p>主要集區所擁有的回應群組可以檢視及修改。</p></li>
<li><p>備份集區所擁有的回應群組可以檢視及修改。</p></li>
<li><p>匯入的回應群組無法與 Lync Server Control Panel 或 [回應群組組態工具] 中，檢視，但可使用 Lync Server 管理命令介面指令程式來設定。</p></li>
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

