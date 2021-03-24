---
title: 設定及管理商務用 Skype 雲端連接器 Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ce323f4b-24e4-4ddf-84a3-67da82bb0c87
description: 瞭解如何設定商務用 Skype 雲端連接器 Edition，這是一種最少的內部部署拓撲，可讓您的內部部署語音基礎結構與電話系統 (Cloud PBX) 語音服務的商務用 Skype Online。
ms.openlocfilehash: 4d24e5a312275158f276856aa78396ad63dff615
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094871"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="4a3ca-103">設定及管理商務用 Skype 雲端連接器 Edition</span><span class="sxs-lookup"><span data-stu-id="4a3ca-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="4a3ca-104">雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="4a3ca-105">當您的組織升級至小組後，請瞭解如何使用 [直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="4a3ca-106">瞭解如何設定商務用 Skype 雲端連接器 Edition，這是一種最少的內部部署拓撲，可讓您的內部部署語音基礎結構與電話系統 (Cloud PBX) 語音服務的商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-106">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="4a3ca-107">開始之前，您應該檢查 [規劃商務用 Skype 雲端連接器 Edition](plan-skype-for-business-cloud-connector-edition.md)的必要條件。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-107">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4a3ca-108">本主題中的步驟僅適用于 Cloud Connector Edition 1.4.1 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-108">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="4a3ca-109">若尚未升級至雲端連接器 Edition 2.1，請參閱 [升級至新版本的雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-109">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="4a3ca-110">您可以從下載安裝檔 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-110">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="4a3ca-111">設定商務用 Skype Cloud Connector Edition 的步驟</span><span class="sxs-lookup"><span data-stu-id="4a3ca-111">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="4a3ca-112">下表列出安裝及設定 Cloud Connector Edition 所需的步驟：</span><span class="sxs-lookup"><span data-stu-id="4a3ca-112">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="4a3ca-113">**步驟**</span><span class="sxs-lookup"><span data-stu-id="4a3ca-113">**Step**</span></span>|<span data-ttu-id="4a3ca-114">**描述**</span><span class="sxs-lookup"><span data-stu-id="4a3ca-114">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4a3ca-115">準備 Cloud Connector 設備</span><span class="sxs-lookup"><span data-stu-id="4a3ca-115">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="4a3ca-116">下載安裝檔，準備憑證，設定 Hyper-V，並為您的雲端連接器部署準備好您的環境。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-116">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="4a3ca-117">在 Cloud Connector 中部署單一網站</span><span class="sxs-lookup"><span data-stu-id="4a3ca-117">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="4a3ca-118">在您的雲端連接器部署中建立網站。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-118">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="4a3ca-119">在 Cloud Connector 中部署多個網站</span><span class="sxs-lookup"><span data-stu-id="4a3ca-119">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="4a3ca-120">將網站新增至您的部署，並瞭解單一和多網站部署之間的差異。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-120">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="4a3ca-121">設定與您的 Microsoft 365 或 Office 365 組織的雲端連接器整合</span><span class="sxs-lookup"><span data-stu-id="4a3ca-121">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="4a3ca-122">新增 DNS 記錄，設定混合式，設定 PSTN 閘道，並為使用者啟用電話系統語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-122">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System voice mail.</span></span>  <br/> |
|[<span data-ttu-id="4a3ca-123">驗證您的 Cloud Connector 部署</span><span class="sxs-lookup"><span data-stu-id="4a3ca-123">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="4a3ca-124">請確定您的部署運作正常。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-124">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="4a3ca-125">升級至新版 Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4a3ca-125">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="4a3ca-126">將現有的雲端連接器部署升級至版本2.1。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-126">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="4a3ca-127">修改現有 Cloud Connector 部署的組態</span><span class="sxs-lookup"><span data-stu-id="4a3ca-127">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="4a3ca-128">在已部署雲端連接器中的設定之後加以變更。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-128">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="4a3ca-129">在雲端連接器 Edition 中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="4a3ca-129">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="4a3ca-130">瞭解如何在雲端連接器中部署媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-130">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="4a3ca-131">Cloud Connector Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="4a3ca-131">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="4a3ca-132">瞭解雲端連接器中使用的 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-132">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="4a3ca-133">疑難排解您的 Cloud Connector 部署</span><span class="sxs-lookup"><span data-stu-id="4a3ca-133">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="4a3ca-134">在雲端連接器部署中遇到的常見問題的解決方案。</span><span class="sxs-lookup"><span data-stu-id="4a3ca-134">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
