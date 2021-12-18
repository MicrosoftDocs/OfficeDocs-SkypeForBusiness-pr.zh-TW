---
title: 為使用者啟用商務用 Skype Server 含內部部署 PSTN 連線功能的電話系統
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 本主題說明如何使用內部部署 PSTN 連線來啟用使用者電話系統。 遵循本主題中的步驟之前，您應該先閱讀下列各項：。
ms.openlocfilehash: ffd7e9f02466dddeef31ba7ffd3a194a04b9b2ff
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563660"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>為使用者啟用商務用 Skype Server 含內部部署 PSTN 連線功能的電話系統

本主題說明如何使用內部部署 PSTN 連線來啟用使用者電話系統。 遵循本主題中的步驟之前，您應該先閱讀下列各項：。
  
- 若要瞭解如何設定混合式連線，請參閱[Plan 商務用 Skype Server 和商務用 Skype online 之間的混合式連線](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)，以及[在商務用 Skype Server 和商務用 Skype 線上之間部署混合式連線](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
    
- 若要瞭解規劃部署，請參閱[在商務用 Skype Server 中使用內部部署 PSTN 連線計畫電話系統](plan-phone-system-with-on-premises-pstn-connectivity.md)。
    
- 若要深入瞭解電話系統，包括授權與計畫，請參閱[商務用 Skype 的 PSTN 通話方案](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
    
> [!Important]
> 已不再支援內部部署環境（不論是透過商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype 線上）的7月31日、2021和 PSTN 連線，已停用商務用 Skype 線上。 瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線至 Teams。

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>使用內部部署 PSTN 連線將使用者移至電話系統

將使用者移到線上商務用 Skype 之前，建議您先在商務用 Skype Server 或 Lync Server 2013 中的使用者上啟用使用者，然後再將其移動到線上。 如需詳細資訊，請參閱[Plan 商務用 Skype Server 與商務用 Skype 的混合式連線](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)和[啟用使用者](enable-the-users-for-enterprise-voice-on-premises.md)在內部部署企業語音的特殊考慮區段 (執行使用者在內部部署) 時執行。 
  
所有使用者都必須在內部部署的 Active Directory 中建立，並與 Microsoft 365 或 Office 365 使用 Azure AD 連接器的支援版本同步處理。 您無法在 Azure AD 中 Office 365 直接建立的電話系統啟用使用者。 若要對 Azure AD 中建立的使用者啟用具有內部部署 PSTN 連線的電話系統，您必須在內部部署 AD 中為該使用者建立新的帳戶，在內部部署中設定帳戶，然後使用支援的 Azure AD 連接器工具版本來同步處理帳戶。 
  
使用內部部署 PSTN 連線讓使用者電話系統，然後將其移至商務用 Skype 線上，需要下列步驟：
  
- 啟用使用者在內部部署) 時執行[企業語音內部部署](enable-the-users-for-enterprise-voice-on-premises.md) (的使用者。
    
- [指派語音路由原則](assign-a-voice-routing-policy.md) (使用者內部部署) 時執行。
    
- 使用 Office 365) [將使用者同步處理至雲端並指派授權](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (執行。
    
- [將內部部署使用者移至商務用 Skype 線上](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (使用內部部署 Windows PowerShell 執行，但使用 Office 365 系統管理員認證) 。
    
- [讓使用者企業語音線上及電話系統語音信箱](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (使用遠端 PowerShell 執行。
