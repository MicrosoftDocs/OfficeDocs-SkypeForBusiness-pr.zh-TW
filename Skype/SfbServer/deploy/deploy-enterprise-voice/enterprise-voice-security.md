---
title: 商務用 Skype Server 中的企業語音安全性與設定先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：瞭解商務用 Skype Server 中企業語音的安全性與設定先決條件。
ms.openlocfilehash: 314c25429dbf346a5f62705afa4f19a5b518452a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767236"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="c0bb0-103">商務用 Skype Server 中的企業語音安全性與設定先決條件</span><span class="sxs-lookup"><span data-stu-id="c0bb0-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="c0bb0-104">**摘要：** 瞭解商務用 Skype Server 中企業語音的安全性與設定先決條件。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="c0bb0-105">在部署企業語音之前，請確認您的基礎結構符合下列安全性、使用者設定和案例特定的硬體先決條件。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="c0bb0-106">管理許可權與證書基礎結構</span><span class="sxs-lookup"><span data-stu-id="c0bb0-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="c0bb0-107">在部署之前，請檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="c0bb0-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="c0bb0-108">部署企業語音的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="c0bb0-109">執行設定任務的系統管理員必須具備足夠的許可權：</span><span class="sxs-lookup"><span data-stu-id="c0bb0-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="c0bb0-110">**CsVoiceAdministrator：** 這個系統管理員角色可以執行語音設定工作、管理語音應用程式，以及將語音原則指派給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="c0bb0-111">**CsUserAdministrator：** 這個系統管理員角色可以管理使用者屬性，例如為使用者啟用企業語音。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-111">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user.</span></span> <span data-ttu-id="c0bb0-112">除了封存原則之外，此管理員角色還可以指派每個使用者的原則;移動使用者;以及管理常見的區域電話和類比裝置。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-112">This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="c0bb0-113">**CsAdministrator：** 此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="c0bb0-114">管理的金鑰結構（MKI）是透過 Microsoft 或協力廠商憑證授權單位（CA）基礎結構來部署和設定。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c0bb0-115">如需商務用 Skype Server 的憑證需求的詳細資訊，請參閱商務用 skype server 2015 或商務用[skype server 2019 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)[的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="c0bb0-116">使用者設定</span><span class="sxs-lookup"><span data-stu-id="c0bb0-116">User configuration</span></span>

<span data-ttu-id="c0bb0-117">如果您在前端部署期間 collocated 每個前端池或標準版伺服器的中繼伺服器，則在安裝這些伺服器角色的檔案期間，系統會自動設定企業語音所需的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="c0bb0-118">如果您目前正在新部署企業語音工作負載，請在開始進行部署程式之前，為您打算啟用企業語音的每位使用者指定主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="c0bb0-119">身為管理員，您必須負責確保此號碼是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="c0bb0-120">在實施前，所有的主要電話號碼都必須經過標準化（正確格式化），並使用商務用 Skype Server 控制台將其複製到每個使用者的**行 URI**屬性。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0bb0-121">如需企業語音部署所需的主要電話號碼範例，請參閱[範例正常化規則](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="c0bb0-122">後續步驟：安裝檔案或設定 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="c0bb0-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="c0bb0-123">在驗證企業語音的軟體與環境先決條件之後，您可以執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c0bb0-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="c0bb0-124">請參閱在商務用 Skype Server 的 [拓撲建立器] 中[部署轉送伺服器](deploy-a-mediation-server.md)（如果您想要部署獨立的中繼伺服器或池），因為在 collocated 時，會將轉送伺服器安裝為前端池或標準版 Server 部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="c0bb0-125">或者，開始設定設定以路由企業語音使用者的呼叫，如在[商務用 Skype Server 中設定 trunks 中](configure-trunks.md)所述。</span><span class="sxs-lookup"><span data-stu-id="c0bb0-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

