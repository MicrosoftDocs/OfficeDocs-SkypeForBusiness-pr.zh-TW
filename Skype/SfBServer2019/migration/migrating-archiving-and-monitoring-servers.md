---
title: 遷移封存與監控伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果您在舊版環境中部署了 [封存伺服器] 和 [監視伺服器], 您可以在您遷移前端池之後, 將這些伺服器部署在商務用 Skype Server 2019 環境中。 不過, 如果封存和監控功能對您的組織而言是至關重要的, 您應該先在您的商務用 Skype Server 2019 試驗區中新增封存與監控, 以便在遷移程式中提供此功能。
ms.openlocfilehash: f259a08d25c93467c79fdaf3550288c6208607c3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238458"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="d2b99-104">遷移封存與監控伺服器</span><span class="sxs-lookup"><span data-stu-id="d2b99-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="d2b99-105">如果您在舊版環境中部署了 [封存伺服器] 和 [監視伺服器], 您可以在您遷移前端池之後, 將這些伺服器部署在商務用 Skype Server 2019 環境中。</span><span class="sxs-lookup"><span data-stu-id="d2b99-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="d2b99-106">不過, 如果封存和監控功能對您的組織而言是至關重要的, 您應該先在您的商務用 Skype Server 2019 試驗區中新增封存與監控, 以便在遷移程式中提供此功能。</span><span class="sxs-lookup"><span data-stu-id="d2b99-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="d2b99-107">如果您想要在遷移期間進行封存與監控, 請記住下列考慮事項:</span><span class="sxs-lookup"><span data-stu-id="d2b99-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="d2b99-108">歸檔資料和監控資料不會移至商務用 Skype Server 2019 部署。</span><span class="sxs-lookup"><span data-stu-id="d2b99-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="d2b99-109">您在解除舊版環境之前備份的資料將是舊版環境中的活動歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="d2b99-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="d2b99-110">舊版本的 [封存伺服器] 和 [監視伺服器] 只能與舊版的 [前端] 池相關聯。</span><span class="sxs-lookup"><span data-stu-id="d2b99-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="d2b99-111">在商務用 Skype Server 2019 中, [封存及監視] 不再是伺服器角色, 但是整合到商務用 Skype Server 2019 前端的服務。</span><span class="sxs-lookup"><span data-stu-id="d2b99-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="d2b99-112">在舊版及商務用 Skype Server 2019 部署期間共存時, 舊版的存檔伺服器與監視伺服器會針對駐留在舊版池中的使用者收集資料。</span><span class="sxs-lookup"><span data-stu-id="d2b99-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="d2b99-113">商務用 Skype Server 2019 中的 [封存與監控] 可收集駐留在商務用 Skype Server 2019 池的使用者資料。</span><span class="sxs-lookup"><span data-stu-id="d2b99-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2b99-114">在遷移階段, 當您仍將舊版 Edge 伺服器與新的商務用 Skype Server 2019 (試用版池) 結合使用時, 舊版本的封存伺服器會繼續收集駐留在舊版池中的使用者資料, 並在商務用 Skype 中進行歸檔伺服器2019會收集駐留在商務用 Skype Server 2019 池的使用者資料。</span><span class="sxs-lookup"><span data-stu-id="d2b99-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="d2b99-115">如果您在商務用 Skype Server 2019 的 [封存與監控] 中使用協力廠商的歸檔與監控解決方案, 請諮詢您的供應商, 以瞭解何時以及如何將協力廠商解決方案與商務用 Skype Server 2019 整合。</span><span class="sxs-lookup"><span data-stu-id="d2b99-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

