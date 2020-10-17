---
title: Lync Server 2013：前端伺服器、立即訊息及顯示狀態的拓撲和元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 103d03920df57023ae7dbb953beb0c426d0a43df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503750"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的拓撲和元件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-24_

立即訊息 (IM) 和目前狀態所需的元件包括：

  - 您組織的前端伺服器或 Standard Edition server。 IM 和目前狀態功能在這些伺服器上一定會啟用。

  - 負載平衡器（如果您有 Enterprise Edition 前端集區）。 如需詳細資訊，請參閱 [Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>規劃前端集區的部署

在 Lync Server 2013 中，前端集區架構已變更，這些變更會影響您應如何規劃及維護前端集區。

建議您的所有 Enterprise Edition 前端集區至少包含三部前端伺服器。 在 Lync Server 中，前端集區的架構使用分散式系統模型，而每個使用者的資料都保存在集區中的三部前端伺服器上。 如需此新架構的相關資訊，請參閱 [Lync Server 2013 中的拓撲變更](lync-server-2013-topology-changes.md)。

如果您不想部署三個 Enterprise Edition 前端伺服器並想要進行嚴重損壞修復，建議您使用 Lync Server Standard Edition，並建立具有成對備份關聯的兩個集區。 這將會提供僅含兩部伺服器的嚴重損壞修復解決方案。 如需詳細資訊，請參閱高可用性和嚴重損壞修復拓撲及功能，請參閱在 [Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>規劃前端集區的管理

針對前端集區，請遵循本節中的指導方針。

<div>

## <a name="ensuring-that-pools-are-functional"></a>確定集區運作正常

使用前端集區的新分散式模型，集區的伺服器必須執行某些號碼，集區才能正常運作。 集區有兩個遺失模式

  - 路由群組層級仲裁遺失，因為特定路由群組的副本伺服器不足。 路由群組是駐留在集區中之一組使用者的集合。 每個路由群組在集區中有三個複本：一個主要和兩個次要複本。

  - 集區層級仲裁遺失，因為集區中沒有足夠的 seed 伺服器正在執行。

<div>

## <a name="routing-group-level-quorum-loss"></a>路由群組層級仲裁遺失

第一次啟動新的前端集區時，85% 的伺服器已啟動且正在執行，這一點很重要，如下表所示。 如果有較少的伺服器正在執行，服務可能會停滯在啟動狀態，而且集區可能無法啟動。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>集區中的伺服器總數</th>
<th>第一次啟動集區時必須執行的伺服器數目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>第</p></td>
<td><p>1 </p></td>
</tr>
<tr class="even">
<td><p>個</p></td>
<td><p>個</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>個</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="odd">
<td><p>8 </p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>9 </p></td>
<td><p>7 </p></td>
</tr>
<tr class="odd">
<td><p>10 </p></td>
<td><p>8 </p></td>
</tr>
<tr class="even">
<td><p>11 </p></td>
<td><p>9 </p></td>
</tr>
<tr class="odd">
<td><p>12 </p></td>
<td><p>10 </p></td>
</tr>
</tbody>
</table>


每次後續的集區啟動時，應啟動85% 的伺服器 (，如上表) 所示。 若無法啟動此伺服器數目 (但是可以啟動足夠的伺服器，以致于您不會在集區層級仲裁遺失) ，您可以使用 **Reset-CsPoolRegistrarState – ResetType QuorumLossRecovery** Cmdlet，讓集區能夠從此路由群組層級仲裁遺失中復原，並取得進展。 如需如何使用此 Cmdlet 的詳細資訊，請參閱 [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)。

<div>


> [!NOTE]  
> 由於 Lync Server 使用主要 SQL 資料庫做為見證，所以如果您關閉主資料庫並切換至鏡像副本，並關閉足夠的前端伺服器，以便根據上表上的表格執行不夠的狀態，則整個集區將會關閉。 如需詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/?linkid=393672">資料庫鏡像見證</A>。



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>集區層級仲裁遺失

若要讓前端集區能夠運作，它無法在集區層級仲裁遺失。 如果執行中的伺服器數目低於功能層級，如下表所示，集區中的剩餘伺服器將停止所有的 Lync Server 服務。 請注意，下表中的數位會假定集區中的後端伺服器正在執行。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>集區中的前端伺服器總數</th>
<th>集區執行運作所需的伺服器數目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>第</p></td>
<td><p>1 </p></td>
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
<td><p>7 </p></td>
<td><p>任何4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>前7部伺服器的任何4個</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>前9部伺服器的任意5個</p></td>
</tr>
</tbody>
</table>


在上表中，第一次啟動集區時，"first servers" 是第一次啟動的伺服器。 若要判斷這些伺服器，您可以使用具有 **– PoolFqdn**選項的**Get-CsComputer** Cmdlet。 此 Cmdlet 會以拓撲中顯示的順序顯示伺服器，而位於清單頂端的伺服器是第一部伺服器。

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>具有兩部前端伺服器的前端集區

建議您不要部署只包含兩部前端伺服器的前端集區。 若您曾經需要部署此類集區，請遵循下列指導方針：

  - 如果兩部前端伺服器之一停機，您應該盡可能將失敗的伺服器重新備份。 同樣地，如果您需要升級兩部伺服器中的其中一部，請在升級完成後立即將其移回線上。

  - 若由於某些原因，您必須同時讓這兩部伺服器停機，請在完成集區的停機時間時，執行下列動作：
    
      - 最佳作法是同時重新開機這兩部前端伺服器。
    
      - 若兩部伺服器不能同時重新開機，您應該以相反順序重新開機它們。
    
      - 如果您無法以該順序重新備份，請在備份組區之前，先使用下列 Cmdlet：。
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>確定集區運作的其他步驟

您應注意其他一些因素，以確保前端集區仍可運作。

  - 當您第一次將使用者移至集區時，請確定至少有三部前端伺服器正在執行。

  - 如果您在此集區與其他集區之間建立配對關係，以進行嚴重損壞修復，則必須確定此集區在一段時間內有三部前端伺服器同時執行，才能正確地同步處理資料與備份組區。 如需有關集區配對和嚴重損壞修復功能的詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>改善集區升級的可靠性

當您需要升級或修補前端集區中的伺服器時，請遵循在 [Lync Server 2013 的升級或更新前端伺服器中](lync-server-2013-upgrade-or-update-front-end-servers.md)顯示的工作流程，以及下列指導方針：

  - 當您從一個升級網域移至另一個升級網域以進行升級時 (請在 [升級或更新 Lync Server 2013) 中的前端伺服器](lync-server-2013-upgrade-or-update-front-end-servers.md) 之後，使用 **Get-CsPoolUpgradeReadinessState** Cmdlet 並檢查 [就緒] 狀態。 在每個升級網域達到「就緒」狀態時，新增20分鐘的等待時間，可使升級更為可靠。 如果在此20分鐘內 **未準備好** ，請重新開機20分鐘計時器。 此外，您也可以在啟動20分鐘的間隔前後執行 **Get-CsPoolFabricState** Cmdlet，並確定路由群組的 primaries 和輔助副本沒有任何變更。

  - 若最後一次修補的升級網域中的任何伺服器都停滯或未重新開機，請勿移至下一個升級網域。 如果升級內的任何伺服器都無法啟動，也會套用這種情況。 請執行 **Get-CsPoolFabricState** ，確定所有路由群組都有主要和至少一個次要;這會確認所有使用者是否都有服務。

  - 如果有些使用者有服務，但其他使用者卻沒有服務，請以– Verbose 選項執行 **Get-CsPoolFabricState** ，檢查是否有遺失複本的路由群組。 請不要重新開機整個集區做為第一個疑難排解步驟。 如需此 Cmdlet 的詳細資訊，請參閱 [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)。

  - 請確定已關閉事件檢視器或效能監視器視窗的所有實例，以進行 windows fabric 安裝/卸載。

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>變更前端集區的設定

每當您將前端伺服器新增至集區，或從集區中移除它們，然後發佈新的拓撲時，請遵循下列指導方針：

  - 發行新的拓撲之後，您必須重新開機集區中的每一部前端伺服器。 一次重新開機一個。

  - 如果在設定變更期間整個集區都已停機，請在發佈新的拓撲之後，執行下列 Cmdlet：
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

如果前端伺服器失敗且不太可能取代一天以上，請從拓撲中移除伺服器。 將新的前端伺服器新增至拓撲，當它再次可用時。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

