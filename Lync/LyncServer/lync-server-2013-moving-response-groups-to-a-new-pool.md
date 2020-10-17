---
title: Lync Server 2013：移動回應群組至新集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6b0af841385bff8b11d46dd24793de5cdcf81da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507100"
---
# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>將回應群組移至 Lync Server 2013 中的新集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Lync Server 2013 引進新的指令程式支援，可將回應群組從一個集區移至另一個集區，即使 (FQDN) 的完整功能變數名稱不同也是一樣。

使用下列程式中的步驟，將回應群組從一個前端集區移至另一個具有不同 FQDN 的前端集區。

<div>


> [!NOTE]  
> 在共存環境中，您只能移動 Lync Server 2013 前端集區之間的回應群組 &nbsp; 。



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>將回應群組移至具有不同 FQDN 的集區

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  匯出來源集區中的回應群組。 在命令列中輸入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    若要在匯出期間從來源集區中移除回應群組，請包括–RemoveExportedConfiguration 參數。 例如：
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  將回應群組匯入目的地集區，並將目的地集區指派為新的擁有者。 在命令列中輸入：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    如果您也想要將來源集區的回應群組應用層級設定複製到目的地集區，請加入– ReplaceExistingRgsSettings 參數。 您只能為每個集區定義一組應用層級的設定。 如果您將應用層級設定從來源集區複製到目的地集區，來源集區的設定會取代目的地集區的設定。 如果您未從來源集區複製應用層級設定，則目的地集區中的現有設定會套用至匯入的回應群組。
    
    例如：
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > 應用層級設定包括預設的等候音樂設定、預設的等候音樂音訊檔、代理程式回電寬限時間，以及通話內容設定。 若要檢視這些組態設定，請執行 <STRONG>Get-CsRgsConfiguration</STRONG> Cmdlet。 如需此 Cmdlet 的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>。

    
    </div>

4.  執行下列動作來顯示匯入的回應群組設定，以確認匯入是否成功：
    
      - 確認已匯入所有工作流程。 在命令列輸入下列命令：
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 確認已匯入所有佇列。 在命令列輸入下列命令：
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 確認已匯入所有代理程式群組。 在命令列輸入下列命令：
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 確認已匯入商務用時數。 在命令列輸入下列命令：
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - 確認已匯入所有假日集。 在命令列輸入下列命令：
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  撥打電話給其中一個回應群組，確認是否已正確處理該呼叫，以確認匯入是否成功。

6.  要求是正式代理群組成員的代理人，以登入目的地集區中的其代理群組。

7.  如果您先前沒有從來源集區移除回應群組，請從來源集區中移除回應群組。 在命令列中輸入：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    例如：
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

