---
title: Lync Server 2013：建立或修改位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a2f2d5575bee6e6b29b6a5c289cfa589a33c411
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改位置原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在 Lync Server 2013 中，您可以使用位置原則，套用與增強型 9-1-1 (E9-1-1) 功能及使用者或連絡人的位置設定相關的設定。 位置原則會判斷使用者是否已啟用 E9-1-1，如果是，則會決定緊急電話的行為。 例如，您可以使用位置原則來定義組成緊急電話的數字 (例如，在美國為 911)、是否應自動告知公司的安全部門，以及應如何路由傳送來電。

您可以在 Lync Server 2013 [控制台] 中的 [**網路**設定] 群組設定位置原則。 從 Lync Server 控制台，您可以查看、建立、修改或刪除位置原則。 本節中的程序可用來建立或修改位置原則。 如需刪除位置原則的詳細資訊，請參閱[刪除位置原則中的 Lync Server 2013](lync-server-2013-deleting-a-location-policy.md)。

在 Lync Server 2013 中，您可以從位置資訊服務覆寫用戶端要求位置更新之間的預設時間長度。 預設值為 4 小時。 使用 **Set-CsLocationPolicy** Cmdlet 搭配 LocationRefreshInterval 參數可以覆寫預設值。

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>在 Lync Server 控制台中建立新的位置原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中按一下 [網路設定]****，然後按一下 [位置原則]****。

4.  在「位置原則」**** 頁面上按一下 [新增]****，然後選取您要建立的原則類型：
    
      - 若要建立網站原則，請按一下 [站台原則]****。在 [選取站台]**** 中選擇要套用原則的網站，然後按一下 [確定]****。在「新增位置原則」**** 頁面上，[範圍]**** 欄位會包含 [站台]**** 值，[名稱]**** 欄位則會包含您所選擇的網站名稱。您無法修改這些欄位。網站原則會自動套用至指定網站上的所有使用者，並且覆寫這些使用者的全域原則。
    
      - 若要建立 [使用者原則]****，請按一下 [使用者原則]****。在 [新增位置原則]**** 中，[範圍]**** 欄位會包含 [使用者]**** 值。您無法修改此值。在 [名稱]**** 欄位中，輸入您要為此原則指定的名稱。使用者原則不會自動套用至任何使用者。在建立使用者原則後，您必須以手動方式將原則授與給要套用此原則的使用者或網路網站。

5.  填入其餘欄位，如下所示：
    
      - **啟用增強型急診服務**    選取此核取方塊可讓與此原則相關聯的使用者 E9-1-1。 啟用緊急服務後，Lync Server 用戶端將會在註冊時取得位置資訊，並在進行緊急通話時包含該資訊。
    
      - **位置**    指定下列其中一個值：
        
          - **必要**    當用戶端在新位置註冊時，系統會提示使用者輸入位置資訊。 使用者可以不輸入任何資訊而將提示關閉。 如果輸入資訊，緊急服務提供者會先接聽緊急電話，以確認該位置在路由傳送至公用安全回應點 (PSAP) 操作員 (也就是911操作員) 。
        
          - **不需要**    不會提示使用者輸入位置。 當通話沒有地點資訊時，緊急服務提供者會接聽來電，並要求地點。
        
          - **免責聲明**    此選項與**必要條件**相同，只是使用者無法在未輸入位置資訊的情況下關閉提示。 使用者仍可完成緊急通話，但沒有輸入資訊，可以完成其他電話。 此外，還會向使用者顯示免責聲明文字，以提醒他們拒絕輸入位置資訊的後果。 若要設定免責聲明文字，您必須使用 Lync Server 管理命令介面來執行**CsLocationPolicy** Cmdlet，或使用 EnhancedEmergencyServiceDisclaimer 參數**New-CsLocationPolicy** Cmdlet。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)或[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 。
            
            <div>
            

            > [!NOTE]  
            > 在 Lync Server 2013 中，您可以使用位置原則，針對不同的地區設定或不同的使用者集合設定不同的免責聲明，不同于在 Lync Server 2010 中，您只能為整個組織指定全域免責聲明。

            
            </div>
    
      - **僅限**     緊急服務的使用位置由於各種原因，Lync 可以使用位置資訊 (例如，將您目前位置的團隊) 通知。 選取此核取方塊可確保位置資訊僅供緊急通話之用。
    
      - **PSTN 使用**     方式公用交換電話網路 (PSTN) 使用方式，用來判斷哪個語音路由將用來從使用此設定檔的用戶端路由緊急通話。 與此使用方式關聯的路由應該指向緊急通話專用的 SIP 主幹，或緊急位置識別號碼 (ELIN) 閘道，可將緊急通話路由傳送至最近的公用安全回復點 (PSAP) 。
    
      - **緊急撥號號碼**    要撥通緊急服務的號碼。 此值在美國為 911。 字串必須由 0 到 9 的數字組成，長度可為 1 到 10 位數字。
    
      - **急診撥號遮罩**    撥打時，要轉譯為 [緊急撥號號碼] 值的數位。 例如，如果您在此欄位中輸入值212，而 [緊急撥號號碼] 欄位的值為911，如果使用者撥打212，將會對911進行呼叫。 這可讓您撥打備用的緊急號碼，並且仍然可以撥打緊急服務 (例如，如果來自國家或地區具有不同緊急號碼的某人嘗試撥打該國家或地區的號碼，而不是其目前在) 中的國家或地區號碼。 您可以使用分號分隔多個值，藉此定義多組緊急撥話遮罩。 例如，212; 414。 字串的長度上限為 100 字元。 每個字元必須是 0 到 9 的數字。
        
        <div>
        

        > [!IMPORTANT]  
        > 確保指定的撥號遮罩值與通話保留範圍中的數字不同。 通話保留路由優先於緊急撥號字串轉換。 若要檢視現有的通話駐留範圍，請按一下左導覽列中的 [語音功能]<STRONG></STRONG>，然後按一下 [通話駐留]<STRONG></STRONG>。 如需詳細資訊，請參閱<A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">在 Lync Server 2013 中設定休止通話的電話號碼分機</A>。

        
        </div>
    
      - **通知 URI**    進行緊急通話時， (URIs) 的一或多個 SIP 統一資源識別項。 例如，每次有人撥打緊急電話時，就會透過立即訊息通知公司的安全部門。 如果可以使用來電者的位置，通知中會包含該位置的資訊。 可以使用逗號分隔的清單包含多個 SIP URI。 例如，"sip： security@litwareinc .com"，"sip： kmyer@litwareinc .com"。 支援通訊群組清單。 字串長度必須介於1到256個字元之間，且必須以前置詞 "sip：" 開頭。 在您按一下 [通知 URI] 欄位之前，會顯示範例。
    
      - **會議 URI**    在此案例中，將警衛至所撥打之任何緊急通話的協力廠商的 SIP URI （此為電話號碼）。 例如，公司的安全性辦公室可在緊急通話時接聽來電，並根據**會議模式**欄位) 中提供的值接聽或參與通話 (。 字串長度必須為 1 到 256 字元，且開頭必須為首碼 sip:。 會顯示範例，直到您在此欄位內按一下。
    
      - **會議模式**    [！注意] 如果您在 [**會議 URI** ] 欄位中指定值，則**會議模式**會決定協力廠商是否可以參與通話或只能接聽。 指定下列其中一個選項：
        
          - **單向**    協力廠商只能接聽來電者與 PSAP 操作員之間的交談。
        
          - **雙向**    協力廠商可以接聽及參與來電者與 PSAP 操作員之間的呼叫。

6.  按一下 [認可]****。
    
    <div>
    

    > [!IMPORTANT]  
    > 當您建立使用者原則時，該原則並不會自動套用至任何使用者或網路網站。若要將原則套用至使用者，請按一下左導覽列中的 [使用者]<STRONG></STRONG>。尋找要套用原則的使用者。在 [編輯]<STRONG></STRONG> 功能表上，按一下 [顯示詳細資料]<STRONG></STRONG>。在 [編輯 Lync Server 使用者]<STRONG></STRONG> 頁面上，從 [位置原則]<STRONG></STRONG> 下拉式清單中選取新的位置原則，然後按一下 [認可]<STRONG></STRONG>。<BR>若要將原則套用至網路網站，請按一下左導覽列中的 [網路設定]<STRONG></STRONG>，然後按一下 [站台]<STRONG></STRONG>。尋找要套用原則的網路網站。在 [編輯]<STRONG></STRONG> 功能表上，按一下 [顯示詳細資料]<STRONG></STRONG>。在 [編輯站台]<STRONG></STRONG> 中，從 [位置原則]<STRONG></STRONG> 下拉式清單中選取新的位置原則，然後按一下 [認可]<STRONG></STRONG>。

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>在 Lync Server 控制台中修改位置原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中按一下 **[網路設定]**，然後按一下 **[位置原則]**。

4.  在 **[位置原則]** 頁面上，選取您要修改的位置原則。

5.  在 [編輯]**** 功能表上，按一下 [顯示詳細資料]****。

6.  在「編輯位置原則」**** 頁面上視需要修改欄位 (如需詳細資訊，請參閱本主題前述＜建立新的位置原則＞程序中的＜步驟 5＞)。

7.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除位置原則](lync-server-2013-deleting-a-location-policy.md)  


[定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)  


[在 Lync Server 2013 中設定休止通話的電話號碼分機號碼](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

