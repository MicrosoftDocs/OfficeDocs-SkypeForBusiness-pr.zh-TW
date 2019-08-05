---
title: 設定及管理商務用 Skype 雲端連接器版本
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: 瞭解如何設定商務用 Skype 雲端連接器版本, 這是一種最小的內部部署拓朴, 可讓您在商務用 Skype Online 的 Office 365 (雲端 PBX) 語音服務中整合您的內部部署語音結構。
ms.openlocfilehash: 49c0ce1a67b579a566e2dd22b9b345c1d6a4afdd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190864"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="2b07f-103">設定及管理商務用 Skype 雲端連接器版本</span><span class="sxs-lookup"><span data-stu-id="2b07f-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="2b07f-104">瞭解如何設定商務用 Skype 雲端連接器版本, 這是一種最小的內部部署拓朴, 可讓您在商務用 Skype Online 的 Office 365 (雲端 PBX) 語音服務中整合您的內部部署語音結構。</span><span class="sxs-lookup"><span data-stu-id="2b07f-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="2b07f-105">開始之前, 您應該先檢查[規劃商務用 Skype 雲端連接器版本](plan-skype-for-business-cloud-connector-edition.md)的先決條件。</span><span class="sxs-lookup"><span data-stu-id="2b07f-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2b07f-106">本主題中的步驟只適用于雲端連接器版本1.4.1 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="2b07f-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="2b07f-107">如果您尚未升級至雲端連接器 Edition 2.1, 請參閱[升級至新版本的雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="2b07f-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="2b07f-108">您可以從[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)下載安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="2b07f-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="2b07f-109">設定商務用 Skype 雲端連接器版本的步驟</span><span class="sxs-lookup"><span data-stu-id="2b07f-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="2b07f-110">下表列出安裝及設定雲端連接器版本所需的步驟:</span><span class="sxs-lookup"><span data-stu-id="2b07f-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="2b07f-111">**循序漸進**</span><span class="sxs-lookup"><span data-stu-id="2b07f-111">**Step**</span></span>|<span data-ttu-id="2b07f-112">**說明**</span><span class="sxs-lookup"><span data-stu-id="2b07f-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2b07f-113">準備雲端連接器裝置</span><span class="sxs-lookup"><span data-stu-id="2b07f-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="2b07f-114">下載安裝檔案、準備證書、設定 Hyper-v, 並為您的雲端連接器部署準備好您的環境。</span><span class="sxs-lookup"><span data-stu-id="2b07f-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="2b07f-115">在雲端連接器中部署單一網站</span><span class="sxs-lookup"><span data-stu-id="2b07f-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="2b07f-116">在雲端連接器部署中建立網站。</span><span class="sxs-lookup"><span data-stu-id="2b07f-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="2b07f-117">在雲端連接器中部署多個網站</span><span class="sxs-lookup"><span data-stu-id="2b07f-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="2b07f-118">將網站新增至您的部署, 並瞭解單一和多網站部署之間的差異。</span><span class="sxs-lookup"><span data-stu-id="2b07f-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="2b07f-119">設定雲端連接器與您的 Office 365 租使用者整合</span><span class="sxs-lookup"><span data-stu-id="2b07f-119">Configure Cloud Connector integration with your Office 365 tenant</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="2b07f-120">您可以在 Office 365 語音信箱中新增 DNS 記錄、設定混合式、設定 PSTN 閘道, 以及啟用手機系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="2b07f-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="2b07f-121">驗證您的雲端連接器部署</span><span class="sxs-lookup"><span data-stu-id="2b07f-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="2b07f-122">請確定您的部署正常運作。</span><span class="sxs-lookup"><span data-stu-id="2b07f-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="2b07f-123">升級至新版雲端連接器</span><span class="sxs-lookup"><span data-stu-id="2b07f-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="2b07f-124">將您現有的雲端連接器部署升級至版本2.1。</span><span class="sxs-lookup"><span data-stu-id="2b07f-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="2b07f-125">修改現有雲端連接器部署的設定</span><span class="sxs-lookup"><span data-stu-id="2b07f-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="2b07f-126">在已部署雲端連接器之後, 變更其中的設定。</span><span class="sxs-lookup"><span data-stu-id="2b07f-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="2b07f-127">在雲端連接器版本中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="2b07f-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="2b07f-128">瞭解如何在雲端連接器中部署媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="2b07f-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="2b07f-129">雲端連接器 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="2b07f-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="2b07f-130">瞭解雲端連接器中使用的 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2b07f-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="2b07f-131">疑難排解雲端連接器部署</span><span class="sxs-lookup"><span data-stu-id="2b07f-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="2b07f-132">在雲端連接器部署中遇到常見問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="2b07f-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

