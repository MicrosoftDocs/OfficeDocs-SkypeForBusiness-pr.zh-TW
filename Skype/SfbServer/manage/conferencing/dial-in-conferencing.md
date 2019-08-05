---
title: 管理商務用 Skype Server 中的電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: '摘要: 瞭解如何在商務用 Skype Server 中管理電話撥入式會議。'
ms.openlocfilehash: e27ee84769d2ba25b3d3ea6689c7125889b4f80e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189664"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>管理商務用 Skype Server 中的電話撥入式會議
 
**摘要:** 瞭解如何在商務用 Skype Server 中管理電話撥入式會議。
  
本主題說明如何管理電話撥入式會議。 如需如何在部署規劃及設定電話撥入式會議的詳細資訊, 請參閱[在商務用 Skype server 中規劃電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md), 以及[在商務用 Skype server 中設定電話撥入式會議](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
  
您可以執行下列工作來管理電話撥入式會議: 啟用或停用電話撥入式會議、管理接入號碼、管理電話會議的 PIN 原則、管理會議加入與離開宣告、修改 DTMF 的金鑰組應[命令], 以及 [歡迎使用者] 撥入式會議。 
  
如需管理撥號方案的詳細資訊, 請參閱[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
如需 PSTN 用法的詳細資訊, 請參閱[在商務用 Skype 中設定語音原則、PSTN 使用方式記錄及語音路由](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)。
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 的 [控制台] 管理電話撥入式會議

若要管理電話撥入式會議的相關資訊:
  
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**]。
    
若要管理有關撥號方案和 PSTN 使用量的資訊:
  
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**語音路由**]。
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management 命令介面管理電話撥入式會議

若要使用商務用 Skype Server Management Shell 管理電話撥入式會議, 請使用下列 Cmdlet:
  
**電話撥入設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |傳回已設定在您組織中使用之會議目錄的相關資訊。 會議目錄可用於協助電話撥入式會議使用者尋找會議資訊。  <br/> |
|[CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |檢索當使用者加入或離開電話撥入式會議時, 商務用 Skype Server 如何回應的相關資訊。  <br/> |
|[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |傳回已設定為在您組織中使用之所有電話撥入式會議存取號碼的相關資訊。  <br/> |
|[CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |傳回用於電話撥入式會議的雙音調多頻率 (DTMF) 信號設定。 [DTMF] 可讓撥入會議的使用者控制會議設定 (例如靜音及 unmuting 本身, 或是使用電話鍵, 在電話上鎖定及解除鎖定會議)。  <br/> |
|[CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |傳回語言清單, 包括地區/少數語言, 與商務用 Skype 伺服器撥入式會議支援搭配使用。 這些語言可用來將音訊訊息與指示中繼給參與會議的使用者, 並使用電話撥入會議。  <br/> |
|[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |傳回貴組織中使用之撥號方案的相關資訊。  <br/> |
|[授與 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |指派撥號方案給一或多個使用者或群組。  <br/> |
|[匯入-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |從 Microsoft Office 通訊伺服器 2007 R2 將會議目錄匯入到商務用 Skype Server。 這有助於在商務用 Skype Server 和 Office 通訊伺服器 2007 R2 之間提供互通性。  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |在集區之間移動現有的會議目錄。  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |建立新的會議目錄供組織使用。  <br/> |
|[新-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |建立新的電話撥入式會議存取號碼。  <br/> |
|[新-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |建立新的電話撥入式會議設定設定集合。 這些設定決定了在使用者加入或離開撥入會議時, 商務用 Skype Server 的回應方式。 具體來說, 會傳回有關加入會議時是否需要參與者記錄其名稱的資訊, 以及系統如何 (或如果是) 系統會宣佈某人已加入或離開通話。  <br/> |
|[新-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |建立新的雙音調多頻率 (DTMF) 信號設定集合, 用於電話撥入式會議。  <br/> |
|[新-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |建立新的撥號方案。  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |移除現有的會議目錄。  <br/> |
|[移除-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |移除現有的電話撥入式會議存取號碼。  <br/> |
|[移除-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |移除一或多個電話撥入式會議設定的集合。 這些設定決定了在使用者加入或離開撥入會議時, 商務用 Skype Server 的回應方式。  <br/> |
|[移除-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |移除在電話撥入式會議中使用的雙音調多頻率 (DTMF) 信號設定的現有集合。  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |修改現有電話撥入式會議存取號碼的屬性值。  <br/> |
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
   

