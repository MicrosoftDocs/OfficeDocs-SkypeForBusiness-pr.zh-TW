---
title: 在商務用 Skype Server 中管理會議原則
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議原則。
---

# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議原則
 
**總結：** 瞭解如何在商務用 Skype Server 中管理會議原則。
  
本主題說明如何管理會議原則。 如需如何規劃及部署會議的詳細資訊，請參閱[商務用 Skype Server 中的會議計畫](../../plan-your-deployment/conferencing/conferencing.md)商務用 Skype Server 中的[部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
會議原則可讓您定義各種各樣的排程和參與選項，範圍是從會議是否可包含 IP 音訊和影片到可參加會議的人員人數上限。 您可以使用會議原則來管理會議的安全性、頻寬和法律方面。
  
您可在三個層級定義會議原則：通用範圍、站台範圍，以及使用者範圍。 設定值會依據最窄的範圍到最寬的範圍，依序套用至特定使用者。 如果您將原則指派給使用者，這些設定會優先。 如果未指派使用者原則，則會套用站台設定。 如果未套用使用者或站台原則，則由通用原則提供預設值。
  
由於通用原則預設已經存在，因此您無法建立新的通用原則。您也無法刪除現有的通用原則，但您可以變更現有通用原則，自訂您自己的預設值。
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台管理會議原則

若要使用商務用 Skype Server 控制台管理會議原則：
  
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面管理會議原則

若要使用商務用 Skype Server 管理命令介面來管理會議，請使用下列 Cmdlet：
  
**會議原則設定**

|**指令程式**|**描述**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |傳回已設定供組織使用之會議原則的資訊。  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每個使用者範圍指派會議原則。  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |建立新的會議原則供您的組織使用。  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |移除指定的會議原則。  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改現有的會議原則。  <br/> |
