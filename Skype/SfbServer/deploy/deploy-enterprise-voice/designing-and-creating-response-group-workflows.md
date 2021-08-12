---
title: 在商務用 Skype 中設計及建立回應群組工作流程
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
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: 在商務用 Skype Server 企業語音中，設計及建立回應群組工作流程。 同時也涵蓋群組搜尋工作流程和互動式工作流程。
ms.openlocfilehash: ac77753e82acc2a7733fb5d273a55b4c9fd0d0fd5466262fec6fdc9a2c223030
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303117"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>在商務用 Skype 中設計及建立回應群組工作流程

在商務用 Skype Server 企業語音中，設計及建立回應群組工作流程。 同時也涵蓋群組搜尋工作流程和互動式工作流程。

工作流程會定義從電話鈴聲開始響起到有人接聽該通電話這段時間的呼叫行為。 工作流程會指定用於進行通話的佇列，並指定用來搜尋群組工作流程的路由方法，或用於互動式回應群組工作流程的問題和解答。

工作流程也定義歡迎訊息、等候音樂、上班時間和假日之類的設定值。

> [!NOTE]
> 您必須先建立代理群組和佇列，再建立使用這些項目的工作流程。

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>建立或修改群組搜尋工作流程

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>使用回應群組設定工具來建立或修改群組搜尋工作流程

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[工作流程]**。

4. 在 **[工作流程]** 頁面上，按一下 **[建立或編輯工作流程]**。

5. 在 [ **選取服務** ] 搜尋欄位中，輸入主控您要建立或變更之工作流程的 **ApplicationServer** 服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。

    > [!NOTE]
    > 回應群組設定工具隨即開啟。 您也可以輸入下列 URL: HTTPs:///RgsConfig.，直接從網頁瀏覽器開啟回應群組設定工具。 \<webPoolFqdn\>

6. 執行下列其中一項：

   - 在 [ **建立新的工作流程**] 下，按一下 [ **群組搜尋**] 旁的 [ **建立**]。

   - 在 **[管理現有工作流程]** 下，找到想要變更的工作流程，然後在 **[動作]** 下按一下 **[編輯]**。

7. 如果您準備好讓使用者開始呼叫工作流程，請選取 **[啟用工作流程**]。

    > [!NOTE]
    >  若要建立受管理的工作流程，您必須選取 **[啟用工作流程**]。 在您儲存使用中的受管理工作流程之後，您可以修改並停用該工作流程。

8. 若要允許同盟使用者撥打群組，請選取 **[針對同盟啟用]** 核取方塊。 您也必須具有適用于同盟設定之回應群組應用程式的外部存取原則。

    > [!NOTE]
    > 全域外部存取原則會套用至回應群組應用程式。 您可以使用商務用 Skype Server 控制台] 或使用 **get-csexternalaccesspolicy** 指令程式將 EnableOutsideAccess 參數設定為 True，設定回應群組同盟的全域原則。 請記住，除非將站台原則或使用者原則指派給使用者，否則通用原則設定適用於所有使用者。 因此在變更回應群組的此設定之前，請確認同盟設定符合您組織的需求。 如需有關如何將原則套用至使用者的詳細資訊，請參閱 [管理組織的外部存取原則](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization)。 如需同盟設定的詳細資訊，請參閱 [Set-get-csexternalaccesspolicy](/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)。

    > [!NOTE]
    > 在商務用 Skype Online 中主控的使用者無法將呼叫放入內部部署中所主控的回應群組。 這在混合式部署中，以及內部部署與商務用 Skype 線上部署的同盟情況皆為 true。

9. 若要在通話期間隱藏代理人的身分識別，請選取 **[啟用代理人匿名]** 核取方塊。

    > [!NOTE]
    > 雖然代理人或來電者可以在建立通話之後新增 IM 及視訊，但是匿名通話不能以立即訊息 (IM) 或視訊開始。 匿名代理人也可以保留通話、轉接通話 (無條件轉接及諮詢轉接)，以及駐留及擷取通話。 匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、白板和資料共同作業，以及通話記錄。 使用 Lync VDI 外掛程式的代理程式可以以匿名方式接收來電，但無法以匿名方式撥打撥出電話。

10. 在 [ **輸入要接聽電話的群組位址**] 下，輸入主要 SIP 統一資源識別項 (URI) 會接聽工作流程呼叫的群組的位址。

    > [!NOTE]
    > 工作流程的主要 URI 是如何識別及參考工作流程。 您輸入的 SIP URI 會建立為 Active Directory 網域服務中的連絡人物件。 若要建立 URI，該物件在 Active Directory 中必須是唯一的。

11. 在 [ **顯示名稱**] 中，輸入您要針對工作流程顯示的名稱 (例如，Sales Response Group) 。

    > [!NOTE]
    > 請不要在顯示名稱中包含 "<" 或 ">" 字元。 請勿使用下列顯示名稱，因為它們是保留的： **RGS 存在觀察** 程式或 **宣告服務**。

12. 在 **[電話號碼]** 下，輸入回應群組的線路 URI (例如，+14255550165)。

13. 在 **[顯示號碼]** 中，輸入想要針對回應群組顯示的號碼 (例如，+1 (425) 555-0165)。

14.  (選用) 在 [**描述**] 中，輸入您想要在商務用 Skype 中的連絡人卡片上顯示之工作流程的描述。

15. 在 [ **工作流程類型**] 中，選取 [ **受** 回應群組管理員管理此工作流程]。 請執行下列動作，將回應群組管理員指派給工作流程：

    a. 為此工作流程輸入管理員的 SIP URI，然後按一下 [ **新增**]。

    b. 輸入其他管理員的 SIP URI，以新增至工作流程，然後按一下 [ **新增**]。

    > [!IMPORTANT]
    > 指定為回應群組管理員的每一位使用者都必須指派 CsResponseGroupManager 角色。 若未指派此角色的使用者，他們就無法管理回應群組。

16. 在 **[步驟 2 選取語言]** 下，按一下要用於語音辨識及文字轉語音的語言。

17. 如果您想要設定歡迎訊息，請在 **[步驟 3 設定歡迎訊息]** 下選取 **[播放歡迎訊息]** 核取方塊，然後執行下列其中一項：

    - 若要以文字輸入為來電者轉換成語音的歡迎訊息，按一下 **[使用文字轉語音]**，然後在文字方塊中輸入歡迎訊息。

    > [!NOTE]
    > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

    - 若要使用聲波 (.wav) 或 Windows Media 音訊 (.wma) 檔案錄音做為歡迎訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的音訊檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。

    > [!NOTE]
    > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的檔案格式的詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。

18. 在 **[步驟 4 指定您的上班時間]** 的 **[您的時區]** 中，按一下工作流程的時區。

    > [!NOTE]
    > 此時區即為工作流程的來電者和專員所在之時區，可用來計算開啟和關閉的時間。例如，如果工作流程設定為使用「北美東部時區」，而工作流程排定為早上 7:00 開啟，晚上 11:00 關閉，則開啟和關閉的時間就會分別假設為東部時區 7:00 和東部時區 23:00。(您必須使用 24 小時時間標記法輸入時間)。

19. 執行下列其中一項，以選取想要使用的上班時間排程類型：

    - 若要使用預先定義的上班時間排程，請按一下 **[使用預設排程]**，然後從下拉式清單中選取想要使用的排程。

      > [!NOTE]
      > 您至少先前必須已定義一個預設排程，才能選取此選項。 您可以使用 **New-CSRgsHoursOfBusiness** Cmdlet，來定義預設排程。 如需詳細資訊，請參閱[商務用 Skype 中的 (選用) 定義回應群組上班時間](optional-define-response-group-business-hours.md)。

      > [!NOTE]
      > 當您選取預設排程時，**[日]**、**[開啟]** 及 **[關閉]** 會自動填入回應群組可用的日及時數。

    - 若要使用只套用至此工作流程的自訂排程，請按一下 **[使用自訂排程]**。

20. 如果您是建立此工作流程的自訂排程，請按一下回應群組可用之一星期的哪幾天的核取方塊。

21. 若要建立自訂排程，請輸入回應群組可供使用的每一天的「 **開啟** 」和「 **關閉** 」時間。

    > [!NOTE]
    > **[開啟]** 及 **[關閉]** 時間必須使用 24 小時時間標記法。例如，如果您辦公室平日的辦公時間為 9 點到 5 點，而且會在中午用餐時間關閉，則會將上班時間指定為 **[開啟]** 9:00、**[關閉]** 12:00、**[開啟]** 13:00 以及 **[關閉]** 17:00。

22. 如果您想要在辦公室關閉時播放訊息，請選取 **[在回應群組下班時播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：

    - 若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。

      > [!NOTE]
      > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

    - 若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。

      > [!NOTE]
      > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的音訊檔案格式的詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。

23. 指定在播放訊息之後如何處理通話 (如果有設定訊息)：

    - 若要中斷來電，按一下 **[中斷通話]**。

    - 若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。 語音信箱位址的格式為 *\<username\>* @ *\<domainName\>* (例如，bob@contoso.com) 。

    - 若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。 使用者位址的格式為 _\<username\>_ @ _\<domainName\>_ 。

    - 若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。 電話號碼的格式為 *\<number\>* @ *\<domainName\>* (例如，+ 14255550121@contoso.com) 。 網域名稱會用來將來電者路由到正確的目的地。

24. 在 **[步驟 5 指定您的假日]** 下，按一下可定義回應群組沒上班之天數的一或多個假日集的核取方塊。

    > [!NOTE]
    > 您需要先定義假日及假日集，再設定工作流程。 使用 **New-CsRgsHoliday** 及 **New-CsRgsHolidaySet** Cmdlet，可定義假日及假日集。 如需詳細資訊，請參閱[商務用 Skype 中的 (選用) 定義回應群組假日集](optional-define-response-group-holiday-sets.md)。

25. 如果您想要在假日時播放訊息，請選取 **[在假日期間播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：

    - 若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。

    > [!NOTE]
    > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

    - 若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。

      > [!NOTE]
      > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的音訊檔案格式的詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。

26. 指定在播放訊息之後如何處理通話 (如果有設定訊息)：

    - 若要中斷來電，按一下 **[中斷通話]**。

    - 若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。 語音信箱位址的格式為 *\<username\>* @ *\<domainName\>* (例如，bob@contoso.com) 。

    - 若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。 使用者位址的格式為 _\<username\>_ @ _\<domainName\>_ 。

    - 若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。 電話號碼的格式為 *\<number\>* @ *\<domainName\>* (例如，+ 14255550121@contoso.com) 。 網域名稱會用來將來電者路由到正確的目的地。

27. 在 **[步驟 6 設定佇列]** 的 **[選取要接聽電話的佇列]** 下，選取想要保留來電者直到專員有空的佇列。

28. 在 **[步驟 7 設定等候音樂]** 下，選擇您要來電者在等候專員時所聆聽的音樂，方法如下：

    - 若要使用預設的等候音樂錄音，按一下 **[使用預設]**。

    - 若要使用音訊檔案錄音做為等候音樂，請按一下 **[選取音樂檔案]**。如果您想要上傳新的音訊檔案，請按一下 **[音樂檔案]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。

      > [!NOTE]
      > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的音訊檔案格式的詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。

29. 按一下 **[部署]**。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>使用商務用 Skype Server 管理命令介面建立或修改群組搜尋工作流程

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3. 建立要對歡迎使用的訊息播放的提示，並將其儲存在變數中。 在命令列中執行：

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    例如：

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > 若要使用音訊檔以進行提示，請使用 **Import-CsRgsAudioFile** Cmdlet。 如需詳細資訊，請參閱 [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。

4. 取得會定向來電之佇列或問題的身分識別。 在命令列中執行：

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    如需建立佇列的詳細資訊，請參閱 [New-CsRgsQueue](/powershell/module/skype/new-csrgsqueue?view=skype-ps)。

5. 定義當工作流程在上班時間開啟時所採取的預設動作，並將其儲存在變數中。 在命令列中執行：

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > 若要群組搜尋工作流程，預設動作必須將來電導向至佇列。 Active 工作流程需要此參數。 不需要使用非使用中的工作流程。

    例如：

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. 若要定義上班時間和假日，您必須在建立或修改工作流程之前加以建立。 如需詳細資訊，請參閱[ (選用) 定義回應群組上班時間商務用 Skype](optional-define-response-group-business-hours.md)和[ (選用) 在商務用 Skype 中定義回應群組假日集](optional-define-response-group-holiday-sets.md)。

7. 如果您想要在上班時間或假期內收到來電的提示，請使用 **New-CsRgsPrompt** Cmdlet 來定義提示，然後使用 **New-CsRgsCallAction** 來定義要在提示之後採取的動作。 如需詳細資訊，請參閱 [New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps) 和 [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)。

8. 取得 Lync Server 回應群組服務的服務名稱，並將其指派給變數。 在命令中執行：

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. 建立或修改工作流程。 若要建立工作流程，請使用 **New-CsRgsWorkflow**。 若要修改工作流程，請使用 **Set-CsRgsWorkflow**。 在命令列中輸入：

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    例如：

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > 指派給工作流程管理員的所有使用者，都必須指派 CsResponseGroupManager 角色。

     > [!NOTE]
     > 如需其他選擇性參數的詳細資訊，請參閱 [New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps) 或 [Set-CsRgsWorkflow](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>設計互動式工作流程

您可以使用互動語音回應 (IVR) 從來電者取得資訊，並將來電導向至適當的佇列。 問題和答案配對決定要使用的佇列。 視來電者的回應而定，來電者可能會聽到後續問題，或會路由傳送至適當的佇列。 IVR 問題及來電者的回應會提供給回應的代理人，以接受通話，並將有價值的資訊提供給代理商。

### <a name="overview-of-ivr-features"></a>IVR 功能的概覽

回應群組應用程式可提供26種語言的語音辨識及文字到語音功能。 您可以使用文字語音轉換或波浪形 ( .wav) 或 Windows 媒體音訊 ( .wma) 檔案輸入 IVR 問題。 來電者可以使用語音或雙音訊式訊號 (DTMF) 回應來回應。

互動工作流程最多支援兩層的問題，而每個問題最多會有四個可能的答案。 IVR 會詢問來電者一個問題，視來電者的回應而定，將來電者路由傳送到佇列或提出第二個問題。 第二個問題最多也有四個可能的答案。 根據來電者對第二層問題的答案，可將來電者路由傳送到適當的佇列。

> [!NOTE]
> 當您使用商務用 Skype Server 管理命令介面設計通話流程時，您可以定義任何數目的 IVR 問題和任何數目的答案。 不過，對於來電者的可用性，我們建議您不要使用三個以上的問題，每個層次都不會有五個以上的答案。 此外，如果您設計的通話流程中有兩個以上的問題，每個層次都有四個以上的答案，您就無法使用商務用 Skype Server 控制台編輯通話流程。

IVR 問題及來電者的回應會提供給接受通話的回應代理人。

### <a name="working-with-speech-technologies"></a>使用語音技術

語音技術（例如語音辨識及文字轉換語音）可以增強客戶體驗，並讓人員更有效率地存取訊號。 不過，您可能會出現語音引擎未正確辨識指定的文字或使用者語音回應的情況。 例如，"#" 符號會由文字到語音引擎轉譯成 "number" 一字。 下列情況可緩解此問題：

- 語音引擎可讓來電者有五個嘗試接聽問題。 如果來電者回答問題的方式不正確 (也就是說，答案不是指定的回應之一) 或根本沒有提供答案，來電者會取得另一個回答問題的機會。 來電者有五個嘗試在中斷連線之前回答問題。 您可以設定 IVR 在每一位來電者錯誤之後播放自訂郵件。 每次都會重複提問。

- 若要將透過語音引擎轉譯成回應的環境噪音可能性降至最低，請使用較長的回應。 例如，回應應該有一個以上的音節，而且應該會有很大的不同。

- 如果您的問題同時有語音和 DTMF 回應，請使用代表概念的字詞（而不是 DTMF 回應）來設定語音回應。 例如，請不要使用 "按或說一個" 使用 "按1或口述帳單。

- 在您設計 IVR 後，請致電工作流程、聆聽提示、使用語音回應每個提示，並確認 IVR 的聲音和行為如預期。 然後，您可以修改 IVR 以修正任何轉譯問題。 在前面的範例中，如果您需要參照 # 鍵，您可以重新寫入您的 IVR 提示字元，而不使用 # 符號。 例如，「與銷售人員交談，按井字鍵。」

### <a name="ivr-design-examples"></a>IVR 設計範例

下列各節包含不同 IVR 案例及問答對的範例。

#### <a name="ivr-with-one-level-of-questions"></a>IVR 具有一個層級的問題

下列範例顯示使用一層問題的 IVR。 它會使用語音辨識偵測來電者的回應。

 **問題：** 「感謝您呼叫人力資源。 如果您想要對工資單講話，請說出工資單。 否則請說「HR」。

- **選取 [選項 1]：** 來電者會路由傳送到工資單小組。

- **選取選項2：** 來電者會路由傳送至人力資源團隊。

下圖顯示通話流程。

 **一層級互動通話流程**

![使用互動語音回應設計通話流程](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>IVR 有兩個層級的問題

下列範例顯示使用兩層級問題的 IVR。 它可讓來電者使用語音或 DTMF 小鍵盤輸入進行回應。

 **問題：** 「感謝您呼叫 IT 問訊台。 如果有網路存取問題，請按1或說網路。 如果您有軟體問題，請按2或口述軟體。 如果有硬體問題，請按3或說硬體。」

- **選取 [選項 1]：** 來電者會路由傳送到網路支援小組。

- **選取選項2：** 來電者會問您追蹤問題：

    **問題：** 「如果這是作業系統問題，請按1或口述作業系統。 如果這是內部應用程式的問題，請按2或說出內部應用程式。 否則，請按3或說其他。」

  - **選取 [選項 1]：** 來電者會路由傳送至作業系統支援小組。

  - **選取選項2：** 來電者會路由傳送到內部應用程式支援小組。

  - **選取 [選項 3]：** 來電者會路由傳送到軟體支援小組。

- **選取 [選項 3]：** 來電者會問您追蹤問題：

    **問題：** 「如果這是印表機問題，請按1。 否則，請按2。

  - **選取 [選項 1]：** 來電者會路由傳送至印表機支援小組。

  - **選取選項2：** 來電者會路由傳送至硬體支援小組。

下圖顯示通話流程。

 **雙層互動式通話流程**

![使用互動語音回應設計通話流程](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>最佳做法

下列清單說明設計 IVR 的一些最佳作法：

- 讓來電者快速取得工作。 避免在 IVR 中提供太多資訊或冗長的行銷訊息。

- 如果您想要包含很長的訊息，請考慮將它附加到第一個問題，而不是加入歡迎使用的郵件。 如果來電者是接聽問題的第一個問題的一部分，來電者可以略過此訊息，但無法略過歡迎訊息。

- 以來電者的語言講話。 避免 stilted 語言。 自然講話。

- 撰寫有效且有效的提示。 移除所有不必要的選項。 構造資訊，使來電者預期的回應位於句子的結尾。 例如，「對銷售團隊講話，請按1。」

- 讓語音回應使用者易記。 例如，如果您同時指定 DTMF 和語音回應，請使用類似下列的內容：「說到銷售團隊，按1或說 sales」。

- 在您的組織中部署使用者之前，請先在使用者群組上測試 IVR。

## <a name="creating-or-modifying-an-interactive-workflow"></a>建立或修改互動式工作流程

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>使用回應群組設定工具來建立或修改互動式工作流程

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[工作流程]**。

4. 在 **[工作流程]** 頁面上，按一下 **[建立或編輯工作流程]**。

5. 在 [ **選取服務** ] 搜尋欄位中，輸入主控您要建立或修改之工作流程的 **ApplicationServer** 服務全部或部分名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。

    > [!NOTE]
    > 回應群組設定工具隨即開啟。 您也可以輸入下列 URL: HTTPs:///RgsConfig.，直接從網頁瀏覽器開啟回應群組設定工具。 \<webPoolFqdn\>

6. 執行下列其中一項：

   - 在 **[建立新的工作流程]** 的 **[互動]** 旁邊，按一下 **[建立]**。

   - 在 **[管理現有工作流程]** 下，找到想要變更的工作流程，然後在 **[動作]** 下按一下 **[編輯]**。

7. 如果尚未準備好讓使用者開始撥號至工作流程，請清除 **[啟用工作流程]** 核取方塊。

    > [!NOTE]
    >  若要建立受管理的工作流程，您必須選取 **[啟用工作流程**]。 在您儲存使用中的受管理工作流程之後，您可以修改並停用該工作流程。

8. 若要允許同盟使用者撥打群組，請選取 **[針對同盟啟用]** 核取方塊。 您也必須具有適用于同盟設定之回應群組應用程式的外部存取原則。

    > [!NOTE]
    > 全域外部存取原則會套用至回應群組應用程式。 您可以使用商務用 Skype Server 控制台] 或使用 **get-csexternalaccesspolicy** 指令程式將 EnableOutsideAccess 參數設定為 True，設定回應群組同盟的全域原則。 請記住，除非將站台原則或使用者原則指派給使用者，否則通用原則設定適用於所有使用者。 因此在變更回應群組的此設定之前，請確認同盟設定符合您組織的需求。 如需有關如何將原則套用至使用者的詳細資訊，請參閱 [管理組織的外部存取原則](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization)。 如需同盟設定的詳細資訊，請參閱檔中 **的 get-csexternalaccesspolicy** 。

    > [!NOTE]
    > 在商務用 Skype Online 中主控的使用者無法將呼叫放入內部部署中所主控的回應群組。 這在混合式部署中，以及內部部署與商務用 Skype 線上部署的同盟情況皆為 true。

9. 若要在通話期間隱藏代理人的身分識別，請選取 **[啟用代理人匿名]** 核取方塊。

    > [!NOTE]
    > 雖然代理人或來電者可以在建立通話之後新增 IM 及視訊，但是匿名通話不能以立即訊息 (IM) 或視訊開始。 匿名代理人也可以保留通話、轉接通話 (無條件轉接及諮詢轉接)，以及駐留及擷取通話。 匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、白板和資料共同作業，以及通話記錄。 使用 Lync VDI 外掛程式的代理程式可以以匿名方式接收來電，但無法以匿名方式撥打撥出電話。

10. 在 [ **輸入要接聽電話的群組位址**] 下，輸入主要 SIP 統一資源識別項 (URI) 會接聽工作流程呼叫的群組的位址。

11. 在 [ **顯示名稱**] 中，輸入您要針對工作流程顯示的名稱 (例如，Sales IVR Response Group) 。

    > [!NOTE]
    > \<" or "\>在顯示名稱中不要包含 "" 字元。 請勿使用下列顯示名稱，因為它們是保留的： **RGS 存在觀察** 程式或 **宣告服務**。

12. 在 **[電話號碼]** 中，輸入回應群組的線路 URI (例如，+14255550165)。

13. 在 **[顯示號碼]** 中，輸入想要針對回應群組顯示的號碼 (例如，+1 (425) 555-0165)。

14.  (選用) 在 [**描述**] 中，輸入您要顯示在商務用 Skype 中連絡人卡片上之工作流程的描述。

15. 在 [ **工作流程類型**] 中，選取 [ **受** 回應群組管理員管理此工作流程]。 請執行下列動作，將回應群組管理員指派給工作流程：

    a. 為此工作流程輸入管理員的 SIP URI，然後按一下 [ **新增**]。

    b. 輸入其他管理員的 SIP URI，以新增至工作流程，然後按一下 [ **新增**]。

    > [!IMPORTANT]
    > 指定為回應群組管理員的每一位使用者都必須指派 CsResponseGroupManager 角色。 若未指派此角色的使用者，他們就無法管理回應群組。

16. 在 **[步驟 2 選取語言]** 下，按一下要用於語音辨識及文字轉換語音的語言。

17. 如果您想要設定歡迎訊息，請在 **[步驟 3 設定歡迎訊息]** 下選取 **[播放歡迎訊息]** 核取方塊，然後執行下列其中一項：

    - 若要以文字輸入為來電者轉換成語音的歡迎訊息，按一下 **[使用文字轉語音]**，然後在文字方塊中輸入歡迎訊息。

    > [!NOTE]
    > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

    - 若要使用 Wave 或 Windows Media 音訊檔案錄音做為歡迎訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的音訊檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。

    > [!NOTE]
    > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的檔案格式的詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。

18. 在 **[步驟 4 指定您的上班時間]** 的 **[您的時區]** 方塊中，按一下工作流程的時區。

    > [!NOTE]
    > 此時區即為工作流程的來電者和專員所在之時區，可用來計算開啟和關閉的時間。例如，如果工作流程設定為使用「北美東部時區」，而工作流程排定為早上 7:00 開啟，晚上 11:00 關閉，則開啟和關閉的時間就會分別假設為東部時區 7:00 和東部時區 11:00:00。(您必須使用 24 小時時間標記法輸入時間)。

19. 執行下列其中一項，以選取想要使用的上班時間排程類型：

    - 若要使用預先定義的上班時間排程，請按一下 **[使用預設排程]**，然後從下拉式清單中選取想要使用的排程。

      > [!NOTE]
      > 您至少先前必須已定義一個預設排程，才能選取此選項。 您可以使用 **CsRgsHoursOfBusiness 指令程式** 來定義預設排程。 如需詳細資訊，請參閱[商務用 Skype 中的 (選用) 定義回應群組上班時間](optional-define-response-group-business-hours.md)。 當您選取預設排程時，**[日]**、**[開啟]** 及 **[關閉]** 會自動填入回應群組可用的日及時數。

    - 若要使用只套用至此工作流程的自訂排程，請按一下 **[使用自訂排程]**。

20. 如果您是建立此工作流程的自訂排程，請按一下回應群組可用之一星期的哪幾天的核取方塊。

21. 若要建立自訂排程，請輸入回應群組可供使用時的 **開啟** 和 **關閉** 小時數。

     > [!NOTE]
     > **[開啟]** 及 **[關閉]** 時間必須使用 24 小時時間標記法。例如，如果您辦公室平日的辦公時間為 9 點到 5 點，而且會在中午用餐時間關閉，則會將上班時間指定為 **[開啟]** 9:00、**[關閉]** 12:00、**[開啟]** 13:00 以及 **[關閉]** 17:00。

22. 如果您想要在辦公室關閉時播放訊息，請選取 **[在回應群組下班時播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：

    - 若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。

      > [!NOTE]
      > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

    - 若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。

    > [!NOTE]
    > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的檔案格式的詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。

23. 指定在播放訊息之後如何處理通話 (如果有設定訊息)：

    - 若要中斷來電，按一下 **[中斷通話]**。

    - 若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。 語音信箱位址的格式為 *\<username\>* @ *\<domainname\>* (例如，bob@contoso.com) 。

    - 若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。 使用者位址的格式為 _\<username\>_ @ _\<domainname\>_ 。

    - 若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。 電話號碼的格式為 *\<number\>* @ *\<domainname\>* (例如，+ 14255550121@contoso.com) 。 網域名稱會用來將來電者路由到正確的目的地。

24. 在 **[步驟 5 指定您的假日]** 下，按一下可定義回應群組沒上班之天數的一或多個假日集的核取方塊。

    > [!NOTE]
    > 您需要先定義假日及假日集，再設定工作流程。 使用 **New-CsRgsHoliday** 及 **New-CsRgsHolidaySet** Cmdlet，可定義假日及假日集。 如需詳細資訊，請參閱[商務用 Skype 中的 (選用) 定義回應群組假日集](optional-define-response-group-holiday-sets.md)。

25. 如果您想要在假日時播放訊息，請選取 **[在假日期間播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：

    - 若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。

      > [!NOTE]
      > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

    - 若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。

      > [!NOTE]
      > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的音訊檔案格式的詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。

26. 指定在播放訊息之後如何處理通話 (如果有設定訊息)：

    - 若要中斷來電，按一下 **[中斷通話]**。

    - 若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。 語音信箱位址的格式為 *\<username\>* @ *\<domainname\>* (例如，bob@contoso.com) 。

    - 若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。 使用者位址的格式為 _\<username\>_ @ _\<domainname\>_ 。

    - 若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。 電話號碼的格式為 *\<number\>* @ *\<domainname\>* (例如，+ 14255550121@contoso.com) 。 網域名稱會用來將來電者路由到正確的目的地。

27. 在 **[步驟 6 設定等候音樂]** 中，選擇您要來電者在等候專員時所聆聽的音樂，方法如下：

    - 若要使用預設的等候音樂錄音，按一下 **[使用預設]**。

    - 若要使用音訊檔案錄音做為等候音樂，請按一下 **[選取音樂檔案]**。如果您想要上傳新的音訊檔案，請按一下 **[音樂檔案]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。

    > [!NOTE]
    > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的檔案格式的詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。

28. 在 **[步驟 7 設定互動語音回應**] 的 **[使用者將聽到下列文字或錄製的訊息]** 標題下，依下列方式指定要詢問來電者的問題：

    - 若要以文字格式輸入問題，按一下 **[使用文字轉語音]**，然後在文字方塊中輸入問題。

    > [!NOTE]
    > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

    > [!NOTE]
    > 文字轉語音引擎會將 "#" 符號轉譯為「號碼」一詞。 如果需要在提示中提及 # 鍵，則應該使用按鍵名稱，而非使用該符號。 例如，「與銷售人員交談，按井字鍵。」

    - 若要使用包含問題的預錄音訊檔案，請按一下 **[選取錄音]**，然後按一下 **[一筆記錄]** 連結以上傳檔案。 在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取音訊檔案，然後按一下 **[開啟]**。 按一下 [ **Upload** ] 以載入檔案，然後選擇性地在文字方塊中輸入問題 (這可讓您將問題及來電者的回應，轉送到回應的代理程式) 。

      > [!NOTE]
      > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的檔案格式的詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。

29. 在 **[回應 1]** 中，藉由下列動作指定問題的第一個可能答覆：

    > [!IMPORTANT]
    > 請不要在任何語音回應中使用引號 (")。引號會導致 IVR 失敗。

    > [!NOTE]
    > 您可以選擇讓來電者使用語音及 (或) 英數鍵台輸入來進行答覆。

    - 如果您想要讓來電者使用語音來回應，請在 **[輸入語音回應]** 中輸入答覆。

    - 如果您想要讓來電者按鍵台上的按鍵來回應，請在 **[數字]** 中按一下鍵台數字。

30. 指定是否要將來電者路由傳送到佇列或詢問另一個問題，如下所述：

    - 若要將來電者路由傳送到佇列，請按一下 **[傳送到佇列]**，並在 **[選取佇列]** 中按一下想要使用的佇列。

    - 若要詢問另一個問題，請按一下 **[詢問另一個問題]**，然後按一下 **[使用文字轉語音]**，並輸入問題，或按一下 **[選取錄音]**。 使用本節中的回應分組，指定其他問題最多四個可能回應，以及用於每個回應的佇列。 若要指定第三或第四種可能的回應，請按一下 [ **回應 3** ] 核取方塊或 [ **回應 4** ] 核取方塊。

31. 重複步驟 28 及 29 指定可能的回應，以及針對每個回應採取的動作，以指定原始問題最多三個可能的答案。若要指定第三個或第四個可能的答案，請按一下 **[回應 3]** 核取方塊或 **[回應 4]** 核取方塊。

32. 按一下 **[部署]**。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>使用商務用 Skype Server 管理命令介面建立或修改互動式工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3. 取得回應群組服務的服務名稱，並將其指派給變數。 在命令列中執行：

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. 互動式工作流程需要兩個以上的佇列以及兩個以上的代理人群組。 首先，建立代理人群組。 運行：

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. 建立佇列。 運行：

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. 建立第一個回應群組提示。 運行：

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. 然後建立在提示後要執行的動作。 運行：

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. 建立第一個回應群組答案。 運行：

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. 現在，建立第二個提示、通話動作和答案。 請先建立提示。 運行：

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. 建立第二個通話動作。 運行：

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. 建立第二個回應群組答案。 運行：

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. 建立最高層級提示。 運行：

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. 建立最上層問題。 運行：

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. 現在建立工作流程。 運行：

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > 指定為回應群組管理員的所有使用者，都必須指派 CsResponseGroupManager 角色。 若未指派此角色的使用者，他們就無法管理回應群組。

## <a name="see-also"></a>另請參閱

[ (選用) 定義回應群組假日集商務用 Skype](optional-define-response-group-holiday-sets.md)

[ (選用) 在商務用 Skype 中定義回應群組上班時間](optional-define-response-group-business-hours.md)

[New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)