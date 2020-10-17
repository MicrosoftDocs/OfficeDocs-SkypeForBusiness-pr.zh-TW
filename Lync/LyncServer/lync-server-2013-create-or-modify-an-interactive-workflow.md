---
title: Lync Server 2013：建立或修改互動式工作流程
description: Lync Server 2013：建立或修改互動式工作流程。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 470a073322c48c351dbfdfb24ce376731b3e7512
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546989"
---
# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改互動式工作流程

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-11_

使用下列其中一個程式來建立或修改互動式工作流程。

<div>


> [!NOTE]  
> 您可以使用 Lync Server 管理命令介面或回應群組設定工具來建立及修改互動式工作流程。 您可以從 Lync Server 控制台存取回應群組設定工具，或是直接從網頁瀏覽器開啟網頁，只要輸入下列 URL: <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>。



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>使用回應群組設定工具來建立或修改互動式工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 **[回應群組]**，然後按一下 **[工作流程]**。

4.  在 **[工作流程]** 頁面上，按一下 **[建立或編輯工作流程]**。

5.  在 [ **選取服務** ] 搜尋欄位中，輸入主控您要建立或修改之工作流程的 **ApplicationServer** 服務全部或部分名稱。 在產生的服務清單中，按一下您想要的服務，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 回應群組設定工具隨即開啟。 您也可以輸入下列 URL: <STRONG>Https://</STRONG> &lt; webPoolFqdn &gt; <STRONG>/RgsConfig</STRONG>，直接從網頁瀏覽器開啟回應群組設定工具。

    
    </div>

6.  執行下列其中一項：
    
      - 在 **[建立新的工作流程]** 的 **[互動]** 旁邊，按一下 **[建立]**。
    
      - 在 **[管理現有工作流程]** 下，找到想要變更的工作流程，然後在 **[動作]** 下按一下 **[編輯]**。

7.  如果尚未準備好讓使用者開始撥號至工作流程，請清除 **[啟用工作流程]** 核取方塊。
    
    <div>
    

    > [!NOTE]  
    > 若要建立受管理的工作流程，您必須選取 <STRONG>[啟用工作流程</STRONG>]。 在您儲存使用中的受管理工作流程之後，您可以修改並停用該工作流程。

    
    </div>

8.  若要允許同盟使用者撥打群組，請選取 **[針對同盟啟用]** 核取方塊。 您也必須具有適用于同盟設定之回應群組應用程式的外部存取原則。
    
    <div>
    

    > [!NOTE]  
    > 全域外部存取原則會套用至回應群組應用程式。 您可以使用 Lync Server 控制台或使用 <STRONG>get-csexternalaccesspolicy</STRONG> 指令程式將 EnableOutsideAccess 參數設定為 True，設定回應群組同盟的全域原則。 請記住，除非將站台原則或使用者原則指派給使用者，否則通用原則設定適用於所有使用者。 因此在變更回應群組的此設定之前，請確認同盟設定符合您組織的需求。 如需有關如何將原則套用至使用者的詳細資訊，請參閱 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy In Lync Server 2013</A>。 如需同盟設定的詳細資訊，請參閱 Lync Server 管理命令介面檔中的 <STRONG>Set-get-csexternalaccesspolicy</STRONG> 。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Online 中主控的使用者無法將呼叫放入內部部署中所主控的回應群組。 這在混合式部署中，以及內部部署與 Lync Online 部署同盟的情況皆為 true。

    
    </div>

9.  若要在通話期間隱藏代理人的身分識別，請選取 **[啟用代理人匿名]** 核取方塊。
    
    <div>
    

    > [!NOTE]  
    > 雖然代理人或來電者可以在建立通話之後新增 IM 及視訊，但是匿名通話不能以立即訊息 (IM) 或視訊開始。 匿名代理人也可以保留通話、轉接通話 (無條件轉接及諮詢轉接)，以及駐留及擷取通話。 匿名通話不支援會議、應用程式共用和桌面共用、檔案傳輸、白板和資料共同作業，以及通話記錄。 使用 Lync VDI 外掛程式的代理程式可以以匿名方式接收來電，但無法以匿名方式撥打撥出電話。

    
    </div>

10. 在 [ **輸入要接聽電話的群組位址**] 下，輸入主要 SIP 統一資源識別項 (URI) 會接聽工作流程呼叫的群組的位址。

11. 在 [ **顯示名稱**] 中，輸入您要針對工作流程顯示的名稱 (例如，Sales IVR Response Group) 。
    
    <div>
    

    > [!NOTE]  
    > &lt;在顯示名稱中不要包含 "" 或 " &gt; " 字元。 下列是保留的顯示名稱，因此請不要使用它們：RGS Presence Watcher 或宣告服務。

    
    </div>

12. 在 **[電話號碼]** 中，輸入回應群組的線路 URI (例如，+14255550165)。

13. 在 **[顯示號碼]** 中，輸入想要針對回應群組顯示的號碼 (例如，+1 (425) 555-0165)。

14.  (選用) 在 [ **描述**] 中，輸入您要顯示在 Lync 用戶端連絡人卡片上之工作流程的描述。

15. 在 [ **工作流程類型**] 中，選取 [ **受** 回應群組管理員管理此工作流程]。 請執行下列動作，將回應群組管理員指派給工作流程：
    
    1.  為此工作流程輸入管理員的 SIP URI，然後按一下 [ **新增**]。
    
    2.  輸入其他管理員的 SIP URI 以新增至工作流程，然後按一下 [ **新增**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 指定為回應群組管理員的每一位使用者都必須指派 CsResponseGroupManager 角色。 若未指派此角色的使用者，他們就無法管理回應群組。

    
    </div>

16. 在 **[步驟 2 選取語言]** 下，按一下要用於語音辨識及文字轉換語音的語言。

17. 如果您想要設定歡迎訊息，請在 **[步驟 3 設定歡迎訊息]** 下選取 **[播放歡迎訊息]** 核取方塊，然後執行下列其中一項：
    
      - 若要以文字輸入為來電者轉換成語音的歡迎訊息，按一下 **[使用文字轉語音]**，然後在文字方塊中輸入歡迎訊息。
        
        <div>
        

        > [!NOTE]  
        > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

        
        </div>
    
      - 若要使用 Wave 或 Windows Media 音訊檔案錄音做為歡迎訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的音訊檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的回應群組技術需求</A>。

        
        </div>

18. 在 **[步驟 4 指定您的上班時間]** 的 **[您的時區]** 方塊中，按一下工作流程的時區。
    
    <div>
    

    > [!NOTE]  
    > 此時區即為工作流程的來電者和專員所在之時區，可用來計算開啟和關閉的時間。例如，如果工作流程設定為使用「北美東部時區」，而工作流程排定為早上 7:00 開啟，晚上 11:00 關閉，則開啟和關閉的時間就會分別假設為東部時區 7:00 和東部時區 11:00:00。(您必須使用 24 小時時間標記法輸入時間)。

    
    </div>

19. 執行下列其中一項，以選取想要使用的上班時間排程類型：
    
      - 若要使用預先定義的上班時間排程，請按一下 **[使用預設排程]**，然後從下拉式清單中選取想要使用的排程。
        
        <div>
        

        > [!NOTE]  
        > 您至少先前必須已定義一個預設排程，才能選取此選項。 您可以使用 <STRONG>New-CSRgsHoursOfBusiness</STRONG> Cmdlet，來定義預設排程。 如需詳細資訊，請參閱 <A href="lync-server-2013-optional-define-response-group-business-hours.md"> (選用) 在 Lync Server 2013 中定義回應群組上班時間</A>。 當您選取預設排程時，<STRONG>[日]</STRONG>、<STRONG>[開啟]</STRONG> 及 <STRONG>[關閉]</STRONG> 會自動填入回應群組可用的日及時數。

        
        </div>
    
      - 若要使用只套用至此工作流程的自訂排程，請按一下 **[使用自訂排程]**。

20. 如果您是建立此工作流程的自訂排程，請按一下回應群組可用之一星期的哪幾天的核取方塊。

21. 如果您是建立自訂排程，請輸入回應群組可用時的 **[開啟]** 及 **[關閉]** 時間。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>[開啟]</STRONG> 及 <STRONG>[關閉]</STRONG> 時間必須使用 24 小時時間標記法。例如，如果您辦公室平日的辦公時間為 9 點到 5 點，而且會在中午用餐時間關閉，則會將上班時間指定為 <STRONG>[開啟]</STRONG> 9:00、<STRONG>[關閉]</STRONG> 12:00、<STRONG>[開啟]</STRONG> 13:00 以及 <STRONG>[關閉]</STRONG> 17:00。

    
    </div>

22. 如果您想要在辦公室關閉時播放訊息，請選取 **[在回應群組下班時播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：
    
      - 若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。
        
        <div>
        

        > [!NOTE]  
        > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

        
        </div>
    
      - 若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的回應群組技術需求</A>。

        
        </div>

23. 指定在播放訊息之後如何處理通話 (如果有設定訊息)：
    
      - 若要中斷來電，按一下 **[中斷通話]**。
    
      - 若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。 語音信箱位址的格式為 \<username\> @ \<domainname\> (例如，bob@contoso.com) 。
    
      - 若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。 使用者位址的格式為 \<username\> @ \<domainname\> 。
    
      - 若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。 電話號碼的格式為 \<number\> @ \<domainname\> (例如，+ 14255550121@contoso.com) 。 網域名稱會用來將來電者路由到正確的目的地。

24. 在 **[步驟 5 指定您的假日]** 下，按一下可定義回應群組沒上班之天數的一或多個假日集的核取方塊。
    
    <div>
    

    > [!NOTE]  
    > 您需要先定義假日及假日集，再設定工作流程。 使用 <STRONG>New-CsRgsHoliday</STRONG> 及 <STRONG>New-CsRgsHolidaySet</STRONG> Cmdlet，可定義假日及假日集。 如需詳細資訊，請參閱 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md"> (選用) 在 Lync Server 2013 中定義回應群組假日集</A>。

    
    </div>

25. 如果您想要在假日時播放訊息，請選取 **[在假日期間播放訊息]** 核取方塊，然後執行下列其中一項，以指定要播放的訊息：
    
      - 若要以文字輸入為來電者轉換成語音的訊息，請按一下 **[使用文字轉語音]**，然後在文字方塊中輸入訊息。
        
        <div>
        

        > [!NOTE]  
        > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

        
        </div>
    
      - 若要使用音訊檔案錄音做為訊息，請按一下 **[選取錄音]**。如果您想要上傳新的音訊檔案，請按一下 **[一筆記錄]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的音訊檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中回應群組的技術需求</A>。

        
        </div>

26. 指定在播放訊息之後如何處理通話 (如果有設定訊息)：
    
      - 若要中斷來電，按一下 **[中斷通話]**。
    
      - 若要將來電轉送到語音信箱，按一下 **[轉送至語音信箱]**，然後輸入語音信箱位址。 語音信箱位址的格式為 \<username\> @ \<domainname\> (例如，bob@contoso.com) 。
    
      - 若要將來電轉送給其他使用者，按一下 **[轉送至 SIP URI]**，然後輸入使用者的位址。 使用者位址的格式為 \<username\> @ \<domainname\> 。
    
      - 若要將來電轉送給其他電話號碼，按一下 **[轉送至電話號碼]**，然後輸入電話號碼。 電話號碼的格式為 \<number\> @ \<domainname\> (例如，+ 14255550121@contoso.com) 。 網域名稱會用來將來電者路由到正確的目的地。

27. 在 **[步驟 6 設定等候音樂]** 中，選擇您要來電者在等候專員時所聆聽的音樂，方法如下：
    
      - 若要使用預設的等候音樂錄音，按一下 **[使用預設]**。
    
      - 若要使用音訊檔案錄音做為等候音樂，請按一下 **[選取音樂檔案]**。如果您想要上傳新的音訊檔案，請按一下 **[音樂檔案]** 連結。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取想要使用的檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入音訊檔案。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的回應群組技術需求</A>。

        
        </div>

28. 在 **[步驟 7 設定互動語音回應**] 的 **[使用者將聽到下列文字或錄製的訊息]** 標題下，依下列方式指定要詢問來電者的問題：
    
      - 若要以文字格式輸入問題，按一下 **[使用文字轉語音]**，然後在文字方塊中輸入問題。
        
        <div>
        

        > [!NOTE]  
        > 請不要在輸入的文字中包括 HTML 標籤。如果您包括 HTML 標籤，則會收到錯誤訊息。

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > 文字轉語音引擎會將 "#" 符號轉譯為「號碼」一詞。 如果需要在提示中提及 # 鍵，則應該使用按鍵名稱，而非使用該符號。 例如，「與銷售人員交談，按井字鍵。」

        
        </div>
    
      - 若要使用包含問題的預錄音訊檔案，請按一下 **[選取錄音]**，然後按一下 **[一筆記錄]** 連結以上傳檔案。在新的瀏覽器視窗中按一下 **[瀏覽]**，並選取音訊檔案，然後按一下 **[開啟]**。按一下 **[上傳]** 載入檔案，然後在文字方塊中選擇性地輸入問題 (如此可將問題和來電者的回應轉送給回應代理人)。
        
        <div>
        

        > [!NOTE]  
        > 所有使用者提供的音訊檔案都必須符合特定要求。 如需支援的檔案格式的詳細資訊，請參閱 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 中的回應群組技術需求</A>。

        
        </div>

29. 在 **[回應 1]** 中，藉由下列動作指定問題的第一個可能答覆：
    
    <div>
    

    > [!IMPORTANT]  
    > 請不要在任何語音回應中使用引號 (")。引號會導致 IVR 失敗。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 您可以選擇讓來電者使用語音及 (或) 英數鍵台輸入來進行答覆。

    
    </div>
    
      - 如果您想要讓來電者使用語音來回應，請在 **[輸入語音回應]** 中輸入答覆。
    
      - 如果您想要讓來電者按鍵台上的按鍵來回應，請在 **[數字]** 中按一下鍵台數字。

30. 指定是否要將來電者路由傳送到佇列或詢問另一個問題，如下所述：
    
      - 若要將來電者路由傳送到佇列，請按一下 **[傳送到佇列]**，並在 **[選取佇列]** 中按一下想要使用的佇列。
    
      - 若要詢問另一個問題，請按一下 **[詢問另一個問題]**，然後按一下 **[使用文字轉語音]**，並輸入問題，或按一下 **[選取錄音]**。 使用本節中的回應分組，指定其他問題最多四個可能回應，以及用於每個回應的佇列。 若要指定第三或第四種可能的回應，請按一下 [ **回應 3** ] 核取方塊或 [ **回應 4** ] 核取方塊。

31. 重複步驟 28 及 29 指定可能的回應，以及針對每個回應採取的動作，以指定原始問題最多三個可能的答案。若要指定第三個或第四個可能的答案，請按一下 **[回應 3]** 核取方塊或 **[回應 4]** 核取方塊。

32. 按一下 **[部署]**。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>使用 Windows PowerShell 建立或修改互動式工作流程

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  取得回應群組服務的服務名稱，並將其指派給變數。 在命令列中執行：
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  互動式工作流程需要兩個以上的佇列以及兩個以上的代理人群組。 首先，建立代理人群組。 運行：
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  建立佇列。 運行：
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  建立第一個回應群組提示。 運行：
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  然後建立在提示後要執行的動作。 運行：
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  建立第一個回應群組答案。 運行：
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  現在，建立第二個提示、通話動作和答案。 請先建立提示。 運行：
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. 建立第二個通話動作。 運行：
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. 建立第二個回應群組答案。 運行：
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. 建立最高層級提示。 運行：
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. 建立最上層問題。 運行：
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. 現在建立工作流程。 運行：
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > 指定為回應群組管理員的所有使用者都必須指派第 CsResponseGroupManager role。 若未指派此角色的使用者，他們就無法管理回應群組。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

