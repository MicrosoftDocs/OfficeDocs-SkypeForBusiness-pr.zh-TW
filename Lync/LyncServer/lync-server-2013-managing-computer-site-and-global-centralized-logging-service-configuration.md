---
title: 管理電腦、 網站及全域集中式記錄服務組態
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
ms.openlocfilehash: 868005d0a719bc8bc021f1a0b82260037c1f6ea6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>管理電腦、 網站及 Lync Server 2013 中全域的集中式記錄服務組態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-04_

在範圍內，其中包含在單一電腦集區的電腦，在網站範圍 （亦即已定義的網站包含一群電腦和集區部署中的 Redmond 網站等），或在全域範圍 （亦即，可以執行 the Centralized Logging Service所有電腦和集區部署中的)。

若要使用 Lync Server 管理命令介面設定集中式記錄服務範圍，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組或包含的自訂 RBAC 角色的成員其中一個這兩個群組。 若要傳回所有獲指派此 cmdlet 的 RBAC 角色清單 （包括您自行建立的任何自訂 RBAC 角色），請從 [Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell 提供更多選項] 和 [不使用 CLSController.exe 的額外的設定選項。 CLSController 提供更快速且簡潔的方法，來執行命令，但限制為一組命令提供的 CLSController。 Windows PowerShell 不限制為只供 CLSController 命令處理器命令，並提供一組更廣的命令和一組更豐富的選項。 例如，CLSController.exe 並未提供範圍] 選項 – 電腦和 – 集區。 您可以使用 Windows PowerShell，指出電腦或集區中大部分的命令，並定義 （CLSController 會有數量有限的案例不是使用者可修改） 的新案例您可以定義網站或全域範圍。 此強大的功能的 Windows PowerShell 可讓您定義案例網站或全域範圍，但限制的電腦或集區的實際記錄。<BR>有您可以在 Windows PowerShell 或 CLSController 中執行命令列工具命令的基本差異。 Windows PowerShell 提供豐富的方法，來設定和定義案例中，以及在有意義的方法，讓您疑難排解案例中重複使用這些案例。 雖然 CLSController 並提供快速和有效率方式來發出命令，並取得結果，設定 CLSController 受限於有限的命令檔] 命令，您必須能從命令列。 不同的 Windows PowerShell cmdlet CLSController 無法定義新的案例中，管理在網站或全域層級及許多其他限制的一組有限的命令，無法以動態方式設定的範圍。 CLSController 提供快速執行，Windows PowerShell 提供方法來擴充以外的功能可能會在使用 CLSController 的集中式記錄服務功能。



</div>

在單一電腦範圍可以定義[Search-csclslogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))、 [Show-csclslogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))、 [Start-csclslogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))、 [Stop-csclslogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))、 [Sync-csclslogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))及[Update-csclslogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))命令使用的執行期間將 – Computers 參數。 – 電腦參數可接受的在目標電腦的完整的網域名稱 (Fqdn) 以逗號分隔清單。

<div>


> [!TIP]
> 您也可以定義 – 集區以及您想要執行記錄命令的集區的逗號分隔清單。



</div>

網站和全域範圍定義**New-**、 **Set-**、 和**Remove-** Centralized Logging Service cmdlet。 下列範例會示範如何設定網站及全域範圍。

<div>


> [!IMPORTANT]
> 參數和其他章節中所述的概念，可能會包含所示的命令。 範例命令主要在示範如何使用<STRONG>– Identity</STRONG>參數，以定義範圍，以及其他參數都包含在內的完整性，並指定範圍。 如需<STRONG>Set-csclsconfiguration</STRONG> cmdlet 的詳細資訊，請參閱作業文件中的<A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-csclsconfiguration</A> 。



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>若要擷取目前的集中式記錄服務組態

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列提示字元處輸入下列命令：
    
        Get-CsClsConfiguration

使用**New-csclsconfiguration**和**Set-csclsconfiguration** cmdlet 來建立新的設定或更新現有的組態。

當您執行**Get-csclsconfiguration**時，它會顯示類似以下螢幕擷取畫面，其中的部署目前具備預設的全域設定，但定義任何網站設定的資訊：

![從 Get-csclsconfiguration 輸出的範例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "從 Get-csclsconfiguration 輸出的範例。")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>若要從電腦本機存放區擷取目前的集中式記錄服務組態

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列提示字元處輸入下列命令：
    
        Get-CsClsConfiguration -LocalStore

當您使用的第一個範例**Get-csclsconfiguration**沒有指定任何參數，命令參照的中央管理存放區的資料。 如果您指定參數 – LocalStore，此命令會參考電腦 LocalStore 而不是中央管理存放區。

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>若要擷取目前定義的案例清單

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列提示字元處輸入下列命令：
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    例如，若要擷取定義於全域範圍的案例：
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

**Get-csclsconfiguration**指令程式永遠會顯示在指定的範圍設定的一部分的案例。 在大多數情況下，所有案例不會顯示，並無條件捨去。 在這裡使用的命令會列出所有的案例和部分資訊何種提供者]，[設定]，並使用旗標。

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>若要使用 Windows PowerShell 更新 the Centralized Logging Service 全域範圍

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列提示字元處輸入下列命令：
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    例如：
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

此命令告知 clsagent 的通訊上每個電腦和集區中部署，以設定為 40 mb 的追蹤檔案變換值的大小。 電腦和集區中的所有網站都受到命令，並會將其設定的追蹤記錄檔變換值設定為 40 mb。

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>若要使用 Windows PowerShell 更新集中式記錄服務的站台範圍

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列提示字元處輸入下列命令：
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    例如：
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > 此範例所述，記錄檔的預設位置是 %temp%\tracing。 不過，因為它是實際 clsagent 的通訊寫入檔案，且 CSLAgent 執行為網路服務，%TEMP%變數就會展開成 %windir%\serviceprofiles\networkservice\appdata\local 中。

    
    </div>

命令會告知 clsagent 的通訊，每個電腦和集區中設定為 40 mb 的追蹤檔案變換值的大小 Redmond 網站上。 電腦和集區中的其他網站不會受到命令，並要繼續使用定義預設 (20 mb) 或啟動記錄工作階段期間的目前設定的追蹤記錄檔變換值。

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>若要建立新的集中式記錄服務組態

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列提示字元處輸入下列命令：
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > New-csclsconfiguration 會提供存取權大量選用的組態設定。 如需組態選項的詳細資訊，請參閱<A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-csclsconfiguration</A>和<A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Lync Server 2013 中的瞭解集中式記錄服務組態設定</A>。

    
    </div>
    
    例如，若要建立新的設定來定義快取檔案，變換記錄檔的時間週期] 與 [記錄檔的變換大小的網路資料夾會輸入：
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

您應仔細規劃建立新的組態，以及如何針對 the Centralized Logging Service 定義新的屬性。 您應該謹慎進行變更，並確定您了解影響上您要適當地記錄問題案例的能力。 您應該將增強您能夠管理記錄檔大小的組態和變換期間，這樣它就會發生時，解決問題，進行變更。

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>若要移除現有的集中式記錄服務組態

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列提示字元處輸入下列命令：
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    例如，若要移除您建立來提高記錄檔變換時間的集中式記錄服務組態，增加變換記錄檔的大小，並設定的記錄檔快取位置到網路共用，如下所示：
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > 這是在 「 建立新的集中式記錄服務組態。 」 程序中建立的新組態

    
    </div>

如果您選擇移除網站層級設定，網站會使用全域設定。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的集中式的記錄服務概觀](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[管理 Lync Server 2013 中的集中式記錄服務組態設定](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-csclsconfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Get-csclsconfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Remove-csclsconfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

