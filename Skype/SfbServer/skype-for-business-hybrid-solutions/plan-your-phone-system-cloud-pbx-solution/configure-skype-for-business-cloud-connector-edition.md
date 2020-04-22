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
description: 瞭解如何設定商務用 Skype 雲端連接器 Edition，這是一種最小的內部部署拓撲，可讓您的內部部署語音基礎結構與商務用 Skype Online 中的 Office 365 （Cloud PBX）語音服務整合。
ms.openlocfilehash: aa0d8fb37dcaddaca3835b25b94eba6a18e03636
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779159"
---
# <a name="configure-and-manage-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="49368-103">設定及管理商務用 Skype 雲端連接器 Edition</span><span class="sxs-lookup"><span data-stu-id="49368-103">Configure and manage Skype for Business Cloud Connector Edition</span></span>
 
<span data-ttu-id="49368-104">瞭解如何設定商務用 Skype 雲端連接器 Edition，這是一種最小的內部部署拓撲，可讓您的內部部署語音基礎結構與商務用 Skype Online 中的 Office 365 （Cloud PBX）語音服務整合。</span><span class="sxs-lookup"><span data-stu-id="49368-104">Learn how to configure Skype for Business Cloud Connector Edition, a minimal on-premises topology to enable integration of your on-premises voice infrastructure with Phone System in Office 365 (Cloud PBX) voice services in Skype for Business Online.</span></span> 
  
<span data-ttu-id="49368-105">開始之前，您應該檢查[規劃商務用 Skype 雲端連接器 Edition](plan-skype-for-business-cloud-connector-edition.md)的必要條件。</span><span class="sxs-lookup"><span data-stu-id="49368-105">Before you start, you should review the prerequisites in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="49368-106">本主題中的步驟僅適用于 Cloud Connector Edition 1.4.1 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="49368-106">The steps in this topic apply only to Cloud Connector Edition 1.4.1 and later.</span></span> <span data-ttu-id="49368-107">若尚未升級至雲端連接器 Edition 2.1，請參閱[升級至新版本的雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="49368-107">If you have not yet upgraded to Cloud Connector Edition 2.1, see [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span> <span data-ttu-id="49368-108">您可以從[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)下載安裝檔。</span><span class="sxs-lookup"><span data-stu-id="49368-108">You can download the installation file from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span> 
  
## <a name="steps-to-configure-skype-for-business-cloud-connector-edition"></a><span data-ttu-id="49368-109">設定商務用 Skype Cloud Connector Edition 的步驟</span><span class="sxs-lookup"><span data-stu-id="49368-109">Steps to configure Skype for Business Cloud Connector Edition</span></span>

<span data-ttu-id="49368-110">下表列出安裝及設定 Cloud Connector Edition 所需的步驟：</span><span class="sxs-lookup"><span data-stu-id="49368-110">The following table lists the steps you'll need to install and configure Cloud Connector Edition:</span></span>
  
|<span data-ttu-id="49368-111">**步驟**</span><span class="sxs-lookup"><span data-stu-id="49368-111">**Step**</span></span>|<span data-ttu-id="49368-112">**描述**</span><span class="sxs-lookup"><span data-stu-id="49368-112">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="49368-113">準備您的雲端連接器裝置</span><span class="sxs-lookup"><span data-stu-id="49368-113">Prepare your Cloud Connector appliance</span></span>](prepare-your-cloud-connector-appliance.md) <br/> |<span data-ttu-id="49368-114">下載安裝檔，準備憑證，設定 Hyper-V，並為您的雲端連接器部署準備好您的環境。</span><span class="sxs-lookup"><span data-stu-id="49368-114">Download the installation file, prepare certificates, configure Hyper-V, and get your environment ready for your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="49368-115">在雲端連接器中部署單一網站</span><span class="sxs-lookup"><span data-stu-id="49368-115">Deploy a single site in Cloud Connector</span></span>](deploy-a-single-site-in-cloud-connector.md) <br/> |<span data-ttu-id="49368-116">在您的雲端連接器部署中建立網站。</span><span class="sxs-lookup"><span data-stu-id="49368-116">Create a site in your Cloud Connector deployment.</span></span>  <br/> |
|[<span data-ttu-id="49368-117">在雲端連接器中部署多個網站</span><span class="sxs-lookup"><span data-stu-id="49368-117">Deploy multiple sites in Cloud Connector</span></span>](deploy-multiple-sites-in-cloud-connector.md) <br/> |<span data-ttu-id="49368-118">將網站新增至您的部署，並瞭解單一和多網站部署之間的差異。</span><span class="sxs-lookup"><span data-stu-id="49368-118">Add sites to your deployment and learn about the differences between single and multi-site deployments.</span></span>  <br/> |
|[<span data-ttu-id="49368-119">設定與 Office 365 組織的雲端連接器整合</span><span class="sxs-lookup"><span data-stu-id="49368-119">Configure Cloud Connector integration with your Office 365 organization</span></span>](configure-cloud-connector-integration-with-your-office-365-tenant.md) <br/> |<span data-ttu-id="49368-120">新增 DNS 記錄，設定混合式，設定 PSTN 閘道，並在 Office 365 語音信箱中啟用電話系統的使用者。</span><span class="sxs-lookup"><span data-stu-id="49368-120">Add DNS records, configure hybrid, set up PSTN gateways, and enable users for Phone System in Office 365 voice mail.</span></span>  <br/> |
|[<span data-ttu-id="49368-121">驗證您的雲端連接器部署</span><span class="sxs-lookup"><span data-stu-id="49368-121">Validate your Cloud Connector deployment</span></span>](validate-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="49368-122">請確定您的部署運作正常。</span><span class="sxs-lookup"><span data-stu-id="49368-122">Make sure your deployment is working correctly.</span></span>  <br/> |
|[<span data-ttu-id="49368-123">升級至新版本的雲端連接器</span><span class="sxs-lookup"><span data-stu-id="49368-123">Upgrade to a new version of Cloud Connector</span></span>](upgrade-to-a-new-version-of-cloud-connector.md) <br/> |<span data-ttu-id="49368-124">將現有的雲端連接器部署升級至版本2.1。</span><span class="sxs-lookup"><span data-stu-id="49368-124">Upgrade your existing Cloud Connector deployment to version 2.1.</span></span>  <br/> |
|[<span data-ttu-id="49368-125">修改現有 Cloud Connector 部署的設定</span><span class="sxs-lookup"><span data-stu-id="49368-125">Modify the configuration of an existing Cloud Connector deployment</span></span>](modify-the-configuration-of-an-existing-cloud-connector-deployment.md) <br/> |<span data-ttu-id="49368-126">在已部署雲端連接器中的設定之後加以變更。</span><span class="sxs-lookup"><span data-stu-id="49368-126">Change settings in Cloud Connector after it is already deployed.</span></span>  <br/> |
|[<span data-ttu-id="49368-127">在雲端連接器 Edition 中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="49368-127">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md) <br/> |<span data-ttu-id="49368-128">瞭解如何在雲端連接器中部署媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="49368-128">Learn how to deploy media bypass in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="49368-129">雲端連接器 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="49368-129">Cloud Connector cmdlet reference</span></span>](cloud-connector-cmdlet-reference.md) <br/> |<span data-ttu-id="49368-130">瞭解雲端連接器中使用的 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="49368-130">Learn about the PowerShell cmdlets used in Cloud Connector.</span></span>  <br/> |
|[<span data-ttu-id="49368-131">您的雲端連接器部署疑難排解</span><span class="sxs-lookup"><span data-stu-id="49368-131">Troubleshoot your Cloud Connector deployment</span></span>](troubleshoot-your-cloud-connector-deployment.md) <br/> |<span data-ttu-id="49368-132">在雲端連接器部署中遇到的常見問題的解決方案。</span><span class="sxs-lookup"><span data-stu-id="49368-132">Solutions to common issues encountered with a Cloud Connector deployment.</span></span>  <br/> |
   

