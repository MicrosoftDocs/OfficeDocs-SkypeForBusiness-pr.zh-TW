---
title: Lync Server 2013 回應群組災害復原程序
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
ms.openlocfilehash: 5325f84ff5bf5a0f8d9d1a856110e0ac18b37d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Lync Server 2013 中的回應群組災害復原程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在災害復原的容錯移轉階段，回應群組位於多個池中： [主要] 池中（即無法使用）及 [備份] 池中。 兩個彙集中的回應群組都有相同的名稱和相同的擁有者（主要池），但它們擁有不同的父項。 在這段時間內，回應群組 Cmdlet 的運作方式稍有不同。 請務必使用下列程式中所指定的參數。 如需有關 Cmdlet 在容錯移轉階段運作方式的詳細資訊，請參閱 NextHop 博客文章「Lync Server 2013：在災害復原期間[http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)復原回應群組」。 此博客文章也適用于 Lync Server 2013 的發行版本。

使用下列程式中的步驟來準備並執行 Lync Server 回應群組服務的災害復原。

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>容錯移轉及容錯回復回應群組

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  定期執行備份。 在命令列中，輸入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  在中斷期間，在容錯移轉至備份池之後，將回應群組匯入到備份區。 在命令列中，輸入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    如果您想要將備份池中的應用層級設定取代為主要池中的設定，請包含– ReplaceExistingSettings 參數。 例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > 如果您不取代備份池中的設定，且無法復原主要池，主要池設定將會遺失。 如需詳細資訊，請參閱<A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">在 Lync Server 2013 中規劃回應群組災害復原</A>。

    
    </div>

4.  顯示已匯入的回應群組，以確認已成功匯入。 匯入的回應群組仍為主要池所擁有。 請執行下列步驟：
    
      - 顯示主要池擁有之備份池中的所有工作流程，並確認所有主要池工作流程都包含在其中。 在命令列中，輸入：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - 顯示主要池擁有之備份池中的所有佇列，並確認所有的主要池佇列都已包含。 在命令列中，輸入：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 顯示主要池擁有之備份池中的所有代理群組，並確認所有的主要池代理程式群組都包含在其中。 在命令列中，輸入：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 在主要池擁有的備份池中顯示所有的商務用時數，並確認已包含所有的主要池時間。 在命令列中，輸入：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 在主要池擁有的備份池中顯示所有假日集，並確認所有主要池假日集都包含在內。 在命令列中，輸入：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        例如：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    或者，您也可以在備份池中顯示所有的回應群組，包括主要池所擁有的全部回應群組，以及由備份池所擁有的所有回應群組，而不是使用– Owner （擁有者）參數。 例如：
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須使用– ShowAll 參數或– Owner 參數。 如果您不使用這兩個參數中的任何一個，您匯入到備份池中的回應群組將不會列在 Cmdlet 所傳回的結果中。

    
    </div>

5.  將呼叫撥入到已匯入的回應群組，並確認正確處理通話，以確認匯入成功。

6.  要求是正式代理群組成員的代理，在備份池中登入其代理群組。

7.  照常管理及修改匯入的回應群組。
    
    <div>
    

    > [!IMPORTANT]  
    > 當回應群組位於 [備份] 池中時，您必須使用 Lync Server Management Shell 來管理它們。 您無法使用 Lync Server [控制台] 來管理您匯入到備份池中的回應群組。

    
    </div>

8.  在主要池已還原且已完成回切之後，請匯出已匯入到備份池中的主要池回應群組。 在命令列中，輸入：
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  將回應群組匯入到主要池。 在命令列中，輸入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > 如果您在恢復期間重建一個池（無論是使用相同或不同的完整功能變數名稱（FQDN）），則必須使用– OverwriteOwner 參數。 就拇指而言，當您將回應群組匯入到主要池中時，您隨時可以使用– OverwriteOwner 參數。

    
    </div>
    
    如果您已部署新的池（具有相同或不同的 FQDN）來取代主要池，且您想要使用來自新池之備份池中的應用層級設定，請包含– ReplaceExistingSettings 參數。 在命令列中，輸入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您不想要使用備份池中的設定取代應用程式層級設定和預設的音樂保留音訊檔案，新的池會使用預設的應用層級設定。

    
    </div>

10. 顯示已匯入的回應群組設定，以確認匯入到主要池成功。 請執行下列步驟：
    
      - 在主要池中顯示所有工作流程，並確認所有已匯入的工作流程都包含在其中。 在命令列中，輸入：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - 顯示主要池中的所有佇列，並確認所有已匯入的佇列都包含在其中。 在命令列中，輸入：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 顯示主要池中的所有代理程式群組，並確認所有已匯入的代理程式群組都已包含。 在命令列中，輸入：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 在主要區中顯示所有的商務用時數，並確認已包含所有的匯入時間。 在命令列中，輸入：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 在主要區中顯示所有假日集，並確認所有匯入的假日集都包含在內。 在命令列中，輸入：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        例如：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. 將呼叫撥入到已匯入的回應群組，並確認正確處理通話，以確認匯入成功。

12. 或者，您也可以從備份池中移除主要池所擁有的回應群組。 在命令列中，輸入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > 這個步驟會以匯出的設定建立新的檔案，然後從備份池中移除該檔案。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

