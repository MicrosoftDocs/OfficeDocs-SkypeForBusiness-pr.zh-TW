---
title: 商務用 Skype Server 中的企業語音安全性與設定先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: '摘要: 瞭解商務用 Skype Server 中企業語音的安全性與設定先決條件。'
ms.openlocfilehash: b3fced9ecac9020da9601c2ab6831769b34ae00a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192585"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>商務用 Skype Server 中的企業語音安全性與設定先決條件
 
**摘要:** 瞭解商務用 Skype Server 中企業語音的安全性與設定先決條件。
  
在部署企業語音之前, 請確認您的基礎結構符合下列安全性、使用者設定和案例特定的硬體先決條件。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>管理許可權與證書基礎結構

在部署之前, 請檢查下列專案:
  
- 部署企業語音的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。
    
- 執行設定任務的系統管理員必須具備足夠的許可權:
    
  - **CsVoiceAdministrator:** 這個系統管理員角色可以執行語音設定工作、管理語音應用程式, 以及將語音原則指派給最終使用者。
    
  - **CsUserAdministrator:** 這個系統管理員角色可以管理使用者屬性, 例如為使用者啟用企業語音。 除了封存原則之外, 此管理員角色還可以指派每個使用者的原則;移動使用者;以及管理常見的區域電話和類比裝置。
    
  - **CsAdministrator:** 此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。
    
- 管理的金鑰結構 (MKI) 是透過 Microsoft 或協力廠商憑證授權單位 (CA) 基礎結構來部署和設定。
    
    > [!NOTE]
    > 如需商務用 Skype Server 的憑證需求的詳細資訊, 請參閱商務用 skype server 2015 或商務用[skype server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)[的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。 
  
## <a name="user-configuration"></a>使用者設定

如果您在前端部署期間 collocated 每個前端池或標準版伺服器的中繼伺服器, 則在安裝這些伺服器角色的檔案期間, 系統會自動設定企業語音所需的使用者設定。
  
如果您目前正在新部署企業語音工作負載, 請在開始進行部署程式之前, 為您打算啟用企業語音的每位使用者指定主要電話號碼。 身為管理員, 您必須負責確保此號碼是唯一的。 在實施前, 所有的主要電話號碼都必須經過標準化 (正確格式化), 並使用商務用 Skype Server 控制台將其複製到每個使用者的**行 URI**屬性。
  
> [!NOTE]
> 如需企業語音部署所需的主要電話號碼範例, 請參閱[範例正常化規則](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>後續步驟: 安裝檔案或設定 PSTN 連線能力

在驗證企業語音的軟體與環境先決條件之後, 您可以執行下列其中一項操作:
  
- 安裝中繼伺服器, 如在商務用 Skype Server 的 [拓撲建立器] 中[部署轉送伺服器](deploy-a-mediation-server.md), 但僅限您想要部署獨立的中繼伺服器或池, 因為已將轉送伺服器安裝為前端的一部分collocated 時的 pool 或 Standard Edition server 部署程式。
    
- 或者, 開始設定設定以路由企業語音使用者的呼叫, 如在[商務用 Skype Server 中設定 trunks 中](configure-trunks.md)所述。
    

