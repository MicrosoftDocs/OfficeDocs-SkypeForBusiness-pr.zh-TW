---
title: Lync Server 2013：規劃回應群組災難修復
description: Lync Server 2013：規劃回應群組災難修復。
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
ms.openlocfilehash: 5294ddf7dbd42d95c5eb17acd6be6a5abc7a5917
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549259"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中規劃回應群組災難修復

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

本節說明為災害復原準備回應群組的一些方法，並提供災害復原程序的概觀。

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>準備回應群組災難修復

當您準備及執行災害復原程序時，請記得下列事項。

<div>


> [!NOTE]  
> 在共存環境中，本檔中所述的嚴重損壞復原程式僅支援 Lync Server 2013 回應群組。



</div>

  - 在進行容量規劃時，請規劃災害復原。 針對災害復原容量，一對集區中的每個集區都應該要能夠處理這兩個集區中所有回應群組的工作量。 如需有關回應群組容量規劃的詳細資訊，請參閱 [Lync Server 2013 中的「回應」群組的容量規劃](lync-server-2013-capacity-planning-for-response-group.md)。

  - 在您部署回應群組應用程式的所有前端集區中，請定期備份所有的回應群組設定，並使用本檔中所述的匯出程式。 如需詳細資訊，請參閱 [Lync Server 2013 中的回應群組嚴重損壞修復程式](lync-server-2013-response-group-disaster-recovery-procedures.md)。 將備份複本保存在安全的地方。

  - 針對回應群組應用程式，保留您使用的所有原始音訊檔的個別備份副本，包括任何錄製和暫止的檔。 將備份檔案保存在安全的地方。

  - 對於 Lync Server 2013 的嚴重損壞修復，所有的回應群組設定都必須在您的部署中具有唯一的名稱。 此需求適用於工作流程、佇列、代理群組、假日集和營業時間。 您應該在主要和備份集區仍作用時，以及在您需要起始任何容錯移轉程序之前，確認是否符合此需求。 如果在將回應群組資料匯入備份集區時，發生名稱衝突，則匯入失敗。 若要完成匯入及容錯移轉程序，您必須將備份集區中的回應群組物件重新命名，以解決名稱衝突的問題，或是使用 **Import-CsRgsConfiguration** Cmdlet 搭配 –ResolveNameConflicts 參數來自動解決衝突，其會在回應群組物件後面加上唯一的識別號碼。

  - 一般而言，我們會建議您執行每日備份，但是如果您有大量變更，也許會想要排定更多次的備份。您在發生災害會遺失的資訊量，取決於備份的頻率，以及變更的頻率和數量。

  - 您可以在發生災害或容錯移轉作業之前，就將回應群組匯入備份集區。 以預先匯入回應群組可減少停機時間，因為在將來電路由傳送至備份組區之後，就可以在備份組區中還原 Lync Server 回應群組服務。
    
    <div>
    

    > [!NOTE]  
    > 在容錯移轉完成之前，回應群組應用程式無法到達任何停用的集區中的代理程式。 在這段時間內，回應群組應用程式會處理呼叫，就像這些代理程式皆無法使用。

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>回應群組災害復原程序

在發生災害時，您可以使用下列任一復原方式來復原回應群組：

  - 容錯移轉至備份集區，然後容錯回復至原始集區。

  - 容錯移轉至備份集區，以不同的完整網域名稱 (FQDN) 建立新集區，然後將回應群組匯入新集區。

在災害復原的容錯移轉階段期間，回應群組位在多個集區中：主要集區 (無法使用) 以及備份集區中。兩個集區中的回應群組都有相同的名稱和相同的擁有者 (主要集區)，但其父系不同。

當您建立不同 FQDN 的新集區來進行復原時，需要在匯入回應群組時，將新集區指派為該回應群組的擁有者。 回應群組的擁有權會一直跟隨著原始集區，除非 (或直到) 您使用 –OverwriteOwner 參數搭配 **Import-CsRgsConfiguration** Cmdlet 來明確地重新指派擁有權。

<div>


> [!NOTE]  
> 您也必須使用– OverwriteOwner 參數，如果您在復原 (期間重建集區，則回應群組資料庫會是空的) （不論您是否使用相同的 FQDN）。 如果您沒有重新建立集區，則不需使用 –OverwriteOwner 參數，但是每當您將回應群組匯入回主要集區時，都可以使用此參數。



</div>

您只能為每個集區定義一組應用層級回應群組設定設定。 這些設定包括預設等候音樂組態、預設等候音樂音訊檔案、代理回電寬限期，以及呼叫內容組態。 若要檢視這些組態設定，請執行 **Get-CsRgsConfiguration** Cmdlet。 如需 **Get-CsRgsConfiguration** Cmdlet 的詳細資訊，請參閱 [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)。

您可以使用 **Import-CsRgsConfiguration** Cmdlet 搭配 –ReplaceExistingSettings 參數，將這些應用程式層級設定從一個集區轉移到另一個集區，但是這麼做會覆寫目的集區中的設定。

<div>


> [!IMPORTANT]  
> 此有關將設定轉移到另一個集區的限制，僅適用於應用程式層級設定和預設等候音樂音訊檔案，不適用於代理群組、佇列、工作流程、營業時間和假日集。



</div>

如果您不想在災害期間取代備份集區中的應用程式層級設定，而且主要集區無法復原，主要集區的應用程式層級設定將會遺失。如果您需要在復原期間建立新集區來取代主要集區，無論是使用相同的 FQDN 或不同的 FQDN，您都無法復原原始應用程式層級設定。在此情況下，您需要設定使用這些設定的新集區，並包含等候音樂音訊檔案。

如果您決定使用 **Import-CsRgsConfiguration** Cmdlet，在災害期間將應用程式層級設定從主要集區轉移到備份集區，您可以在復原期間將這些設定從備份集區轉移到新集區，方法就和您將其從主要集區轉移到備份集區一樣。

下表是有關復原回應群組的步驟概觀。

如需執行這些步驟的詳細資訊，請參閱 [Lync Server 2013 中的回應群組嚴重損壞修復程式](lync-server-2013-response-group-disaster-recovery-procedures.md)。

### <a name="response-group-disaster-recovery-steps"></a>回應群組災害復原步驟

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>所需群組和角色</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>系統中斷之前</p></td>
<td><p>請定期執行 <strong>Export-CsRgsConfiguration</strong> Cmdlet，以在部署回應群組應用程式的所有前端集區中，建立所有回應群組設定的備份。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>系統中斷期間</p></td>
<td><p>執行 <strong>Import-CsRgsConfiguration</strong> Cmdlet，將備份的 Lync Server 回應群組服務設定從主要集區匯入至備份組區。</p>
<div>

> [!NOTE]  
> 如果您想要以主要集區的設定取代備份組區中的應用層回應群組設定，請使用–ReplaceExistingSettings 參數。 如果您不將應用程式層級設定從主要集區轉移到備份集區，而且主要集區無法復原，您將會遺失主要集區的設定。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>匯入之後</p></td>
<td><p>使用–ShowAll 參數 (執行回應群組指令程式，以顯示所有回應群組) 或「–擁有者」參數 (只顯示匯入的回應群組) ，以確認所有回應群組設定已匯入備份組區。</p>
<div>

> [!IMPORTANT]  
> 如果您不使用 –ShowAll 參數，也不使用 –Owner 參數，您匯入備份集區的回應群組將不會列示在 Cmdlet 傳回的結果中。


</div>
<p>執行下列 Cmdlet：</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>容錯移轉之後</p></td>
<td><ul>
<li><p>撥打測試通話至已匯入備份集區的回應群組，確認可正確處理該通話。</p></li>
<li><p>所有正式代理程式都必須再次登入備份集區上的正式群組。</p></li>
<li><p>管理組態變更：</p>
<p>在系統中斷期間，仍可像平常一樣修改備份集區中的回應群組 (無論是匯入備份集區或為備份集區所擁有)。</p>
<div>

> [!IMPORTANT]  
> 您必須使用 Lync Server 管理命令介面來管理已匯入備份組區的回應群組。 在備份組區中時，您無法使用 Lync Server 控制台管理這些回應群組。


</div></li>
</ul></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>復原之後，容錯回復之前</p></td>
<td><p>執行 <strong>Export-CsRgsConfiguration</strong> Cmdlet，將 -Source 參數指定為備份集區，將 –Owner 參數指定為主要集區，以從備份集區匯出主要集區擁有的回應群組。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>容錯回復之後</p></td>
<td><ul>
<li><p>執行 <strong>Import-CsRgsConfiguration</strong> Cmdlet，將回應群組匯入回主要集區。</p>
<div>

> [!NOTE]  
> 如果無法復原主要集區，而您部署新的集區來將其取代，請使用 –ReplaceExistingSettings 參數，將應用程式層級設定從備份集區轉移到新集區。如果您沒有從備份集區轉移設定，新集區將會使用預設設定。


</div></li>
<li><p>執行下列 Cmdlet 搭配 –ShowAll 參數 (顯示所有回應群組) 或 –Owner 參數 (只顯示匯入的回應群組)，以確認所有回應群組組態都已成功匯入回主要集區：</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>撥打測試通話至已匯入回主要集區的回應群組，確認可正確處理該通話。</p></li>
<li><p>(選用) 在備份集區上執行 <strong>Export-CsRgsConfiguration</strong> Cmdlet 搭配 –RemoveExportedConfiguration 參數，將主要集區擁有的回應群組從備份集區移除。</p></li>
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

