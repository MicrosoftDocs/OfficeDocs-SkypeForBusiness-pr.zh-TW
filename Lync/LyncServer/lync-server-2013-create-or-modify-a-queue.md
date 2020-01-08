---
title: Lync Server 2013：建立或修改佇列
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6bc1e5f956b5b975e14f07a3c37f2802d1b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改佇列

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

使用下列其中一個程式來建立或修改佇列。

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>使用 Lync Server [控制台] 來建立或修改佇列

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。
    
    <div>
    

    > [!NOTE]  
    > 如果您是受管理工作流程的委派回應群組管理員之一，您可以建立或修改回應群組佇列，並將其指派給您管理的工作流程。

    
    </div>

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**佇列**]。

4.  在 [**佇列**] 頁面上，執行下列其中一項操作：
    
      - 若要建立新的佇列，請按一下 [**新增**]。 在 [**選取服務**] 中，在 [搜尋] 欄位中，輸入您要新增佇列之**ApplicationServer**服務的部分或所有名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。
    
      - 若要修改現有的佇列，請在 [搜尋] 欄位中輸入全部或部分的佇列名稱。 在產生的佇列清單中，按一下您想要的佇列，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**名稱**] 中，輸入佇列的識別名稱。

6.  在 [**描述**] 中，輸入佇列的描述。

7.  在 [**群組**] 中，指定您要指派給佇列的群組。 請執行下列其中一項操作：
    
      - 若要在佇列中新增群組，請按一下 [**選取**]。 在 [**選取群組**搜尋] 欄位中，輸入您要指派給佇列之 agent 群組的全部或部分名稱，按一下您想要的 agent 群組，然後按一下 **[確定]**。
    
      - 若要從佇列中移除群組，請在 [代理群組] 清單中，按一下您要移除的群組，然後按一下 [**移除**]。
    
      - 若要變更代理的搜尋順序，請在 [代理程式群組] 清單中，按一下群組，然後按一下向上箭號或向下箭號。
        
        <div>
        

        > [!NOTE]  
        > 當伺服器搜尋佇列的可用代理程式時，它會使用群組順序。 也就是說，會先搜尋清單中的第一個群組，然後搜尋清單中的第二個群組，依此類推。

        
        </div>

8.  若要指定呼叫者在工程師接聽通話之前等待的時間上限，請選取 [**啟用佇列超時設定**] 核取方塊，然後執行下列動作：
    
    1.  在 **[超時時間（秒）**] 中，指定呼叫者等待代理接聽通話的最大秒數。
    
    2.  在 [**通話**中] 中，選取撥打電話時所發生的動作，如下所示：
    
    <!-- end list -->
    
      - 若要在超時之後中斷通話，請按一下 **[中斷**連線]。
    
      - 若要將來電轉寄到語音信箱，請按一下 [**轉寄給語音信箱**]，然後在 [ **sip 位址**] 欄位中，輸入\<[sip：使用者名\>@\<功能變數名稱\> ] 中的語音信箱位址（例如，sip:bob@contoso.com）。
    
      - 若要將來電轉接到另一個電話號碼，請按一下 [**轉寄電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip：\<號碼\>@\<功能變數名稱\> ] （例如，sip:+14255550121@contoso.com）中的電話號碼。
    
      - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，輸入\<[sip： username\>@\<功能變數名稱\>] 的使用者 URI。
    
      - 若要將來電轉接到另一個佇列，請按一下 [**轉寄至另一份佇列**]，然後流覽至您要使用的佇列。

9.  若要指定佇列可以保留的呼叫數目上限，請選取 [**啟用佇列溢出**] 核取方塊，然後執行下列動作：
    
    1.  在 [**最大通話數**] 中，選取您希望佇列保留的最大通話數。
    
    2.  在**轉寄通話**中，選取當佇列已滿時要轉寄的通話： [**最新通話**] 或 [**最舊通話**]。
    
    3.  在 [**呼叫] 動作**中，選取符合溢出閾值時所發生的動作，如下所示：
    
    <!-- end list -->
    
      - 若要在超時之後中斷通話，請按一下 **[中斷**連線]。
    
      - 若要將來電轉寄到語音信箱，請按一下 [**轉寄給語音信箱**]，然後在 [ **sip 位址**] 欄位中，輸入\<[sip：使用者名\>@\<功能變數名稱\> ] 中的語音信箱位址（例如，sip:bob@contoso.com）。
    
      - 若要將來電轉接到另一個電話號碼，請按一下 [**轉寄電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip：\<號碼\>@\<功能變數名稱\> ] （例如，sip:+14255550121@contoso.com）中的電話號碼。
    
      - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，輸入\<[sip： username\>@\<功能變數名稱\>] 的使用者 URI。
    
      - 若要將來電轉接到另一個佇列，請按一下 [**轉寄至另一份佇列**]，然後流覽至您要使用的佇列。

10. 按一下 [認可]****。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>使用 Windows PowerShell 建立或修改佇列

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。
    
    <div>
    

    > [!NOTE]  
    > 如果您是受管理工作流程的委派回應群組管理員，您就可以建立代理群組和佇列，並將代理群組指派給佇列。

    
    </div>

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在達到佇列的超時閾值時，建立要播放的提示，然後將它儲存在變數中。 在命令列上執行：
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    例如：
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > 若要在提示時使用音訊檔案，請使用<STRONG>CsRgsAudioFile</STRONG> Cmdlet。 如需詳細資訊，請參閱匯<A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">入-CsRgsAudioFile</A>。

    
    </div>

4.  定義達到佇列的超時閾值時所採取的動作，並將它儲存在變數中。 在命令列上執行：
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > 如需可能動作及其語法的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">新 CsRgsCallAction</A>。

    
    </div>
    
    例如：
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  建立在符合佇列溢出閾值時要播放的提示，並將它儲存在變數中。 在命令列上執行：
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    例如：
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > 若要在提示時使用音訊檔案，請使用<STRONG>CsRgsAudioFile</STRONG> Cmdlet。 如需詳細資訊，請參閱匯<A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">入-CsRgsAudioFile</A>。

    
    </div>

6.  定義達到佇列溢出閾值時所採取的動作，並將它儲存在變數中。 在命令列上執行：
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > 如需可能動作及其語法的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">新 CsRgsCallAction</A>。

    
    </div>
    
    例如：
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  檢索回應群組服務的服務名稱，並將它指派給變數。 在命令列上執行：
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  取得指派給佇列的代理群組身分識別。 在命令列上執行：
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > 如需建立代理群組的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">新 CsRgsAgentGroup</A>

    
    </div>

9.  建立佇列。 在命令列上執行：
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    例如：
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. 確認已建立佇列。 用盡
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>請參閱


[新-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[新-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[新-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[匯入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[移除-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

