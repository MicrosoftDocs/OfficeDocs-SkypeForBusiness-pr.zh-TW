---
title: Tenants 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: '[承租人] 資料表是一個支援資料表, 可儲存各種租使用者的清單。 資料表中的每一筆記錄代表一個租使用者。'
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192786"
---
# <a name="tenants-table"></a><span data-ttu-id="cc0a9-104">Tenants 表格</span><span class="sxs-lookup"><span data-stu-id="cc0a9-104">Tenants table</span></span>
 
<span data-ttu-id="cc0a9-105">[承租人] 資料表是一個支援資料表, 可儲存各種租使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="cc0a9-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="cc0a9-106">資料表中的每一筆記錄代表一個租使用者。</span><span class="sxs-lookup"><span data-stu-id="cc0a9-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc0a9-107">在內部部署中, CDR 使用內傳內部租使用者識別碼來指示不同的驗證類型, 例如公用 IM 連線、同盟與匿名。</span><span class="sxs-lookup"><span data-stu-id="cc0a9-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="cc0a9-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="cc0a9-108">**Column**</span></span>|<span data-ttu-id="cc0a9-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="cc0a9-109">**Data Type**</span></span>|<span data-ttu-id="cc0a9-110">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="cc0a9-110">**Key/Index**</span></span>|<span data-ttu-id="cc0a9-111">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="cc0a9-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc0a9-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="cc0a9-112">**TenantId**</span></span> <br/> |<span data-ttu-id="cc0a9-113">int</span><span class="sxs-lookup"><span data-stu-id="cc0a9-113">int</span></span>  <br/> |<span data-ttu-id="cc0a9-114">首選</span><span class="sxs-lookup"><span data-stu-id="cc0a9-114">Primary</span></span>  <br/> |<span data-ttu-id="cc0a9-115">標識此租使用者識別碼的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="cc0a9-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="cc0a9-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="cc0a9-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="cc0a9-117">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc0a9-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="cc0a9-118">允許的值:</span><span class="sxs-lookup"><span data-stu-id="cc0a9-118">Allowed values:</span></span> <br/>  <span data-ttu-id="cc0a9-119">00000000-0000-0000-0000-000000000000-企業</span><span class="sxs-lookup"><span data-stu-id="cc0a9-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="cc0a9-120">00000000-0000-0000-0000-000000000001-同盟</span><span class="sxs-lookup"><span data-stu-id="cc0a9-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="cc0a9-121">00000000-0000-0000-0000-000000000002-匿名</span><span class="sxs-lookup"><span data-stu-id="cc0a9-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="cc0a9-122">00000000-0000-0000-0000-000000000003-公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="cc0a9-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

