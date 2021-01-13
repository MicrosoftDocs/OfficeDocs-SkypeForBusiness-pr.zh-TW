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
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="90195-103">商務用 Skype Server 中的 Enterprise Voice 安全性和設定先決條件</span><span class="sxs-lookup"><span data-stu-id="90195-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="90195-104">**摘要：** 深入瞭解商務用 Skype Server 中的 Enterprise Voice 安全性和設定先決條件。</span><span class="sxs-lookup"><span data-stu-id="90195-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="90195-105">部署 Enterprise Voice 之前，請確認您的基礎結構符合下列安全性、使用者設定及案例特有的硬體先決條件。</span><span class="sxs-lookup"><span data-stu-id="90195-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="90195-106">系統管理許可權和憑證基礎結構</span><span class="sxs-lookup"><span data-stu-id="90195-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="90195-107">部署之前，請先檢查下列各項：</span><span class="sxs-lookup"><span data-stu-id="90195-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="90195-108">部署 Enterprise Voice 的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="90195-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="90195-109">執行設定工作的系統管理員必須具備適當的權限：</span><span class="sxs-lookup"><span data-stu-id="90195-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="90195-110">**CsVoiceAdministrator：** 此系統管理員角色可以執行語音設定工作、管理語音應用程式，以及指派語音原則給一般使用者。</span><span class="sxs-lookup"><span data-stu-id="90195-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="90195-p101">**CsUserAdministrator：** 此系統管理員角色可以管理使用者屬性，例如啟用使用者的 Enterprise Voice。此系統管理員角色也可以指派個別使用者原則，封存原則除外；移動使用者；管理公用區電話和類比裝置。</span><span class="sxs-lookup"><span data-stu-id="90195-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="90195-113">**CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。</span><span class="sxs-lookup"><span data-stu-id="90195-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="90195-114">已經使用 Microsoft 或協力廠商憑證授權單位 (CA) 的基礎結構，完成 Managed 金鑰基礎結構 (MKI) 的部署和設定。</span><span class="sxs-lookup"><span data-stu-id="90195-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90195-115">如需商務用 Skype Server 中憑證需求的詳細資訊，請參閱商務用 skype server [2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 或 [商務用 skype Server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90195-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="90195-116">使用者設定</span><span class="sxs-lookup"><span data-stu-id="90195-116">User configuration</span></span>

<span data-ttu-id="90195-117">如果您組合轉送伺服器與每個前端集區或 Standard Edition Server 的前端部署期間，則在安裝這些伺服器角色的檔案時，會自動設定企業語音所需的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="90195-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="90195-118">如果您此時是全新部署 Enterprise Voice 工作量，在開始部署程序前，請先為每個您計畫要啟用 Enterprise Voice 的使用者指定主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="90195-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="90195-119">身為系統管理員，您要負責確認這個號碼是唯一的。</span><span class="sxs-lookup"><span data-stu-id="90195-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="90195-120">在實施之前，所有的主要電話號碼都必須正規化 (以商務用 Skype Server 控制台正確格式化) 並複製到每個使用者的 **行 URI** 屬性。</span><span class="sxs-lookup"><span data-stu-id="90195-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90195-121">如需 Enterprise Voice deployment 所需的主要電話號碼範例，請參閱 [範例正常化規則](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。</span><span class="sxs-lookup"><span data-stu-id="90195-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="90195-122">後續步驟：安裝檔或設定 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="90195-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="90195-123">在驗證 Enterprise Voice 的軟體和環境必要條件之後，您可以：</span><span class="sxs-lookup"><span data-stu-id="90195-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="90195-124">如在 [商務用 Skype server](deploy-a-mediation-server.md)中的拓撲產生器中部署轉送伺服器所述，安裝轉送伺服器，但只有在您要部署獨立轉送伺服器或集區時，因為在組合時已將轉送伺服器安裝為前端集區或 Standard Edition Server 部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="90195-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="90195-125">或者，若要開始設定設定以路由傳送 Enterprise Voice 使用者的通話，請參閱 [Configure 主幹 In 商務用 Skype Server 中](configure-trunks.md)所述。</span><span class="sxs-lookup"><span data-stu-id="90195-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

