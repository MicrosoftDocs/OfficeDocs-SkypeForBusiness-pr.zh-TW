---
title: Lync Server 2013：規劃回應群組災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3a196a258198fe0bc65b533841544decd96aa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中規劃回應群組災害復原

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

本節將說明一些針對災難復原準備回應群組的方法，並提供災害復原程式的概覽。

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>準備回應群組災害復原

當您準備及執行災害復原程式時，請記住下列事項。

<div>


> [!NOTE]  
> 在共存環境中，本檔中所述的災難復原程式只支援 Lync Server 2013 回應群組。



</div>

  - 在您進行容量規劃時規劃災害復原。 針對災害復原容量，配對池中的每個池都應該能夠處理兩個池中所有回應群組的工作量。 如需回應群組容量規劃的詳細資料，請參閱[Lync Server 2013 中的 [回應] 群組容量規劃](lync-server-2013-capacity-planning-for-response-group.md)。

  - 使用本文所述的 export 程式，在您部署回應群組應用程式的所有前端池中，定期執行所有回應群組設定的一般備份複本。 如需詳細資訊，請參閱[Lync Server 2013 中的回應群組災害復原程式](lync-server-2013-response-group-disaster-recovery-procedures.md)。 將備份複本保留在安全的位置。

  - 針對您用於回應群組應用程式的所有原始音訊檔案，保留一個單獨的備份複本，包括任何錄製和音樂保留中的檔案。 將備份檔案保留在安全的位置。

  - 針對 Lync Server 2013 災害復原，所有回應群組設定在您的部署中都必須有唯一的名稱。 此需求適用于工作流程、[佇列]、[代理群組]、[假日集] 和 [工作時間]。 當主要和備份池仍在使用中時，以及在您需要啟動任何容錯移轉程式之前，您應該確認符合此需求。 如果您在將回應群組資料匯入到備份區時遇到名稱衝突，匯入就會失敗。 若要完成匯入及容錯移轉程式，您必須先重新命名備份池中的回應群組物件，或使用**CsRgsConfiguration** Cmdlet 和– ResolveNameConflicts 參數來解決名稱衝突，方法是將唯一識別號碼附加至回應群組物件，以自動解決衝突。

  - 一般來說，我們建議您執行每日備份，但如果您有大量的變更，您可能會想要排程更頻繁的備份。 災難事件中可能會遺失的資訊量，取決於備份頻率，以及變更的頻率與數量。

  - 您可以在發生災難或容錯移轉作業之前，將回應群組匯入到備份池。 快速匯入回應群組會減少停機時間，因為呼叫傳送至備份池之後，就可以在備份池中還原 Lync Server 回應群組服務。
    
    <div>
    

    > [!NOTE]  
    > 在容錯移轉完成之前，回應群組應用程式無法到達任何駐留在非作用中的池中的代理程式。 在此期間，回應群組應用程式會處理呼叫，就好像這些代理無法使用一樣。

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>回應群組災害復原程式

在發生災難的情況下，您可以使用下列其中一種恢復方法來復原回應群組：

  - 容錯移轉到備份池，然後將容錯回復回原始池。

  - 容錯移轉到備份池中，使用不同的完整功能變數名稱（FQDN）建立新的池，然後將回應群組匯入新的池中。

在災害復原的容錯移轉階段，回應群組位於多個池中： [主要] 池中（即無法使用）及 [備份] 池中。 兩個彙集中的回應群組都有相同的名稱和相同的擁有者（主要池），但它們擁有不同的父項。

當您使用不同的 FQDN 建立新的池來復原時，您必須將新的池指派為在您匯入時將它指派給回應群組的擁有者。 回應群組的擁有者仍會保留在原始池中，除非或在您明確地重新指派擁有權的情況下，將-OverwriteOwner 參數與**Import CsRgsConfiguration** Cmdlet 結合使用。

<div>


> [!NOTE]  
> 如果您在復原期間重建池（亦即回應群組資料庫為空白），無論您是否使用相同的 FQDN，您也必須使用– OverwriteOwner 參數。 如果您沒有重建該池，就不需要使用– OverwriteOwner 參數，但只要將回應群組匯入主要的池中，就可以使用這個參數。



</div>

每個 pool 只能定義一組應用層回應群組設定設定。 這些設定包括預設的 [隨用音樂保留] 設定、預設的 [音樂保留] 音訊檔案、[代理程式 ringback 寬限期]，以及 [通話內容] 設定。 若要查看這些設定，請執行**CsRgsConfiguration** Cmdlet。 如需**CsRgsConfiguration** Cmdlet 的詳細資訊，請參閱[CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)。

您可以使用**CsRgsConfiguration** Cmdlet 和– ReplaceExistingSettings 參數，將這些應用程式層級的設定從一個池中轉移到另一個，但這樣做會覆寫目的地池中的設定。

<div>


> [!IMPORTANT]  
> 關於將設定轉移至另一個池的限制式，只適用于應用程式層級設定和預設的音樂保留音訊檔案。 它不適用於 [代理群組]、[佇列]、[工作流程]、[上班時間] 和 [假日集]。



</div>

如果您不想在災難期間取代備份池中的應用層級設定，且無法復原主要池，則主要池中的應用層級設定將會遺失。 如果您需要在恢復期間建立新的池來取代主要池，您可以使用相同的 FQDN 或不同的 FQDN，來復原原始的應用層級設定。 在這種情況下，您需要使用這些設定來設定新的池子，並包含 [音樂保留] 音訊檔案。

如果您決定使用**Import CsRgsConfiguration** Cmdlet，在災難期間將應用程式層級設定從主要池中傳送到備份池，您可以在恢復期間將這些設定從主要池轉移到新的池中，就與從主要的池中轉移到備份池一樣。

下表是說明復原群組中所涉及之步驟的概覽。

如需執行這些步驟的詳細資訊，請參閱[Lync Server 2013 中的回應群組災害復原程式](lync-server-2013-response-group-disaster-recovery-procedures.md)。

### <a name="response-group-disaster-recovery-steps"></a>回應群組災害復原步驟

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>必要的群組和角色</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>在中斷前</p></td>
<td><p>定期執行<strong>Export CsRgsConfiguration</strong> Cmdlet，在部署回應群組應用程式的所有前端池中，建立所有回應群組設定的備份。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>在中斷期間</p></td>
<td><p>執行匯<strong>入-CsRgsConfiguration</strong> Cmdlet，將備份的 Lync Server 回應群組服務設定從主要池中匯入到備份池。</p>
<div>

> [!NOTE]  
> 如果您想要將備份池中的應用層回應群組設定取代為主要池中的設定，請使用– ReplaceExistingSettings 參數。 如果您沒有將應用程式層級設定從主要池轉移到備份池，且無法復原主要池，您將會遺失主要池中的設定。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>匯入之後</p></td>
<td><p>執行回應群組 Cmdlet 時，請使用– ShowAll 參數（顯示所有回應群組）或– Owner 參數（若要只顯示已匯入的回應群組），以驗證是否已將所有回應群組設定匯入到備份池中。</p>
<div>

> [!IMPORTANT]  
> 如果您不使用– ShowAll 參數或– Owner 參數，您匯入到備份池中的回應群組將不會列在 Cmdlet 所傳回的結果中。


</div>
<p>執行下列 Cmdlet：</p>
<ul>
<li><p><strong>CsRgsWorkflow</strong></p></li>
<li><p><strong>CsRgsQueue</strong></p></li>
<li><p><strong>CsRgsAgentGroup</strong></p></li>
<li><p><strong>CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>容錯移轉之後</p></td>
<td><ul>
<li><p>將測試呼叫放到已匯入到備份池中的回應群組，並確認正確處理該通話。</p></li>
<li><p>所有正式代理程式都必須重新登入其備份池上的正式群組。</p></li>
<li><p>管理設定變更：</p>
<p>備份池中的回應群組（無論是匯入到備份池或由備份池所擁有），都可以在中斷期間修改為正常。</p>
<div>

> [!IMPORTANT]  
> 您必須使用 Lync Server 管理命令介面來管理您匯入到備份池中的回應群組。 當這些回應群組位於備份池中時，您無法使用 Lync Server [控制台] 管理這些回應群組。


</div></li>
</ul></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>在恢復之後，在回切前</p></td>
<td><p>執行<strong>匯出-CsRgsConfiguration</strong> Cmdlet，指定-Source 參數作為備份池，並將– Owner （擁有者）參數做為主要池，以匯出來自備份池中的主要池所擁有的回應群組。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>回切後</p></td>
<td><ul>
<li><p>執行匯<strong>入-CsRgsConfiguration</strong> Cmdlet，將回應群組匯入到主要池。</p>
<div>

> [!NOTE]  
> 如果無法復原主要池，且您要部署新的池來取代它，請使用– ReplaceExistingSettings 參數，將應用程式層級設定從備份池中轉移到新的池中。 如果您沒有從備份池中轉移設定，新的池會使用預設設定。


</div></li>
<li><p>請執行下列 Cmdlet 與– ShowAll 參數（以顯示所有回應群組）或– Owner 參數（若要只顯示匯入的回應群組），以確認所有回應群組設定都已成功匯入到主要池中：</p>
<ul>
<li><p><strong>CsRgsWorkflow</strong></p></li>
<li><p><strong>CsRgsQueue</strong></p></li>
<li><p><strong>CsRgsAgentGroup</strong></p></li>
<li><p><strong>CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>將測試呼叫放到已匯入到主要池的回應群組，並確認正確處理該通話。</p></li>
<li><p>您也可以在備份池中執行<strong>Export CsRgsConfiguration</strong> Cmdlet 與– RemoveExportedConfiguration 參數，將主要池所擁有的回應群組從備份池中移除。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

