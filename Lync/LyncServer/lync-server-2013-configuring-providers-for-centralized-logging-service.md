---
title: Lync Server 2013：設定集中式記錄服務的提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5d280d05089c4f1efc4fd8c54ab4841d24621d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535000"
---
# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中設定集中式記錄服務的提供者

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-19_

集中式記錄服務中 *提供者* 的概念和設定是最重要的一點。 *提供者*會直接對應至 lync server 追蹤模型中的 lync server server 角色元件。 提供者會定義將要追蹤的 Lync Server 2013 元件、郵件類型 (例如，要收集的郵件類型、嚴重、錯誤、警告) ，以及旗標 (例如 TF \_ Connection 或 tf the \_) 。 提供者是每個 Lync Server server role 中可追蹤的元件。 藉由使用提供者，可讓您定義在元件上追蹤的層級和類型 (例如 S4、SIPStack、IM 和目前狀態)。 定義的提供者會用於案例中，以針對處理特定問題狀況的某個邏輯集合來對所有提供者進行分組。

若要使用 Lync Server 管理命令介面來執行集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之一的自訂 RBAC 角色。 若要傳回所有角色型存取控制的清單 (RBAC) role 此 Cmdlet 已指派給 (包括您) 自行建立的任何自訂 RBAC 角色，請從 [Lync Server 管理命令介面] 或 [Windows PowerShell] 提示字元執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主題的其餘內容將特別針對定義提供者、修改提供者的方式，及提供者定義所包含的內容做討論，以使您的疑難排解作業獲得最佳成效。 有兩種方式可發出集中式記錄服務命令。 在下列目錄中，您可以使用 \\ \\ \\ Microsoft Lync Server 2013 CLSAgent 中的目錄 C： Program Files 通用檔案中所 CLSController.exe 的預設值 \\ 。 或者，您可以使用 Lync Server 管理命令介面來發出 Windows PowerShell 命令。 其中重要區別在於，當您在命令列上使用 CLSController.exe 時，選擇會侷限於提供者已定義好而無法變更的可用案例中，但您可以定義記錄層級。 使用 Windows PowerShell，您可以定義在記錄會話中使用的新提供者，並對其建立、他們收集的內容，以及收集資料的層級有完全的控制權。

<div class="">


> [!IMPORTANT]  
> 如前所述，提供者的功能強大。不過，案例的作用卻更為強大，因為它們包含全部所需具體資訊，可用以在提供者代表的元件上設定和執行追蹤作業。若與做為提供者集合的案例進行約略比較，它就像執行包含數百個命令的批次檔，可用來收集大量資訊，而非在命令列上以一次一個的方式發行數百個命令。<BR>集中式記錄服務會提供許多已經為您定義的案例，而不需要您深入瞭解提供者的詳細資料。 所提供的案例涵蓋您可能會遭遇的絕大多數問題。 在一些罕見的情況下，您可能需建立並定義提供者，並將其指派給案例。 我們強烈建議您在調查需求以建立新提供者和案例前，先熟悉所提供的每個案例。 您可在這裡找到建立提供者的資訊，以熟悉案例使用提供者元素收集追蹤資訊的方式，而此時並不會提供提供者本身的詳細資料。



</div>

簡介：在 [Lync Server 2013 中引入集中式記錄服務](lync-server-2013-overview-of-the-centralized-logging-service.md)，定義提供者以用於案例中的主要元素包括：

  - **提供者**    如果您熟悉 OCSLogger，提供者就是您所選擇的元件，以告知 OCSLogger 追蹤引擎應從何處收集記錄。 提供者是相同的元件，在許多情況下，與 OCSLogger 中的元件具有相同的名稱。 如果您不熟悉 OCSLogger，提供者是集中式記錄服務可從中收集記錄的伺服器角色特定元件。 在集中式記錄服務的情況下，CLSAgent 是集中式記錄服務的架構元件，它會執行您在提供者設定中所定義的元件追蹤。

  - **記錄層級**    OCSLogger 提供選擇所收集資料的詳細資料層級的選項。 這項功能是集中式記錄服務和案例中不可或缺的一部分，並由 **Type** 參數定義。 您可以選擇下列項目：
    
      - **全部**    針對已定義的提供者，將類型為嚴重、錯誤、警告和資訊的追蹤訊息收集到記錄檔。
    
      - **致命**    只收集指出定義的提供者失敗的追蹤訊息。
    
      - **錯誤**    只收集指出已定義提供者的錯誤的追蹤訊息，以及致命的訊息。
    
      - **警告**    只收集表示已定義提供者的警告的追蹤訊息，以及致命錯誤和錯誤訊息。
    
      - **資訊**    只收集表明已定義的提供者的資訊訊息的追蹤訊息，加上嚴重、錯誤和警告訊息。
    
      - **Verbose**    針對已定義的提供者，收集類型為嚴重、錯誤、警告和資訊的所有追蹤訊息。

  - **旗標**    OCSLogger 提供的選項可為定義您從追蹤檔案中取得的資訊類型的每個提供者選擇旗標。 您可以依據提供者選擇下列旗標：
    
      - **TF \_Connection**     提供連線相關的記錄專案。 這些記錄檔包含與特定元件建立之連接的相關資訊。 這也可能包括大量的網路層級資訊 (，也就是針對不含 connection) 概念的元件。
    
      - **TF \_安全性**     提供所有與安全性相關的事件/記錄專案。 例如，針對 SipStack，這些是安全性事件，例如網域驗證失敗，以及用戶端驗證/授權失敗。
    
      - **TF \_診斷**     程式提供診斷事件，可供您用來診斷或疑難排解元件。 例如，針對 SipStack，這些是憑證失敗或 DNS 警告/錯誤。
    
      - **TF \_通訊協定**     提供通訊協定和組合的群組編解碼器封包訊息。
    
      - **TF \_元件**     可對指定為提供者一部分的元件進行記錄。
    
      - **全部**    設定提供者可使用的所有可用旗標。

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>若要查看現有集中式記錄服務案例提供者的相關資訊

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要檢視現有提供者的設定，請輸入下列項目：
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    例如，若要檢視全域會議服務員的資訊，請輸入：
    
        Get-CsClsScenario -Identity "global/CAA"
    
    命令會顯示內含相關旗標、設定和元件的提供者清單。 如果顯示的資訊不夠，或是預設 Windows PowerShell 清單格式的清單過長，您可以透過定義不同的輸出方法來顯示其他資訊。 若要進行這項作業，請輸入：
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    此命令的輸出會以五行的格式顯示每名提供者，其中包含提供者名稱、記錄類型、記錄層次、旗標、GUID 和角色，每個項目位於個別一行。

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>若要定義新的集中式記錄服務案例提供者

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  案例提供者是由待追蹤的元件、要使用的旗標和收集的詳細資料等級所組成。若要進行這項作業，請輸入：
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    例如，追蹤提供者的定義會定義收集的項目及來自如下所示之 Lyss 提供者的詳細資料層級：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level 會收集嚴重、錯誤、警告和資訊訊息。 使用的旗標全都為 Lyss 提供者所定義，並包含 TF \_ Connection、tf \_ 診斷和 TF \_ Protocol。

在定義變數 $LyssProvider 之後，您可以透過 **New-CsClsScenario** Cmdlet 加以使用，以便收集來自 Lyss 提供者的追蹤。 若要完成建立提供者，或將其指派給新案例，請輸入：

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

當中的 $LyssProvider 是變數，其中包含與 **New-CsClsProvider** 一起建立之已定義的案例。

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>變更現有的集中式記錄服務案例提供者

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要更新或變更現有提供者的設定，請輸入：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    然後您可輸入下列項目來更新案例，以指派提供者：
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

命令的最終結果是，案例 site:Redmond/RedmondLyssInfo 會有更新的旗標和層級供指派給案例的提供者使用。 您可以使用 Get-CsClsScenario 檢視新案例。 如需詳細資訊，請參閱 [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)。

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> 不會進行檢查來決定旗標是否有效。 請確認旗標的拼字 (例如 TF_DIAG 或 TF_CONNECTION) 正確無誤。 如果旗標的拼字不正確，提供者就無法傳回預期的記錄資訊。



</div>

如果您想要將其他提供者新增至此案例，請輸入下列項目：

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

在那裏，使用「新增」指示詞加以定義的每個提供者，都已經使用 **New-CsClsProvider** 程序加以定義。

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>移除案例提供者

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  所提供的 Cmdlet 可讓您新增現有的提供者以及建立新的提供者。 若要移除提供者，您必須針對 **Set-CsClsScenario** 的 Provider 參數使用 Replace 指示詞。 完全移除提供者的唯一方式，是以相同名稱之重新定義的提供者來加以取代，並使用 Update 指示詞。 例如，我們的提供者 LyssProvider 會定義為 WPP 為記錄類型、設定為調試的層級，而旗標為 TF \_ CONNECTION 和 tf the \_ 。 您需將旗標變更為“All”。 若要變更提供者，請輸入下列項目：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  若要完全移除某案例和與其相關的提供者，請輸入下列項目：
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    例如：
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > Cmdlet <STRONG>Remove-CsClsScenario</STRONG> 不會提示您進行確認。 案例會連同指派給它的提供者一併遭刪除。 您可以重新執行一開始用來建立案例的命令以重新建立案例。 您無法還原遭移除的案例或提供者。

    
    </div>

在使用 **Remove-CsClsScenario** Cmdlet 移除案例時，您可以將案例從範圍完全移除。 若要使用您建立的案例，及使用做為案例之一部分的提供者，您需建立新的提供者，並將其指派給新的案例。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

