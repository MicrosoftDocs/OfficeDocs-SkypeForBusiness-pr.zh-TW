---
title: Lync Server 2013：回應群組應用程式的概覽
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
ms.openlocfilehash: 2b01181296a42f786a4739b5ec59d775212baaf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Lync Server 2013 中的回應群組應用程式概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

當來電者呼叫回應群組時，通話會根據查尋群組或來電者對互動式語音回應（IVR）問題的答案來傳送給代理程式。 回應群組應用程式會使用標準的回應群組路由方法，將呼叫路由至下一個可用的代理程式。 呼叫路由方法包括串列、最長閒置、並行、迴圈，以及助理路由（也就是，所有的代理程式都是在每次撥入通話時呼叫，不論其目前的狀態為何）。 如果沒有可用的代理，通話會一直保留在佇列中，直到有可用的代理程式。 在佇列中，來電者會聽到音樂，直到可用的代理程式接受通話。 如果佇列已滿，或通話在佇列中超時，來電者可能會聽到訊息，然後中斷連線或傳送到不同的目的地。 當代理程式接受來電時，呼叫者可能也可能無法看到代理人的身分識別，視系統管理員設定回應群組的方式而定。 Agent 可以是正式的，這表示他們必須先登入群組，才能接受路由到群組的呼叫，或者是非正式的，這表示它們不會登入和登出群組以接受通話。

<div>


> [!NOTE]  
> 只有內部部署使用者可以使用代理程式。 如果代理程式是從內部部署移至線上，回應群組呼叫將不會路由至該代理程式。



</div>

<div>


> [!NOTE]  
> 回應群組應用程式使用名為 [相符] 的內部服務來排隊通話，並尋找可用的代理程式。 每個執行回應群組應用程式的電腦都會執行相符的服務，但一次只能有一個相符的服務是作用中的每個 Lync Server pool; 其他是被動的。 如果在未計畫的停機期間，使用中的 [相符] 使服務變為無法使用，其中一個被動的相符，就會變成作用中。 回應群組應用程式最能確保呼叫路由和佇列繼續不間斷地進行。 不過，當相符的服務轉換發生時，任何在該時間傳輸的呼叫都會遺失。 例如，如果您的轉換是由於前端伺服器即將停機而引起，則目前由作用中的 Match 所處理的任何呼叫都會在該前端伺服器上執行的服務也會遺失。



</div>

在 Lync Server 2013 中，有兩個管理角色可用來管理回應群組： [回應群組管理員] 和 [回應群組管理員]。 回應群組管理員可以管理任何回應群組的任何方面。 回應群組管理員只能管理特定的部分，而且只能管理自己擁有的回應群組。 新的管理員角色可協助降低管理成本，因為您可以將特定回應群組的有限職責委派給任何已啟用企業語音的使用者。

為了適應新的管理員角色，Lync Server 2013 回應群組應用程式引入了託管或非託管的**工作流程類型**。 下表說明受管理和未受管理的回應群組。

### <a name="managed-and-unmanaged-response-groups"></a>受管理和未受管理的回應群組

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>回應群組類型</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>管</p></td>
<td><ul>
<li><p>未受管理的回應群組沒有已指派的管理員。 只有回應群組管理員可以設定這些回應群組。</p></li>
<li><p>多個未受管理的回應群組可以共用 [佇列] 或 [代理] 群組。</p></li>
<li><p>當您將回應群組從先前的版本遷移至 Lync Server 2013 時，該類型會設定為 [未管理]。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>被</p></td>
<td><ul>
<li><p>回應群組管理員可以設定受管理回應群組的任何方面。</p></li>
<li><p>回應群組管理員無法查看或修改未明確指派給他們的回應群組。</p></li>
<li><p>回應群組管理員只能針對明確指派給他們的回應群組設定部分設定。</p></li>
<li><p>受管理的回應群組無法與任何其他回應群組、託管或未受管理的人共用任何佇列或代理群組。</p></li>
</ul></td>
</tr>
</tbody>
</table>


下表說明回應群組管理員可以對指派給他們的回應群組執行哪些動作。

### <a name="response-group-manager-capabilities"></a>回應群組管理員功能

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>可以設定：</th>
<th>可以建立、刪除或設定：</th>
<th>不</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>代理程式</p></li>
<li><p>歡迎訊息</p></li>
<li><p>回應群組名稱</p></li>
<li><p>說明</p></li>
<li><p>顯示數位</p></li>
<li><p>商務時間</p></li>
<li><p>等候音樂</p></li>
<li><p>狀態（有效/非使用中）</p></li>
<li><p>查尋群組工作流程或互動式語音回應（IVR）工作流程</p></li>
</ul></td>
<td><ul>
<li><p>代理群組</p></li>
<li><p>佇列</p></li>
<li><p>假日集</p></li>
</ul></td>
<td><ul>
<li><p>建立或刪除任何類型的工作流程</p></li>
<li><p>修改核心回應群組設定，例如： <strong>SIP URI</strong>、<strong>電話號碼</strong>或<strong>工作流程類型</strong>。</p></li>
</ul></td>
</tr>
</tbody>
</table>


回應群組管理員可以使用下列工具來管理其指定的回應群組。

  - Lync Server 控制台
    
    <div>
    

    > [!NOTE]  
    > 回應群組管理員只能使用此工具管理回應群組設定。 管理員無法使用其他 Lync Server 設定。

    
    </div>

  - 回應群組設定工具

  - Lync Server 管理命令介面

回應群組很適合部門或工作組環境（如需詳細資訊，請參閱[Lync Server 2013 中的 [回應] 群組容量規劃](lync-server-2013-capacity-planning-for-response-group.md)），而且可以在全新的電話安裝中部署。 它支援來自企業語音部署和來自本機電信公司網路的傳入通話。 代理程式可以使用 Lync 2013、Lync 2010、Lync 2010，或 Lync Phone Edition，讓通話傳送給他們。

回應群組應用程式是企業語音的元件。 當您部署企業語音時，系統會自動安裝並啟用回應群組應用程式。

</div>

<span> </span>

</div>

</div>

</div>

