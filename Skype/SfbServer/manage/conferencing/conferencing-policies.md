---
title: 在商務用 Skype Server 中管理會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: '摘要: 瞭解如何在商務用 Skype Server 中管理會議原則。'
ms.openlocfilehash: d835c4760ef3e77bc36f21e64cb80aeb618526ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191269"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中管理會議原則
 
**摘要:** 瞭解如何在商務用 Skype Server 中管理會議原則。
  
本主題說明如何管理會議原則。 如需如何規劃及部署會議的詳細資訊, 請參閱[在商務用 Skype server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md), 以及[在商務用 Skype 伺服器中部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
  
會議原則可讓您定義各種排程和參與選項, 包括從會議是否可以將 IP 音訊與影片加入到可參與的人數上限。 您可以使用會議原則來管理會議的安全性、頻寬和法律方面。
  
您可以在三個層級定義會議原則: 全域範圍、網站範圍和使用者範圍。 [設定] 會將最窄範圍的特定使用者套用至最廣泛的範圍。 如果您將原則指派給使用者, 這些設定就會優先使用。 如果您沒有指派使用者原則, 就會套用 [網站設定]。 如果沒有適用的使用者或網站原則, 全域原則就會提供預設設定。
  
全域原則預設存在, 所以您無法建立新的全域原則。 您也無法刪除現有的全域原則, 但您可以變更現有的全域原則, 來自訂您的預設設定。
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 管理會議原則

若要使用商務用 Skype Server [控制台] 管理會議原則, 請執行下列動作:
  
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [**會議原則**]。
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 管理會議原則

若要使用商務用 Skype Server Management Shell 管理會議, 請使用下列 Cmdlet:
  
**會議原則設定**

|**Cmdlet**|**說明**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |傳回已設定為在您組織中使用之會議原則的相關資訊。  <br/> |
|[授與 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |在每個使用者範圍指派會議原則。  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |建立新的會議原則供您的組織使用。  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |移除指定的會議原則。  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |修改現有的會議原則。  <br/> |
   

