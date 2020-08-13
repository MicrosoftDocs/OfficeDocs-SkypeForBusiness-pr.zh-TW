---
title: Lync Server 2013 回應群組災難修復程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 254f9e95edfb445d996948a17064ae460dbdb7d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Lync Server 2013 的回應群組嚴重損壞修復程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在災害復原的容錯移轉階段期間，回應群組位在多個集區中：主要集區 (無法使用) 以及備份集區中。 兩個集區中的回應群組都有相同的名稱和相同的擁有者 (主要集區)，但其父系不同。 在這段時間內，回應群組 Cmdlet 的運作方式稍有不同。 請務必依照下列程式所指定的方法使用參數。 如需在容錯移轉階段內 Cmdlet 如何運作的詳細資訊，請參閱《 Lync Server 2013：在嚴重損壞復原期間復原回應群組」中的 NextHop 博客文章 [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957) 。 此博客文章也適用于已發行版本本的 Lync Server 2013。

使用下列程式中的步驟來準備和執行 Lync Server 回應群組服務的嚴重損壞修復。

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>容錯移轉和容錯回復回應群組

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  定期執行備份。 在命令列中輸入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  在中斷期間，在容錯移轉至備份組區之後，將回應群組匯入至備份組區。 在命令列中輸入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    如果您想要以主要集區中的設定取代備份組區中的應用層級設定，請加入–ReplaceExistingSettings 參數。 例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > 如果您未取代備份組區中的設定，且無法復原主要集區，主要集區設定將會遺失。 如需詳細資訊，請參閱 <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">在 Lync Server 2013 中規劃回應群組</A>嚴重損壞修復。

    
    </div>

4.  顯示匯入的回應群組，以確認匯入成功。 匯入的回應群組仍然歸主要集區所有。 執行下列動作：
    
      - 顯示主要集區所擁有之備份組區中的所有工作流程，並確認包括所有主要集區工作流程。 在命令列中輸入：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - 顯示主要集區所擁有之備份組區中的所有佇列，並確認所有主要集區佇列都已包含。 在命令列中輸入：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 顯示主要集區所擁有之備份組區中的所有代理程式群組，並確認所有的主要集區代理程式群組都包含在內。 在命令列中輸入：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 顯示主要集區所擁有之備份組區中的所有上班時間，並確認包括所有的主要集區工作。 在命令列中輸入：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 顯示主要集區所擁有之備份組區中的所有假日集，並確認所有主要集區假日集皆已包含在內。 在命令列中輸入：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    或者，您可以顯示備份組區中所有的回應群組，包括主要集區所擁有的所有回應群組，以及備份組區所擁有的任何回應群組，而不是–ShowAll 使用– Owner 參數。 例如：
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須使用–ShowAll 參數或– Owner 參數。 如果您不使用這兩個參數，您匯入到備份組區的回應群組將不會列在 Cmdlet 所傳回的結果中。

    
    </div>

5.  撥打已匯入的回應群組，並確認已正確處理呼叫，以確認匯入是否成功。

6.  要求是正式代理群組成員的代理人，以登入其備份組區中的代理人群組。

7.  照常管理及修改匯入的回應群組。
    
    <div>
    

    > [!IMPORTANT]  
    > 當回應群組位於備份組區中時，您必須使用 Lync Server 管理命令介面來管理這些群組。 您無法使用 Lync Server 控制台管理匯入到備份組區的回應群組。

    
    </div>

8.  在還原主要集區並完成回切後，請將匯入的主要集區回應群組匯出至備份組區。 在命令列中輸入：
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  將回應群組匯入回主要集區。 在命令列中輸入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > 如果您在復原期間重建集區，不論是否使用相同或不同的完整功能變數名稱 (FQDN) ，您必須使用– OverwriteOwner 參數。 根據經驗的經驗，您可以在將回應群組匯回主要集區時，永遠使用– OverwriteOwner 參數。

    
    </div>
    
    如果您部署了具有相同或不同 FQDN 的新集區 () 取代主要集區，而您想要使用來自新集區之備份組區的應用層級設定，請包含–ReplaceExistingSettings 參數。 在命令列中輸入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您不想要使用備份組區中的設定取代新集區的應用層級設定和預設的等候音樂音訊檔，新集區將會使用預設的應用層級設定。

    
    </div>

10. 顯示匯入的回應群組設定，以確認匯入至主要集區成功。 執行下列動作：
    
      - 顯示主要集區中的所有工作流程，並確認包括所有匯入的工作流程。 在命令列中輸入：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - 顯示主要集區中的所有佇列，並確認所有匯入的佇列都包含在內。 在命令列中輸入：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 顯示主要集區中的所有代理程式群組，並確認所有匯入的 agent 群組都包含在內。 在命令列中輸入：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 顯示主要集區中的所有上班時間，並確認包括所有匯入的公司內下班。 在命令列中輸入：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 顯示主要集區中的所有假日集，並確認包括所有匯入的假日集。 在命令列中輸入：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. 撥打已匯入的回應群組，並確認已正確處理呼叫，以確認匯入是否成功。

12. （選用）從備份組區中移除主要集區所擁有的回應群組。 在命令列中輸入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > 此步驟會使用匯出的設定來建立新檔案，然後將其從備份組區中移除。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

