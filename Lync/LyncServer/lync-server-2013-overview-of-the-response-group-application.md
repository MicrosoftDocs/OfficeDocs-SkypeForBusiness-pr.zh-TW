---
title: Lync Server 2013：回應群組應用程式的簡介
description: Lync Server 2013：回應群組應用程式的簡介。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763a64adcf0eaf43e8f98a49cd850882ca9c91c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552379"
---
# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Lync Server 2013 的回應群組應用程式概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

來電者與回應群組通話時，該通話會根據群組搜尋或來電者對互動語音回應 (IVR) 問題的回答，路由傳送給代理人。 回應群組應用程式會使用標準回應群組路由方法，將通話路由傳送至下一個可用的代理程式。 通話路由方法包括序列、最長閒置時間、平行、循環配置資源及應答路由 (也就是說，所有代理人都會同時接獲每一通來電，不論他們目前是否有空)。 如果沒有代理人有空，則會將通話保留在佇列中，直到某位代理人有空。 通話保留在佇列時，來電者會聽到音樂，直到某位有空的代理人受理該通話。 如果佇列已滿，或通話在佇列中逾時，則來電者可能會聽到訊息，然後便中斷通話或將通話轉接至不同的目的地。 依系統管理員設定回應群組的方式不同，代理人受理通話時，來電者不一定會看到代理人的身分識別。 代理人得以正式方式受理通話 (表示他們必須先登入群組，才能受理路由傳送給群組的通話)，或以非正式方式受理通話 (表示他們未登入及登出群組就受理通話)。

<div>


> [!NOTE]  
> 只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。



</div>

<div>


> [!NOTE]  
> 回應群組應用程式使用稱為「符合」的內部服務，以佇列通話並尋找可用的代理程式。 每一部執行回應群組應用程式的電腦都會執行相符服務，但是一次只能有一個符合每個 Lync 伺服器集區的服務，另一個是被動。 如果主動配對服務在意外中斷服務期間無法使用，則被動配對服務其中之一會變成主動配對服務。 回應群組應用程式會盡力確保通話路由和佇列繼續不間斷地繼續進行。 但是在轉換配對服務時，所有轉接中的通話都會中斷。 例如，如果轉換是由於前端伺服器即將停機，則目前正由使用中的相符服務所處理的所有呼叫都會遺失該前端伺服器上的服務。



</div>

在 Lync Server 2013 中，有兩個管理角色可用於管理回應群組：回應群組管理員及回應群組管理員。 回應群組管理員可以管理任何回應群組的任何方面。 回應群組管理員只可管理特定的部分，而且只可管理其擁有的回應群組。 新的管理員角色可協助減少管理成本，因為您可以將特定回應群組的有限責任委派給已啟用 Enterprise Voice 的任何使用者。

為了容納新的管理員角色，Lync Server 2013 回應群組應用程式引入了 Managed 或非管理 **工作流程類型** 。 下表描述「已受管理」與「未受管理」回應群組內容。

### <a name="managed-and-unmanaged-response-groups"></a>受管理與未受管理回應群組

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>回應群組類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>非 託管</p></td>
<td><ul>
<li><p>未受管理的回應群組沒有指定的管理員。 只有回應群組管理員可以設定這些回應群組。</p></li>
<li><p>多個未受管理回應群組可共用一個佇列或代理人群組。</p></li>
<li><p>當您將回應群組從先前版本遷移至 Lync Server 2013 時，此類型會設定為 [未管理]。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>受管理</p></td>
<td><ul>
<li><p>回應群組管理員可以設定受管理回應群組的任何方面。</p></li>
<li><p>回應群組管理員無法查看或修改未明確指派給他們的回應群組。</p></li>
<li><p>回應群組管理員可以只為明確指派給他們的回應群組設定部分設定。</p></li>
<li><p>受管理的回應群組無法與其他任何受管理或未受管理的回應群組共用任何佇列或代理人群組。</p></li>
</ul></td>
</tr>
</tbody>
</table>


下表說明回應群組管理員可對指派給他們的回應群組執行和無法執行的動作。

### <a name="response-group-manager-capabilities"></a>回應群組管理員功能

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>可設定：</th>
<th>可建立、刪除或設定：</th>
<th>不能：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agents</p></li>
<li><p>歡迎訊息</p></li>
<li><p>回應群組名稱</p></li>
<li><p>描述</p></li>
<li><p>顯示號碼</p></li>
<li><p>營業時間</p></li>
<li><p>保留音樂</p></li>
<li><p>狀態 (使用中/非使用中)</p></li>
<li><p>群組搜尋工作流程或互動語音回應 (IVR) 工作流程</p></li>
</ul></td>
<td><ul>
<li><p>代理人群組</p></li>
<li><p>佇列</p></li>
<li><p>假日集</p></li>
</ul></td>
<td><ul>
<li><p>建立或刪除任何工作流程類型</p></li>
<li><p>修改核心回應群組設定，例如：<strong>[SIP URI]</strong>、<strong>[電話號碼]</strong> 或 <strong>[工作流程類型]</strong>。</p></li>
</ul></td>
</tr>
</tbody>
</table>


回應群組管理員可使用下列工具來管理其指定的回應群組。

  - Lync Server 控制台
    
    <div>
    

    > [!NOTE]  
    > 回應群組管理員只能使用此工具來管理回應群組設定。 其他 Lync Server 設定無法供管理員使用。

    
    </div>

  - 回應群組設定工具

  - Lync Server 管理命令介面

回應群組可非常適合部門或工作組環境 (如需詳細資訊，請參閱 [在 Lync Server 2013) 中規劃回應群組的容量](lync-server-2013-capacity-planning-for-response-group.md) ，而且可以部署全新的電話語音安裝。 它支援來自 Enterprise Voice 部署和本機電信公司網路的撥入電話。 代理程式可以使用 Lync 2013、Lync 2010、Lync 2010 語音應答或 Lync Phone Edition，將通話路由傳送給他們。

回應群組應用程式是 Enterprise Voice 的元件。 當您部署企業語音時，會自動安裝及啟用回應群組應用程式。

</div>

<span> </span>

</div>

</div>

</div>

