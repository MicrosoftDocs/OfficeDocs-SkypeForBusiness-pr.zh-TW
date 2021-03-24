---
title: 在商務用 Skype 中建立或修改佇列
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 在商務用 Skype Server Enterprise Voice 中建立或修改回應群組佇列。
ms.openlocfilehash: b355cde0d8a99938538488152276a6c8eb4c6d4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103579"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>在商務用 Skype 中建立或修改佇列
 
在商務用 Skype Server Enterprise Voice 中建立或修改回應群組佇列。
  
佇列會使來電者等候，直到代理接聽電話為止。 當回應群組應用程式搜尋可用的代理程式時，它會依照列出的順序來搜尋代理人群組。 您可以選取指派給佇列的代理群組，並指定佇列行為，例如限制佇列中可以包含的電話數目，以及限制在代理接聽電話之前，電話等候的時間長度。
  
使用下列其中一個程式來建立或修改佇列。
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>使用商務用 Skype Server 控制台建立或修改佇列

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。
    
    > [!NOTE]
    > 如果您是受管理工作流程的其中一位委派回應群組管理員，您可以建立或修改回應群組佇列，並將其指派給您管理的工作流程。 
  
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。  
    
3. 在左導覽列中，按一下 **[回應群組]**，然後按一下 **[佇列]**。
    
4. 在 [ **佇列** ] 頁面上，執行下列其中一項動作：
    
   - 若要建立新的佇列，請按一下 [ **新增**]。 在 [ **選取服務**] 中，在 [搜尋] 欄位中輸入您要在其中新增佇列的 **ApplicationServer** 服務的部分或全部名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。
    
   - 若要修改現有的佇列，請在搜尋欄位中輸入全部或部分的佇列名稱。 在產生的佇列清單中，按一下您想要的佇列，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。
    
5. 在 [ **名稱**] 中，輸入佇列的識別名稱。
    
6. 在 **[描述]** 中，輸入佇列的描述。
    
7. 在 [ **群組**] 中，指定您想要指派給佇列的群組。 執行下列其中一項： 
    
   - 若要將群組新增至佇列，請按一下 [ **選取**]。 在 [ **選取群組** ] 搜尋欄位中，輸入您要指派給佇列的代理人群組全部或部分名稱，然後按一下您想要的代理人群組，然後按一下 **[確定]**。
    
   - 若要從佇列中移除群組，請在代理程式群組清單中，按一下您要移除的群組，然後按一下 [ **移除**]。
    
   - 若要變更代理人的搜尋順序，請在代理人群組清單中，按一下群組，然後按一下向上箭號或向下箭號。
    
     > [!NOTE]
     > 當伺服器搜尋佇列的可用代理程式時，會使用群組順序。 也就是會先搜尋清單中的第一個群組，然後是清單中的第二個群組，以此類推。 
  
8. 若要指定來電者等候專員接聽通話之前的最長保留期間，請選取 **[啟用佇列逾時]** 核取方塊，然後執行下列動作：
    
    a. 在 **[逾時期限 (秒)]** 中，指定來電者等候專員接聽通話的最長秒數。
    
    b. 在 **[撥號動作]** 中，選取通話逾時時進行的動作 (如下所示)：
    
   - 若要在逾時之後中斷通話，請按一下 **[中斷連線]**。
    
   - 若要將來電轉接至語音信箱，請按一下 [**轉寄至語音信箱**]，然後在 [ **sip 位址**] 欄位中輸入語音信箱位址，格式為 SIP： *\<username\>* @  *\<domainname\>* (例如，sip:bob@contoso.com) 。
    
   - 若要將通話轉寄給另一個電話號碼，請按一下 [**轉寄給電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入以 [sip： (格式] 的電話號碼（ *\<number\>* @  *\<domainname\>* 例如，sip:+14255550121@contoso.com) ）。
    
   - 若要將呼叫轉寄給另一位使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，以 [sip：] 的格式輸入使用者的 URI _\<username\>_ @  _\<domainname\>_ 。
    
   - 若要將通話轉接至另一個佇列，請按一下 **[轉接至其他佇列]**，然後瀏覽至想要使用的佇列。
    
9. 若要指定佇列可以保留的通話數目上限，請選取 **[啟用佇列溢位]** 核取方塊，然後執行下列動作：
    
    a. 在 **[通話數目上限]** 中，選取想要佇列保留的通話數目上限。 
    
    b. 在 **[轉接來電]** 中，選取佇列已滿時要轉接的通話：**[最新通話]** 或 **[最早通話]**。
    
    c. 在 [ **通話動作**] 中，選取符合溢出閾值時所發生的動作，如下所示：
    
   - 若要在逾時之後中斷通話，請按一下 **[中斷連線]**。
    
   - 若要將來電轉接至語音信箱，請按一下 [**轉寄至語音信箱**]，然後在 [ **sip 位址**] 欄位中輸入語音信箱位址，格式為 SIP： *\<username\>* @  *\<domainname\>* (例如，sip:bob@contoso.com) 。
    
   - 若要將通話轉寄給另一個電話號碼，請按一下 [**轉寄給電話號碼**]，然後在 [ **sip 位址**] 欄位中，輸入以 [sip： (格式] 的電話號碼（ *\<number\>* @  *\<domainname\>* 例如，sip:+14255550121@contoso.com) ）。
    
   - 若要將呼叫轉寄給另一位使用者，請按一下 [**轉寄給 SIP 位址**]，然後在 [ **sip 位址**] 欄位中，以 [sip：] 的格式輸入使用者的 URI _\<username\>_ @  _\<domainname\>_ 。
    
   - 若要將通話轉接至另一個佇列，請按一下 **[轉接至其他佇列]**，然後瀏覽至想要使用的佇列。
    
10. 按一下 **[認可]**。
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>使用商務用 Skype Server 管理命令介面來建立或修改佇列

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。
    
    > [!NOTE]
    > 如果您是受管理工作流程的其中一位委派回應群組管理員，則可以建立代理人群組和佇列，並將代理群組指派給佇列。 
  
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
3. 建立當達到佇列的超時臨界值時要播放的提示，並將它儲存在變數中。 在命令列中執行：
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   例如：
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > 若要使用音訊檔以進行提示，請使用 **Import-CsRgsAudioFile** Cmdlet。 如需詳細資訊，請參閱 [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。 
  
4. 定義達到佇列的超時臨界值時要採取的動作，並將它儲存在變數中。 在命令列中執行：
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > 如需可能的動作及其語法的詳細資訊，請參閱 [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)。 
  
    例如：
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. 建立在達到佇列溢出閾值時要播放的提示，並將其儲存在變數中。 在命令列中執行：
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   例如：
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > 若要使用音訊檔以進行提示，請使用 **Import-CsRgsAudioFile** Cmdlet。 如需詳細資訊，請參閱 [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。 
  
6. 定義達到佇列溢出閾值時要採取的動作，並將其儲存在變數中。 在命令列中執行：
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > 如需可能的動作及其語法的詳細資訊，請參閱 [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)。 
  
    例如：
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. 取得回應群組服務的服務名稱，並將其指派給變數。 在命令列中執行：
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. 取得要指派給佇列的代理人群組的身分識別。 在命令列中執行：
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > 如需建立代理人群組的詳細資訊，請參閱 [New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. 建立佇列。 在命令列中執行：
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   例如：
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. 確認已建立佇列。 執行：
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>另請參閱

[New-CsRgsQueue](/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](/powershell/module/skype/remove-csrgsqueue?view=skype-ps)