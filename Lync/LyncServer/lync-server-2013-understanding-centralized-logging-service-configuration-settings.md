---
title: 瞭解集中式記錄服務配置設定
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
ms.openlocfilehash: a766756f082e6666d37dff793c457cb335736fe0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>瞭解 Lync Server 2013 中的集中式記錄服務配置設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

集中式記錄服務會設定為定義記錄服務的預期收集方式、收集方式、收集來源，以及記錄設定的位置。 您可以全域定義這些設定（也就是整個部署）或網站（也就是您部署中的命名網站）。 您定義的任何記錄，都會使用適合用來啟動、停止、清除及搜尋記錄的身分識別的設定。

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>顯示目前的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示處輸入下列內容：
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > 您可以縮小或擴大由定義<CODE>-Identity</CODE>和範圍（例如「Site：北京」）傳回的設定設定範圍，只傳回網站雷蒙德的 CsClsConfiguration。 如果您想要有關設定的指定部分的詳細資料，您可以將輸出輸送至另一個 Windows PowerShell Cmdlet。 例如，若要取得網站「雷蒙德」設定中所定義之案例的詳細資料，請輸入：<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Get-CsClsConfiguration 輸出範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration 輸出範例。")
    
    此 Cmdlet 的結果會顯示集中式記錄服務的目前設定。
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>配置設定</th>
    <th>說明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Identity</strong></p></td>
    <td><p>識別此設定的範圍和名稱。 只有一個全域配置，且每個網站都有一個設定。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>案例</strong></p></td>
    <td><p>此設定所定義之所有案例的清單。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>已定義配置的搜尋字詞。 Office 365，而非內部部署。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>已定義的安全性群組可控制誰（也就是安全性群組的成員）可以查看以他們所在的網站為基礎的電腦。 在此內容中，網站是在拓撲建立器中定義的網站。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>地區</strong></p></td>
    <td><p>已定義的區域是用來將 SecurityGroups 收集到某個地區（例如 EMEA）。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>已定義在電腦上寫入記錄檔案之位置的路徑。 CLSAgent 會寫入記錄檔，並在網路服務的內容下執行。 在此案例中，% TEMP% 會展開為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>在建立新的事件追蹤記錄（.etl）檔案之前，此參數會指出記錄檔的大小上限。 即使在 EtlFileRolloverMinutes 中設定的最大時間尚未達到，也會在已定義的大小達到時建立新的記錄檔。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>已定義在建立新的 .etl 檔案之前可以經過的最大時間長度（以分鐘為單位）。 當計時器過期時，即使已在 EtlFileRolloverSizeMB 中設定的大小上限尚未達到，新的記錄檔案也會建立。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>[追蹤郵件格式] 檔案的搜尋位置。 [追蹤郵件格式] 檔案是用來將二進位檔案轉換成人類可讀格式。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>已定義在電腦上寫入快取檔案之位置的路徑。 CLSAgent 會寫入快取檔案，並在網路服務的內容下執行。 在此案例中，% TEMP% 會展開為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。 根據預設，會將緩存檔案和記錄檔寫入相同的目錄。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>您可以定義通用命名慣例（UNC）路徑，以在記錄作業期間接收快取檔案。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
    <td><p>定義為保留快取檔案的最長時間（以天為單位）。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>定義為快取檔案可以使用的磁碟空間百分比。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ComponentThrottleLimit</strong></p></td>
    <td><p>在觸發自動節流 limiter 前，定義為每秒可產生的追蹤數上限。</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>ComponentThrottleLimit 可超過60秒數的次數。</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
    <td><p>允許執行的 CLSAgent 最低版本。 此元素適用于 Office 365。</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的集中式記錄服務概覽](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[移除-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

