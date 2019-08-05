---
title: 在商務用 Skype Server 中定義緊急通話的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: 摘要說明在商務用 Skype Server Enterprise Voice 中啟用 E9-1-1-1-1-1-1 服務提供者或 ELIN 閘道所需的步驟。
ms.openlocfilehash: 9e6ccd4b93416d49993dbc24ee0592d130e25de8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187735"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="2e58c-103">在商務用 Skype Server 中定義緊急通話的需求</span><span class="sxs-lookup"><span data-stu-id="2e58c-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="2e58c-104">摘要說明在商務用 Skype Server Enterprise Voice 中啟用 E9-1-1-1-1-1-1 服務提供者或 ELIN 閘道所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="2e58c-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="2e58c-105">在您開始使用商務用 Skype Server E9-1-1 1 版部署之前, 您應該先能夠回答下列各節所述的問題。</span><span class="sxs-lookup"><span data-stu-id="2e58c-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="2e58c-106">您需要執行的規劃取決於您選擇部署的 E9-1-1 解決方案類型, 即 SIP 幹線 E9-1 服務提供者, 或緊急位置識別號碼 (ELIN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="2e58c-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="2e58c-107">下表說明本規劃活頁簿中您需要針對每個方案進行審查的章節。</span><span class="sxs-lookup"><span data-stu-id="2e58c-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="2e58c-108">**依 E9 類型 (1-1-1) 方案規劃步驟**</span><span class="sxs-lookup"><span data-stu-id="2e58c-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="2e58c-109">**SIP 中繼服務提供者**</span><span class="sxs-lookup"><span data-stu-id="2e58c-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="2e58c-110">**ELIN 閘道**</span><span class="sxs-lookup"><span data-stu-id="2e58c-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2e58c-111">在商務用 Skype Server 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="2e58c-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="2e58c-112">在商務用 Skype Server 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="2e58c-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="2e58c-113">定義用來判斷商務用 Skype Server 中的位置的網路元素</span><span class="sxs-lookup"><span data-stu-id="2e58c-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="2e58c-114">定義用來判斷商務用 Skype Server 中的位置的網路元素</span><span class="sxs-lookup"><span data-stu-id="2e58c-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="2e58c-115">在商務用 Skype Server 中啟用 E9-1-1 的使用者</span><span class="sxs-lookup"><span data-stu-id="2e58c-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="2e58c-116">在商務用 Skype Server 中啟用 E9-1-1 的使用者</span><span class="sxs-lookup"><span data-stu-id="2e58c-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="2e58c-117">在商務用 Skype Server 中管理 SIP 中繼服務提供者的位置</span><span class="sxs-lookup"><span data-stu-id="2e58c-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="2e58c-118">在商務用 Skype Server 中管理 ELIN 閘道的位置</span><span class="sxs-lookup"><span data-stu-id="2e58c-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="2e58c-119">定義在商務用 Skype Server 中手動取得位置的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="2e58c-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="2e58c-120">定義在商務用 Skype Server 中手動取得位置的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="2e58c-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="2e58c-121">在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="2e58c-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="2e58c-122">在商務用 Skype Server 中加入安全服務台</span><span class="sxs-lookup"><span data-stu-id="2e58c-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="2e58c-123">在商務用 Skype Server 中加入安全服務台</span><span class="sxs-lookup"><span data-stu-id="2e58c-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="2e58c-124">規劃商務用 Skype Server 的位置原則</span><span class="sxs-lookup"><span data-stu-id="2e58c-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="2e58c-125">選擇適用于商務用 Skype Server 的 E9-1 服務提供者</span><span class="sxs-lookup"><span data-stu-id="2e58c-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="2e58c-126">在商務用 Skype Server 中指派位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="2e58c-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="2e58c-127">規劃商務用 Skype Server 的位置原則</span><span class="sxs-lookup"><span data-stu-id="2e58c-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="2e58c-128">在商務用 Skype Server 中指派位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="2e58c-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

