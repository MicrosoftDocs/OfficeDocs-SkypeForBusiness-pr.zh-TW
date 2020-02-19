---
title: 將 Start 用於集中式記錄服務以擷取記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ef2900d66796ec261e7abd9c8c6d910eb6c0e81
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>將 Start 用於集中式記錄服務以擷取在 Lync Server 2013 中的記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

若要擷取使用集中式記錄服務的追蹤記錄檔，您會發出命令，以開始登入一或多個電腦和集區。 您也發出的電腦或集區]，定義的參數 （例如 AlwaysOn、 另一個預先定義的案例中或您已建立的案例） 執行哪些案例、 追蹤哪些 Lync Server 元件 （例如，S4 裡包含 SipStack）。

為了擷取正確的資訊，您必須確定使用正確的案例來收集問題的相關資訊。 在集中式記錄服務中，分析藍本是開啟記錄根據一群伺服器元件、 記錄層級和旗標，也就更有效率且實用比不必在各伺服器上定義這些元素的概念。 您可以定義及指定要執行的案例，這些案例會在基礎結構範圍內的所有伺服器和集區上持續執行。

預設案例稱為 **AlwaysOn**。AlwaysOn 的預定目的是持續執行案例 (如案例名稱所指)。AlwaysOn 案例針對許多最常見的伺服器元件，收集資訊層級的資訊 (請注意，資訊記錄層次除了資訊訊息之外，還包含 [嚴重]、[錯誤] 及 [警告])。AlwaysOn 會收集發生問題前後及期間的資訊。這與之前的記錄工具 (例如 OCSLogger) 的一般行為大不相同。您會在發生問題之後執行 OCSLogger，這讓疑難排解工作更加困難，因為您擁有的資料只會被動回應，而無法主動解決問題。如果 AlwaysOn 所包含的資訊，不是您想要指向問題元件及指出修正步驟的資訊 (在 AlwaysOn 提供者的深度和廣度下，此情形並不常見)，AlwaysOn 會指出合理的資訊層級，以決定必須執行的其他動作，例如建立新的案例、收集其他資訊、執行其他搜尋以收集更集中的詳細資料等。

The Centralized Logging Service 提供兩種問題的命令。 主題數目有跡象著重於使用透過 Lync Server 管理命令介面的 Windows PowerShell。 若要使用的複雜的組態和命令的數字的能力偏好 Centralized Logging Service 使用 Windows PowerShell。 透過 Lync Server 管理命令介面的 Windows PowerShell 是幾乎無所不在的 Lync Server 中的所有功能，因為會討論僅限 Windows PowerShell 命令。

<div>


> [!NOTE]
> 如果您決定使用有限的命令設定能從命令列，您可以使用取得說明 CLSController.exe 輸入<CODE>ClsController.exe</CODE>。 根據預設， <STRONG>ClsController.exe</STRONG>安裝在目錄 C:\Program Files\Microsoft Lync Server 2013\ClsAgent。



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>若要使用 Windows PowerShell 使用基本命令執行 Start-csclslogging

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  從 the Centralized Logging Service 記錄案例開始輸入下列命令：
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    例如，若要啟動 **AlwaysOn** 案例，請輸入：
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > AlwaysOn 案例沒有預設期間。 此案例會一直執行，直到您使用 <STRONG>Stop-CsClsLogging</STRONG> Cmdlet 明確加以停止。 如需詳細資訊，請參閱＜<A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>＞。 其他所有案例的預設期間為 4 小時。

    
    </div>

3.  按 Enter 鍵執行命令。
    
    <div>
    

    > [!NOTE]
    > 可能需要一點時間 (30 到 60 秒) 才能執行命令，並接收部署中的電腦傳回的狀態。

    
    </div>
    
    ![執行 Start-csclslogging。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "執行 Start-csclslogging。")

4.  若要啟動另一種情況，使用**Start-csclslogging** cmdlet 的其他案例名稱來執行，如下所示 （例如，「**驗證**」 案例）：
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > 在任何時候，最多可以在任何指定的電腦上執行兩個案例。 如果命令的範圍為全域，部署中的所有電腦都會執行這些案例。 若要啟動第三個案例，您必須從要執行新案例的電腦、集區、網站或全域範圍停止記錄。 如果已啟動全域範圍，您可以在一或多部電腦和集區上停止記錄一或兩個案例。 如需管理案例正在執行哪些，請參閱<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">使用集中式記錄服務的 Lync Server 2013 中停止</A>並<A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-csclslogging</A>。

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>若要使用 Windows PowerShell 使用進階的命令執行 Start-csclslogging

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  您可以使用其他參數管理記錄命令。 您可以使用 –Duration 調整執行案例的時間長度。 您也可以定義 –Computers，以逗號分隔列出完整網域名稱 (FQDN)；或定義 –Pools，以逗號分隔列出執行記錄所在集區的 FQDN。
    
    您在集區 」 pool01.contoso.net 」 上啟動*UserReplicator*案例記錄工作階段。 您也可以將記錄工作階段期間定義為 8 小時。 若要執行這項操作，請輸入：
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    成功執行此案例會傳回類似如下的結果：
    
    ![執行 Start-csclslogging。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "執行 Start-csclslogging。")
    
    請注意，在此範例中，AlwaysOn 案例和 UserReplicator 案例都在執行中。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的集中式的記錄服務概觀](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

