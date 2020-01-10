---
title: 在商務用 Skype 中建立或修改佇列
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 在商務用 Skype Server Enterprise Voice 中建立或修改回應群組佇列。
ms.openlocfilehash: 9027c239c92c7c04b9de8b5579d7ebb73069b1a3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001703"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>在商務用 Skype 中建立或修改佇列
 
在商務用 Skype Server Enterprise Voice 中建立或修改回應群組佇列。
  
[佇列] 會按住呼叫者，直到工程師接聽通話。 當回應群組應用程式搜尋可用的代理時，會按照您列出的順序來搜尋代理群組。 您可以選取指派給佇列的代理群組，並指定佇列行為，例如限制該列隊可以保留的呼叫次數，以及呼叫在工程師接聽通話之前等待的時間。
  
使用下列其中一個程式來建立或修改佇列。
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>使用商務用 Skype Server 的 [控制台] 來建立或修改佇列

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。
    
    > [!NOTE]
    > 如果您是受管理工作流程的委派回應群組管理員之一，您可以建立或修改回應群組佇列，並將其指派給您管理的工作流程。 
  
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**佇列**]。
    
4. 在 [**佇列**] 頁面上，執行下列其中一項操作：
    
   - 若要建立新的佇列，請按一下 [**新增**]。 在 [**選取服務**] 中，在 [搜尋] 欄位中，輸入您要新增佇列之**ApplicationServer**服務的部分或所有名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。
    
   - 若要修改現有的佇列，請在 [搜尋] 欄位中輸入全部或部分的佇列名稱。 在產生的佇列清單中，按一下您想要的佇列，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
5. 在 [**名稱**] 中，輸入佇列的識別名稱。
    
6. 在 [**描述**] 中，輸入佇列的描述。
    
7. 在 [**群組**] 中，指定您要指派給佇列的群組。 請執行下列其中一項操作： 
    
   - 若要在佇列中新增群組，請按一下 [**選取**]。 在 [**選取群組**搜尋] 欄位中，輸入您要指派給佇列之 agent 群組的全部或部分名稱，按一下您想要的 agent 群組，然後按一下 **[確定]**。
    
   - 若要從佇列中移除群組，請在 [代理群組] 清單中，按一下您要移除的群組，然後按一下 [**移除**]。
    
   - 若要變更代理的搜尋順序，請在 [代理程式群組] 清單中，按一下群組，然後按一下向上箭號或向下箭號。
    
     > [!NOTE]
     > 當伺服器搜尋佇列的可用代理程式時，它會使用群組順序。 也就是說，會先搜尋清單中的第一個群組，然後搜尋清單中的第二個群組，依此類推。 
  
8. 若要指定呼叫者在工程師接聽通話之前等待的時間上限，請選取 [**啟用佇列超時設定**] 核取方塊，然後執行下列動作：
    
    是. 在 **[超時時間（秒）**] 中，指定呼叫者等待代理接聽通話的最大秒數。
    
    乙. 在 [**通話**中] 中，選取撥打電話時所發生的動作，如下所示：
    
   - 若要在超時之後中斷通話，請按一下 **[中斷**連線]。
    
   - 若要將來電轉寄到語音信箱，請按一下 [**轉寄給語音信箱**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip： * \< \>使用者名*@ *\<功能變數名稱\> * ] 中的語音信箱位址（例如，sip:bob@contoso.com）。
    
   - 若要將來電轉接到另一個電話號碼，請按一下 [**轉寄電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip： * \<號碼\>*@ *\<功能變數名稱\> * ] （例如，sip:+14255550121@contoso.com）中的電話號碼。
    
   - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip： _ \< \>username_@ _\<功能變數名稱\>_] 的使用者 URI。
    
   - 若要將來電轉接到另一個佇列，請按一下 [**轉寄至另一份佇列**]，然後流覽至您要使用的佇列。
    
9. 若要指定佇列可以保留的呼叫數目上限，請選取 [**啟用佇列溢出**] 核取方塊，然後執行下列動作：
    
    是. 在 [**最大通話數**] 中，選取您希望佇列保留的最大通話數。 
    
    乙. 在**轉寄通話**中，選取當佇列已滿時要轉寄的通話： [**最新通話**] 或 [**最舊通話**]。
    
    c-clip. 在 [**呼叫] 動作**中，選取符合溢出閾值時所發生的動作，如下所示：
    
   - 若要在超時之後中斷通話，請按一下 **[中斷**連線]。
    
   - 若要將來電轉寄到語音信箱，請按一下 [**轉寄給語音信箱**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip： * \< \>使用者名*@ *\<功能變數名稱\> * ] 中的語音信箱位址（例如，sip:bob@contoso.com）。
    
   - 若要將來電轉接到另一個電話號碼，請按一下 [**轉寄電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip： * \<號碼\>*@ *\<功能變數名稱\> * ] （例如，sip:+14255550121@contoso.com）中的電話號碼。
    
   - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，輸入 [sip： _ \< \>username_@ _\<功能變數名稱\>_] 的使用者 URI。
    
   - 若要將來電轉接到另一個佇列，請按一下 [**轉寄至另一份佇列**]，然後流覽至您要使用的佇列。
    
10. 按一下 [認可]****。
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>若要使用商務用 Skype Server Management Shell 來建立或修改佇列

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。
    
    > [!NOTE]
    > 如果您是受管理工作流程的委派回應群組管理員，您就可以建立代理群組和佇列，並將代理群組指派給佇列。 
  
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 在達到佇列的超時閾值時，建立要播放的提示，然後將它儲存在變數中。 在命令列上執行：
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   例如：
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > 若要在提示時使用音訊檔案，請使用**CsRgsAudioFile** Cmdlet。 如需詳細資訊，請參閱匯[入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。 
  
4. 定義達到佇列的超時閾值時所採取的動作，並將它儲存在變數中。 在命令列上執行：
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > 如需可能動作及其語法的詳細資訊，請參閱[新 CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。 
  
    例如：
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. 建立在符合佇列溢出閾值時要播放的提示，並將它儲存在變數中。 在命令列上執行：
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   例如：
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > 若要在提示時使用音訊檔案，請使用**CsRgsAudioFile** Cmdlet。 如需詳細資訊，請參閱匯[入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。 
  
6. 定義達到佇列溢出閾值時所採取的動作，並將它儲存在變數中。 在命令列上執行：
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > 如需可能動作及其語法的詳細資訊，請參閱[新 CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。 
  
    例如：
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. 檢索回應群組服務的服務名稱，並將它指派給變數。 在命令列上執行：
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. 取得指派給佇列的代理群組身分識別。 在命令列上執行：
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > 如需建立代理群組的詳細資訊，請參閱[新 CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. 建立佇列。 在命令列上執行：
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   例如：
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. 確認已建立佇列。 用盡
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>另請參閱

[新-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[新-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[新-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[匯入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[移除-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
