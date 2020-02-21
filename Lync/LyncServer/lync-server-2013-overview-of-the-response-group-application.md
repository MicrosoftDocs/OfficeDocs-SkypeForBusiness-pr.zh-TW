---
title: 回應群組應用程式的 Lync Server 2013： 概觀
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
ms.openlocfilehash: 007d6b21ab37aee16ae8c98b202bd3900f4dab45
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Lync Server 2013 中的回應群組應用程式概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-11_

來電者與回應群組通話時，該通話會根據群組搜尋或來電者對互動語音回應 (IVR) 問題的回答，路由傳送給代理人。 回應群組應用程式使用的標準回應群組路由方法，將呼叫路由至下一個線上專員。 通話路由方法包括序列、最長閒置時間、平行、循環配置資源及應答路由 (也就是說，所有代理人都會同時接獲每一通來電，不論他們目前是否有空)。 如果沒有代理人有空，則會將通話保留在佇列中，直到某位代理人有空。 通話保留在佇列時，來電者會聽到音樂，直到某位有空的代理人受理該通話。 如果佇列已滿，或通話在佇列中逾時，則來電者可能會聽到訊息，然後便中斷通話或將通話轉接至不同的目的地。 依系統管理員設定回應群組的方式不同，代理人受理通話時，來電者不一定會看到代理人的身分識別。 代理人得以正式方式受理通話 (表示他們必須先登入群組，才能受理路由傳送給群組的通話)，或以非正式方式受理通話 (表示他們未登入及登出群組就受理通話)。

<div>


> [!NOTE]  
> 只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。



</div>

<div>


> [!NOTE]  
> 回應群組應用程式會使用稱為配對，內部服務佇列通話，然後尋找可用的代理程式。 每一部執行回應群組應用程式的電腦執行配對服務，但只有一個符合項目進行的服務，每個 Lync 伺服器集區為作用中一次-其他是被動。 如果主動配對服務在意外中斷服務期間無法使用，則被動配對服務其中之一會變成主動配對服務。 回應群組應用程式達到最佳若要確定該通話路由傳送並佇列會繼續執行不會中斷。 但是在轉換配對服務時，所有轉接中的通話都會中斷。 例如，如果轉換是因為前端伺服器下降目前所處理的作用中配對服務，任何呼叫前端伺服器也是遺失。



</div>

在 Lync Server 2013 中，有兩個管理角色可供管理回應群組： 回應群組管理員及回應群組管理員。 回應群組管理員可以管理任何回應群組的任何層面。 回應群組管理員可管理特定層面，並僅用於回應群組，其所擁有。 新的 「 管理員 」 角色可以協助減少管理成本，因為您可以將委派有限的責任對於特定的回應群組，已啟用 Enterprise Voice 的任何使用者。

若要容納新的 「 管理員 」 角色，Lync Server 2013 回應群組應用程式會介紹受管理或未受管理的**工作流程類型**。 下表描述「已受管理」與「未受管理」回應群組內容。

### <a name="managed-and-unmanaged-response-groups"></a>受管理與未受管理回應群組

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
<td><p>未受管理</p></td>
<td><ul>
<li><p>未受管理的回應群組沒有指定的管理員。 只有回應群組管理員可以設定這些回應群組。</p></li>
<li><p>多個未受管理回應群組可共用一個佇列或代理人群組。</p></li>
<li><p>當您從舊版移轉回應群組至 Lync Server 2013 時，此類型設為未受管理。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>受管理</p></td>
<td><ul>
<li><p>回應群組管理員可以設定受管理之回應任何的群組層面。</p></li>
<li><p>回應群組管理員無法檢視或修改未明確指派給他們的回應群組。</p></li>
<li><p>回應群組管理員可以設定僅一些明確指派給他們的回應群組設定。</p></li>
<li><p>受管理的回應群組無法與其他任何受管理或未受管理的回應群組共用任何佇列或代理人群組。</p></li>
</ul></td>
</tr>
</tbody>
</table>


下表說明回應群組經理可以和指派給他們的回應群組無法執行的動作。

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
<th>無法：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>代理程式</p></li>
<li><p>歡迎訊息</p></li>
<li><p>回應群組名稱</p></li>
<li><p>說明</p></li>
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


回應群組管理員可以使用下列工具來管理其指定的回應群組。

  - Lync Server 控制台
    
    <div>
    

    > [!NOTE]  
    > 回應群組管理員只能管理回應群組設定，使用此工具。 其他 Lync Server 的設定不提供給主管。

    
    </div>

  - 回應群組設定工具

  - Lync Server 管理命令介面

回應群組比例很適合用來部門或工作群組環境 （如需詳細資訊，請參閱[Capacity planning for Lync Server 2013 中的回應群組](lync-server-2013-capacity-planning-for-response-group.md)），並可以部署在全新電話語音安裝。 它支援從 Enterprise Voice 部署和本機通信業者網路的傳入呼叫。 代理程式可以使用 Lync 2013、 Lync 2010、 Lync 2010 Attendant 或 Lync Phone Edition，才會路由傳送至他們的通話。

回應群組應用程式是企業語音元件。 當您部署企業語音時，回應群組應用程式已安裝，並自動啟動。

</div>

<span> </span>

</div>

</div>

</div>

