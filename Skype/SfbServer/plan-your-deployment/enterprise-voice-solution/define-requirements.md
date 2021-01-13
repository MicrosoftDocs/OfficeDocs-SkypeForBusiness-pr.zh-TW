---
title: 在商務用 Skype Server 中定義緊急通話的需求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: 摘要說明啟用 E9-1-1 in 商務用 Skype Server Enterprise Voice （取決於您是否有 SIP 主幹 E9-1-1 服務提供者或 ELIN 閘道）所需的步驟。
ms.openlocfilehash: 8efd38657a80bee1ecd979e8730feacfb980053e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825813"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="789b7-103">在商務用 Skype Server 中定義緊急通話的需求</span><span class="sxs-lookup"><span data-stu-id="789b7-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="789b7-104">摘要說明啟用 E9-1-1 in 商務用 Skype Server Enterprise Voice （取決於您是否有 SIP 主幹 E9-1-1 服務提供者或 ELIN 閘道）所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="789b7-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="789b7-105">開始商務用 Skype Server E9-1-1 部署之前，您應該先可以回答下列各節所述的問題。</span><span class="sxs-lookup"><span data-stu-id="789b7-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="789b7-106">您需要執行的規劃視您選擇部署的 E9-1-1 解決方案類型— SIP 主幹 E9-1-1 服務提供者或緊急位置識別碼 (ELIN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="789b7-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="789b7-107">下表識別此規劃活頁簿中的區段，您必須針對每個解決方案進行審查。</span><span class="sxs-lookup"><span data-stu-id="789b7-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="789b7-108">**規劃步驟 (依 E9-1-1 解決方案的類型)**</span><span class="sxs-lookup"><span data-stu-id="789b7-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="789b7-109">**SIP 主幹服務提供者**</span><span class="sxs-lookup"><span data-stu-id="789b7-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="789b7-110">**ELIN 閘道**</span><span class="sxs-lookup"><span data-stu-id="789b7-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="789b7-111">在商務用 Skype Server 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="789b7-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="789b7-112">在商務用 Skype Server 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="789b7-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="789b7-113">定義用來判斷商務用 Skype Server 中的位置的網路元素</span><span class="sxs-lookup"><span data-stu-id="789b7-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="789b7-114">定義用來判斷商務用 Skype Server 中的位置的網路元素</span><span class="sxs-lookup"><span data-stu-id="789b7-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="789b7-115">為商務用 Skype Server 中的 E9-1-1 啟用使用者</span><span class="sxs-lookup"><span data-stu-id="789b7-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="789b7-116">為商務用 Skype Server 中的 E9-1-1 啟用使用者</span><span class="sxs-lookup"><span data-stu-id="789b7-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="789b7-117">在商務用 Skype Server 中管理 SIP 主幹服務提供者的位置</span><span class="sxs-lookup"><span data-stu-id="789b7-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="789b7-118">在商務用 Skype Server 中管理 ELIN 閘道的位置</span><span class="sxs-lookup"><span data-stu-id="789b7-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="789b7-119">定義在商務用 Skype Server 中手動取得位置的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="789b7-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="789b7-120">定義在商務用 Skype Server 中手動取得位置的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="789b7-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="789b7-121">在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="789b7-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="789b7-122">在商務用 Skype 中包含安全性桌面伺服器</span><span class="sxs-lookup"><span data-stu-id="789b7-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="789b7-123">在商務用 Skype 中包含安全性桌面伺服器</span><span class="sxs-lookup"><span data-stu-id="789b7-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="789b7-124">規劃商務用 Skype Server 的位置原則</span><span class="sxs-lookup"><span data-stu-id="789b7-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="789b7-125">為商務用 Skype Server 選擇 E9-1-1 服務提供者</span><span class="sxs-lookup"><span data-stu-id="789b7-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="789b7-126">在商務用 Skype Server 中指派位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="789b7-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="789b7-127">規劃商務用 Skype Server 的位置原則</span><span class="sxs-lookup"><span data-stu-id="789b7-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="789b7-128">在商務用 Skype Server 中指派位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="789b7-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

