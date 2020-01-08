---
title: 使用「開始」進行集中式記錄服務來捕獲記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5033b4a8dfd8121e2f0b5926623a55358188935e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>在 Lync Server 2013 中使用 [開始使用集中式記錄服務] 來捕獲記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

若要使用集中式記錄服務來捕獲追蹤記錄，您需要發出命令，以便在一或多部電腦和池上開始記錄。 您也可以發出定義哪些電腦或池、要執行哪些情況（例如，AlwaysOn、另一個預先定義的案例或您所建立之案例）的參數，以及要追蹤哪些 Lync Server 元件（例如，S4、SipStack）。

若要捕獲正確的資訊，您必須確認使用正確的案例，才能收集與問題相關的資訊。 在集中式記錄服務中，案例是根據伺服器元件集合、記錄層級和旗標來開啟記錄的概念，這比要在每個伺服器上定義這些元素更有效率且更有用。 您定義並指定要執行的案例，並在整個基礎結構範圍中的所有伺服器和池上一致地執行該案例。

預設案例稱為 [ **AlwaysOn**]。 AlwaysOn 的預期用途是經常執行該案例，因為案例的名稱所隱含。 AlwaysOn 案例會收集資訊層級資訊（請注意，資訊記錄層級除了資訊訊息之外，還包含許多最常見伺服器元件的致命、錯誤和警告）。 AlwaysOn 會在問題發生之前、期間及之後收集資訊。 這與前一筆記錄工具（例如 OCSLogger）的一般行為有顯著的差異。 您在問題發生之後執行了 OCSLogger，因為您所擁有的資料是被動而非主動，所以您的疑難排解工作變得更困難。 如果 AlwaysOn 不包含您要尋找的資訊，而是要指向問題元件，並指出一個動作程式來修正它（不太可能是在 AlwaysOn 中提供提供者的廣度與深度），它會指出適當的資訊層級rmation 以判斷您需要執行的其他動作，例如建立新案例、收集其他資訊、執行不同的搜尋，以收集更專注的詳細資料等等。

集中式記錄服務提供兩種方式來發出命令。 您可以透過 Lync Server 管理命令介面，在 Windows PowerShell 中，有許多主題是以焦點恰好的方式進行。 使用許多複雜的設定和命令的能力，有利於使用 Windows PowerShell 來集中式記錄服務。 因為 Windows PowerShell 透過 Lync server 管理命令介面幾乎無處不在 Lync Server 中的所有函數，所以只討論 Windows PowerShell 命令。

<div>


> [!NOTE]
> 如果您決定使用可從命令列使用的有限命令集，您可以輸入<CODE>ClsController.exe</CODE>CLSController 以取得協助。 根據預設， <STRONG>ClsController</STRONG>會安裝在目錄 C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent 中。



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>使用基本命令在 Windows PowerShell 中執行開始 CsClsLogging

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  輸入以下內容，以集中式記錄服務開機記錄案例：
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    例如，若要啟動**AlwaysOn**案例，請輸入：
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > AlwaysOn 案例沒有預設的持續時間。 這個案例將會在您明確地停止使用<STRONG>CsClsLogging</STRONG> Cmdlet 之前執行。 如需詳細資訊，請參閱<A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">停止 CsClsLogging</A>。 在所有其他案例中，預設期間是4小時。

    
    </div>

3.  按 Enter 以執行命令。
    
    <div>
    

    > [!NOTE]
    > 您可能需要花很短的時間（30到60秒），才能執行這些命令，並從您的部署中的電腦接收傳回的狀態。

    
    </div>
    
    ![正在執行開始-CsClsLogging。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "正在執行開始-CsClsLogging。")

4.  若要開始其他案例，請使用**CsClsLogging** Cmdlet 及其他案例的名稱來執行，如下所示（例如，案例**驗證**）：
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > 您可以隨時在任何指定電腦上執行兩種情況。 如果命令是全域在範圍中，則您部署中的所有電腦都會執行案例或案例。 若要開始第三個案例，您必須停止記錄您想要在其上執行新案例的電腦、池、網站或全域範圍。 如果您已開始全域範圍，您可以在一或多部電腦和池上停止記錄一或兩個案例的記錄。 如需管理正在執行哪些案例的詳細資訊，請參閱<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 Lync Server 2013 中針對集中式記錄服務使用 [停止</A>]，然後<A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">CsClsLogging [停止</A>]。

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>使用 [高級命令] 在 Windows PowerShell 中執行開始 CsClsLogging

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  還有其他參數可供您記錄管理命令。 您可以使用-Duration 來調整案例執行的時間長度。 您也可以在電腦上定義電腦的完整功能變數名稱（Fqdn）清單，並以逗號（或-Pool）分隔，您想要執行記錄的池以逗號分隔的 Fqdn 清單。
    
    您在「pool01.contoso.net」的 [ *UserReplicator* ] 案例中開機記錄會話。 您也可以在8小時定義記錄會話的持續時間。 若要這樣做，請輸入：
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    這個案例的成功執行會傳回如下所示的結果：
    
    ![正在執行開始-CsClsLogging。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "正在執行開始-CsClsLogging。")
    
    請注意，在這個範例中，AlwaysOn 案例正在執行，且 UserReplicator 案例正在執行。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的集中式記錄服務概覽](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

