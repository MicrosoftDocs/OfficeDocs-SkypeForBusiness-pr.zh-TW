---
title: 商務用 Skype Server 中的 Enterprise Voice 安全性和設定先決條件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 摘要：瞭解商務用 Skype Server 中的 Enterprise Voice 安全性和設定先決條件。
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830843"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>商務用 Skype Server 中的 Enterprise Voice 安全性和設定先決條件
 
**摘要：** 深入瞭解商務用 Skype Server 中的 Enterprise Voice 安全性和設定先決條件。
  
部署 Enterprise Voice 之前，請確認您的基礎結構符合下列安全性、使用者設定及案例特有的硬體先決條件。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>系統管理許可權和憑證基礎結構

部署之前，請先檢查下列各項：
  
- 部署 Enterprise Voice 的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。
    
- 執行設定工作的系統管理員必須具備適當的權限：
    
  - **CsVoiceAdministrator：** 此系統管理員角色可以執行語音設定工作、管理語音應用程式，以及指派語音原則給一般使用者。
    
  - **CsUserAdministrator：** 此系統管理員角色可以管理使用者屬性，例如啟用使用者的 Enterprise Voice。此系統管理員角色也可以指派個別使用者原則，封存原則除外；移動使用者；管理公用區電話和類比裝置。
    
  - **CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。
    
- 已經使用 Microsoft 或協力廠商憑證授權單位 (CA) 的基礎結構，完成 Managed 金鑰基礎結構 (MKI) 的部署和設定。
    
    > [!NOTE]
    > 如需商務用 Skype Server 中憑證需求的詳細資訊，請參閱商務用 skype server [2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 或 [商務用 skype Server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。 
  
## <a name="user-configuration"></a>使用者設定

如果您組合轉送伺服器與每個前端集區或 Standard Edition Server 的前端部署期間，則在安裝這些伺服器角色的檔案時，會自動設定企業語音所需的使用者設定。
  
如果您此時是全新部署 Enterprise Voice 工作量，在開始部署程序前，請先為每個您計畫要啟用 Enterprise Voice 的使用者指定主要電話號碼。 身為系統管理員，您要負責確認這個號碼是唯一的。 在實施之前，所有的主要電話號碼都必須正規化 (以商務用 Skype Server 控制台正確格式化) 並複製到每個使用者的 **行 URI** 屬性。
  
> [!NOTE]
> 如需 Enterprise Voice deployment 所需的主要電話號碼範例，請參閱 [範例正常化規則](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>後續步驟：安裝檔或設定 PSTN 連線能力

在驗證 Enterprise Voice 的軟體和環境必要條件之後，您可以：
  
- 如在 [商務用 Skype server](deploy-a-mediation-server.md)中的拓撲產生器中部署轉送伺服器所述，安裝轉送伺服器，但只有在您要部署獨立轉送伺服器或集區時，因為在組合時已將轉送伺服器安裝為前端集區或 Standard Edition Server 部署程式的一部分。
    
- 或者，若要開始設定設定以路由傳送 Enterprise Voice 使用者的通話，請參閱 [Configure 主幹 In 商務用 Skype Server 中](configure-trunks.md)所述。
    

