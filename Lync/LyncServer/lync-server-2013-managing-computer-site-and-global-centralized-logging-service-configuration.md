---
title: 管理電腦、網站和全域集中式記錄服務設定
description: 管理電腦、網站和全域集中式記錄服務設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37dee125d69e17664fddd0c32feb3048ffcf91b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570379"
---
# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中管理電腦、網站和全域集中式記錄服務設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

集中式記錄服務可以在包含單一電腦、電腦集區、網站範圍 (，也就是定義的網站（例如，包含部署) 中的電腦及集區集合的網站 Redmond）執行，也可以在全域範圍 (（即部署) 中的所有電腦與集區）的範圍內執行。

若要使用 Lync Server 管理命令介面來設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。 若要傳回所有獲指派此 Cmdlet 的 RBAC 角色清單 (包括您自行建立的自訂 RBAC 角色) ，請從 Lync Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell 會提供更多選項及其他無法使用 CLSController.exe 所無法使用的設定選項。 CLSController 提供一種快速、簡潔的方法來執行命令，但僅限於可用於 CLSController 的命令集。 Windows PowerShell 不僅限於 CLSController 的命令處理器可使用的命令，而且提供更多的命令和一組更豐富的選項。 例如，CLSController.exe 確實為您提供了-電腦和–集區的範圍選項。 透過 Windows PowerShell，您可以在大多數命令中指出電腦或集區，並在定義新案例時 (CLSController 具有有限數量的案例，而這些案例並非使用者可修改) 您可以定義網站或全域範圍。 Windows PowerShell 的這項強大功能可讓您定義網站或全域範圍的案例，但限制實際記錄為電腦或集區。<BR>您可以在 Windows PowerShell 或 CLSController 中執行的命令列命令之間有基本差異。 Windows PowerShell 提供豐富的方法來設定及定義案例，並以有意義的方式針對疑難排解案例重複使用這些案例。 雖然 CLSController 提供快速且有效的方式來發出命令並取得結果，但 CLSController 的命令設定會受限於您在命令列中使用的有限命令。 與 Windows PowerShell Cmdlet 不同的是，CLSController 無法定義新案例、管理網站或全域層級的範圍，以及無法動態設定之有限命令集的其他許多限制。 雖然 CLSController 提供快速執行的方法，但 Windows PowerShell 提供一種方法來擴充集中式記錄服務功能，以超越 CLSController 的可能。



</div>

使用– computer 參數，可在執行 [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))、 [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))、 [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))、 [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))、 [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) 和 [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) 命令期間定義單一電腦範圍。 – Computer 參數會接受以逗號分隔的完整功能變數名稱清單，該清單是目的電腦的 (Fqdn) 。

<div>


> [!TIP]
> 您也可以定義集區和以逗號分隔的集區清單，您想要在其上執行記錄指令。



</div>

網站和全域範圍是在 **新的**、 **集合**及 **移除** 集中式記錄服務 Cmdlet 中定義。 下列範例會示範如何設定網站和全域範圍。

<div>


> [!IMPORTANT]
> 所顯示的命令可能包含其他章節中所涵蓋的參數和概念。 範例命令的目的是為了示範如何使用 <STRONG>-Identity</STRONG> 參數來定義範圍，並包含其他參數，以進行完整性及指定範圍。 如需 <STRONG>Set-CsClsConfiguration</STRONG> Cmdlet 的詳細資訊，請參閱 Operations 檔中的 <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> 。



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>若要取得目前的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示字元處，輸入下列命令：
    
        Get-CsClsConfiguration

使用 **New-CsClsConfiguration** 和 **Set-CsClsConfiguration** Cmdlet 來建立新的設定或更新現有的設定。

當您執行 **Get-CsClsConfiguration**時，它會顯示與下列螢幕擷取畫面類似的資訊，其中的部署目前具有預設全域設定，但未定義網站配置：

![Get-CsClsConfiguration 的輸出範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration 的輸出範例。")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>從電腦本地存放區中取得目前的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示字元處，輸入下列命令：
    
        Get-CsClsConfiguration -LocalStore

當您使用第一個範例，其中 **Get-CsClsConfiguration** 未指定任何參數時，此命令會參考資料的中央管理存放區。 如果您指定參數– LocalStore，此命令會參照電腦 LocalStore 而非中央管理存放區。

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>若要取得目前定義的案例清單

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示字元處，輸入下列命令：
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    例如，若要檢索在全域範圍內定義的案例：
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Cmdlet **Get-CsClsConfiguration** 一定會顯示屬於特定範圍設定之部分的案例。 在大多數情況下，不會顯示所有案例，而且會被截斷。 此處所用的命令會列出使用的提供者、設定及旗標的所有案例及部分資訊。

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 更新集中式記錄服務的全域範圍

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示字元處，輸入下列命令：
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    例如：
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

命令會告訴部署中每台電腦及集區上的 CLSAgent，將追蹤檔案的變換值大小設定為 40 mb。 所有網站中的電腦與集區都會受到命令的影響，並會將其設定的追蹤記錄檔翻轉值設定為 40 mb。

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 更新集中式記錄服務的網站範圍

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示字元處，輸入下列命令：
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    例如：
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > 如範例中所述，記錄檔的預設位置是%TEMP%\Tracing。 不過，由於實際 CLSAgent 是寫入檔案，而 CSLAgent 以網路服務方式執行，所以%TEMP% 變數會擴充為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。

    
    </div>

命令會告訴 site Redmond 中每一部電腦及集區上的 CLSAgent，將追蹤檔案的變換值大小設定為 40 mb。 其他網站中的電腦及集區不會受到命令的影響，而且會繼續使用目前設定的追蹤記錄檔滾動更新值，此值是由預設 (20 mb) 或開始記錄會話期間所定義。

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>若要建立新的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示字元處，輸入下列命令：
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > New-CsClsConfiguration 提供大量選用設定設定的存取權。 如需設定選項的詳細資訊，請參閱 <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> 及 <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">瞭解 Lync Server 2013 中的集中式記錄服務設定設定</A>。

    
    </div>
    
    例如，若要建立新的設定以定義快取檔案的網路資料夾、滾動表檔的記錄檔和翻轉大小的時間週期，您可以輸入：
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

您應該仔細規劃新設定的建立，以及如何定義集中式記錄服務的新屬性。 您應謹慎進行變更，並確定您瞭解能夠正確記錄問題案例的影響。 您應該對設定進行變更，以增強您記錄管理大小的能力，以及可在發生問題時進行問題解決的翻轉期間。

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>移除現有的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示字元處，輸入下列命令：
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    例如，若要移除您已建立的集中式記錄服務設定，以增加記錄檔翻轉時間、增加翻轉記錄檔大小，並將記錄檔快取位置設為網路共用，如下所示：
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > 這是在「建立新的集中式記錄服務設定」過程中建立的新設定。

    
    </div>

如果您選擇移除網站層級設定，則網站會使用通用設定。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的集中式記錄服務概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[在 Lync Server 2013 中管理集中式記錄服務設定設定](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

