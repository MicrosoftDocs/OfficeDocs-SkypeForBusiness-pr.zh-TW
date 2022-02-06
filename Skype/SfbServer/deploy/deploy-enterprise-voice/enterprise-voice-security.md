---
title: 商務用 Skype Server 中企業語音的安全性和設定必要條件
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 摘要：瞭解商務用 Skype Server 中企業語音的安全性和設定必要條件。
---

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>商務用 Skype Server 中企業語音的安全性和設定必要條件
 
**總結：** 深入瞭解商務用 Skype Server 中企業語音的安全性和設定必要條件。
  
在部署企業語音之前，請確認您的基礎結構符合下列安全性、使用者設定及案例特有的硬體先決條件。 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>系統管理許可權和憑證基礎結構

部署之前，請先檢查下列各項：
  
- 部署 Enterprise Voice 的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。
    
- 執行設定工作的系統管理員必須具備適當的權限：
    
  - **CsVoiceAdministrator：** 此系統管理員角色可以執行語音設定工作、管理語音應用程式，以及指派語音原則給一般使用者。
    
  - **CsUserAdministrator：** 此系統管理員角色可以管理使用者屬性，例如啟用使用者的 Enterprise Voice。此系統管理員角色也可以指派個別使用者原則，封存原則除外；移動使用者；管理公用區電話和類比裝置。
    
  - **CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。
    
- 已經使用 Microsoft 或協力廠商憑證授權單位 (CA) 的基礎結構，完成 Managed 金鑰基礎結構 (MKI) 的部署和設定。
    
    > [!NOTE]
    > 如需商務用 Skype Server 中憑證需求的詳細資訊，請參閱商務用 Skype Server 2019 商務用 Skype Server 2015 或[伺服器需求](../../../SfBServer2019/plan/system-requirements.md)[的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。 
  
## <a name="user-configuration"></a>使用者設定

如果您組合轉送伺服器與每個前端集區或 Standard Edition 伺服器的前端部署期間，則企業語音的必要使用者設定會在安裝這些伺服器角色的檔案期間自動設定。
  
如果您此時是全新部署 Enterprise Voice 工作量，在開始部署程序前，請先為每個您計畫要啟用 Enterprise Voice 的使用者指定主要電話號碼。 身為系統管理員，您要負責確認這個號碼是唯一的。 在實施之前，所有的主要電話號碼都必須正規化 (正確格式化) ，並使用商務用 Skype Server 控制台將其複製到每個使用者的 **行 URI** 屬性。
  
> [!NOTE]
> 如需企業語音部署的主要電話號碼範例，請參閱[範例正常化規則](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>後續步驟：安裝檔或設定 PSTN 連線能力

驗證企業語音的軟體和環境必要條件之後，您可以：
  
- 安裝轉送伺服器（如在商務用 Skype Server 的[拓撲](deploy-a-mediation-server.md)產生器中部署轉送伺服器所述），但只有當您想要部署獨立轉送伺服器或集區時，因為轉送伺服器已安裝為前端集區的一部分，或組合時 Standard Edition 伺服器部署程式。
    
- 或者，開始設定企業語音使用者的通話路由設定，如[商務用 Skype Server 設定主幹中](configure-trunks.md)所述。
    

