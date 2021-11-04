---
title: 管理增強型9-1-1 與位置服務
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 商務用 Skype Server 支援從商務用 Skype 用戶端呼叫的增強型 9-1-1 (E9-1-1) 。 當您設定 E9-1-1 的商務用 Skype Server，緊急通話從商務用 Skype 中包含緊急回應位置 (ERL) 資訊從位置資訊服務資料庫。
ms.openlocfilehash: cff19de879066163f53de6b8d51ef8384d451438
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763771"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>在 Busines Server 的 Skype 中管理增強型9-1-1 與位置服務

商務用 Skype Server 支援從商務用 Skype 用戶端呼叫的增強型 9-1-1 (E9-1-1) 。 當您設定 E9-1-1 的商務用 Skype Server，緊急通話從商務用 Skype 中包含緊急回應位置 (ERL) 資訊從位置資訊服務資料庫。 使用本文中的程式來管理位置原則。

> [!Note]
> 如需部署高級企業語音功能（如 E9-1-1 和 Location 資訊服務）的詳細資訊，請參閱[部署 advanced 企業語音功能](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md)。

在商務用 Skype Server 中，您可以使用位置原則，套用與增強型 9-1-1 (E9-1-1) 功能及使用者或連絡人的位置設定相關的設定。 位置原則會判斷使用者是否已啟用 E9-1-1，如果是，則會決定緊急電話的行為。 例如，您可以使用位置原則來定義組成緊急電話的數字 (例如，在美國為 911)、是否應自動告知公司的安全部門，以及應如何路由傳送來電。

您可以從商務用 Skype Server 控制台中的 [**網路** 設定] 群組設定位置原則。 您可以從商務用 Skype Server 控制台，查看、建立、修改或刪除位置原則。 請使用下列程序來檢視位置原則的相關資訊。 


## <a name="view-location-policy-information"></a>查看位置原則資訊 

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **位置原則**]。

4.  在 **[位置原則]** 頁面上，選取您要修改的位置原則。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。
 
    > [!NOTE]  
    > 您一次只能檢視一個位置原則的相關資訊。

依預設會有名為「通用」的單一原則存在，且無法刪除或重新命名。但您可以修改全域原則。若您未建立網站原則或個別使用者原則，則所有使用者與連絡人都會套用此原則。特定的使用者必須套用個別使用者原則。


## <a name="create-or-modify-a-location-policy"></a>建立或修改位置原則 

在商務用 Skype Server 中，您可以從 location 資訊服務覆寫用戶端要求進行位置更新之間的預設時間長度。 預設值為 4 小時。 使用 **Set-CsLocationPolicy** Cmdlet 搭配 LocationRefreshInterval 參數可以覆寫預設值。


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中建立新的位置原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **位置原則**]。

4.  在「位置原則」頁面上按一下 [新增]，然後選取您要建立的原則類型：
    
      - 若要建立網站原則，請按一下 [站台原則]。在 [選取站台] 中選擇要套用原則的網站，然後按一下 [確定]。在「新增位置原則」頁面上，[範圍] 欄位會包含 [站台] 值，[名稱] 欄位則會包含您所選擇的網站名稱。您無法修改這些欄位。網站原則會自動套用至指定網站上的所有使用者，並且覆寫這些使用者的全域原則。
    
      - 若要建立 [使用者原則]，請按一下 [使用者原則]。在 [新增位置原則] 中，[範圍] 欄位會包含 [使用者] 值。您無法修改此值。在 [名稱] 欄位中，輸入您要為此原則指定的名稱。使用者原則不會自動套用至任何使用者。在建立使用者原則後，您必須以手動方式將原則授與給要套用此原則的使用者或網路網站。

5.  填入其餘欄位，如下所示：
    
      - **啟用增強型急診服務**   選取此核取方塊可讓與此原則相關聯的使用者 E9-1-1。 啟用緊急服務時，商務用 Skype Server 用戶端將會在註冊時取得位置資訊，並在進行緊急通話時包含該資訊。
    
      - **位置**   指定下列其中一個值：
        
          - **必要**   當用戶端在新位置登錄時，會提示使用者輸入位置資訊。使用者可以不輸入任何資訊而將提示關閉。如果輸入資訊，則緊急通話會先由緊急服務提供者接聽以確認位置，然後再路由傳送到公眾安全回應點 (PSAP) 接線員 (即 911 接線員)。
        
          - **不需要**   將不會提示使用者輸入位置。當撥打的電話沒有位置資訊時，緊急服務提供者會接聽來電，並要求提供位置。
        
          - **免責聲明**   此選項與 **必要條件** 相同，只是使用者無法在未輸入位置資訊的情況下關閉提示。 使用者仍可完成緊急通話，但沒有輸入資訊，可以完成其他電話。 此外，還會向使用者顯示免責聲明文字，以提醒他們拒絕輸入位置資訊的後果。 若要設定免責聲明文字，您必須使用商務用 Skype Server 管理命令介面執行 **set-CsLocationPolicy 指令程式**，或使用 EnhancedEmergencyServiceDisclaimer 參數來執行 **New-CsLocationPolicy** Cmdlet。 如需詳細資訊，請參閱 [Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 或 [New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy)。
          
    
      - **僅限緊急服務的使用位置** 商務用 Skype 可以出於各種原因使用位置資訊 (例如，將您目前位置) 的團隊成員通知給小組成員。 選取此核取方塊可確保位置資訊僅供緊急通話之用。
    
      - **PSTN 使用方式**   公用交換電話網路 (PSTN) 的使用方式，可以用來決定要使用哪一個語音路由來路由傳送使用此設定檔的用戶端所撥打的緊急電話。與此使用方式相關聯的路由應指向專用於緊急通話的 SIP 主幹，或指向可將緊急通話路由傳送至最近公共安全勤務中心 (PSAP) 的緊急位置識別碼 (ELIN) 閘道。
    
      - **緊急撥號**   聯絡緊急服務時所撥打的號碼。此值在美國為 911。字串必須由 0 到 9 的數字組成，長度可為 1 到 10 位數字。
    
      - **緊急撥號遮罩**   一個要在撥號時轉譯成緊急撥號值的號碼。例如，若您在此欄位中輸入值 212，而緊急撥號欄位的值為 911，當使用者撥打 212 時，通話將會轉接至 911。如此即可撥打替代的緊急電話號碼，而且依然可以讓電話轉接到緊急服務 (例如，若某個國家或地區的緊急電話號碼不同，來自該國家或地區的人會嘗試撥打該國家或地區的緊急電話號碼，而非所在國家或地區的緊急電話號碼)。您可以使用分號分隔多個值，藉此定義多組緊急撥話遮罩。例如 212;414。字串的長度上限為 100 個字元。每個字元必須是 0 到 9 的數字。
      

        > [!IMPORTANT]  
        > 確保指定的撥號遮罩值與通話保留範圍中的數字不同。 通話保留路由優先於緊急撥號字串轉換。 若要檢視現有的通話駐留範圍，請按一下左導覽列中的 [語音功能]，然後按一下 [通話駐留]。 

    
      - **通知 URI**   撥打緊急電話時所通知的一或多個 SIP 統一資源識別項 (URI)。例如，每次有人撥打緊急電話時，就會透過立即訊息通知公司的安全部門。如果可以使用來電者的位置，通知中會包含該位置的資訊。可以使用逗號分隔的清單包含多個 SIP URI。例如 "sip:security@litwareinc.com","sip:kmyer@litwareinc.com"。可支援通訊群組清單。字串長度必須為 1 到 256 個字元，且開頭必須為首碼 "sip:"。在您按一下 [通知 URI] 欄位之前會顯示範例。
    
      - **會議 URI**   第三方的 SIP URI (本案例中為電話號碼)，將會加入任何所撥打之緊急電話的電話會議中。例如，當有人撥打緊急電話時，公司的安全部門會接聽該電話，並聆聽電話內容或參與通話 (取決於 [會議模式] 欄位中所提供的值)。字串長度必須為 1 到 256 個字元，且開頭必須為首碼 sip:。在您按一下此欄位之前將會持續顯示範例。
    
      - **會議模式**   如果您指定了 [會議 URI] 欄位中的值，[會議模式] 將會決定第三方是能夠參與通話，還是只能聆聽。請指定下列其中一個選項：
        
          - **單向**   第三方只能聆聽來電者與 PSAP 接線員之間的對話。
        
          - **雙向**   第三方可聆聽並參與來電者與 PSAP 接線員之間的通話。

6.  按一下 [認可]。


    > [!IMPORTANT]  
    > 當您建立使用者原則時，該原則並不會自動套用至任何使用者或網路網站。 若要將原則套用至使用者，請按一下左導覽列中的 [使用者]。 尋找要套用原則的使用者。 在 [編輯] 功能表上，按一下 [顯示詳細資料]。 在 [ **編輯服務器使用者** ] 頁面上，從 [ **位置原則** ] 下拉式清單中選取新的位置原則，然後按一下 [ **認可**]。<BR>若要將原則套用至網路網站，請按一下左導覽列中的 [網路設定]，然後按一下 [站台]。尋找要套用原則的網路網站。在 [編輯] 功能表上，按一下 [顯示詳細資料]。在 [編輯站台] 中，從 [位置原則] 下拉式清單中選取新的位置原則，然後按一下 [認可]。


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>在商務用 Skype Server 控制台中修改位置原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **位置原則**]。

4.  在 **[位置原則]** 頁面上，選取您要修改的位置原則。

5.  在 [編輯] 功能表上，按一下 [顯示詳細資料]。

6.  在「編輯位置原則」 頁面上視需要修改欄位 (如需詳細資訊，請參閱本主題前述＜建立新的位置原則＞程序中的＜步驟 5＞)。

7.  按一下 [認可]。

        
## <a name="delete-a-location-policy"></a>刪除位置原則


1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 

3.  在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **位置原則**]。

4.  在 [ **位置原則** ] 頁面上，選取您要刪除的位置原則。
   
    > [!NOTE]  
    > 您可以一次刪除一個以上的位置原則。 若要執行此動作，請按住 CTRL 鍵並選取多個原則，並按住 CTRL 鍵。 或者，若要選取所有原則，請按一下 [**編輯**] 功能表上的 [全 **選**]。


5.  在 **[編輯]** 功能表中，按一下 **[刪除]**。

6.  按一下 [確定]。

    > [!IMPORTANT]  
    > 您無法刪除全域位置原則。 如果您嘗試刪除通用原則，您會收到警告訊息，而且該原則會重設為其預設值。


## <a name="see-also"></a>另請參閱

[建立或修改網路網站](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](/powershell/module/skype/Get-CsLocationPolicy)