---
title: 移轉封存伺服器和監控伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果您已在舊版環境中部署封存伺服器和監控伺服器，您可以在遷移前端集區之後，將這些伺服器部署在商務用 Skype Server 2019 環境中。 不過，如果封存和監控功能對您的組織而言很重要，您應該在遷移之前，先在商務用 Skype Server 2019 試驗集區中新增封存和監控功能，以便在遷移程式期間使用該功能。
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752665"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="d399f-104">移轉封存伺服器和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="d399f-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="d399f-105">如果您已在舊版環境中部署封存伺服器和監控伺服器，您可以在遷移前端集區之後，將這些伺服器部署在商務用 Skype Server 2019 環境中。</span><span class="sxs-lookup"><span data-stu-id="d399f-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="d399f-106">不過，如果封存和監控功能對您的組織而言很重要，您應該在遷移之前，先在商務用 Skype Server 2019 試驗集區中新增封存和監控功能，以便在遷移程式期間使用該功能。</span><span class="sxs-lookup"><span data-stu-id="d399f-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="d399f-107">移轉過程中，如果您需要存封和監控功能，請記住以下注意事項：</span><span class="sxs-lookup"><span data-stu-id="d399f-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="d399f-108">封存資料和監控資料不會移至商務用 Skype Server 2019 部署。</span><span class="sxs-lookup"><span data-stu-id="d399f-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="d399f-109">解除委任舊版環境之前所備份的資料，將是舊版環境中的活動歷史。</span><span class="sxs-lookup"><span data-stu-id="d399f-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="d399f-110">舊版本的封存伺服器和監控伺服器只能與舊版前端集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="d399f-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="d399f-111">在商務用 Skype Server 2019 中，封存與監控不再是伺服器角色，但已整合至商務用 Skype Server 2019 前端集區的服務。</span><span class="sxs-lookup"><span data-stu-id="d399f-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="d399f-112">在舊版和商務用 Skype Server 2019 部署共存期間，舊版本的封存伺服器和監控伺服器會收集位於舊版集區上之使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="d399f-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="d399f-113">商務用 Skype 2019 Server 中的封存與監控為位於商務用 Skype Server 2019 集區的使用者收集資料。</span><span class="sxs-lookup"><span data-stu-id="d399f-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d399f-114">在遷移階段，當您仍然使用舊版 Edge server 搭配新的商務用 Skype Server 2019 試驗集區時，舊版本的封存伺服器會繼續收集位於舊版集區上的使用者資料，而在商務用 Skype 2019 Server 中封存，則會收集位於商務用 Skype Server 2019 集區之使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="d399f-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="d399f-115">如果您使用協力廠商封存與監控解決方案搭配商務用 Skype Server 2019 中的封存與監控，請洽詢廠商，以瞭解如何與商務用 Skype Server 2019 整合協力廠商解決方案。</span><span class="sxs-lookup"><span data-stu-id="d399f-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

