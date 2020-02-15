---
title: 了解集中式記錄服務組態設定
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
ms.openlocfilehash: 1bda4fe432841cd005671b18a163df57bd6e0bb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>了解在 Lync Server 2013 中的集中式記錄服務組態設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

The Centralized Logging Service 設定來定義記錄服務是用來收集、 及其收集的方式，它會收集，並記錄檔設定為何。 定義這些設定全域 (也就是整個部署) 或針對網站 （也就是您在部署中的具名網站）。 任何您定義的記錄都會依據您在進行開始、停止、清除及搜尋記錄命令時所使用的身分，而使用適當的設定。

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>若要顯示目前的集中式記錄服務組態

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列提示輸入下列命令：
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > 您可以縮小或傳回所定義的組態設定的範圍依序展開 [<CODE>-Identity</CODE>和範圍，例如"Site: Redmond"傳回僅針對 Redmond 網站 CsClsConfiguration。 如果您想設定的指定部分詳細，您可以將輸出內容輸送到另一個的 Windows PowerShell cmdlet。 例如，若要取得有關站台"Redmond"的設定中所定義案例的詳細資訊，請輸入：<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![從 Get-csclsconfiguration 輸出的範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "從 Get-csclsconfiguration 輸出的範例。")
    
    Cmdlet 的結果會顯示目前的集中式記錄服務組態。
    
    
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
    <td><p>定義組態的搜尋字詞。 Office 365、 不在內部部署。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>定義安全性群組，根據其所在的網站，控制誰 (亦即安全性群組的成員) 可以看到電腦。 網站，在此上下文中，是站台拓撲產生器中所定義。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>區域</strong></p></td>
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
    <td><p>允許執行的 CLSAgent 最小版本。 這個項目適用於 Office 365。</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的集中式的記錄服務概觀](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-csclsconfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Remove-csclsconfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Get-csclsconfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

