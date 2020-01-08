---
title: Lync Server 2013：建立或修改互動式工作流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede826df74d63270afe2ea3f4e992cdcddbbe412
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改互動式工作流程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-11_

使用下列其中一個程式來建立或修改互動式工作流程。

<div>


> [!NOTE]  
> 您可以使用 Lync Server 管理命令介面或 [回應群組設定] 工具來建立及修改互動式工作流程。 您可以從 Lync Server [控制台] 存取 [回應群組設定] 工具，或是透過在網頁瀏覽器中輸入下列 URL 來直接開啟網頁： <STRONG>HTTPs://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>。



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>使用 [回應群組設定] 工具來建立或修改互動式工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**回應群組**]，然後按一下 [**工作流程**]。

4.  在 [**工作流程**] 頁面上，按一下 [**建立或編輯工作流程**]。

5.  在 [**選取服務**搜尋] 欄位中，輸入您要建立或修改之工作流程之**ApplicationServer**服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > [回應群組設定] 工具隨即開啟。 您也可以輸入下列 URL，直接從網頁瀏覽器開啟 [回應群組設定] 工具： <STRONG>HTTPs://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>。

    
    </div>

6.  請執行下列其中一項操作：
    
      - 在 [**建立新工作流程**] 底下，按一下 [**互動式**] 旁的 [**建立**]。
    
      - 在 [**管理現有的工作流程**] 底下，找出您要變更的工作流程，然後在 [**動作**] 底下，按一下 [**編輯**]。

7.  如果您未準備好讓使用者開始呼叫工作流程，請清除 [**啟用工作流程**] 核取方塊。
    
    <div>
    

    > [!NOTE]  
    > 如果您要建立受管理的工作流程，您必須選取 [<STRONG>啟用工作流程</STRONG>]。 儲存作用中受管理的工作流程之後，您就可以進行修改及停用。

    
    </div>

8.  若要允許聯盟使用者呼叫群組，請選取 [**啟用聯盟**] 核取方塊。 您也必須有可套用至針對同盟設定之回應群組應用程式的外部存取原則。
    
    <div>
    

    > [!NOTE]  
    > 全域外部存取原則會套用至回應群組應用程式。 您可以使用 Lync Server [控制台]，或使用<STRONG>CsExternalAccessPolicy</STRONG> Cmdlet 將 EnableOutsideAccess 參數設定為 True，來設定回應群組同盟的全域原則。 請記住，除非指派網站或使用者原則，否則全域原則設定將會套用至所有使用者。 因此，在變更回應群組的此設定之前，請確定同盟設定符合貴組織的需求。 如需如何將原則套用至使用者的詳細資料，請參閱<A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">在 Lync Server 2013 中管理外部存取原則</A>。 如需同盟設定的詳細資訊，請參閱 Lync Server 管理命令介面檔中的<STRONG>設定 CsExternalAccessPolicy</STRONG> 。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Online 中託管的使用者無法將呼叫權放在內部部署中託管的回應群組。 這在混合式部署中，以及內部部署與 Lync Online 部署聯盟的情況下，都是如此。

    
    </div>

9.  若要在呼叫期間隱藏代理程式的身分識別，請選取 [**啟用代理程式匿名**] 核取方塊。
    
    <div>
    

    > [!NOTE]  
    > 匿名通話不能以立即訊息（IM）或影片啟動，不過代理或來電者可以在通話建立之後，新增 IM 和影片。 匿名代理程式也可以保留通話、轉接呼叫（盲人與顧問式轉移），以及寄存與取回通話。 匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、whiteboarding 與資料共同作業，以及通話錄製。 使用 Lync VDI 外掛程式的代理程式可以匿名接收來電，但不能匿名撥出來電。

    
    </div>

10. 在 [**輸入將會接收來電的群組的位址**] 底下，輸入群組的主要 SIP 統一資源識別項（URI）位址，將會應答工作流程的呼叫。

11. 在 [**顯示名稱**] 中，輸入您要顯示的工作流程名稱（例如 [銷售 IVR] 回應群組）。
    
    <div>
    

    > [!NOTE]  
    > 不要在顯示名稱中&lt;包含 ""&gt;或 "" 字元。 請勿使用下列顯示名稱，因為它們是保留的： RGS 目前狀態觀察程式或宣告服務。

    
    </div>

12. 在 [**電話號碼**] 中，輸入回應群組的行 URI （例如 + 14255550165）。

13. 在 [**顯示號碼**] 中，輸入您想要顯示給回應群組的數位（例如 + 1 （425）555-0165）。

14. 可選在 [**描述**] 中，輸入您想要在 Lync 用戶端的連絡人卡片上顯示之工作流程的描述。

15. 在 [**工作流程類型**] 中，如果此工作流程將由回應群組管理員管理，請選取 [**管理**]。 請執行下列動作，將回應群組管理員指派給工作流程：
    
    1.  輸入此工作流程的管理員 SIP URI，然後按一下 [**新增**]。
    
    2.  輸入要新增至工作流程的其他管理員 SIP URI，然後按一下 [**新增**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 指派為回應群組管理員的每位使用者，都必須獲指派 CsResponseGroupManager 角色。 如果沒有為使用者指派這個角色，就不能管理回應群組。

    
    </div>

16. 在 [**步驟2選取語言**] 底下，按一下要用於語音辨識和文字轉換語音的語言。

17. 如果您想要設定歡迎訊息，請在 [**步驟3設定歡迎訊息**] 底下，選取 [**播放歡迎訊息**] 核取方塊，然後執行下列其中一項操作：
    
      - 若要將歡迎郵件輸入為已轉換為呼叫者語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入歡迎訊息。
        
        <div>
        

        > [!NOTE]  
        > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

        
        </div>
    
      - 若要使用波形或 Windows Media 音訊檔案錄製以取得歡迎訊息，請按一下 [**選取錄製**]。 如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。 在新的瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的音訊檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。

        
        </div>

18. 在 [**步驟4指定您的工作**時間] 底下的 [**您的時區**] 方塊中，按一下工作流程的時區。
    
    <div>
    

    > [!NOTE]  
    > [時區] 是工作流程的呼叫者和代理程式所在的時區。 它是用來計算開啟和關閉時間。 例如，如果工作流程設定為使用北美東部時區，且工作流程排程在 7:00 A.M. 開啟。 接著，請在 11:00 P.M.，將開啟和關閉時間分別視為7:00 東部時間和11:00 東部時間。 （您必須以24小時制時間格式輸入時間。）

    
    </div>

19. 請執行下列其中一項動作，選取您要使用的商務時間排程類型：
    
      - 若要使用預先定義的上班時間排程，請按一下 [**使用預設排程**]，然後從下拉式清單中選取您要使用的排程。
        
        <div>
        

        > [!NOTE]  
        > 您之前必須已定義至少一個預設排程，才能選取此選項。 您可以使用<STRONG>CSRgsHoursOfBusiness</STRONG> Cmdlet 來定義預設排程。 如需詳細資訊，請參閱<A href="lync-server-2013-optional-define-response-group-business-hours.md">（選用）在 Lync Server 2013 中定義回應群組的上班時間</A>。 當您選取 [預置] 排程、[<STRONG>天</STRONG>]、[<STRONG>開啟</STRONG>] 和 [<STRONG>關閉</STRONG>] 時，系統會自動填入回應群組可用的日期和時間。

        
        </div>
    
      - 若要使用只適用于此工作流程的自訂排程，請按一下 [**使用自訂排程**]。

20. 如果您要建立此工作流程的自訂排程，請按一下回應群組可用之周的日期核取方塊。

21. 如果您要建立自訂排程，請在回應群組可用時，輸入 [**開啟**] 和 [**關閉**] 時間。
    
    <div>
    

    > [!NOTE]  
    > [<STRONG>開啟</STRONG>] 和 [<STRONG>關閉</STRONG>] 時間必須是24小時制時間格式。 例如，如果您的 office 的工作時間為9到5個工作日，而午餐時間為中午，則會將上班時間指定為<STRONG>開啟</STRONG>9:00、<STRONG>關閉</STRONG>12:00、<STRONG>開啟</STRONG>13:00，然後<STRONG>關閉</STRONG>17:00。

    
    </div>

22. 如果您想要在 office 未開啟時播放郵件，請選取 [**當回應群組在上班時間以外時播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：
    
      - 若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。
        
        <div>
        

        > [!NOTE]  
        > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

        
        </div>
    
      - 若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。 如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。 在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。

        
        </div>

23. 指定在播放郵件後如何處理呼叫（如果已設定郵件）：
    
      - 若要中斷通話，請按一下 **[中斷通話]**。
    
      - 若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。 語音信箱位址的\<格式是 [使用者名\>@\<功能變數名稱\> ] （例如，bob@contoso.com）。
    
      - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。 使用者位址的\<格式是 [使用者名\>@\<功能變數名稱\>]。
    
      - 若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。 電話\<號碼的格式是數位\>@\<domainname\> （例如，+ 14255550121@contoso.com）。 功能變數名稱是用來將呼叫者路由至正確的目的地。

24. 在 [**步驟5指定您的假日**] 底下，按一下一或多組假期的核取方塊，以定義回應群組結束的日期。
    
    <div>
    

    > [!NOTE]  
    > 您必須先定義假日和假日集，然後才能設定工作流程。 使用<STRONG>新的-CsRgsHoliday</STRONG>和<STRONG>CsRgsHolidaySet</STRONG> Cmdlet 來定義假日和假日集。 如需詳細資訊，請參閱<A href="lync-server-2013-optional-define-response-group-holiday-sets.md">（選用）在 Lync Server 2013 中定義回應群組假日集</A>。

    
    </div>

25. 如果您想要在假日上播放郵件，請選取 [在**假日期間播放郵件**] 核取方塊，然後執行下列其中一項動作來指定要播放的訊息：
    
      - 若要將郵件輸入為來電者已轉換為語音的文字，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入訊息。
        
        <div>
        

        > [!NOTE]  
        > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

        
        </div>
    
      - 若要在郵件中使用音訊檔案錄製，請按一下 [**選取錄製**]。 如果您想要上傳新的音訊檔案，請按一下 [**錄製**] 連結。 在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的音訊檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。

        
        </div>

26. 指定在播放郵件後如何處理呼叫（如果已設定郵件）：
    
      - 若要中斷通話，請按一下 **[中斷通話]**。
    
      - 若要將來電轉接至 [語音信箱]，請按一下 [**轉寄給語音信箱**]，然後輸入語音信箱位址。 語音信箱位址的\<格式是 [使用者名\>@\<功能變數名稱\> ] （例如，bob@contoso.com）。
    
      - 若要將呼叫轉寄給其他使用者，請按一下 [**轉寄給 SIP URI**]，然後輸入使用者位址。 使用者位址的\<格式是 [使用者名\>@\<功能變數名稱\>]。
    
      - 若要將來電轉接至其他電話號碼，請按一下 [**轉寄電話號碼**]，然後輸入電話號碼。 電話\<號碼的格式是數位\>@\<domainname\> （例如，+ 14255550121@contoso.com）。 功能變數名稱是用來將呼叫者路由至正確的目的地。

27. 在 [**步驟6設定暫停的音樂**] 底下，請執行下列其中一項動作，選擇您想要讓呼叫者在等待代理程式時聆聽的內容：
    
      - 若要使用預設的音樂保留錄製，請按一下 [**使用預設值**]。
    
      - 若要將音訊檔案錄製用於等候音樂，請按一下 [**選取音樂**檔案]。 如果您想要上傳新的音訊檔案，請按一下 [**音樂**檔案] 連結。 在新瀏覽器視窗中，按一下 **[流覽**]，選取您要使用的檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入音訊檔案。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。

        
        </div>

28. 在 [**步驟7設定互動式語音回應**] 底下的 **[使用者將會聽到下列文字] 或 [錄製的郵件**] 標題中，指定要求呼叫者的問題，如下所示：
    
      - 若要以文字格式輸入問題，請按一下 [**使用文字轉換語音**]，然後在文字方塊中輸入問題。
        
        <div>
        

        > [!NOTE]  
        > 請勿在您輸入的文字中包含 HTML 標籤。 如果您包含 HTML 標籤，您會收到錯誤訊息。

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > "#" 符號是由文字到語音引擎轉譯為「數位」一詞。 如果您需要參照 # 鍵，您應該在提示中使用索引鍵名稱，而不是符號。 例如，若要與銷售額交談，請按井號鍵。

        
        </div>
    
      - 若要使用含有問題的預先錄製音訊檔案，請按一下 [**選取錄製**]，然後按一下 [**錄製**] 連結來上傳檔案。 在新的瀏覽器視窗中，按一下 **[流覽]**，選取音訊檔案，然後按一下 [**開啟**]。 按一下 **[上傳**] 載入檔案，然後選擇您可以在文字方塊中輸入問題（這可讓您將問題及來電者回應轉寄到回應的代理程式）。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔都必須符合特定的需求。 如需支援的檔案格式的詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的 [回應] 群組技術需求</A>。

        
        </div>

29. 在 [**回應 1**] 底下，請執行下列動作，以指定第一次可能的問題答案：
    
    <div>
    

    > [!IMPORTANT]  
    > 請勿在任何語音回復中使用引號（"）。 引號會導致 IVR 失敗。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 您可以選擇允許呼叫者使用語音、數位數位鍵台輸入或兩者同時接聽。

    
    </div>
    
      - 如果您想要讓來電者使用語音進行回應，請在 [**輸入語音回應**] 中輸入答案。
    
      - 如果您想要允許呼叫者以鍵盤上的按鍵進行回應，請按一下 [**數位**] 中的小數位。

30. 指定是否要將呼叫者路由到佇列，或是依以下方式提出其他問題：
    
      - 若要將呼叫者路由到佇列，請按一下 [**傳送至佇列**]，然後在 [**選取佇列**] 中，按一下您要使用的佇列。
    
      - 若要提出其他問題，請按一下 [**提出其他問題**]，然後按一下 [**使用文字轉換語音**] 並輸入問題，或按一下 [**選取錄製**]。 使用本節中的 [回應群組]，指定最多四個可能回應其他問題的回應，以及每個回應所要使用的佇列。 若要指定第三或第四種可能的回復，請按一下 [**回應 3** ] 核取方塊或 [**回應 4** ] 核取方塊。

31. 重複步驟28和29，以指定可能的回應，以及針對每個回應所採取的動作，指定最多三個可能的原始問題答案。 若要指定第三個或第四個可能的答案，請按一下 [**回應 3** ] 核取方塊或 [**回應 4** ] 核取方塊。

32. 按一下 [**部署**]。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>使用 Windows PowerShell 來建立或修改互動式工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  檢索回應群組服務的服務名稱，並將它指派給變數。 在命令列上執行：
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  互動式工作流程需要兩個或多個佇列，以及兩個以上的代理群組。 首先，建立代理程式群組。 用盡
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  建立佇列。 用盡
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  建立第一個回應群組提示。 用盡
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  然後建立在提示之後要執行的動作。 用盡
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  建立第一個回應群組答案。 用盡
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  現在，建立第二個提示、通話動作及答案。 首先建立提示。 用盡
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. 建立第二個通話動作。 用盡
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. 建立第二個回應群組答案。 用盡
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. 建立最上層的提示。 用盡
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. 建立最上層的問題。 用盡
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. 現在，建立工作流程。 用盡
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > 已指定為回應群組管理員的所有使用者，都必須指派第 CsResponseGroupManager 角色。 如果沒有為使用者指派這個角色，就不能管理回應群組。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

