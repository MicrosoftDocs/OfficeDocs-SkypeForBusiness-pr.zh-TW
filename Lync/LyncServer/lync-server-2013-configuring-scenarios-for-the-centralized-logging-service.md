---
title: Lync Server 2013：組態集中式記錄服務的案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc0be2ac6459c34546de41ee7e2c709e0d0c0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中組態集中式記錄服務的案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

案例定義範圍（即全域、網站、池或電腦），以及要在集中式記錄服務中使用的提供者。 使用案例，您可以啟用或停用提供者的追蹤功能（例如，S4、SIPStack、IM 和目前狀態）。 透過設定案例，您可以將特定的邏輯集合的所有提供者分組，以解決特定問題的情況。 如果您發現案例需要修改以符合您的疑難排解和記錄需要，則 Lync Server 2013 調試工具會提供名為 ClsController 的 Windows PowerShell 模組，其中包含名為*Edit-CsClsScenario*的函數 *。* 模組的用途是編輯命名案例的屬性。 本主題提供此模組運作方式的範例。 Lync Server 2013 調試工具會從下列連結下載：[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> 針對任何指定的範圍（網站、全域、池或電腦），您最多可以在任何指定時間執行兩種案例。 若要判斷目前正在執行哪些案例，請使用 Windows PowerShell 並<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">CsClsScenario</A>。 透過使用 Windows PowerShell 和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">設定 CsClsScenario</A>，您可以動態變更正在執行的案例。 您可以修改記錄會話期間執行的案例，以調整或精煉您要收集的資料，以及從哪些提供者處。



</div>

若要使用 Lync Server 管理命令介面執行集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是包含下列任一項的自訂 RBAC 角色：在這兩個群組中。 若要傳回這個 Cmdlet 已獲指派的所有 RBAC 角色清單，包括您自行建立的任何自訂 RBAC 角色，請從 Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主題的其餘部分將重點放在如何定義案例、修改案例、檢索正在執行的案例、移除案例，以及指定案例中所包含的專案，以優化您的疑難排解。 有兩種方式可以發出集中式記錄服務命令。 在預設\\情況下，您可以使用 CLSController 中的 [目錄 C： Program files\\] （\\Microsoft Lync Server 2013\\CLSAgent）常見檔案。 或者，您可以使用 Lync Server Management Shell 來頒發 Windows PowerShell 命令。 重要的區別是，當您在命令列中使用 CLSController 時，會有有限的可用案例選項。 當您使用 Windows PowerShell 時，您可以定義在記錄會話中使用的新案例。

如[Lync Server 2013 中的集中式記錄服務簡介](lync-server-2013-overview-of-the-centralized-logging-service.md)所述，該案例的元素如下：

  - **提供者**   如果您熟悉 OCSLogger，提供者就是您選擇的元件，可告訴 OCSLogger 追蹤引擎應從哪個部分收集記錄。 提供者是相同的元件，且在許多情況下，與 OCSLogger 中的元件名稱相同。 如果您不熟悉 OCSLogger，提供者是集中式記錄服務可以從中收集記錄的伺服器角色特定元件。 如需提供者設定的詳細資料，請參閱[在 Lync Server 2013 中設定集中式記錄服務的提供者](lync-server-2013-configuring-providers-for-centralized-logging-service.md)。

  - **身分識別**   參數–身分識別案例的範圍和名稱。 例如，您可以設定範圍 "global"，並以 "LyssServiceScenario" 識別案例。 當您結合兩個時，您會定義身分識別（例如，"global/LyssServiceScenario"）。
    
    或者，您也可以使用– Name 和– Parent 參數。 您可以定義 Name 參數來唯一識別該案例。 如果您使用 [名稱]，您也必須使用上層將案例新增至 [全域] 或 [網站]。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您使用 Name 和 Parent 參數，就無法使用–身分<STRONG>識別</STRONG>參數。

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>使用新的-CsClsScenario Cmdlet 建立新的案例

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要建立記錄會話的新案例，請使用[新的-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)並定義案例的名稱（也就是唯一識別該案例的方式）。 從 WPP （也就是 Windows 軟體追蹤預處理程式及預設值）、EventLog （也就是 Windows 事件記錄檔格式）或 IISLog （也就是以 IIS 日誌檔案格式為基礎的 ASCII 格式檔案），選擇一種記錄格式。 接著，定義階層（如本主題中的記錄層級所定義），以及旗標（如本主題中的 [旗標] 所定義）。
    
    在這個範例案例中，我們使用 LyssProvider 做為範例提供者變數。
    
    若要使用定義的選項建立案例，請輸入：
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    例如：
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    使用– Name 與– Parent 的替代格式：
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>使用新的-CsClsScenario Cmdlet 來建立多個提供者的新案例

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  每個範圍限制在兩個案例中。 不過，您不受限於一組提供者數目的限制。 在這個範例中，假設我們已建立三個提供者，而且您想要將這三個程式指派給您所定義的情況。 提供者變數名稱為 LyssProvider、ABServerProvider 和 SIPStackProvider。 若要定義多個提供者並將其指派給某個案例，請在 Lync Server 管理命令介面或 Windows PowerShell 命令提示字元輸入下列專案：
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > 就像在 Windows PowerShell 中已知一樣，建立使用<CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE>的雜湊值資料表的慣例稱為<EM>splatting</EM>。 如需有關 Windows PowerShell 中 splatting 的詳細<A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>資訊，請參閱。

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>使用 CsClsScenario Cmdlet 修改現有的案例

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  每個範圍限制在兩個案例中。 您可以隨時變更正在執行的案例，即使正在進行記錄捕獲會話也一樣。 如果您重新定義執行中的案例，目前的記錄會話將停止使用已移除的案例，然後開始使用新的案例。 不過，已移除之案例所捕獲的記錄資訊會保留在捕獲的記錄中。 若要定義新的案例，請執行下列動作（也就是假設已將已定義的提供者加上名為 "S4Provider"）：
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    例如：
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    如果您想要取代提供者，請定義單一提供者或逗號分隔的提供者清單，以取代目前的集合。 如果您只想要取代其中一個提供者，請將目前的提供者新增至新的提供者，以建立一組新的提供者，以包含新的提供者與現有的提供者。 若要將所有提供者替換成新的集合，請輸入下列內容：
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    例如，若要以 $LyssServiceProvider 取代目前的一組 $LyssProvider、$ABServerProvider 及 $SIPStackProvider：
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    若要只用 $LyssServiceProvider 的目前 $LyssProvider 集合、$ABServerProvider 和 $SIPStackProvider 來取代 $LyssProvider 提供者，請輸入下列內容：
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>使用 CsClsScenario Cmdlet 移除現有的案例

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  如果您想要移除先前定義的案例，請輸入下列專案：
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    例如，若要移除已定義的案例網站：雷德蒙/LyssServiceScenario：
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

**CsClsScenario** Cmdlet 會移除指定的案例，但已捕獲的跟蹤仍可供您在記錄中搜尋。

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>使用 ClsController psm1 模組載入和卸載編輯 CsClsScenario Cmdlet

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。
    
    <div>
    

    > [!IMPORTANT]  
    > ClsController psm1 模組是作為單獨的網頁下載提供。 模組是 Lync Server 2013 調試工具的一部分。 根據預設，調試工具會安裝在目錄 C:\Program Files\Lync Server 2013 \ 調試工具中。

    
    </div>

2.  在 Windows PowerShell 中，鍵入：
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > 成功載入模組時，會將您傳回 Windows PowerShell 命令提示字元。 若要確認是否已載入模組，且可以使用編輯 CsClsScenario，請輸入<CODE>Get-Help Edit-CsClsScenario</CODE>。 您應該會看到 EditCsClsScenario 語法的基本摘要。

    
    </div>

3.  若要卸載模組，請輸入：
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > 成功卸載該模組後，就會傳回您至 Windows PowerShell 命令提示字元。 若要確認已卸載該模組，請<CODE>Get-Help Edit-CsClsScenario</CODE>輸入。 Windows PowerShell 會嘗試找出 Cmdlet 的說明並失敗。

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>使用 [編輯 ClsController] 模組從案例中移除現有的提供者

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要從 AlwaysOn 案例中移除提供者，請輸入：
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    例如：
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    參數 ScenarioName 和 ProviderName 是位置（也就是說，它們必須在命令列的預期位置中定義）參數。 如果案例名稱是位於第二個位置，且提供者的位置是以位置1為 Cmdlet 的名稱，則無需要明確定義參數名稱。 使用這項資訊，前一個命令會輸入如下：
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    放置參數值的位置只適用于–案例和–提供者。 所有其他參數都必須明確定義。

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>使用編輯 ClsController 模組將提供者新增到案例

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要將提供者新增至 AlwaysOn 案例，請輸入：
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    例如：
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-Loglevel 可以是 [致命]、[錯誤]、[警告]、[資訊]、[調試] 或 [全部] 的類型。 –旗可以是提供者所支援的任何標誌，例如 TF\_COMPONENT、tf settings。\_ –標誌也可以是 ALL 值
    
    您也可以使用 Cmdlet 的位置功能，在前面的範例中進行輸入。 例如，若要將提供者 ChatServer 新增至 AlwaysOn 案例，請輸入：
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

