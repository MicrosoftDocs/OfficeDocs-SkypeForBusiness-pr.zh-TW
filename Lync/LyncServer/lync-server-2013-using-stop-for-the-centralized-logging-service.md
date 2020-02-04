---
title: Lync Server 2013：針對集中式記錄服務使用停止功能
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
ms.openlocfilehash: 621d7c02530fea62b1601c1db755292c8f819a6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中針對集中式記錄服務使用停止功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以停止目前正在執行的記錄會話與 CsClsLogging Cmdlet。 一般來說，在許多情況下，您不需要停止記錄會話。 例如，您可以搜尋記錄並變更配置，而不需要先停止記錄。 如果您有兩種情況（例如，AlwaysOn 和 UserReplicator），而您需要收集驗證的相關資訊，您必須先停止其他案例（全域、網站、池或電腦範圍），才能開始執行到驗證案例。 如需詳細資訊，請參閱[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)。

<div>


> [!NOTE]  
> 在判斷您可以在指定的部署、池或電腦上執行哪些案例時，請記住，您只能在<STRONG>每台電腦</STRONG>上執行兩種案例。 如果您要記錄池中的活動，您應該將一個池視為單一實體。 在大部分的情況下，在池中的每個電腦上執行不同的案例不是很有意義的。 您可以在收集資料時查看問題，並思考在整個部署中的指定電腦上最有意義的案例，這是很有説明的。 例如，如果您認為 UserReplicator 案例，在 Edge 伺服器或 Edge 池中執行 UserReplicator 時，會有非常小的值。<BR>在您瞭解問題及影響範圍之後，您應該謹慎選擇要在哪些電腦和池中執行哪些案例。 雖然 AlwaysOn 作用中的應用程式會在各種提供者上收集資訊，但 AlwaysOn 情況是有意義的，因為它會在特定的電腦或池中只有應用程式值。 此外，您也應該小心地開機記錄會話，而不需要先瞭解特定案例的價值。 如果您使用的是錯誤的案例，或是您使用適合工作的案例，且您在錯誤的範圍（全域、網站、池或電腦）中套用案例，您就可以取得可疑的資料，這並不是很實用的，就像您沒有執行該案例一樣。



</div>

若要使用 Lync Server 管理命令介面控制集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是包含下列內容的自訂 RBAC 角色：這兩個群組的其中一個。 若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從 Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>停止目前正在執行的集中式記錄服務會話

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在集中式記錄服務中輸入下列命令，以查詢目前正在執行的案例：
    
        Show-CsClsLogging
    
    ![呼叫 Show-CsCl 之後的 Windows PowerShell 主控台](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "呼叫 Show-CsCl 之後的 Windows PowerShell 主控台")
    
    CsClsLogging 的結果就是執行中之案例的摘要，以及它們正在執行的範圍。 如需詳細資訊，請參閱[顯示-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)。

3.  若要停止目前正在執行的記錄會話與特定案例，請輸入：
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    例如：
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    這個命令會在 pool01.contoso.net 上停止記錄 UserReplicatior 案例。
    
    <div>
    

    > [!NOTE]  
    > 使用 UserReplicator 案例在這個記錄會話期間建立的記錄不會被刪除。 您仍可使用 [搜尋-CsClsLogging] 命令來執行搜尋的記錄。 如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">搜尋-CsClsLogging</A>。

    
    </div>

作為開始 CsClsLogging 的操作命令，Stop CsClsLogging Cmdlet 會結束記錄會話，由案例定義，並保留記錄會話所建立的記錄。 您可以隨時在指定的電腦上執行兩種案例。 停止某個案例以使用其他案例收集資訊的方法，是您可以在大部分工作負載疑難排解期間執行的一般工作。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中使用 [開始使用集中式記錄服務] 來捕獲記錄](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Lync Server 2013 中的集中式記錄服務概覽](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[顯示-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[開始-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

