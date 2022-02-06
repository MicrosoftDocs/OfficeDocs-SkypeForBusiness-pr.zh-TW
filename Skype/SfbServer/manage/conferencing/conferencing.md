---
title: 在商務用 Skype Server 中管理會議
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議。
---

# <a name="manage-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議
 
**總結：** 瞭解如何在商務用 Skype Server 中管理會議。
  
本主題說明如何管理會議。 如需如何規劃及部署會議的詳細資訊，請參閱[商務用 Skype Server 中的會議計畫](../../plan-your-deployment/conferencing/conferencing.md)商務用 Skype Server 中的[部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
在商務用 Skype Server 中，您可以依照下列方式指定設定和原則設定，以管理會議的詳細資料。 請注意，字詞會議和會議有時候會互換使用。 不過，一般而言，您可以將會議視為特定會議實例。
  
- **會議原則設定** 包含各種各樣的排程和參與選項，範圍是從會議是否可包含 IP 音訊和影片到可參加會議的人員人數上限。 您可以使用會議原則來管理會議的安全性、頻寬和法律方面。
    
    請注意，會議原則會套用至使用者或網站，且無法套用至特定會議。 因此，在會議開始之前，您可以在一周內預先建立會議的會議邀請，但必須將限制性會議原則套用至會議召集人的商務用 Skype 帳戶。 
    
    如果為會議召集人角色使用專用帳戶，則會議原則可以保持指派給該帳戶。 若會議召集人使用一般商務用 Skype 帳戶，則必須在會議完成後移除原則。
    
- **會議設定設定** 會口述使用者可以建立的會議類型，除了控制 (，甚至) 匿名使用者和電話撥入式會議使用者是否可以加入這些會議。 請注意，這些設定只會影響已排程的會議。 會議設定會依每個集區、網站或全域方式套用。
    
- 會議 **配置設定** 會決定會議內容和講義的允許大小上限等專案;應用程式共用會議服務的最大頻寬量;儲存量限制和到期期限;支援之用戶端的內部及外部下載的 URLs;指向內部和外部 URLs 的指標，使用者可以在其中取得會議説明和資源;以及用來進行應用程式共用、用戶端音訊、檔案傳輸和媒體流量的埠。
    
    這些設定可讓您自行管理實際的伺服器。 這些設定只能使用商務用 Skype Server 管理命令介面來設定。 
    
- **撥入訪問設定** 可讓您定義使用者是否以及如何從電話撥入的相關資訊。 您可以從 [控制台] 的 [語音路由] 索引標籤中，指定某些撥入訪問資訊，例如存取號碼、控制台的 [會議] 索引標籤和某些撥入資訊，例如撥號對應表、語音原則、路由及 PSTN 使用方式。
    
- **Pin 原則設定** 可讓您命名及定義參與者用於撥入存取的 pin 碼。
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面來管理會議

您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面來管理大多數會議原則及設定設定。 有些設定設定只適用于使用商務用 Skype Server 管理命令介面。
  
- 若要管理會議原則設定：
    
  - 選取 [控制台] 中的 [ **會議] |會議原則**。
    
  - 在 PowerShell 中，搜尋 **-CsConferencingPolicy** Cmdlet。
    
- 若要管理會議配置設定：
    
  - 選取 [控制台] 中的 [ **會議] |會議** 設定。
    
  - 在商務用 Skype Server 管理命令介面中，搜尋 **-CsMeetingConfiguration** Cmdlet。
    
- 若要管理撥入存取號碼設定：
    
  - 選取 [控制台] 中的 [ **會議] |撥入存取號碼**。
    
  - 在商務用 Skype Server 管理命令介面中，搜尋 **-test-csdialinconferencing** Cmdlet。
    
- 若要管理撥入訪問資訊，例如撥號對應表、語音原則、路由及 PSTN 使用狀況，請執行下列動作： 
    
  - 選取 [控制台] 中的 [ **會議] |語音路由**。
    
  - 在商務用 Skype Server 管理命令介面中，搜尋 **-get-csdialplan** 及 **-CsVoice** Cmdlet。
    
- 若要管理 PIN 原則設定：
    
  - 選取 [控制台] 中的 [ **會議] |PIN 原則**。
    
  - 在商務用 Skype Server 管理命令介面中，搜尋 **-get-cspinpolicy** Cmdlet。
    
- 若要管理會議配置設定，您必須使用商務用 Skype Server 管理命令介面。 搜尋 **-CsConferencingConfiguration** Cmdlet。
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>商務用 Skype Server 管理命令介面 Cmdlet

您可以使用下列商務用 Skype Server 管理命令介面 Cmdlet 來管理會議： 
  
**會議原則設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |傳回已設定供組織使用之會議原則的資訊。 會議原則可決定會議所能使用的功能，包括會議是否可以加入 IP 音訊和視訊，乃至於會議出席人數的上限等等。  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每個使用者範圍指派會議原則。  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |建立新的會議原則供您的組織使用。  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |移除指定的會議原則。  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改現有的會議原則。  <br/> |
   
**會議組態設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |會傳回組織中目前使用之會議設定設定的相關資訊。 會議設定設定協助口述使用者可以建立的會議類型，並控制) 匿名使用者和電話撥入式會議使用者是否可以加入這些會議 (或甚至如何。  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在網站或服務範圍建立新的會議組態設定集合。 請注意，這些設定只會影響排程的會議;它們不會影響在商務用 Skype 中按一下 [立即開會] 選項所建立的特定會議。  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |會刪除現有的會議配置設定集合。  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改組織中目前使用的會議設定設定。  <br/> |
   
**會議配置設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |傳回組織的會議設定設定資訊。 會議設定會判斷會議內容和講義大小上限為允許的大小、內容寬限期 (也就是說，在刪除) 之前會儲存內容的時間量，以及支援之用戶端的內部及外部下載 URLs。  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |建立新的會議配置設定集合。  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |移除指定的會議配置設定集合。  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改現有會議配置設定的集合。  <br/> |
   
**撥入配置設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |傳回設定供組織使用之會議目錄的資訊。 會議目錄可協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |會在使用者加入或離開電話撥入式會議時，檢索商務用 Skype Server 的回應方式資訊。  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |傳回設定供組織使用之所有電話撥入式會議存取號碼的資訊。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |傳回電話撥入式會議所要使用的複頻式 (DTMF) 訊號設定。 DTMF 可讓撥電話參與會議的使用者使用其電話鍵盤控制會議設定 (例如自行設定靜音和解除靜音，或鎖定和解除鎖定會議)。  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |會傳回語言清單，其中包括地區/少數語言，支援與商務用 Skype Server 電話撥入式會議搭配使用。 這些語言會用於將音訊訊息與指示轉送給透過電話參與會議的使用者。  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |傳回組織所使用之撥號對應表的相關資訊。  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |指派撥號對應用表給一或多個使用者或群組。  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |從 Microsoft Office 通訊伺服器 2007 R2 匯入會議目錄，以商務用 Skype Server。 這有助於在商務用 Skype Server 和 Office 通訊伺服器 2007 R2 之間提供互通性。  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |將現有的會議目錄從一個集區移至另一個集區。 會議目錄可協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |建立新的會議目錄，供您的組織使用。 會議目錄可協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |會建立新的電話撥入式會議存取號碼。  <br/> |
|[新 CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |會建立新的電話撥入式會議設定的集合。 這些設定會決定使用者加入或離開電話撥入式會議時商務用 Skype Server 的回應方式。 具體而言，會傳回信息有關參與者加入會議時是否需要記錄其名稱，以及 (或) 系統是否會宣佈某人已加入或離開通話的方式。  <br/> |
|[新 Set-csdialinconferencingdtmfconfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |建立新的雙音多頻 (DTMF) 訊號設定集合，供電話撥入式會議使用。  <br/> |
|[新 Get-csdialplan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |建立新的撥號對應表。  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |移除現有的會議目錄。 會議目錄可協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |移除現有的電話撥入式會議存取號碼。  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |移除一或多個電話撥入式會議組態設定的集合。 這些設定會決定使用者加入或離開電話撥入式會議時商務用 Skype Server 的回應方式。  <br/> |
|[Remove-Set-csdialinconferencingdtmfconfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |移除一組現有的雙音調多重頻率 (DTMF) 信號設定用於電話撥入式會議。  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改現有電話撥入式會議存取號碼的屬性值。 電話撥入式會議可讓使用者使用一般的電話、行動電話或公用交換電話網路 (PSTN) 上的其他裝置加入會議的音訊部分。  <br/> |
|[CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |修改設定，決定當使用者加入或離開電話撥入式會議時商務用 Skype Server 的回應方式。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |修改雙色調頻式訊號 (DTMF) 用於電話撥入式會議的信號設定。  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |修改現有的撥號對應表。  <br/> |
   
**PIN 原則設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |傳回設定供組織使用之用戶端個人識別碼 (PIN) 原則的資訊。 pin 驗證可讓使用者提供 PIN 碼來存取商務用 Skype Server，而不是使用者名稱和密碼。  <br/> |
|[授與 Get-cspinpolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |指派用戶端個人身分識別號碼 (PIN) 原則指派給使用者或使用者群組。  <br/> |
|[新 Get-cspinpolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> | (PIN) 原則中建立新的用戶端個人身分識別號碼。  <br/> |
|[Remove-Get-cspinpolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |移除指定的個人識別碼 (PIN) 原則。  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |修改一或多個現有的用戶端個人識別碼 (PIN) 原則。  <br/> |
   
**其他會議設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |停用商務用 Skype Server 會議室。 會議室是專為小型會議室之視訊會議及共同作業案例而設計的會議裝置。 當您停用會議室物件時，會移除所有指派給代表會議室之使用者帳戶的商務用 Skype Server 特定 Active Directory 屬性。 不過，不會刪除 Active Directory 使用者帳戶。  <br/> |
|[Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |啟用商務用 Skype Server 會議室。 若要啟用會議室，您必須先建立會代表該系統的 Active Directory 使用者帳戶。 請注意，雖然會議室物件是以使用者帳戶為基礎的，但當您執行 Get-CsUser Cmdlet 時，這些物件將不會顯示。  <br/> |
|[Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |傳回組織所使用之會議免責聲明的資訊。 會議免責聲明是一則訊息，會顯示給使用超連結加入會議之使用者 (例如將會議連結貼入 Windows Internet Explorer 等瀏覽器的使用者) 參閱。  <br/> |
|[Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |會傳回設定供組織使用之所有商務用 Skype Server 會議室的資訊。  <br/> |
|[Move-CsMeetingRoom](/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |將商務用 Skype Server 會議室物件從一個註冊機構集區移至另一個。  <br/> |
|[Remove-Get-csconferencedisclaimer](/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |清除組織所使用之會議免責聲明標頭和本文中的文字。 會議免責聲明是一則訊息，會顯示給使用超連結加入會議之使用者 (例如將會議連結貼入 Windows Internet Explorer 等瀏覽器的使用者) 參閱。  <br/> |
|[Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |修改現有商務用 Skype Server 會議室的屬性值。  <br/> |
   
**測試設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Test-CsASConference](/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |測試一對使用者在應用程式共用會議中參與的能力。  <br/> |
|[Test-CsAudioConferencingProvider](/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |測試以查看使用者是否可以連線到其音訊會議提供者。 音訊會議提供者是協力廠商公司，為組織提供會議服務。 除了其他事項之外，音訊會議提供者也可讓使用者進入離站網站，而不是連線至公司網路或網際網路，以參與會議或會議的音訊部分。  <br/> |
|[Test-CsAVConference](/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |測試一組使用者在音訊/視頻 (A/V) 會議中取得的能力。  <br/> |
|[Test-CsDataConference](/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |驗證是否有一組使用者可以參與商務用 Skype Server 的 web 會議，該會議包含共用或查看 PowerPoint 投影片、白板或投票等活動。 此 Cmdlet 也會驗證商務用 Skype Server web 會議服務是否可以探索 Office web apps server，以及用戶端可以透過 Office web apps server 上傳 PowerPoint 檔案進行廣播。  <br/> |
|[Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |檢查使用者是否可以加入電話撥入式會議會話。  <br/> |
|[Test-CsDialPlan](/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |會針對撥號對應表測試電話號碼 (以前稱為位置設定檔) ，並且會傳回套用至編號的正規化規則，以及套用正規化規則之後的轉譯號碼。  <br/> |
|[Test-CsMcxConference](/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |測試三位使用者加入商務用 Skype Server 行動服務會議的能力。 行動服務可讓行動電話的使用者（例如 iphone 和 Windows 電話）執行諸如 exchange 立即訊息和目前狀態資訊等動作、內部儲存及取回語音信箱，而不是透過其無線提供者進行呼叫; 並利用商務用 Skype Server 功能（例如透過工作和撥出會議進行呼叫）。  <br/> **注意：** 商務用 Skype Server 2019 不支援使用 MCX 的用戶端。|
|[Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |測試一組使用者對使用整合通訊 Web API (UCWA) 進行排程、加入和執行線上會議的能力。  <br/> |
|[CsDataConference](/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |會傳回商務用 Skype Server 所包含之資料會議功能的診斷資訊。  <br/> |
