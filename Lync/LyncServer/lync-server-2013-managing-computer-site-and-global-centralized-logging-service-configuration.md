---
title: 管理電腦、網站和全域集中式記錄服務設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c18e57b81daf93139493d046b8b2124e04e767
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中管理電腦、網站和全域集中式記錄服務設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-04_

集中式記錄服務可以在包含單一電腦的範圍中執行，也就是在網站範圍（也就是已定義的網站（例如在您的部署中包含電腦和池集合的網站雷蒙德），或全域範圍（也就是在您部署中的所有電腦和池）。

若要使用 Lync Server 管理命令介面設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是包含下列內容的自訂 RBAC 角色：這兩個群組的其中一個。 若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從 Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell 提供其他選項和其他無法使用 CLSController 提供的配置選項。 CLSController 提供一種快速、簡明的方法來執行命令，但僅限於可供 CLSController 使用的命令組。 Windows PowerShell 不受限於 CLSController 命令處理器提供的命令，並提供更多組的命令及更豐富的選項。 例如，CLSController 會提供-電腦和– pool 的範圍選項。 在 Windows PowerShell 中，您可以在大部分命令中指示電腦或池，當您定義新的案例時（CLSController 的案例不一定是使用者可修改的），您可以定義網站或全域範圍。 Windows PowerShell 的這項強大功能可讓您定義網站或全域範圍的案例，但限制實際記錄到電腦或池。<BR>您可以在 Windows PowerShell 或 CLSController 中執行的命令列命令之間有一些基本差異。 Windows PowerShell 提供豐富的方法來設定及定義案例，並以一種有意義的方式在疑難排解案例中重複使用這些案例。 雖然 CLSController 確實提供快速且高效的方式來發出命令並取得結果，但 CLSController 的命令會受到您在命令列中提供的有限命令的限制。 與 Windows PowerShell Cmdlet 不同，CLSController 無法定義新案例、管理網站或全域階層的範圍，以及無法動態設定之有限命令集的許多其他限制。 雖然 CLSController 提供快速執行的方法，但 Windows PowerShell 提供了一種方式，可讓集中式記錄服務功能延伸到可能的 CLSController 以外。



</div>

在[搜尋 CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))（[顯示-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))、 [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))、 [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))、 [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))和[Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15))命令）中，可以使用-電腦參數定義單一電腦範圍。 -電腦參數會接受以逗號分隔的目的電腦完整功能變數名稱（Fqdn）清單。

<div>


> [!TIP]
> 您也可以定義您想要執行記錄命令的 [彙集] 和 [逗號分隔的池清單]。



</div>

[網站] 和 [全域範圍] 是在**新**的、**集合**和**移除**集中式記錄服務 Cmdlet 中定義。 下列範例示範如何設定網站和全域範圍。

<div>


> [!IMPORTANT]
> 所顯示的命令可能包含其他章節所涵蓋的參數和概念。 這個範例命令是用來示範如何使用–身分<STRONG>識別</STRONG>參數來定義作用域，而其他參數則包括完整性並指定範圍。 如需<STRONG>設定 CsClsConfiguration</STRONG> Cmdlet 的詳細資料，請參閱作業檔中的<A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">CsClsConfiguration</A> 。



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>若要取得目前的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示處輸入下列內容：
    
        Get-CsClsConfiguration

使用**新的 CsClsConfiguration**和**CsClsConfiguration** Cmdlet 來建立新的設定或更新現有的配置。

當您執行**CsClsConfiguration**時，它會顯示類似下列螢幕擷取畫面的資訊，其中的部署目前具有預設的全域設定，但未定義網站配置：

![從 CsClsConfiguration 輸出的範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "從 CsClsConfiguration 輸出的範例。")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>從電腦當地商店中取得目前的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示處輸入下列內容：
    
        Get-CsClsConfiguration -LocalStore

當您使用**CsClsConfiguration**未指定任何參數的第一個範例時，該命令會參照資料的中央管理儲存體。 如果您指定參數-LocalStore，命令會參照電腦 LocalStore，而不是中央管理儲存體。

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>若要檢索目前定義的案例清單

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示處輸入下列內容：
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    例如，若要檢索在全域範圍內定義的案例：
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Cmdlet **CsClsConfiguration**會始終顯示屬於指定範圍之設定的情況。 在大多數情況下，不會顯示所有案例，而且會被截斷。 此處使用的命令會列出所有案例，以及使用哪些提供者、設定和標誌的部分資訊。

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 來更新集中式記錄服務的全域範圍

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示處輸入下列內容：
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    例如：
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

此命令會告知部署中每個電腦和池中的 CLSAgent，將描摹檔案的滾動更新大小設定為 40 mb。 所有網站中的電腦和池都會受到命令的影響，並將其設定的追蹤記錄滾動更新值設為 40 mb。

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 來更新集中式記錄服務的網站範圍

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示處輸入下列內容：
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    例如：
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > 如範例所述，記錄檔的預設位置是%TEMP%\Tracing。 不過，因為實際 CLSAgent 正在寫入檔案並 CSLAgent [以網路服務執行]，因此% TEMP% 變數會展開為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。

    
    </div>

此命令會告知 [網站雷蒙德] 中每個電腦和池中的 CLSAgent，將 [追蹤檔案] 上的 [翻轉] 值的大小設定為 40 mb。 在其他網站中的電腦和池不會受到命令影響，而且會繼續使用目前已設定的追蹤記錄滾動更新值（預設為 20 mb），或在記錄會話開始時使用。

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>若要建立新的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示處輸入下列內容：
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > 新-CsClsConfiguration 提供大量選用設定的存取權。 如需設定選項的詳細資訊， <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)"></A>請參閱<A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">在 Lync Server 2013 中 CsClsConfiguration 及瞭解集中式記錄服務設定設定</A>。

    
    </div>
    
    例如，若要建立新的設定，以定義快取檔案的網路資料夾、滾動更新記錄檔的時間週期，以及記錄檔的滾動盤大小，您可以輸入：
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

您應該仔細規劃新配置的建立，以及如何定義集中式記錄服務的新屬性。 您應該小心地進行變更，並確認您已瞭解對您能否正確記錄問題案例的影響。 您應該對設定進行變更，以增強您記錄管理的能力，讓您能夠在出現問題時進行問題的疑難排解。

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>移除現有的集中式記錄服務設定

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列提示處輸入下列內容：
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    例如，若要移除您建立的集中式記錄服務設定以增加記錄檔滾動時間，請增加滾動更新記錄檔大小，並將記錄檔案快取位置設定為網路共用，如下所示：
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > 這是在「建立新的集中式記錄服務設定」過程中建立的新設定。

    
    </div>

如果您選擇移除網站層級的設定，網站將會使用全域設定。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的集中式記錄服務概覽](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[在 Lync Server 2013 中管理集中式記錄服務設定設定](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[移除-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

