---
title: Lync Server 2013：將回應群組移至新的池中
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e682ce99826cd5b9f2812c358e1028bfb491ddef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>在 Lync Server 2013 中將回應群組移至新的文件庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Lync Server 2013 引入了新的 Cmdlet 支援，可將回應群組從一個池移到另一個池中，即使完全符合的功能變數名稱（FQDN）不同也一樣。

使用下列程式中的步驟，將回應群組從一個前端池移到另一個具有不同 FQDN 的 [前端] 池。

<div>


> [!NOTE]  
> 在共存環境中，您只能在 Lync Server 2013&nbsp;前端池之間移動回應群組。



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>若要將回應群組移到具有不同 FQDN 的池

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  匯出來源池中的回應群組。 在命令列中，輸入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    若要在匯出期間從來源池中移除回應群組，請包括-RemoveExportedConfiguration 參數。 例如：
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  匯入回應群組至目的地池中，並將目的地池指派為新的擁有者。 在命令列中，輸入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    如果您也想要將 [回應] 群組的應用層級設定從來源池複製到目的地池，請包含– ReplaceExistingRgsSettings 參數。 每個 pool 只能定義一組應用層級設定。 如果您將應用程式層級設定從來源池複製到目的地池，來源池中的設定會取代目的地池的設定。 如果您沒有從來源池中複製應用程式層級設定，目的地池中的現有設定就會套用至匯入的回應群組。
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > 應用程式層級設定包括預設的 [隨用音樂保留] 設定、預設的 [音樂保留] 音訊檔案、[代理程式 ringback 寬限期]，以及 [通話內容] 配置。 若要查看這些設定，請執行<STRONG>CsRgsConfiguration</STRONG> Cmdlet。 如需此 Cmdlet 的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">CsRgsConfiguration</A>。

    
    </div>

4.  您可以執行下列動作，透過顯示匯入的回應群組設定來確認匯入成功：
    
      - 確認所有工作流程都已匯入。 在命令列中，輸入下列內容：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 確認已匯入所有佇列。 在命令列中，輸入下列內容：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 確認已匯入所有的代理程式群組。 在命令列中，輸入下列內容：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 確認已匯入所有上班時間。 在命令列中，輸入下列內容：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - 確認所有假日集都已匯入。 在命令列中，輸入下列內容：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  將呼叫撥到其中一個回應群組，並確認正確處理通話，以確認匯入成功。

6.  要求是正式代理群組成員的代理，在目的地池中登入其代理群組。

7.  如果您之前從未從來源池中移除回應群組，請從來源池中移除回應群組。 在命令列中，輸入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

