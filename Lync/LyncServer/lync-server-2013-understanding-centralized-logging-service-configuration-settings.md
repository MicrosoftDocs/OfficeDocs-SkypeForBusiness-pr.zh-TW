---
title: 瞭解集中式記錄服務設定設定
description: 瞭解集中式記錄服務的配置設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f99dbffe15c4b3f0dc13d231c3a2732a8554397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542399"
---
# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>瞭解 Lync Server 2013 中的集中式記錄服務設定設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

集中式記錄服務設定為定義記錄服務的預定目標、收集方式、收集位置及記錄設定的方式。 您可以將這些設定定義為全域 (，也就是針對整個部署) 或網站 (（也就是部署) 中已命名的網站）。 任何您定義的記錄都會依據您在進行開始、停止、清除及搜尋記錄命令時所使用的身分，而使用適當的設定。

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>顯示目前的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示輸入下列命令：
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > 您可以縮小或展開定義及範圍所傳回的設定設定範圍 <CODE>-Identity</CODE> ，例如 "Site:Redmond"，只傳回 Site Redmond 的 set-csclsconfiguration。 如果您想要有關設定之特定部分的詳細資料，您可以將輸出輸送到另一個 Windows PowerShell Cmdlet 中。 例如，若要取得網站 "Redmond" 設定中所定義案例的詳細資料，請輸入： <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Get-CsClsConfiguration 的輸出範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration 的輸出範例。")
    
    Cmdlet 的結果會顯示集中式記錄服務的目前設定。
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>組態設定</th>
    <th>描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>身分識別</strong></p></td>
    <td><p>識別此組態的範圍及名稱。只有一個全域組態，而每個網站有一個組態。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Scenarios</strong></p></td>
    <td><p>列出針對此組態定義的所有案例。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>定義組態的搜尋字詞。 Office 365 或 Microsoft 365，而非內部部署。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>定義安全性群組，根據其所在的網站，控制誰 (亦即安全性群組的成員) 可以看到電腦。 在此內容中，網站是在拓撲產生器中定義的網站。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>地區</strong></p></td>
    <td><p>定義地區，用於將 SecurityGroups 集合至地區，例如 EMEA。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>定義將記錄檔寫入電腦所在位置的路徑。CLSAgent 寫入記錄檔並在網路服務環境下執行。在此情況下，%TEMP% 會展開為 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>此參數指示在建立新的事件追蹤記錄 (.etl) 檔之前，記錄檔的大小上限。達到定義的大小時，即使還未達到 EtlFileRolloverMinutes 中設定的時間上限，還是會建立新的記錄檔。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>定義在建立新的 .etl 檔之前，記錄檔可以存在的時間上限 (分)。計時器逾期時，即使還未達到 EtlFileRolloverSizeMB 中設定的大小上限，還是會建立新的記錄檔。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>搜尋追蹤訊息格式檔的位置。追蹤訊息格式檔是用於將二進位檔案轉換為人類看得懂的格式。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>定義將快取檔案寫入電腦所在位置的路徑。CLSAgent 寫入快取檔案並在網路服務環境下執行。在此情況下，%TEMP% 會展開為 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。依據預設，快取檔案及記錄檔會寫入相同的目錄。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>您可以定義通用命名慣例 (UNC) 路徑，以在記錄作業時接收快取檔案。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
    <td><p>定義快取檔案保留的時間上限 (天)。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>定義快取檔案可使用的磁碟空間百分比。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ComponentThrottleLimit</strong></p></td>
    <td><p>定義在觸發自動節流限制器之前，元件每秒可以產生的追蹤上限。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>60 秒內可超過 ComponentThrottleLimit 的次數。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
    <td><p>允許執行的 CLSAgent 最小版本。 此元素適用于 Office 365 或 Microsoft 365。</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的集中式記錄服務概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

