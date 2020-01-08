---
title: Lync Server 2013：針對集中式記錄服務配置提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11af1a56e3975f96e19dc43dff27aef1d512ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中組態集中式記錄服務的提供者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-19_

集中式記錄服務*提供者*的概念與設定是最重要的功能之一。 *提供者*會直接對應到 lync server 追蹤模型中的 lync server server 角色元件。 提供者會定義要追蹤的 Lync Server 2013 元件、要收集的訊息類型（例如，致命、錯誤或警告），以及旗標（例如 TF\_CONNECTION 或 TF\_傳送程式）。 提供者是每個 Lync Server 伺服器角色中可追蹤的元件。 使用提供者，您可以定義元件的追蹤層級與類型（例如，S4、SIPStack、IM 和目前狀態）。 已定義的提供者會在案例中用來針對特定的邏輯集合，針對特定的問題條件來分組所有提供者。

若要使用 Lync Server 管理命令介面執行集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是包含下列其中一項的自訂 RBAC 角色：這兩個群組。 若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請從 Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主題的其餘部分將重點放在如何定義提供者、修改提供者以及提供者定義所包含的內容來優化您的疑難排解。 有兩種方式可以發出集中式記錄服務命令。 在預設\\情況下，您可以使用 CLSController 中的 [目錄 C： Program files\\] （\\Microsoft Lync Server 2013\\CLSAgent）常見檔案。 或者，您可以使用 Lync Server Management Shell 來頒發 Windows PowerShell 命令。 重要的區別是，當您在命令列中使用 CLSController 時，有一個有限的方案選擇，這些案例已定義且無法進行改變，但您可以定義記錄層級。 使用 Windows PowerShell，您可以定義在記錄會話中使用的新提供者，並完全控制自己的建立、收集的內容，以及它們收集資料的層級。

<div class="">


> [!IMPORTANT]  
> 如前文所述，提供者功能非常強大。 不過，案例的功能更強大，因為它們包含在提供者所代表的元件上設定和執行追蹤所需的所有資訊的 embodiment。 隨著案例成為提供者集合，與執行的批次處理檔案相比，這可能是鬆散的，在命令列中，您可以使用包含上百個命令的批次檔案來收集大量的資訊，而不是一次發出一個命令。<BR>[集中式記錄] 服務提供已為您定義的許多案例，而不是要求您深入瞭解提供者的詳細資料。 提供的案例涵蓋絕大多數您可能會遇到的問題。 在少數情況下，您可能需要建立並定義提供者，並將其指派給案例。 我們強烈建議您先熟悉所提供的各個案例，然後再調查需要建立新的提供者和案例的需求。 您可以在這裡找到有關建立提供者的資訊，讓您熟悉案例如何使用提供者元素來收集追蹤資訊，目前不提供提供者本身的詳細資料。



</div>

在[Lync Server 2013 中簡介集中式記錄服務](lync-server-2013-overview-of-the-centralized-logging-service.md)，定義案例中要使用之提供者的主要元素如下：

  - **提供者**   如果您熟悉 OCSLogger，提供者就是您選擇的元件，可告訴 OCSLogger 追蹤引擎應從哪個部分收集記錄。 提供者是相同的元件，且在許多情況下，與 OCSLogger 中的元件名稱相同。 如果您不熟悉 OCSLogger，提供者是集中式記錄服務可以從中收集記錄的伺服器角色特定元件。 在集中式記錄服務的情況下，CLSAgent 是集中式記錄服務的結構元件，可追蹤您在提供者配置中定義的元件。

  - **記錄層級**   OCSLogger 提供的選項可為收集的資料選擇詳細層級。 這個功能是集中式記錄服務和案例的有機組成部分，且由**Type**參數定義。 您可以從下列選項中進行選擇：
    
      - **All**   會收集已定義提供者記錄中類型為致命、錯誤、警告及資訊的追蹤訊息。
    
      - **[致命**   ] 只會收集指出已定義的提供者失敗的追蹤訊息。
    
      - **錯誤**   ：只收集指出已定義之提供者的錯誤的追蹤訊息，以及致命的訊息。
    
      - **警告**   ：只會收集指出已定義的提供者發出警告的追蹤訊息，以及致命及錯誤訊息。
    
      - **[資訊**   ] 只會收集指出已定義提供者的資訊訊息的追蹤訊息，以及致命、錯誤和警告訊息。
    
      - **詳細**   收集已定義提供者的所有類型為致命、錯誤、警告及資訊的追蹤訊息。

  - **旗標**   OCSLogger 提供選項，為每個提供者選擇一個定義您可以從追蹤檔案中檢索之資訊類型的提供者。 您可以根據提供者選擇下列標誌：
    
      - **TF\_** 連線   提供與連接相關的記錄專案。 這些記錄包含與特定元件建立的連線的相關資訊。 這也可能包含大量的網路層級資訊（也就是不含連線概念的元件）。
    
      - **TF\_security**   會提供與安全性有關的所有事件/記錄專案。 例如，在 SipStack 中，這些是安全事件，例如網域驗證失敗，以及用戶端驗證/授權失敗。
    
      - **TF\_** diagnostics   提供診斷事件，可供您用來診斷元件或對元件進行疑難排解。 例如，在 SipStack 中，這些是證書失敗，或 DNS 警告/錯誤。
    
      - **TF\_protocol**   提供通訊協定，例如 SIP 及組合的群組編解碼器套件訊息。
    
      - **TF\_元件**   可讓您登入指定為提供者一部分的元件。
    
      - **[全部**   ] 會設定提供者可用的所有可用旗標。

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>若要查看現有集中式記錄服務案例提供者的相關資訊

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要查看現有提供者的設定，請輸入下列內容：
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    例如，若要查看全域會議助理的相關資訊，請輸入：
    
        Get-CsClsScenario -Identity "global/CAA"
    
    該命令會顯示包含相關聯標誌、設定和元件的提供者清單。 如果顯示的資訊不足，或者清單對於預設的 Windows PowerShell 清單格式而言太長，您可以透過定義不同的輸出方法來顯示其他資訊。 若要這樣做，請輸入：
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    這個命令的輸出會以五行格式顯示每個提供者，其中包含提供者名稱、記錄類型、記錄層級、旗標、GUID 和角色，每個提供者都在個別的行上。

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>定義新的集中式記錄服務案例提供者

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  案例提供者包含要追蹤的元件、要使用的旗標，以及要收集的詳細資料層級。 若要執行此動作，請輸入：
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    例如，[追蹤提供者] 定義定義要收集哪些內容，以及從 Lyss 提供者的詳細資料層級看起來如下：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

– Level 會收集致命、錯誤、警告及資訊訊息。 所使用的標誌全都是為 Lyss 提供者所定義的，並且包含\_tf CONNECTION、\_tf 診斷和\_TF 通訊協定。

在定義 $LyssProvider 變數之後，您可以將它與**新的-CsClsScenario** Cmdlet 搭配使用，以從 Lyss 提供者收集蹤跡。 若要完成建立並將提供者指派給新的案例，請輸入：

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

其中 $LyssProvider 是包含使用**新 CsClsProvider**建立之已定義之案例的變數。

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>變更現有的集中式記錄服務案例提供者

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要更新或變更現有提供者的設定，請輸入：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    然後，您可以輸入下列內容來更新案例以指派提供者：
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

此命令的最終結果是案例網站： [雷德蒙]/[RedmondLyssInfo] 會針對指派給它的提供者更新旗標和層級。 您可以使用 [取得 CsClsScenario] 來查看新案例。 如需詳細資訊，請參閱[CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)。

<div class="">


> [!WARNING]  
> <STRONG>新的-ClsCsProvider</STRONG>不會檢查以判斷旗標是否有效。 請確定旗標（例如 TF_DIAG 或 TF_CONNECTION）拼寫正確無誤。 如果旗標沒有正確拼寫，提供者就無法傳回預期的記錄資訊。



</div>

如果您想要在此案例中新增其他提供者，請輸入下列專案：

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

每個使用 Add 指令定義的提供者，都已使用**新的-CsClsProvider**程式進行定義。

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>移除案例提供者

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  提供的 Cmdlet 可讓您更新現有的提供者，並建立新的提供者。 若要移除提供者，您必須使用提供者參數的 Replace 指令來**設定-CsClsScenario**。 完全移除提供者的唯一方式是將它替換成相同名稱的重新定義提供者，並使用 Update 指令。 例如，我們的提供者 LyssProvider 定義了 WPP 作為記錄類型、將層級設為 Debug，以及旗標與\_TF （tf\_）的組合。 您必須將 [旗標] 變更為 [全部]。 若要變更提供者，請輸入下列內容：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  如果您想要完全移除某個案例，以及與其相關聯的提供者，請輸入下列內容：
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    例如：
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > Cmdlet<STRONG>移除-CsClsScenario</STRONG>不會提示您進行確認。 隨後會刪除該案例，以及已指派給它的提供者。 您可以重新執行用來建立該案例的命令來重新建立。 沒有復原已移除之案例或提供者的程式。

    
    </div>

當您使用**CsClsScenario** Cmdlet 移除案例時，您會完全移除範圍中的案例。 若要使用您所建立的案例，以及該案例中的提供者，您可以建立新的提供者，並將它們指派給新的案例。

</div>

<div>

## <a name="see-also"></a>請參閱


[CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[新-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[移除-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[新-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

