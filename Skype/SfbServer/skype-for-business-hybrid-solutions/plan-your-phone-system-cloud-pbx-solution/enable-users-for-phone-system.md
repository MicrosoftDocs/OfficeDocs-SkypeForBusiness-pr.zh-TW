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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 本主題說明如何使用內部部署 PSTN 連線來啟用使用者的電話系統。 遵循本主題中的步驟之前，您應該先閱讀下列各項：。
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359139"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>為使用者啟用商務用 Skype Server 含內部部署 PSTN 連線功能的電話系統

本主題說明如何使用內部部署 PSTN 連線來啟用使用者的電話系統。 遵循本主題中的步驟之前，您應該先閱讀下列各項：。
  
- 若要瞭解如何設定混合式連線，請參閱 [規劃商務用 Skype server 與商務用 Skype online 之間的混合式連線](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) ，以及 [在商務用 Skype server 與商務用 Skype online 之間部署混合](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)式連接。
    
- 若要瞭解規劃部署，請參閱 [在商務用 Skype Server 中規劃使用內部部署 PSTN 連線的電話系統](plan-phone-system-with-on-premises-pstn-connectivity.md)。
    
- 若要深入瞭解電話系統，包括授權與計畫，請參閱 [適用于商務用 Skype 的 PSTN 通話方案](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
    
> [!Important]
> 在2021年7月31日之後，商務用 Skype Online 將會停用，在此之後將無法再存取服務。  此外，您的內部部署環境之間的 PSTN 連線，不論是透過商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype Online，都將不再支援。  瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>使用內部部署 PSTN 連線將使用者移至電話系統

將使用者移至商務用 Skype Online 之前，建議您先在商務用 Skype Server 或 Lync Server 2013 中，啟用您的使用者，然後再將其移動到線上。 如需詳細資訊，請參閱 [規劃商務用 Skype Server 與商務用 Skype Online 的混合式連線](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) ，以及在使用者執行內部部署) 時， [啟用使用者的企業語音語音](enable-the-users-for-enterprise-voice-on-premises.md) (的特殊考慮一節。 
  
所有使用者都必須在內部部署的 Active Directory 中建立，並使用 Azure AD Connector 的支援版本同步處理至 Microsoft 365 或 Office 365。 您無法在 Office 365 中為直接在 Azure AD 中建立的電話系統啟用使用者。 如果您想要針對 Azure AD 中建立的使用者啟用具有內部部署 PSTN 連線的電話系統，您必須在內部部署 AD 中為該使用者建立新的帳戶，在內部部署中設定帳戶，然後使用 Azure AD Connector 工具支援的版本同步處理帳戶。 
  
使用具有內部部署 PSTN 連線的電話系統啟用使用者，然後將其移至商務用 Skype Online，需要下列步驟：
  
- 啟用使用者在內部部署) 時執行的[Enterprise Voice 使用者](enable-the-users-for-enterprise-voice-on-premises.md) (執行。
    
- [指派語音路由原則](assign-a-voice-routing-policy.md) (使用者內部部署) 時執行。
    
- 使用 Office 365) [，將使用者同步處理至雲端並指派授權](synchronize-users-to-the-cloud-and-assign-licenses.md) (執行。
    
- [將內部部署使用者移至商務用 Skype Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (執行使用 Windows PowerShell 內部部署，但使用 Office 365 系統管理員認證) 。
    
- 使用遠端 PowerShell，[讓使用者可使用企業語音線上和電話語音語音信箱](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (執行。
    

