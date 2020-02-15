---
title: Lync Server 2013： 設定集中式記錄服務提供的者
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
ms.openlocfilehash: 51dbb8c1a2e24290e4ab2805bed191e5f2dc86bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中設定集中式記錄服務提供的者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-03-19_

概念和集中式記錄服務中*提供者*的設定是 providers 的下列其中一個要掌握最重要。 *提供者*直接要對應的 Lync Server 追蹤模型中的 Lync Server 伺服器角色元件。 提供者定義的 Lync Server 2013，將會追蹤的郵件 （例如嚴重、 錯誤或警告） 來收集和旗標類型的元件 (例如，TF\_連線或 TF\_Diag)。 提供者是在每個 Lync Server 伺服器角色中的追蹤元件。 藉由使用提供者，可讓您定義在元件上追蹤的層級和類型 (例如 S4、SIPStack、IM 和目前狀態)。 定義的提供者會用於案例中，以針對處理特定問題狀況的某個邏輯集合來對所有提供者進行分組。

若要執行使用 Lync Server 管理命令介面的集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組或包含任一的自訂 RBAC 角色的成員這兩個群組。 若要傳回的所有清單 （包括您自行建立的任何自訂 RBAC 角色），獲指派此 cmdlet 的角色型存取控制 (RBAC) 角色會從 Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主題的其餘內容將特別針對定義提供者、修改提供者的方式，及提供者定義所包含的內容做討論，以使您的疑難排解作業獲得最佳成效。 有兩種方式來發出 Centralized Logging Service 命令。 您可以使用位於，根據預設，在目錄 c: CLSController.exe\\Program Files\\通用檔案\\Microsoft Lync Server 2013\\clsagent 的通訊。 或者，您可以使用 Lync Server 管理命令介面來發出 Windows PowerShell 命令。 其中重要區別在於，當您在命令列上使用 CLSController.exe 時，選擇會侷限於提供者已定義好而無法變更的可用案例中，但您可以定義記錄層級。 使用 Windows PowerShell，您可以定義新的提供者使用您記錄工作階段中並具有完全控制權其建立、 項目會收集，並在哪些層級會收集資料。

<div class="">


> [!IMPORTANT]  
> 如前所述，提供者的功能強大。不過，案例的作用卻更為強大，因為它們包含全部所需具體資訊，可用以在提供者代表的元件上設定和執行追蹤作業。若與做為提供者集合的案例進行約略比較，它就像執行包含數百個命令的批次檔，可用來收集大量資訊，而非在命令列上以一次一個的方式發行數百個命令。<BR>而不需要您深度深入的提供者的詳細資料，the Centralized Logging Service 會為您提供了數已定義的案例。 所提供的案例涵蓋您可能會遭遇的絕大多數問題。 在一些罕見的情況下，您可能需建立並定義提供者，並將其指派給案例。 我們強烈建議您在調查需求以建立新提供者和案例前，先熟悉所提供的每個案例。 您可在這裡找到建立提供者的資訊，以熟悉案例使用提供者元素收集追蹤資訊的方式，而此時並不會提供提供者本身的詳細資料。



</div>

[Overview of the Centralized Logging Service 中 Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)中引進，定義案例中的 [使用的提供者的主要元素為：

  - **提供者**   提供者如果您已熟悉 OCSLogger，是您選擇要告訴 OCSLogger 追蹤引擎應從中收集記錄的元件。 提供者是相同的元件，以及在許多情況下元件相同的名稱中包含 OCSLogger。 如果您不熟悉 OCSLogger，提供者是伺服器角色，the Centralized Logging Service 可以收集特定元件的記錄。 若是 the Centralized Logging Service，clsagent 的通訊是 the Centralized Logging Service，所做的動作，您定義的提供者設定中的元件追蹤架構的一部分。

  - **記錄層級**   OCSLogger 提供選擇的詳細資料收集的資料層級數目。 這項功能是不可或缺的一部分的集中式記錄服務和案例中，與**Type**參數所定義。 您可以選擇下列項目：
    
      - **所有**   記錄檔收集追蹤郵件類型為嚴重、 錯誤、 警告及資訊已定義的提供者。
    
      - **嚴重**   收集僅針對已定義的提供者表示失敗的追蹤訊息。
    
      - **錯誤**   收集只定義的提供者，表示錯誤的追蹤訊息以及嚴重訊息。
    
      - **警告**   收集只追蹤訊息，指出一則警告，已定義的提供者，以及嚴重和錯誤訊息。
    
      - **資訊**   收集只追蹤訊息，指出資訊訊息已定義的提供者，以及嚴重、 錯誤和警告訊息。
    
      - **Verbose**   已定義的提供者會收集所有的類型為嚴重、 錯誤、 警告和資訊的追蹤訊息。

  - **Flags**   OCSLogger 所提供的選項的定義哪些類型的資訊您每個提供者無法擷取追蹤檔案中，選擇 [旗標。 您可以依據提供者選擇下列旗標：
    
      - **TF\_連線**   提供連線相關的記錄項目。 這些記錄檔包含建立到及傳送自特定元件的連線資訊。 這也可能包含重要的網路層級資訊 (也就是沒有連線的概念的元件)。
    
      - **TF\_安全性**   提供安全性相關的所有事件/記錄項目。 例如，如裡包含 SipStack，這些是安全性事件，例如網域驗證失敗和用戶端驗證和授權失敗。
    
      - **TF\_Diag**   提供您可用於診斷或疑難排解元件的診斷事件。 例如，如裡包含 SipStack，這些是憑證失敗或 DNS 警告/錯誤。
    
      - **TF\_通訊協定**   提供 SIP 和結合社群轉碼器套件訊息等通訊協定訊息。
    
      - **TF\_元件**   可登入指定做為提供者的一部分的元件。
    
      - **所有**   設定提供者可用的所有可用旗標。

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>若要檢閱現有的集中式記錄服務案例提供者的資訊

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  若要檢視現有提供者的設定，請輸入下列項目：
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    例如，若要檢視全域會議服務員的資訊，請輸入：
    
        Get-CsClsScenario -Identity "global/CAA"
    
    命令會顯示內含相關旗標、設定和元件的提供者清單。 如果顯示的資訊不足或清單的預設 Windows PowerShell 的清單格式太長，您可以藉由定義不同的輸出方法來顯示其他資訊。 若要進行這項作業，請輸入：
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    此命令的輸出會以五行的格式顯示每名提供者，其中包含提供者名稱、記錄類型、記錄層次、旗標、GUID 和角色，每個項目位於個別一行。

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>若要定義新的集中式記錄服務案例提供者

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  案例提供者是由待追蹤的元件、要使用的旗標和收集的詳細資料等級所組成。若要進行這項作業，請輸入：
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    例如，追蹤提供者的定義會定義收集的項目及來自如下所示之 Lyss 提供者的詳細資料層級：
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

–Level 會收集嚴重、錯誤、警告和資訊訊息。 使用的旗標所定義之 Lyss 提供者的所有且包含 TF\_連線、 TF\_Diag 和 TF\_通訊協定。

在定義變數 $LyssProvider 之後，您可以透過 **New-CsClsScenario** Cmdlet 加以使用，以便收集來自 Lyss 提供者的追蹤。 若要完成建立提供者，或將其指派給新案例，請輸入：

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

當中的 $LyssProvider 是變數，其中包含與 **New-CsClsProvider** 一起建立之已定義的案例。

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>若要變更現有的集中式記錄服務案例提供者

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

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

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  所提供的 Cmdlet 可讓您新增現有的提供者以及建立新的提供者。 若要移除提供者，您必須針對 **Set-CsClsScenario** 的 Provider 參數使用 Replace 指示詞。 完全移除提供者的唯一方式，是以相同名稱之重新定義的提供者來加以取代，並使用 Update 指示詞。 例如，我們 LyssProvider 以 WPP 做為記錄類型定義的提供者，level 設為偵錯]，且旗標設定 TF\_連線和 TF\_斜筆 您需將旗標變更為“All”。 若要變更提供者，請輸入下列項目：
    
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


[Get-csclsscenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[New-csclsscenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[Remove-csclsscenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-csclsscenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[New-csclsprovider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

