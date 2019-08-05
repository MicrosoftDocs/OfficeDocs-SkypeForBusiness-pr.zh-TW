---
title: 在商務用 Skype Server 中使用內部部署 PSTN 連線, 在 Office 365 中啟用電話系統的使用者
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 本主題說明如何使用內部部署 PSTN 連線, 在 Office 365 中啟用電話系統的使用者。 在遵循本主題中的步驟之前, 請先閱讀下列內容:。
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190834"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在商務用 Skype Server 中使用內部部署 PSTN 連線, 在 Office 365 中啟用電話系統的使用者
 
本主題說明如何使用內部部署 PSTN 連線, 在 Office 365 中啟用電話系統的使用者。 在遵循本主題中的步驟之前, 請先閱讀下列內容:。
  
- 若要瞭解如何設定混合式連線性, 請參閱[規劃商務用 Skype server 與商務用 Skype online 之間的混合式連接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md), 以及[在商務用 Skype server 和商務用 Skype online 之間部署混合式連接](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。
    
- 若要瞭解規劃部署, 請參閱在[商務用 Skype Server 中使用內部部署 PSTN 連線來規劃 Office 365 中的電話系統](plan-phone-system-with-on-premises-pstn-connectivity.md)。
    
- 若要深入瞭解 Office 365 中的電話系統, 包括授權和方案, 請參閱[商務用 Skype 的 PSTN 通話方案](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>使用內部部署 PSTN 連線將使用者移至 Office 365 中的電話系統

在將您的使用者移至商務用 Skype Online 之前, 建議您在商務用 Skype Server 或 Lync Server 2013 中啟用您的使用者, 然後在線上移動。 如需詳細資訊, 請參閱[規劃商務用 Skype Server 與商務用 Skype Online 之間的混合式連接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md), 以及[啟用企業內部部署使用者](enable-the-users-for-enterprise-voice-on-premises.md)的特殊考慮區段 (在使用者託管時執行)內部部署)。 
  
所有使用者都必須在內部部署的 Active Directory 中建立, 並使用支援的 Azure AD 連接器版本同步處理到 Office 365。 您無法在 Office 365 中啟用直接在 Azure AD 中建立的手機系統使用者。 如果您想要在 Office 365 中啟用電話系統, 並在 Azure AD 中建立的使用者使用內部部署 PSTN 連線, 您將需要在內部部署 AD 中為該使用者建立新帳戶, 並在內部部署中設定帳戶, 然後使用下列程式同步處理帳戶:受支援的 Azure AD 連接器工具版本。 
  
在使用內部部署 PSTN 連線, 然後將其移至商務用 Skype Online 的 Office 365 使用者, 需要執行下列步驟:
  
- [啟用企業內部部署的使用者](enable-the-users-for-enterprise-voice-on-premises.md)(在使用者託管內部部署時執行)。
    
- [指派語音路由策略](assign-a-voice-routing-policy.md)(在使用者託管內部部署時執行)。
    
- [同步處理使用者至雲端並指派授權](synchronize-users-to-the-cloud-and-assign-licenses.md)(使用 Office 365 執行)。
    
- [將內部部署使用者移至商務用 Skype Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online)(使用 Windows PowerShell 內部部署執行, 但使用您的 Office 365 系統管理員認證)。
    
- [讓使用者在 Office 365 語音信箱中使用企業語音線上和手機系統](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)(使用遠端 PowerShell 執行。
    

