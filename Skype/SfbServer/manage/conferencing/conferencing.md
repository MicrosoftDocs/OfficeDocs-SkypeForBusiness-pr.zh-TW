---
title: 在商務用 Skype Server 中管理會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: '摘要: 瞭解如何在商務用 Skype Server 中管理會議。'
ms.openlocfilehash: 55fd2ff645e6e95199b2558ef494eea019b155bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188959"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議
 
**摘要:** 瞭解如何在商務用 Skype Server 中管理會議。
  
本主題說明如何管理會議。 如需如何規劃及部署會議的詳細資訊, 請參閱[在商務用 Skype server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md), 以及[在商務用 Skype 伺服器中部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
在商務用 Skype Server 中, 您可以透過指定設定及原則設定, 來管理會議的詳細資料, 如下所示。 請注意, 術語會議與會議有時可以互換使用。 但一般來說, 您可以將會議看作是會議的特定實例。
  
- **會議原則設定**包含各種排程和參與選項, 包括從會議是否可以將 IP 音訊與影片加入到可參與的人數上限。 您可以使用會議原則來管理會議的安全性、頻寬和法律方面。
    
    請注意, 會議原則會套用至使用者或網站, 且無法套用至特定會議。 因此, 在會議開始之前, 您可以在幾周內提前建立會議的會議邀請, 但必須先將限制式會議原則套用到會議召集人的商務用 Skype 帳戶。 
    
    如果將專用帳戶用於會議召集人角色, 會議原則就可以維持指派給該帳戶。 如果會議召集人使用一般商務用 Skype 帳戶, 則必須在會議完成後移除原則。
    
- [**會議設定] 設定**決定使用者可以建立的會議類型, 除了控制匿名使用者和電話撥入式會議使用者是否可以加入這些會議。 請注意, 這些設定只會影響排程的會議。 每個池、每個網站或全域套用會議配置。
    
- **會議設定設定**會決定會議內容和講義的允許大小上限等專案,應用程式共用會議服務的頻寬最大使用量;儲存空間限制與到期期;受支援之用戶端內部和外部下載的 Url;使用者可取得會議說明和資源之內部和外部 Url 的指標;以及用於應用程式共用、用戶端音訊、檔案傳輸及媒體流量的埠。
    
    這些設定可讓您管理實際的伺服器本身。 這些設定只能使用商務用 Skype Server Management Shell 來設定。 
    
- [**撥入存取設定**] 可讓您定義使用者是否從手機撥入, 以及如何進行撥號的相關資訊。 您可以從 [控制台] 的 [會議] 索引標籤和一些撥入資訊 (例如撥號方案、語音原則、路由和 PSTN 使用), 從 [控制台] 的 [語音路由] 索引標籤中, 指定一些撥入存取訊號, 例如存取號碼。
    
- **Pin 原則設定**可讓您命名及定義參與者用來進行撥入存取的 pin。
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management 命令介面管理會議

您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面, 管理大多數會議原則和設定設定。 某些設定的設定只能透過商務用 Skype Server Management Shell 使用。
  
- 管理會議原則設定:
    
  - 在 [控制台] 中, 選取 [**會議] |會議原則**。
    
  - 在 PowerShell 中, 搜尋 **-CsConferencingPolicy** Cmdlet。
    
- 管理會議設定:
    
  - 在 [控制台] 中, 選取 [**會議] |會議配置**。
    
  - 在商務用 Skype Server Management 命令介面中, 搜尋 **-CsMeetingConfiguration** Cmdlet。
    
- 管理撥入存取號碼設定:
    
  - 在 [控制台] 中, 選取 [**會議] |撥入存取號碼**。
    
  - 在商務用 Skype Server Management 命令介面中, 搜尋 **-CsDialInConferencing** Cmdlet。
    
- 管理撥入存取訊號, 例如撥號計畫、語音原則、路由及 PSTN 使用: 
    
  - 在 [控制台] 中, 選取 [**會議] |語音路由**。
    
  - 在商務用 Skype Server Management 命令介面中, 搜尋 **-CsDialPlan**和 **-CsVoice** Cmdlet。
    
- 管理 PIN 原則設定:
    
  - 在 [控制台] 中, 選取 [**會議] |PIN 原則**。
    
  - 在商務用 Skype Server Management 命令介面中, 搜尋 **-CsPinPolicy** Cmdlet。
    
- 若要管理會議設定, 您必須使用商務用 Skype Server 管理命令介面。 搜尋**CsConferencingConfiguration**的 Cmdlet。
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>商務用 Skype Server Management 命令介面 Cmdlet

您可以使用下列商務用 Skype Server Management Shell Cmdlet 來管理會議: 
  
**會議原則設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |傳回已設定為在您組織中使用之會議原則的相關資訊。 會議原則決定可在會議中使用的功能和功能;這包括無論會議是否可將 IP 音訊與影片加入會議的人數上限, 都能包括在內。  <br/> |
|[授與 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每個使用者範圍指派會議原則。  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |建立新的會議原則供您的組織使用。  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |移除指定的會議原則。  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改現有的會議原則。  <br/> |
   
**會議配置設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |傳回目前在貴組織中使用之會議配置設定的相關資訊。 [會議設定] 設定可協助您決定使用者可以建立的會議類型, 並控制匿名使用者和電話撥入式會議使用者可以加入這些會議的方式 (或甚至是如何)。  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |在網站或服務範圍建立新的會議配置設定集合。 請注意, 這些設定只會影響排程的會議;它們不會影響在商務用 Skype 中按一下 [立即開會] 選項所建立的即席會議。  <br/> |
|[移除-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |刪除現有的會議配置設定集合。  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |修改組織中目前使用的會議設定設定。  <br/> |
   
**會議配置設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |傳回貴組織會議配置設定的相關資訊。 [會議設定] 決定會議內容與講義的大小上限, 例如內容寬限期 (也就是要在刪除內容之前儲存的時間), 以及內部與外部下載的 Url。支援的用戶端。  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |建立新的會議配置設定集合。  <br/> |
|[移除-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |移除指定的會議配置設定集合。  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |修改現有的會議配置設定集合。  <br/> |
   
**電話撥入設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |傳回已設定在您組織中使用之會議目錄的相關資訊。 會議目錄可用於協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |檢索當使用者加入或離開電話撥入式會議時, 商務用 Skype Server 如何回應的相關資訊。  <br/> |
|[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |傳回已設定為在您組織中使用之所有電話撥入式會議存取號碼的相關資訊。  <br/> |
|[CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |傳回電話撥入式會議所用的雙音調 multifrequency (DTMF) 信號設定。 [DTMF] 可讓撥入會議的使用者控制會議設定 (例如靜音及 unmuting 本身, 或是使用電話鍵, 在電話上鎖定及解除鎖定會議)。  <br/> |
|[CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |傳回語言清單, 包括地區/少數語言, 與商務用 Skype 伺服器撥入式會議支援搭配使用。 這些語言可用來將音訊訊息與指示中繼給參與會議的使用者, 並使用電話撥入會議。  <br/> |
|[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |傳回貴組織中使用之撥號方案的相關資訊。  <br/> |
|[授與 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |指派撥號方案給一或多個使用者或群組。  <br/> |
|[匯入-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |從 Microsoft Office 通訊伺服器 2007 R2 將會議目錄匯入到商務用 Skype Server。 這有助於在商務用 Skype Server 和 Office 通訊伺服器 2007 R2 之間提供互通性。  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |在集區之間移動現有的會議目錄。 會議目錄可用於協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |建立新的會議目錄供組織使用。 會議目錄可用於協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[新-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |建立新的電話撥入式會議存取號碼。  <br/> |
|[新-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |建立新的電話撥入式會議設定設定集合。 這些設定決定了在使用者加入或離開撥入會議時, 商務用 Skype Server 的回應方式。 具體來說, 會傳回有關加入會議時是否需要參與者記錄其名稱的資訊, 以及系統如何 (或如果是) 系統會宣佈某人已加入或離開通話。  <br/> |
|[新-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |建立新的雙音調 multifrequency (DTMF) 信號設定集合, 用於電話撥入式會議。  <br/> |
|[新-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |建立新的撥號方案。  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |移除現有的會議目錄。 會議目錄可用於協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[移除-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |移除現有的電話撥入式會議存取號碼。  <br/> |
|[移除-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |移除一或多個電話撥入式會議設定的集合。 這些設定決定了在使用者加入或離開撥入會議時, 商務用 Skype Server 的回應方式。  <br/> |
|[移除-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |移除在電話撥入式會議中使用的雙音調多頻率 (DTMF) 信號設定的現有集合。  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改現有電話撥入式會議存取號碼的屬性值。 電話撥入式會議提供一種方式, 讓使用者使用「一般」電話、行動電話或公用交換電話網絡 (PSTN) 上的其他裝置加入會議的音訊部分。  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |修改決定商務用 Skype Server 在使用者加入或離開電話撥入式會議時的回應方式設定。  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |修改用於電話撥入式會議的雙音調 multifrequency (DTMF) 信號設定。  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |修改現有的撥號方案。  <br/> |
   
**釘選原則設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |傳回已設定為在貴組織中使用之用戶端個人識別碼 (PIN) 原則的相關資訊。 PIN 驗證可讓使用者透過提供 PIN (而不是使用者名稱和密碼) 來存取商務用 Skype Server。  <br/> |
|[授與 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |將用戶端個人身分識別號碼 (PIN) 原則指派給使用者或使用者群組。  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |建立新的用戶端個人識別碼 (PIN) 原則。  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |移除指定的個人識別碼 (PIN) 原則。  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |修改一或多個現有的用戶端個人識別碼 (PIN) 原則。  <br/> |
   
**其他會議設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |停用商務用 Skype Server 會議室。 會議室是專為小型會議室之視訊會議及共同作業案例而設計的會議裝置。 當您停用會議室物件時, 您會移除指派給代表會議室之使用者帳戶的所有商務用 Skype 伺服器的 Active Directory 屬性。 不過, Active Directory 使用者帳戶本身並不會被刪除。  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |啟用商務用 Skype Server 會議室。 若要啟用會議室, 您必須先建立將代表該系統的 Active Directory 使用者帳戶。 請注意, 雖然會議室物件是以使用者帳戶為基礎, 但是當您執行 Move-csuser Cmdlet 時, 這些物件將不會顯示。  <br/> |
|[CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |傳回貴組織中使用之會議免責聲明的相關資訊。 [會議免責聲明] 是透過使用超連結向加入會議的使用者顯示的一則訊息 (例如, 將會議連結貼到 Windows Internet Explorer 等瀏覽器的使用者)。  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |傳回已設定為在組織中使用之所有商務用 Skype Server 會議室的相關資訊。  <br/> |
|[移動流覽 CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |將商務用 Skype Server 會議室物件從一個註冊機構池移至另一個。  <br/> |
|[移除-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |清除貴組織中使用之會議免責聲明的標題和本文中的文字。 [會議免責聲明] 是透過使用超連結向加入會議的使用者顯示的一則訊息 (例如, 將會議連結貼到 Windows Internet Explorer 等瀏覽器的使用者)。  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |修改現有商務用 Skype Server 會議室的屬性值。  <br/> |
   
**測試設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |測試使用者對參與應用程式共用會議的能力。  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |測試以查看使用者是否可以連線到自己的音訊會議提供者。 音訊會議提供者是協力廠商的公司, 提供含會議服務的組織。 除了其他事項之外, 音訊會議提供者還能讓使用者離開網站, 而且未連線至公司網路或網際網路, 以參與會議或會議的音訊部分。  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |測試一對使用者參與音訊/視頻 (A/V) 會議的能力。  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |驗證是否有一對使用者可以參與商務用 Skype Server web 會議, 包括共用或查看 PowerPoint 投影片、白板或投票等活動。 這個 Cmdlet 也會確認商務用 Skype Server web 會議服務可以探索 Office Web Apps 伺服器, 而且用戶端可以透過 Office Web Apps 伺服器上傳供廣播使用的 PowerPoint 檔案。  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |檢查使用者是否可以參與電話撥入式會議會話。  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |根據撥號方案 (先前稱為位置設定檔) 來測試電話號碼, 並在套用正常化規則之後, 傳回要套用到該數位的正常化規則, 以及已翻譯的數位。  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |測試三位使用者參與商務用 Skype Server 行動服務會議的能力。 行動服務可讓行動電話 (例如 Iphone 和 Windows phone) 的使用者執行諸如 exchange 立即訊息和目前狀態資訊等動作。在內部儲存及檢索語音信箱, 而不是使用其無線提供者。透過商務用 Skype 伺服器功能 (例如透過工作和撥出式會議通話) 來充分運用。  <br/> **注意:** 商務用 Skype Server 2019 不支援使用 MCX 的用戶端。|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |使用整合通訊 Web API (UCWA) 測試一組使用者進行排程、加入, 然後進行線上會議的能力。  <br/> |
|[調試-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |針對商務用 Skype Server 中包含的資料會議功能, 返回診斷資訊。  <br/> |
   

