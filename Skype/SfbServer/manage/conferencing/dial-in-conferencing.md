---
title: 在商務用 Skype Server 中管理電話撥入式會議
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
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 摘要：瞭解如何在商務用 Skype Server 中管理電話撥入式會議。
---

# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中管理電話撥入式會議
 
**總結：** 瞭解如何在商務用 Skype Server 中管理電話撥入式會議。
  
本主題說明如何管理電話撥入式會議。 如需如何在部署中規劃及設定電話撥入式會議的詳細資訊，請參閱[商務用 Skype Server 中的計畫撥號會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)和[設定商務用 Skype Server 中的電話撥入式會議](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
  
您可以執行下列工作來管理電話撥入式會議：啟用或停用電話撥入式會議、管理存取號碼、管理撥號加入會議的 PIN 碼原則、管理會議加入和離開宣告、修改 DTMF 命令的按鍵對應，以及歡迎使用者撥入式會議。 
  
如需管理撥號對應表的詳細資訊，請參閱[在商務用 Skype Server 中建立或修改撥號](../../deploy/deploy-enterprise-voice/dial-plans.md)對應表。
  
如需 PSTN 使用方式的詳細資訊，請參閱[在商務用 Skype 中設定語音原則、PSTN 使用方式記錄和語音路由](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)。
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台管理電話撥入式會議

若要管理電話撥入式會議的相關資訊：
  
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左側導覽列中，按一下 **[會議]**。
    
若要管理撥號對應表及 PSTN 使用狀況的相關資訊：
  
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **語音路由**]。
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面管理電話撥入式會議

若要使用商務用 Skype Server 管理命令介面來管理電話撥入式會議，請使用下列 Cmdlet：
  
**撥入配置設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |傳回設定供組織使用之會議目錄的資訊。 會議目錄可協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |會在使用者加入或離開電話撥入式會議時，檢索商務用 Skype Server 的回應方式資訊。  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |傳回設定供組織使用之所有電話撥入式會議存取號碼的資訊。  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |會傳回雙音調多重頻率 (DTMF) 用於電話撥入式會議的信號設定。 DTMF 可讓撥電話參與會議的使用者使用其電話鍵盤控制會議設定 (例如自行設定靜音和解除靜音，或鎖定和解除鎖定會議)。  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |會傳回語言清單，其中包括地區/少數語言，支援與商務用 Skype Server 電話撥入式會議搭配使用。 這些語言會用於將音訊訊息與指示轉送給透過電話參與會議的使用者。  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |傳回組織所使用之撥號對應表的相關資訊。  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |指派撥號對應用表給一或多個使用者或群組。  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |從 Microsoft Office 通訊伺服器 2007 R2 匯入會議目錄，以商務用 Skype Server。 這有助於在商務用 Skype Server 和 Office 通訊伺服器 2007 R2 之間提供互通性。  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |將現有的會議目錄從一個集區移至另一個集區。  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |建立新的會議目錄，供您的組織使用。  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |會建立新的電話撥入式會議存取號碼。  <br/> |
|[新 CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |會建立新的電話撥入式會議設定的集合。 這些設定會決定使用者加入或離開電話撥入式會議時商務用 Skype Server 的回應方式。 具體而言，會傳回信息有關參與者加入會議時是否需要記錄其名稱，以及 (或) 系統是否會宣佈某人已加入或離開通話的方式。  <br/> |
|[新 Set-csdialinconferencingdtmfconfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |會建立新的雙音調多重頻率集合， (DTMF) 用於電話撥入式會議的信號設定。  <br/> |
|[新 Get-csdialplan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |建立新的撥號對應表。  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |移除現有的會議目錄。  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |移除現有的電話撥入式會議存取號碼。  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |移除一或多個電話撥入式會議組態設定的集合。 這些設定會決定使用者加入或離開電話撥入式會議時商務用 Skype Server 的回應方式。  <br/> |
|[Remove-Set-csdialinconferencingdtmfconfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |移除一組現有的雙音調多重頻率 (DTMF) 信號設定用於電話撥入式會議。  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改現有電話撥入式會議存取號碼的屬性值。  <br/> |
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
