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
ms.openlocfilehash: 9cd5fe66b6092b0ac21af4c425f662d18d96ab49
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221093"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="bb12d-104">為使用者啟用商務用 Skype Server 含內部部署 PSTN 連線功能的電話系統</span><span class="sxs-lookup"><span data-stu-id="bb12d-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="bb12d-105">本主題說明如何使用內部部署 PSTN 連線來啟用使用者的電話系統。</span><span class="sxs-lookup"><span data-stu-id="bb12d-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="bb12d-106">遵循本主題中的步驟之前，您應該先閱讀下列各項：。</span><span class="sxs-lookup"><span data-stu-id="bb12d-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="bb12d-107">若要瞭解如何設定混合式連線，請參閱[規劃商務用 Skype server 與商務用 Skype online 之間的混合式連線](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)，以及[在商務用 Skype server 與商務用 Skype online 之間部署混合](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)式連接。</span><span class="sxs-lookup"><span data-stu-id="bb12d-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="bb12d-108">若要瞭解規劃部署，請參閱[在商務用 Skype Server 中規劃使用內部部署 PSTN 連線的電話系統](plan-phone-system-with-on-premises-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="bb12d-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="bb12d-109">若要深入瞭解電話系統，包括授權與計畫，請參閱[適用于商務用 Skype 的 PSTN 通話方案](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)。</span><span class="sxs-lookup"><span data-stu-id="bb12d-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="bb12d-110">使用內部部署 PSTN 連線將使用者移至電話系統</span><span class="sxs-lookup"><span data-stu-id="bb12d-110">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="bb12d-111">將使用者移至商務用 Skype Online 之前，建議您先在商務用 Skype Server 或 Lync Server 2013 中，啟用您的使用者，然後再將其移動到線上。</span><span class="sxs-lookup"><span data-stu-id="bb12d-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="bb12d-112">如需詳細資訊，請參閱[規劃在商務用 Skype Server 與商務用 Skype Online 之間的混合式連線](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[啟用企業語音內部部署的使用者](enable-the-users-for-enterprise-voice-on-premises.md)的特殊考慮一節（當使用者在內部部署時執行）。</span><span class="sxs-lookup"><span data-stu-id="bb12d-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="bb12d-113">所有使用者都必須在內部部署的 Active Directory 中建立，並使用 Azure AD Connector 的支援版本同步處理至 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="bb12d-113">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="bb12d-114">您無法在 Office 365 中為直接在 Azure AD 中建立的電話系統啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="bb12d-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="bb12d-115">如果您想要針對 Azure AD 中建立的使用者啟用具有內部部署 PSTN 連線的電話系統，您必須在內部部署 AD 中為該使用者建立新的帳戶，在內部部署中設定帳戶，然後使用 Azure AD Connector 工具支援的版本同步處理帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb12d-115">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="bb12d-116">使用具有內部部署 PSTN 連線的電話系統啟用使用者，然後將其移至商務用 Skype Online，需要下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bb12d-116">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="bb12d-117">[為使用者啟用企業語音的內部部署](enable-the-users-for-enterprise-voice-on-premises.md)（使用者位於內部部署時執行）。</span><span class="sxs-lookup"><span data-stu-id="bb12d-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="bb12d-118">[指派語音路由原則](assign-a-voice-routing-policy.md)（在使用者裝載內部部署時執行）。</span><span class="sxs-lookup"><span data-stu-id="bb12d-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="bb12d-119">[將使用者同步處理至雲端並指派授權](synchronize-users-to-the-cloud-and-assign-licenses.md)（使用 Office 365 執行）。</span><span class="sxs-lookup"><span data-stu-id="bb12d-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="bb12d-120">[將內部部署使用者移至商務用 Skype Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) （使用 Windows PowerShell 內部部署，但使用您的 Office 365 系統管理員認證）。</span><span class="sxs-lookup"><span data-stu-id="bb12d-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="bb12d-121">[為使用者啟用企業語音線上和電話語音信箱](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md)（使用遠端 PowerShell 執行。</span><span class="sxs-lookup"><span data-stu-id="bb12d-121">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

