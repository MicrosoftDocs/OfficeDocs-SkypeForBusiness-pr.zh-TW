---
title: Lync Server 2013：前端伺服器、立即訊息及顯示狀態的拓撲和元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc44790fc9584676cdd10305085b23bd5e99299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的拓撲和元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-24_

立即訊息（IM）與目前狀態所需的元件如下：

  - 貴組織的前端伺服器或標準版伺服器。 在這些伺服器上，系統永遠都能啟用 IM 和目前狀態功能。

  - [負載平衡器] （如果您有企業版的 [前端] 池）。 如需詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>規劃頂層端池的部署

在 Lync Server 2013 中，前端池架構已變更，這些變更會影響您應該如何規劃及維護您的前端池。

我們建議您所有的企業版前端池都包含至少三個前端伺服器。 在 Lync Server 中，前端池的架構使用分散式系統模型，每個使用者的資料都會保留在池中的三個前端伺服器上。 如需此新架構的詳細資訊，請參閱[Lync Server 2013 中的拓撲變更](lync-server-2013-topology-changes.md)。

如果您不想部署三個企業版前端伺服器並想要進行災難復原，我們建議您使用 Lync Server 標準版，並建立具有成對備份關聯的兩個池。 這將會提供只包含兩個伺服器的災害復原方案。 如需詳細資訊，請參閱高可用性與災害復原拓撲及功能，請參閱[在 Lync Server 2013 中規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原。

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>規劃頂層端池的管理

針對 [前端] 池，請遵循本節中的指導方針。

<div>

## <a name="ensuring-that-pools-are-functional"></a>確保池運作正常

使用新的 [前端] 池分散式模型，必須執行一些池伺服器的特定編號，才能讓該池正常運作。 有兩種池的遺失模式

  - 路由群組層級仲裁損失，因為特定路由群組沒有足夠的複本伺服器。 路由群組是駐留在池中的一組使用者集合。 每個路由群組在該池中都有三個複本：一個主要和兩個次要資料庫。

  - 當池中沒有足夠的種子伺服器執行時，會導致池層級仲裁遺失。

<div>

## <a name="routing-group-level-quorum-loss"></a>路由群組層級仲裁損失

第一次開始新的前端池時，85% 的伺服器必須正常運作，如下表所示。 如果有較少的伺服器正在執行，服務可能會停滯在起始狀態，而且該池可能無法啟動。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中的伺服器總數</th>
<th>必須執行才能第一次啟動該池的伺服器數量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pplx-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>500</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>utf-7</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>型</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>9</p></td>
<td><p>utf-7</p></td>
</tr>
<tr class="odd">
<td><p>第</p></td>
<td><p>型</p></td>
</tr>
<tr class="even">
<td><p>11</p></td>
<td><p>9</p></td>
</tr>
<tr class="odd">
<td><p>之間</p></td>
<td><p>第</p></td>
</tr>
</tbody>
</table>


每次啟動該池之後，伺服器的85% 應該會啟動（如前面的資料表所示）。 如果此伺服器數無法啟動（但可以啟動足夠的伺服器，因此您不在池層級的仲裁遺失），您可以使用**Reset-CsPoolRegistrarState-ResetType QuorumLossRecovery** Cmdlet，讓該池能夠從這種路由群組層級的仲裁遺失中復原並產生進度。 如需如何使用此 Cmdlet 的詳細資訊，請參閱[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)。

<div>


> [!NOTE]  
> 因為 Lync Server 會使用主要的 SQL 資料庫做為見證，所以如果您關閉主資料庫並切換到鏡像複本，然後關閉足夠的前端伺服器，以使其根據前面的資料表執行時，整個池都會向下移動。 如需詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/?linkid=393672">資料庫鏡像見證</A>。



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>池層級仲裁損失

若要讓前臺端池完全正常運作，它不能在 pool 階層的仲裁遺失中。 如果執行中的伺服器數目低於功能層級，如下表所示，池中剩餘的伺服器將停止所有 Lync Server 服務。 請注意，下表中的數位假設池中的後端伺服器正在執行。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>池中的前端伺服器總數</th>
<th>必須執行才能供擁有池中運作的伺服器數量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pplx-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>任何2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>任何3</p></td>
</tr>
<tr class="even">
<td><p>utf-7</p></td>
<td><p>任何4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>前7個伺服器中的任何4個</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>前9個伺服器中的任何5個</p></td>
</tr>
</tbody>
</table>


在前一個表格中，「第一台伺服器」是指第一次啟動該池時所發生的伺服器。 若要判斷這些伺服器，您可以使用**CsComputer** Cmdlet 和 **– PoolFqdn**選項。 這個 Cmdlet 會以拓撲結構中出現的順序顯示伺服器，而清單頂端的是第一個伺服器。

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>具有兩個前端伺服器的前端池

我們不建議您部署只包含兩個前端伺服器的 [前端] 池。 如果您需要部署此類池，請遵循下列指導方針：

  - 如果兩個前端伺服器中有一個是關閉的，您應該儘快將失敗的伺服器移回原位。 同樣地，如果您需要升級兩個伺服器的其中一個，請在升級完成後立即將它重新連線。

  - 如果您出於某種原因，您需要同時將兩個伺服器移至一段時間，請在池的停機時間結束時，執行下列動作：
    
      - 最佳做法是同時重新開機這兩個前端伺服器。
    
      - 如果兩個伺服器不能同時重新開機，您應該以相反順序將這些伺服器放回它們的順序。
    
      - 如果您無法以這種順序傳回它們，請先使用下列 Cmdlet，然後再重新開機該池：。
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>確定池運作的其他步驟

您應該留意幾個其他因素，以確保您的前端池仍能正常運作。

  - 當您第一次將使用者移至該池時，請確定至少有三個前端伺服器正在執行。

  - 如果您在這個池與另一個用來進行災害復原的池之間建立配對關係，則必須確定此池中有三個前端伺服器同時執行，才能正確同步處理包含備份池的資料。 如需有關池配對及災害復原功能的詳細資訊，請參閱[在 Lync Server 2013 中規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原。

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>改善池升級的可靠性

當您需要升級或修補前端池中的伺服器時，請遵循在[Lync Server 2013 升級或更新前端伺服器中](lync-server-2013-upgrade-or-update-front-end-servers.md)顯示的工作流程，以及下列指導方針：

  - 當您從一個升級網域移到另一個升級網域進行升級時（遵循在[Lync Server 2013 中升級或更新前端伺服器](lync-server-2013-upgrade-or-update-front-end-servers.md)的工作流程），您將會使用**CsPoolUpgradeReadinessState** Cmdlet 並檢查 [就緒] 的狀態。 在每個升級網域達到 [就緒] 後，在每個升級網域之間加上20分鐘的等待，即可使升級更加可靠。 如果在此20分鐘內**未準備好**，請重新開機20分鐘計時器。 此外，您可以在啟動20分鐘間隔之前和之後執行**CsPoolFabricState** Cmdlet，並確定路由群組的 primaries 和輔助副本沒有任何變更。

  - 如果在最後一次補丁的升級網域中有任何伺服器停滯或未重新開機，請勿移至下一個升級網域。 如果升級中的任何伺服器無法啟動，這也適用。 請執行**CsPoolFabricState** ，確定所有路由群組都有主要及至少一個副，這將會確認所有使用者是否都有服務。

  - 如果有些使用者有服務且其他人不具備，請執行**CsPoolFabricState**與-Verbose 選項，以檢查是否有遺失複本的路由群組。 請勿重新開機整個池做為第一個疑難排解步驟。 如需此 Cmdlet 的詳細資訊，請參閱[CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)。

  - 請確定已關閉事件檢視器或效能監視器視窗的所有實例，以供 windows fabric 安裝/卸載。

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>變更前端池的設定

每當您將前端伺服器新增到某個池，或從池中移除該伺服器，然後發佈新的拓撲時，請遵循下列指導方針：

  - 發佈新拓撲之後，您必須重新開機池中的每個前端伺服器。 一次重新開機一個。

  - 如果在設定變更期間，整個池都已停機，請在發佈新拓撲之後，執行下列 Cmdlet：
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

如果前端伺服器發生故障，且不太可能被取代數天以上，請從拓撲中移除伺服器。 當新的前端伺服器再次可用時，將它新增到拓撲。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

