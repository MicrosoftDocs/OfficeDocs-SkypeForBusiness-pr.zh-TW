---
title: Lync Server 2013： 將 Stop 用於集中式記錄服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f764bbc93ae327e30fa6ac9daf3128963856460
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>將 Stop 用於 Lync Server 2013 中的集中式的記錄服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

您可以用 Stop-CsClsLogging Cmdlet 來停止目前執行中的記錄工作階段。 一般來說，並沒有很多狀況會需要停止記錄工作階段。 例如，您不需要先停止記錄，就可以搜尋記錄及變更設定。 如果您有兩個案例正在執行，例如 AlwaysOn 和 UserReplicator，而您需要收集有關驗證的資訊，則必須先停止其中一個案例 (在全域、網站、集區或電腦範圍)，才能開始執行驗證案例。 如需詳細資訊，請參閱＜[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)＞。

<div>


> [!NOTE]  
> 在判斷您可以在給定的部署部署、集區或電腦上執行哪些案例時，必須記得您有「每部電腦」<STRONG></STRONG>只能執行兩個案例的限制。 如果您要在集區上記錄活動，則應將集區當做單一實體來處理。 在大部分情況下，在集區中的每部電腦上執行不同的案例並沒有意義。 但是查看您收集資料的相關問題，並思考在整體部署中，哪個案例對給定電腦的影響最大，這就有意義了。 例如，如果您考慮 UserReplicator 案例，會有極少的值在 Edge Server 或 Edge 集區上執行 UserReplicator。<BR>在了解問題及影響的範圍之後，應謹慎選擇要在哪些電腦和集區上執行什麼案例。雖然 AlwaysOn 案例對大範圍的應用有意義，因為它會收集各種提供者的資訊，但是特定案例對特定電腦或集區只有應用價值。此外，在未了解給定案例的價值之前，就隨機啟動記錄工作階段的話，要特別小心。如果您使用錯誤的案例，或是所使用的案例適合該工作，而您將案例套用在錯誤的範圍 (可能是全域、網站、集區或電腦)，所得到的問題資料可能不是很有用，就像根本沒有執行案例一樣。



</div>

若要使用 Lync Server 管理命令介面來控制的集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組或包含的自訂 RBAC 角色的成員其中一個這兩個群組。 若要傳回所有獲指派此 cmdlet 的 RBAC 角色清單 （包括您自行建立的任何自訂 RBAC 角色），請從 [Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>若要停止目前正在執行的集中式記錄服務工作階段

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  查詢集中式記錄服務若要了解哪些案例目前正在執行輸入下列命令：
    
        Show-CsClsLogging
    
    ![在呼叫 Show CsCl 後的 Windows PowerShell 主控台](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "在呼叫 Show CsCl 後的 Windows PowerShell 主控台")
    
    Show-CsClsLogging 的結果是執行中案例及其執行範圍的摘要。 如需詳細資訊，請參閱＜[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)＞。

3.  若要停止使用特定案例的目前執行中記錄工作階段，請輸入：
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    例如：
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    此命令將會停止 pool01.contoso.net 上使用 UserReplicatior 案例的記錄。
    
    <div>
    

    > [!NOTE]  
    > 在此記錄工作階段期間，使用 UserReplicator 案例來建立的記錄並不會刪除。 您還是可以使用該記錄來執行使用 Search-CsClsLogging 命令的搜尋作業。 如需詳細資訊，請參閱＜<A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>＞。

    
    </div>

Stop-CsClsLogging Cmdlet 與 Start-CsClsLogging 搭配使用時，會結束記錄工作階段 (由案例定義)，並保留記錄工作階段所建立的記錄。您隨時都可以在給定的電腦上執行兩個案例。用一個案例停止另一個案例來收集資訊的方法，是在大部分工作量疑難排解期間都可以執行的常用工作。

</div>

<div>

## <a name="see-also"></a>另請參閱


[將 Start 用於集中式記錄服務以擷取在 Lync Server 2013 中的記錄](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Lync Server 2013 中的集中式的記錄服務概觀](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show-csclslogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Start-csclslogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Stop-csclslogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

