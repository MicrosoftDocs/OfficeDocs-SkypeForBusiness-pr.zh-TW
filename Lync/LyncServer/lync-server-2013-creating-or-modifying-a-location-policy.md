---
title: Lync Server 2013：建立或修改位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 173cfd6ce158a089e03a9eded12c3c6920183463
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改位置原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在 Lync Server 2013 中，您可以使用位置原則來套用與增強版9-1-1 （E9-1）功能相關的設定，以及使用者或連絡人的位置設定。 位置原則會判斷使用者是否已啟用 E9-1-1，以及是否有緊急通話的行為。 例如，您可以使用位置原則來定義代表緊急通話的號碼（例如，911在美國）、企業安全性是否應該自動收到通知，以及如何路由通話。

您可以在 Lync Server 2013 [控制台] 的 [**網路**設定] 群組中設定位置原則。 在 Lync Server [控制台] 中，您可以查看、建立、修改或刪除位置原則。 使用本節中的程式來建立或修改位置原則。 如需有關刪除位置原則的詳細資訊，請參閱[刪除 Lync Server 2013 中的位置原則](lync-server-2013-deleting-a-location-policy.md)。

在 Lync Server 2013 中，您可以覆寫來自位置資訊服務之位置更新之用戶端要求的預設時間長度。 預設值為4小時。 將**CsLocationPolicy** Cmdlet 與 LocationRefreshInterval 參數搭配使用，以覆寫預設值。

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>在 Lync Server [控制台] 中建立新的位置原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**位置原則**]。

4.  在 [**位置原則**] 頁面上，按一下 [**新增**]，然後選取您要建立的原則類型：
    
      - 若要建立網站原則，按一下 [**網站原則**]。 在 [**選取網站**] 中，選擇您要套用原則的網站，然後按一下 **[確定]**。 在 [**新的位置原則**] 頁面上，[**範圍**] 欄位包含 [值]**網站**，而 [**名稱**] 欄位則包含您所選擇的網站名稱。 您無法修改其中一個欄位。 網站原則會自動套用至指定網站上的所有使用者，並覆寫這些使用者的全域原則。
    
      - 若要建立**使用者原則**，按一下 [**使用者原則**]。 在**新的位置原則**中，[**範圍**] 欄位包含 [**使用者**] 值。 您無法修改這個值。 在 [**名稱**] 欄位中，輸入您要賦予此原則的名稱。 使用者原則不會自動套用至任何使用者。 建立使用者原則之後，您必須手動將原則授與您要套用原則的使用者或網路網站。

5.  請按照下列步驟填寫其餘欄位：
    
      - **啟用 [增強緊急服務**   ] 選取此核取方塊，以啟用與此原則關聯的使用者 E9-1-1。 啟用緊急服務時，Lync Server 用戶端會在註冊時取得位置資訊，並在發出緊急通話時包含該資訊。
    
      - **位置**   指定下列其中一個值：
        
          - **必要**   ：用戶端在新位置註冊時，系統會提示使用者輸入位置資訊。 使用者可以關閉提示，而不需輸入任何資訊。 如果輸入了資訊，緊急電話會在傳送到公用安全應答點（PSAP）運算子（也就是911運算子）之前，先由緊急服務提供者應答以驗證該位置。
        
          - **不需要**   使用者系統不會提示您輸入位置。 當通話不含位置資訊時，緊急服務提供者將接聽通話並要求位置。
        
          - **免責聲明**   除了使用者無法在不輸入位置資訊的情況下關閉提示之外，這個選項也是**必要**的。 使用者仍然可以完成緊急通話，但不需輸入資訊，就能完成其他通話。 此外，系統會向使用者顯示免責聲明文字，讓他們能夠提醒您拒絕輸入位置資訊的後果。 若要設定免責聲明文字，您必須使用 Lync Server Management Shell 來執行**CsLocationPolicy** Cmdlet，或使用 EnhancedEmergencyServiceDisclaimer 參數的**新 CsLocationPolicy** Cmdlet。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的[設定 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)或[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 。
            
            <div>
            

            > [!NOTE]  
            > 在 Lync Server 2013 中，您可以使用位置原則，針對不同的地區設定或不同的使用者組設定不同的免責聲明，不像在 Lync Server 2010 中，您只能為整個組織指定全域免責聲明。

            
            </div>
    
      - **針對急診 services 使用位置只有**   Lync 可以出於各種原因使用位置資訊（例如，通知小組目前的位置）。 選取此核取方塊以確保位置資訊只能供緊急通話使用。
    
      - **PSTN 使用**   公開交換電話網絡（PSTN）用法，用來判斷哪種語音路線將用來從使用此設定檔的用戶端傳送緊急通話。 與此使用相關聯的路線應該指向專用於緊急通話的 SIP 幹線，或指向將緊急呼叫路由到最接近的公用安全應答點（PSAP）的緊急位置識別號碼（ELIN）閘道。
    
      - **緊急撥號號碼**   撥號以達到緊急服務的號碼。 在美國，此值為911。 字串必須由數位0到9組成，且長度不能超過1到10個數字。
    
      - **緊急撥號遮罩**   您要在撥入時，要轉換成 [緊急撥號號碼] 值的數位。 例如，如果您在這個欄位中輸入212的值，而 [緊急電話撥入號碼] 欄位的值為911，則使用者212撥打電話時，將會對911進行該通話。 這可讓您撥打備用的緊急電話號碼，而且仍能撥打電話給緊急服務（例如，如果某個國家或地區有不同緊急號碼的人嘗試撥打該國家或地區的號碼，而不是他們目前所在的國家或地區）。 您可以使用分號來分隔值，以定義多個緊急撥號遮罩。 例如，212; 414。 字串的最大長度為100個字元。 每個字元都必須是數位0到9。
        
        <div>
        

        > [!IMPORTANT]  
        > 確定指定的撥號遮罩值與 [通話駐留] 軌道範圍中的數位不同。 通話駐留路由將會優先于緊急撥號字串轉換。 若要查看現有的通話公園軌道範圍，請按一下左側導覽列中的 [<STRONG>語音功能</STRONG>]，然後按一下 [<STRONG>通話駐留</STRONG>]。 如需詳細資訊，請參閱<A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">在 Lync Server 2013 中設定停用通話的電話號碼延伸</A>。

        
        </div>
    
      - **通知 URI**   一或多個 SIP 統一資源識別項（uri），會在發出緊急通話時收到通知。 例如，只要進行緊急通話，公司安全性 office 就會透過立即訊息通知。 如果呼叫者的位置可供使用，該位置將會包含在通知中。 多個 SIP Uri 可以包含為以逗號分隔的清單。 例如，"sip： security@litwareinc .com"，"sip： kmyer@litwareinc .com"。 支援通訊群組清單。 字串的長度必須是1到256個字元，且必須以前置詞「sip：」開頭。 在您按一下 [通知 URI] 欄位之前，會顯示範例。
    
      - **會議 uri**   在此案例中，將會 conferenced 到所進行的任何緊急呼叫的 SIP uri （在此例中為）的電話號碼。 例如，當緊急通話發出並接聽電話或參與通話時（視 [**會議模式]** 欄位中提供的值而定），公司安全性 office 可能會接聽來電。 字串必須是介於1到256個字元的長度，且必須以前置詞 sip 開頭：。 在此欄位內按一下，就會顯示範例。
    
      - **[會議模式]**   如果您在 [**會議 URI** ] 欄位中指定值，**會議模式**會判斷協力廠商是否可以參與通話，或只能接聽。 指定下列其中一個選項：
        
          - **單向第**三方只能聽取來電者與 PSAP 操作員之間的交談。   
        
          - **** 協力廠商可以接聽並參與呼叫者與 PSAP 操作員之間的通話。   

6.  按一下 [認可]****。
    
    <div>
    

    > [!IMPORTANT]  
    > 當您建立使用者原則時，最初該原則不會套用至任何使用者或網路網站。 若要將原則套用至使用者，請按一下左側導覽列中的 [<STRONG>使用者</STRONG>]。 尋找您要套用原則的使用者。 按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。 在 [<STRONG>編輯 Lync Server 使用者</STRONG>] 頁面上，從 [<STRONG>位置原則</STRONG>] 下拉式清單中選取新的位置原則，然後按一下 [Commit] （<STRONG>提交</STRONG>）。<BR>若要將原則套用至網路網站，請按一下左側導覽列中的 [<STRONG>網路</STRONG>設定]，然後按一下 [<STRONG>網站</STRONG>]。 尋找您要套用原則的網路網站。 按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。 在 [<STRONG>編輯網站</STRONG>] 中，從 [<STRONG>位置原則</STRONG>] 下拉式清單中選取新的位置原則，然後按一下 [Commit] （<STRONG>提交</STRONG>）。

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>在 Lync Server [控制台] 中修改位置原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**位置原則**]。

4.  在 [**位置原則**] 頁面上，選取您要修改的位置原則。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯位置原則**] 頁面上，視需要修改欄位（如需詳細資訊，請參閱本主題前面的「建立新位置原則中的步驟5」）。

7.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[刪除 Lync Server 2013 中的位置原則](lync-server-2013-deleting-a-location-policy.md)  


[定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)  


[在 Lync Server 2013 中設定停用通話的電話號碼延伸](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

