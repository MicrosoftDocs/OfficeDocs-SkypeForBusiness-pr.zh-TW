---
title: 在商務用 Skype 中設計及建立回應群組工作流程
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
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: 在商務用 Skype Server Enterprise Voice 中設計及建立回應群組工作流程。 已覆蓋查尋群組工作流程和互動式工作流程。
ms.openlocfilehash: 5b48816a3eb528a1ff96097c135697d8f9cb22d8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002583"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>在商務用 Skype 中設計及建立回應群組工作流程

在商務用 Skype Server Enterprise Voice 中設計及建立回應群組工作流程。 已覆蓋查尋群組工作流程和互動式工作流程。

工作流程會定義撥打電話到某人接聽來電之時間的通話行為。 工作流程會指定要用來進行通話的佇列，並指定用於查尋群組工作流程的傳送方法，或是用於互動式回應群組工作流程的問題與解答。

工作流程也會定義設定，例如 [歡迎] 訊息、[等候音樂]、[上班時間] 和 [假日]。

> [!NOTE]
> 您必須先建立代理群組和佇列，才能建立使用它們的工作流程。

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>建立或修改查尋群組工作流程

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>使用 [回應群組設定] 工具來建立或修改查尋群組工作流程

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**工作流程**]。

4. 在 [**工作流程**] 頁面上，按一下 [**建立或編輯工作流程**]。

5. 在 [**選取服務**搜尋] 欄位中，輸入您要建立或變更之工作流程之**ApplicationServer**服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。

    > [!NOTE]
    > [回應群組設定] 工具隨即開啟。 您也可以輸入下列 URL，在網頁瀏覽器中直接開啟 [回應群組設定] 工具：\<Https://\>webPoolFqdn/RgsConfig。

6. 請執行下列其中一項操作：

   - 在 [**建立新工作流程**] 底下，按一下 [**查尋群組**] 旁的 [**建立**]。

   - 在 [**管理現有的工作流程**] 底下，找出您要變更的工作流程，然後在 [**動作**] 底下，按一下 [**編輯**]。

7. 如果您已準備好讓使用者開始呼叫工作流程，請選取 [**啟用工作流程**]。

    > [!NOTE]
    >  如果您要建立受管理的工作流程，您必須選取 [**啟用工作流程**]。 儲存作用中受管理的工作流程之後，您就可以進行修改及停用。

8. 若要允許聯盟使用者呼叫群組，請選取 [**啟用聯盟**] 核取方塊。 您也必須有可套用至針對同盟設定之回應群組應用程式的外部存取原則。

    > [!NOTE]
    > 全域外部存取原則會套用至回應群組應用程式。 您可以使用商務用 Skype Server 的 [控制台]，或使用**CsExternalAccessPolicy** Cmdlet 將 EnableOutsideAccess 參數設定為 True，來設定回應群組同盟的全域原則。 請記住，除非指派網站或使用者原則，否則全域原則設定將會套用至所有使用者。 因此，在變更回應群組的此設定之前，請確定同盟設定符合貴組織的需求。 如需有關如何將原則套用至使用者的詳細資訊，請參閱[管理貴組織的外部存取原則](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)。 如需同盟設定的詳細資訊，請參閱[設定 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)。

    > [!NOTE]
    > 在商務用 Skype Online 中託管的使用者無法將呼叫權放在內部部署中託管的回應群組。 這在混合式部署中，以及內部部署與商務用 Skype Online 部署聯盟的情況下，都是如此。

9. 若要在呼叫期間隱藏代理程式的身分識別，請選取 [**啟用代理程式匿名**] 核取方塊。

    > [!NOTE]
    > 匿名通話不能以立即訊息（IM）或影片啟動，不過代理或來電者可以在通話建立之後，新增 IM 和影片。 匿名代理程式也可以保留通話、轉接呼叫（盲人與顧問式轉移），以及寄存與取回通話。 匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、whiteboarding 與資料共同作業，以及通話錄製。 使用 Lync VDI 外掛程式的代理程式可以匿名接收來電，但不能匿名撥出來電。

10. 在 [**輸入將會接收來電的群組的位址**] 底下，輸入群組的主要 SIP 統一資源識別項（URI）位址，將會應答工作流程的呼叫。

    > [!NOTE]
    > 工作流程的主要 URI 是識別及參照工作流程的方式。 您輸入的 SIP URI 是在 Active Directory 網域服務中建立為連絡人物件。 若要建立 URI，物件在 Active Directory 中必須是唯一的。

11. 在 [**顯示名稱**] 中，輸入您要顯示的工作流程名稱（例如 [銷售回應] 群組）。

    > [!NOTE]
    > 請勿在顯示名稱中包含「<」或「>」字元。 請勿使用下列顯示名稱，因為它們是保留的： **RGS 目前狀態觀察**程式或**宣告服務**。

12. 在 [**電話號碼**] 下，輸入回應群組的行 URI （例如 + 14255550165）。

13. 在 [**顯示號碼**] 中，輸入您想要顯示給回應群組的數位（例如 + 1 （425）555-0165）。

14. 可選在 [**描述**] 中，輸入您想要在商務用 Skype 的連絡人卡片上顯示之工作流程的描述。

15. 在 [**工作流程類型**] 中，如果此工作流程將由回應群組管理員管理，請選取 [**管理**]。 請執行下列動作，將回應群組管理員指派給工作流程：

    是. 輸入此工作流程的管理員 SIP URI，然後按一下 [**新增**]。

    乙. 輸入要新增至工作流程的其他管理員 SIP URI，然後按一下 [**新增**]。

    > [!IMPORTANT]
    > 指派為回應群組管理員的每位使用者，都必須獲指派 CsResponseGroupManager 角色。 如果沒有為使用者指派這個角色，就不能管理回應群組。

16. 在 [**步驟2選取語言**] 底下，按一下您要用於語音辨識和文字轉換語音的語言。

17. 如果您想要設定歡迎訊息，請在 [**步驟3設定歡迎訊息**] 底下，選取 [**播放歡迎訊息**] 核取方塊，然後執行下列其中一項操作：

    - 若要將歡迎郵件輸入為已轉換為呼叫者語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入歡迎訊息。

    > [!NOTE]
    > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

    - 若要使用波形（.wav）或 Windows Media 音訊（.wma）檔案錄製 [歡迎] 訊息，請按一下 [**選取錄製**]。 如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。 在新的瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的音訊檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。

    > [!NOTE]
    > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

18. 在 [**步驟 4**] 底下的 [**您的時區**] 中，按一下該工作流程的時區。

    > [!NOTE]
    > [時區] 是工作流程的呼叫者和代理程式所在的時區。 它是用來計算開啟和關閉時間。 例如，如果工作流程設定為使用北美東部時區，且工作流程排程在 7:00 A.M. 開啟。 接著，請在 11:00 P.M.，將開啟和關閉時間分別視為7:00 東部時間和23:00 東部時間。 （您必須以24小時制時間格式輸入時間。）

19. 請執行下列其中一項動作，選取您要使用的商務時間排程類型：

    - 若要使用預先定義的上班時間排程，請按一下 [**使用預設排程**]，然後從下拉式清單中選取您要使用的排程。

      > [!NOTE]
      > 您之前必須已定義至少一個預設排程，才能選取此選項。 您可以使用**CSRgsHoursOfBusiness** Cmdlet 來定義預設排程。 如需詳細資訊，請參閱[（選用）在商務用 Skype 中定義回應群組的上班時間](optional-define-response-group-business-hours.md)。

      > [!NOTE]
      > 當您選取 [預置] 排程、[**天**]、[**開啟**] 和 [**關閉**] 時，系統會自動填入回應群組可用的日期和時間。

    - 若要使用只適用于此工作流程的自訂排程，請按一下 [**使用自訂排程**]。

20. 如果您要建立此工作流程的自訂排程，請按一下回應群組可用之周的日期核取方塊。

21. 如果您要建立自訂排程，請輸入回應群組可用之周的每一天的 [**開啟**] 和 [**結束**] 時間。

    > [!NOTE]
    > [**開啟**] 和 [**關閉**] 時間必須是24小時制時間格式。 例如，如果您的 office 的工作時間為9到5個工作日，而午餐時間為中午，則會將上班時間指定為**開啟**9:00、**關閉**12:00、**開啟**13:00，然後**關閉**17:00。

22. 如果您想要在 office 未開啟時播放郵件，請選取 [**當回應群組在上班時間以外時播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：

    - 若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。

      > [!NOTE]
      > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

    - 若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。 如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。 在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。

      > [!NOTE]
      > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的音訊檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

23. 指定在播放郵件後如何處理呼叫（如果已設定郵件）：

    - 若要中斷通話，請按一下 **[中斷通話]**。

    - 若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。 語音信箱位址的格式是@ * \<[使用者名\>**\<功能變數名稱\> * ] （例如，bob@contoso.com）。

    - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。 使用者位址的格式是@ _ \<[使用者名\>__\<功能變數名稱\>_]。

    - 若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。 電話號碼的格式是* \<數位\>*@*\<domainName\> * （例如，+ 14255550121@contoso.com）。 功能變數名稱是用來將呼叫者路由至正確的目的地。

24. 在 [**步驟5指定您的假日**] 底下，按一下一或多組假期的核取方塊，以定義回應群組結束的日期。

    > [!NOTE]
    > 您必須先定義假日和假日集，然後才能設定工作流程。 使用**新的-CsRgsHoliday**和**CsRgsHolidaySet** Cmdlet 來定義假日和假日集。 如需詳細資訊，請參閱[（選用）在商務用 Skype 中定義回應群組假日集](optional-define-response-group-holiday-sets.md)。

25. 如果您想要在假日上播放郵件，請選取 [在**假日期間播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：

    - 若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。

    > [!NOTE]
    > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

    - 若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。 如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。 在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。

      > [!NOTE]
      > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的音訊檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

26. 指定在播放郵件後如何處理呼叫（如果已設定郵件）：

    - 若要中斷通話，請按一下 **[中斷通話]**。

    - 若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。 語音信箱位址的格式是@ * \<[使用者名\>**\<功能變數名稱\> * ] （例如，bob@contoso.com）。

    - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。 使用者位址的格式是@ _ \<[使用者名\>__\<功能變數名稱\>_]。

    - 若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。 電話號碼的格式是* \<數位\>*@*\<domainName\> * （例如，+ 14255550121@contoso.com）。 功能變數名稱是用來將呼叫者路由至正確的目的地。

27. 在 [**步驟6設定佇列**] 底下的 **[選取將接收通話的佇列**] 中，選取您要保留呼叫者的佇列，直到有可用的代理程式。

28. 在 [**步驟7設定暫停的音樂**] 底下，請執行下列其中一項動作，選擇您想要呼叫者在等候代理程式時聆聽的音樂：

    - 若要使用預設的 [暫候] 錄製，請按一下 [**使用預設值**]。

    - 若要在等候音樂時使用音訊檔案錄製，請按一下 [**選取音樂**檔案]。 如果您想要上傳新的音訊檔案，請按一下 [**音樂**檔案] 連結。 在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。

      > [!NOTE]
      > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的音訊檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

29. 按一下 [**部署**]。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>若要使用商務用 Skype Server Management Shell 來建立或修改查尋群組工作流程

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。

2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

3. 建立要在歡迎訊息中播放的提示，然後將它儲存在變數中。 在命令列上執行：

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    例如：

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > 若要在提示時使用音訊檔案，請使用**CsRgsAudioFile** Cmdlet。 如需詳細資訊，請參閱匯[入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)。

4. 取得要導向通話的佇列或問題的身分識別。 在命令列上執行：

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    如需建立佇列的詳細資料，請參閱[新 CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)。

5. 定義工作流程開啟時要採取的預設動作，然後將其儲存在變數中。 在命令列上執行：

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > 在查尋群組工作流程中，預設動作必須將呼叫定向至佇列。 此參數對於使用中的工作流程是必要的。 非作用中工作流程不需要。

    例如：

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. 如果您想要定義上班時間和假日，您必須先建立，才能建立或修改工作流程。 如需詳細資訊，請參閱[（選用）在商務用 skype 中定義回應群組的商務時間](optional-define-response-group-business-hours.md) [（選用）在商務用 Skype 中定義回應群組假日集](optional-define-response-group-holiday-sets.md)。

7. 如果您想要針對在上班時間以外或假期收到的通話發出提示，請使用**CsRgsPrompt** Cmdlet 來定義提示，然後使用**新的-CsRgsCallAction**來定義提示之後要採取的動作。 如需詳細資訊，請參閱[新 CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)和[CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)。

8. 檢索 Lync Server 回應群組服務的服務名稱，並將它指派給一個變數。 在命令上執行：

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. 建立或修改工作流程。 若要建立工作流程，請使用 [**新-CsRgsWorkflow**]。 若要修改工作流程，請使用 [**設定-CsRgsWorkflow**]。 在命令列中，輸入：

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    例如：

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > 指派工作流程管理員的所有使用者，都必須獲指派 CsResponseGroupManager 角色。

     > [!NOTE]
     > 如需其他選擇性參數的詳細資訊，請參閱[新 CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)或[設定 CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>設計互動式工作流程

您可以使用互動式語音回應（IVR），從來電者取得資訊，並將呼叫定向至適當的佇列。 問題與答案配對決定要使用哪個佇列。 視來電者的回應而定，來電者可能會聽到後續問題，或是路由至適當的佇列。 IVR 問題與來電者的回應會提供給接受通話的回應代理程式，提供有價值的資訊給代理程式。

### <a name="overview-of-ivr-features"></a>IVR 功能概覽

回應群組應用程式提供的語音辨識和文字轉換語音功能都有26種語言。 您可以使用文字轉換語音或波形（.wav）或 Windows Media 音訊（.wma）檔案輸入 IVR 問題。 呼叫者可以使用語音或雙音調 multifrequency （DTMF）回應來回應。

互動式工作流程最多可支援兩個層級的問題，每個問題都有四個可能的答案。 IVR 會向呼叫者提出問題，視來電者的回應而定，將呼叫者路由至佇列或提出第二個問題。 第二個問題也可能有四個可能的答案。 根據第二層問題的答案而定，來電者會路由至適當的佇列。

> [!NOTE]
> 當您使用商務用 Skype Server Management Shell 設計通話流程時，您可以定義任何數目的 IVR 問題以及任何數目的答案。 不過，對於呼叫者的可用性，我們建議您不要使用超過三層的問題，每一個都不超過五個答案。 此外，如果您設計的通話流程中有兩個以上的問題，每個層次都有四個以上的答案，您就無法使用商務用 Skype Server [控制台] 來編輯通話流程。

IVR 問題及來電者的回應會提供給接受通話的回應代理程式。

### <a name="working-with-speech-technologies"></a>使用語音技術

語音技術（例如語音辨識和文字轉換語音）可加強客戶體驗，讓使用者更容易地存取訊號。 不過，您可能會有語音引擎無法正確辨識指定文字或使用者語音回應的情況。 例如，「#」符號是由文字到語音引擎轉譯為「數位」字樣。 您可以透過下列方式緩解此問題：

- 語音引擎提供給呼叫者五次，回答問題。 如果來電者回答的問題不正確（也就是說，答案不是指定的回應），或是根本無法提供答案，則呼叫者會收到另一個回答問題的機會。 呼叫者有五個嘗試在中斷連線之前回答問題。 您可以將 IVR 設定為在每個本機號碼之後，播放自訂的訊息。 每次都會重複出現這個問題。

- 若要將由語音引擎轉譯為回應的環境干擾可能性降至最低，請使用較長的回應。 例如，回應應該有一個以上的音節，而且應該會有很大的差異。

- 如果您的問題同時具有語音和 DTMF 回應，請使用代表概念的文字（而不是 DTMF 回應）來設定語音回應。 例如，請不要使用「按下或說一次」，而是按1或說帳單。」

- 在您設計 IVR 之後，請呼叫工作流程、聆聽提示、使用語音回應每個提示，並確認 IVR 的音效和行為如期運作。 然後，您可以修改 IVR 以修正任何轉譯問題。 在前面的範例中，如果您需要參照 # 鍵，可以重新寫入 IVR 提示，以使用索引鍵名稱，而不是 # 符號。 例如，若要與銷售額交談，請按井號鍵。

### <a name="ivr-design-examples"></a>IVR 設計範例

下列各節包含不同 IVR 案例與問題與答案組的範例。

#### <a name="ivr-with-one-level-of-questions"></a>包含一層問題的 IVR

下列範例顯示使用一層問題的 IVR。 它會使用語音辨識來偵測來電者的回應。

 **問題：**「感謝您打電話給人力資源。 如果您想要與工資單通話，請說出工資。 否則請說人力資源。」

- **已選取選項1：** 來電者會傳送給工資小組。

- **已選取選項2：** 來電者會傳送給人力資源小組。

下圖顯示通話流程。

 **一對一互動式呼叫流程**

![使用互動語音回應設計通話流程](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>IVR 有兩個等級的問題

下列範例顯示的是使用兩層問題的 IVR。 它可讓呼叫者使用語音或 DTMF 小鍵盤輸入來回應。

 **問題：**「感謝您致電 IT 技術支援人員。 如果有網路存取問題，請按1或說 [網路]。 如果您有軟體問題，請按2或說軟體。 如果有硬體問題，請按3或說硬體。」

- **已選取選項1：** 來電者會路由至網路支援小組。

- **已選取選項2：** 來電者會問到待處理問題：

    **問題：**「如果這是作業系統問題，請按1或說作業系統。 如果這是內部應用程式的問題，請按2或說出內部應用程式。 否則，請按3或說 [其他]。

  - **已選取選項1：** 來電者會路由至作業系統支援小組。

  - **已選取選項2：** 來電者會路由到內部應用程式支援小組。

  - **已選取選項3：** 來電者會傳送給軟體支援小組。

- **已選取選項3：** 來電者會問到待處理問題：

    **問題：**「如果這是印表機問題，請按1。 否則，請按2。

  - **已選取選項1：** 來電者會傳送給印表機支援小組。

  - **已選取選項2：** 來電者會路由到硬體支援小組。

下圖顯示通話流程。

 **兩層互動式通話流程**

![使用互動語音回應設計通話流程](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>最佳做法

下列清單說明設計 IVR 的一些最佳做法：

- 讓呼叫者快速取得工作。 避免在您的 IVR 中提供太多的資訊或冗長的行銷訊息。

- 如果您想要包含較長的訊息，請考慮將它附加到第一個問題，而不是加入 [歡迎使用] 訊息。 如果您回答的問題是第一個問題的一部分，來電者可以略過這封郵件，但他們無法略過歡迎訊息。

- 在來電者語言中說話。 避免 stilted 語言。 自然說話。

- 撰寫高效且有效的提示。 移除任何不必要的選項。 構造資訊，讓來電者預期的回應在句子的結尾。 例如，「若要與銷售團隊通話，請按1。」

- 讓語音回復使用者更容易。 例如，如果您指定 DTMF 和語音回應，請使用如下所示的內容：「若要與銷售團隊進行通話，請按1或說出銷售。」

- 在您的組織中部署使用者群組之前，請先測試一組使用者的 IVR。

## <a name="creating-or-modifying-an-interactive-workflow"></a>建立或修改互動式工作流程

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>使用 [回應群組設定] 工具來建立或修改互動式工作流程

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**工作流程**]。

4. 在 [**工作流程**] 頁面上，按一下 [**建立或編輯工作流程**]。

5. 在 [**選取服務**搜尋] 欄位中，輸入您要建立或修改之工作流程之**ApplicationServer**服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。

    > [!NOTE]
    > [回應群組設定] 工具隨即開啟。 您也可以輸入下列 URL，在網頁瀏覽器中直接開啟 [回應群組設定] 工具：\<Https://\>webPoolFqdn/RgsConfig。

6. 請執行下列其中一項操作：

   - 在 [**建立新工作流程**] 底下，按一下 [**互動式**] 旁的 [**建立**]。

   - 在 [**管理現有的工作流程**] 底下，找出您要變更的工作流程，然後在 [**動作**] 底下，按一下 [**編輯**]。

7. 如果您未準備好讓使用者開始呼叫工作流程，請清除 [**啟用工作流程**] 核取方塊。

    > [!NOTE]
    >  如果您要建立受管理的工作流程，您必須選取 [**啟用工作流程**]。 儲存作用中受管理的工作流程之後，您就可以進行修改及停用。

8. 若要允許聯盟使用者呼叫群組，請選取 [**啟用聯盟**] 核取方塊。 您也必須有可套用至針對同盟設定之回應群組應用程式的外部存取原則。

    > [!NOTE]
    > 全域外部存取原則會套用至回應群組應用程式。 您可以使用商務用 Skype Server 的 [控制台]，或使用**CsExternalAccessPolicy** Cmdlet 將 EnableOutsideAccess 參數設定為 True，來設定回應群組同盟的全域原則。 請記住，除非指派網站或使用者原則，否則全域原則設定將會套用至所有使用者。 因此，在變更回應群組的此設定之前，請確定同盟設定符合貴組織的需求。 如需有關如何將原則套用至使用者的詳細資訊，請參閱[管理貴組織的外部存取原則](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)。 如需同盟設定的詳細資訊，請參閱在檔中**設定 CsExternalAccessPolicy** 。

    > [!NOTE]
    > 在商務用 Skype Online 中託管的使用者無法將呼叫權放在內部部署中託管的回應群組。 這在混合式部署中，以及內部部署與商務用 Skype Online 部署聯盟的情況下，都是如此。

9. 若要在呼叫期間隱藏代理程式的身分識別，請選取 [**啟用代理程式匿名**] 核取方塊。

    > [!NOTE]
    > 匿名通話不能以立即訊息（IM）或影片啟動，不過代理或來電者可以在通話建立之後，新增 IM 和影片。 匿名代理程式也可以保留通話、轉接呼叫（盲人與顧問式轉移），以及寄存與取回通話。 匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、whiteboarding 與資料共同作業，以及通話錄製。 使用 Lync VDI 外掛程式的代理程式可以匿名接收來電，但不能匿名撥出來電。

10. 在 [**輸入將會接收來電的群組的位址**] 底下，輸入群組的主要 SIP 統一資源識別項（URI）位址，將會應答工作流程的呼叫。

11. 在 [**顯示名稱**] 中，輸入您要顯示的工作流程名稱（例如 [銷售 IVR] 回應群組）。

    > [!NOTE]
    > 不要在顯示名稱中\<包含 ""\>或 "" 字元。 請勿使用下列顯示名稱，因為它們是保留的： **RGS 目前狀態觀察**程式或**宣告服務**。

12. 在 [**電話號碼**] 中，輸入回應群組的行 URI （例如 + 14255550165）。

13. 在 [**顯示號碼**] 中，輸入您想要顯示給回應群組的數位（例如 + 1 （425）555-0165）。

14. 可選在 [**描述**] 中，輸入您想要在商務用 Skype 的連絡人卡片上顯示之工作流程的描述。

15. 在 [**工作流程類型**] 中，如果此工作流程將由回應群組管理員管理，請選取 [**管理**]。 請執行下列動作，將回應群組管理員指派給工作流程：

    是. 輸入此工作流程的管理員 SIP URI，然後按一下 [**新增**]。

    乙. 輸入要新增至工作流程的其他管理員 SIP URI，然後按一下 [**新增**]。

    > [!IMPORTANT]
    > 指派為回應群組管理員的每位使用者，都必須獲指派 CsResponseGroupManager 角色。 如果沒有為使用者指派這個角色，就不能管理回應群組。

16. 在 [**步驟2選取語言**] 底下，按一下要用於語音辨識和文字轉換語音的語言。

17. 如果您想要設定歡迎訊息，請在 [**步驟3設定歡迎訊息**] 底下，選取 [**播放歡迎訊息**] 核取方塊，然後執行下列其中一項操作：

    - 若要將歡迎郵件輸入為已轉換為呼叫者語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入歡迎訊息。

    > [!NOTE]
    > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

    - 若要使用波形或 Windows Media 音訊檔案錄製以取得歡迎訊息，請按一下 [**選取錄製**]。 如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。 在新的瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的音訊檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。

    > [!NOTE]
    > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

18. 在 [**步驟4指定您的工作**時間] 底下的 [**您的時區**] 方塊中，按一下工作流程的時區。

    > [!NOTE]
    > [時區] 是工作流程的呼叫者和代理程式所在的時區。 它是用來計算開啟和關閉時間。 例如，如果工作流程設定為使用北美東部時區，且工作流程排程在 7:00 A.M. 開啟。 接著，請在 11:00 P.M.，將開啟和關閉時間分別視為7:00 東部時間和11:00 東部時間。 （您必須以24小時制時間格式輸入時間。）

19. 請執行下列其中一項動作，選取您要使用的商務時間排程類型：

    - 若要使用預先定義的上班時間排程，請按一下 [**使用預設排程**]，然後從下拉式清單中選取您要使用的排程。

      > [!NOTE]
      > 您之前必須已定義至少一個預設排程，才能選取此選項。 您可以使用**CsRgsHoursOfBusiness** Cmdlet 來定義預設排程。 如需詳細資訊，請參閱[（選用）在商務用 Skype 中定義回應群組的上班時間](optional-define-response-group-business-hours.md)。 當您選取 [預置] 排程、[**天**]、[**開啟**] 和 [**關閉**] 時，系統會自動填入回應群組可用的日期和時間。

    - 若要使用只適用于此工作流程的自訂排程，請按一下 [**使用自訂排程**]。

20. 如果您要建立此工作流程的自訂排程，請按一下回應群組可用之周的日期核取方塊。

21. 如果您要建立自訂排程，請在回應群組可供使用時，輸入**開啟**和**關閉**的時間。

     > [!NOTE]
     > [**開啟**] 和 [**關閉**] 時間必須是24小時制時間格式。 例如，如果您的 office 的工作時間為9到5個工作日，而午餐時間為中午，則會將上班時間指定為**開啟**9:00、**關閉**12:00、**開啟**13:00，然後**關閉**17:00。

22. 如果您想要在 office 未開啟時播放郵件，請選取 [**當回應群組在上班時間以外時播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：

    - 若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。

      > [!NOTE]
      > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

    - 若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。 如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。 在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。

    > [!NOTE]
    > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

23. 指定在播放郵件後如何處理呼叫（如果已設定郵件）：

    - 若要中斷通話，請按一下 **[中斷通話]**。

    - 若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。 語音信箱位址的格式是@ * \<[使用者名\>**\<功能變數名稱\> * ] （例如，bob@contoso.com）。

    - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。 使用者位址的格式是@ _ \<[使用者名\>__\<功能變數名稱\>_]。

    - 若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。 電話號碼的格式是* \<數位\>*@*\<domainname\> * （例如，+ 14255550121@contoso.com）。 功能變數名稱是用來將呼叫者路由至正確的目的地。

24. 在 [**步驟5指定您的假日**] 底下，按一下一或多組假期的核取方塊，以定義回應群組結束的日期。

    > [!NOTE]
    > 您必須先定義假日和假日集，然後才能設定工作流程。 使用**新的-CsRgsHoliday**和**CsRgsHolidaySet** Cmdlet 來定義假日和假日集。 如需詳細資訊，請參閱[（選用）在商務用 Skype 中定義回應群組假日集](optional-define-response-group-holiday-sets.md)。

25. 如果您想要在假日上播放郵件，請選取 [在**假日期間播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：

    - 若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。

      > [!NOTE]
      > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

    - 若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。 如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。 在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。

      > [!NOTE]
      > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的音訊檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

26. 指定在播放郵件後如何處理呼叫（如果已設定郵件）：

    - 若要中斷通話，請按一下 **[中斷通話]**。

    - 若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。 語音信箱位址的格式是@ * \<[使用者名\>**\<功能變數名稱\> * ] （例如，bob@contoso.com）。

    - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。 使用者位址的格式是@ _ \<[使用者名\>__\<功能變數名稱\>_]。

    - 若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。 電話號碼的格式是* \<數位\>*@*\<domainname\> * （例如，+ 14255550121@contoso.com）。 功能變數名稱是用來將呼叫者路由至正確的目的地。

27. 在 [**步驟6設定暫停的音樂**] 底下，請執行下列其中一項動作，選擇您想要讓呼叫者在等待代理程式時聆聽的內容：

    - 若要使用預設的音樂保留錄製，請按一下 [**使用預設值**]。

    - 若要將音訊檔案錄製用於等候音樂，請按一下 [**選取音樂**檔案]。 如果您想要上傳新的音訊檔案，請按一下 [**音樂**檔案] 連結。 在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。

    > [!NOTE]
    > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

28. 在 [**步驟7設定互動式語音回應**] 底下的 **[使用者將會聽到下列文字] 或 [錄製的郵件**] 標題中，指定要求呼叫者的問題，如下所示：

    - 若要以文字格式輸入問題，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入問題。

    > [!NOTE]
    > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

    > [!NOTE]
    > "#" 符號是由文字到語音引擎轉譯為「數位」一詞。 如果您需要參照 # 鍵，您應該在提示中使用索引鍵名稱，而不是符號。 例如，若要與銷售額交談，請按井號鍵。

    - 若要使用含有問題的預先錄製音訊檔案，請按一下 [**選取錄製**]，然後按一下 [**錄製**] 連結來上傳檔案。 在新的瀏覽器視窗中，按一下 **[流覽]**，選取音訊檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入檔案，然後選擇您可以在文字方塊中輸入問題（這可讓您將問題及來電者回應轉寄到回應的代理程式）。

      > [!NOTE]
      > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的檔案格式的詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。

29. 在 [**回應 1**] 底下，請執行下列動作，以指定第一次可能的問題答案：

    > [!IMPORTANT]
    > 請勿在任何語音回復中使用引號（"）。 引號會導致 IVR 失敗。

    > [!NOTE]
    > 您可以選擇允許呼叫者使用語音、數位數位鍵台輸入或兩者同時接聽。

    - 如果您想要讓來電者使用語音進行回應，請在 [**輸入語音回應**] 中輸入答案。

    - 如果您想要允許呼叫者以鍵盤上的按鍵進行回應，請按一下 [**數位**] 中的小數位。

30. 指定是否要將呼叫者路由到佇列，或是依以下方式提出其他問題：

    - 若要將呼叫者路由到佇列，請按一下 [**傳送至佇列**]，然後在 [**選取佇列**] 中，按一下您要使用的佇列。

    - 若要提出其他問題，請按一下 [**提出其他問題**]，然後按一下 [**使用文字轉換語音**] 並輸入問題，或按一下 [**選取錄製**]。 使用本節中的 [回應群組]，指定最多四個可能回應其他問題的回應，以及每個回應所要使用的佇列。 若要指定第三或第四種可能的回復，請按一下 [**回應 3** ] 核取方塊或 [**回應 4** ] 核取方塊。

31. 重複步驟28和29，以指定可能的回應，以及針對每個回應所採取的動作，指定最多三個可能的原始問題答案。 若要指定第三個或第四個可能的答案，請按一下 [**回應 3** ] 核取方塊或 [**回應 4** ] 核取方塊。

32. 按一下 [**部署**]。

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>若要使用商務用 Skype Server Management Shell 來建立或修改互動式工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。

2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

3. 檢索回應群組服務的服務名稱，並將它指派給變數。 在命令列上執行：

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. 互動式工作流程需要兩個或多個佇列，以及兩個以上的代理群組。 首先，建立代理程式群組。 用盡

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. 建立佇列。 用盡

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. 建立第一個回應群組提示。 用盡

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. 然後建立在提示之後要執行的動作。 用盡

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. 建立第一個回應群組答案。 用盡

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. 現在，建立第二個提示、通話動作及答案。 首先建立提示。 用盡

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. 建立第二個通話動作。 用盡

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. 建立第二個回應群組答案。 用盡

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. 建立最上層的提示。 用盡

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. 建立最上層的問題。 用盡

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. 現在，建立工作流程。 用盡

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > 已指定為回應群組管理員的所有使用者，都必須獲指派 CsResponseGroupManager 角色。 如果沒有為使用者指派這個角色，就不能管理回應群組。

## <a name="see-also"></a>另請參閱

[可選在商務用 Skype 中定義回應群組假日集](optional-define-response-group-holiday-sets.md)

[可選在商務用 Skype 中定義回應群組上班時間](optional-define-response-group-business-hours.md)

[新-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[新-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[新-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

