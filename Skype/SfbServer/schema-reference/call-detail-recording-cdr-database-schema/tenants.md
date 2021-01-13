---
title: 承租人表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: 承租人資料表是一種支援資料表，可儲存各種承租人的清單。 表格中的每筆記錄代表一位承租人。
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831713"
---
# <a name="tenants-table"></a><span data-ttu-id="8fee6-104">承租人表格</span><span class="sxs-lookup"><span data-stu-id="8fee6-104">Tenants table</span></span>
 
<span data-ttu-id="8fee6-105">承租人資料表是一種支援資料表，可儲存各種承租人的清單。</span><span class="sxs-lookup"><span data-stu-id="8fee6-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="8fee6-106">表格中的每筆記錄代表一位承租人。</span><span class="sxs-lookup"><span data-stu-id="8fee6-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8fee6-107">在內部部署中，CDR 使用內建承租人租使用者識別碼來表示不同的驗證類型，例如公用 IM 連線、同盟和匿名。</span><span class="sxs-lookup"><span data-stu-id="8fee6-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="8fee6-108">**欄**</span><span class="sxs-lookup"><span data-stu-id="8fee6-108">**Column**</span></span>|<span data-ttu-id="8fee6-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8fee6-109">**Data Type**</span></span>|<span data-ttu-id="8fee6-110">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="8fee6-110">**Key/Index**</span></span>|<span data-ttu-id="8fee6-111">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="8fee6-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8fee6-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="8fee6-112">**TenantId**</span></span> <br/> |<span data-ttu-id="8fee6-113">int</span><span class="sxs-lookup"><span data-stu-id="8fee6-113">int</span></span>  <br/> |<span data-ttu-id="8fee6-114">主要</span><span class="sxs-lookup"><span data-stu-id="8fee6-114">Primary</span></span>  <br/> |<span data-ttu-id="8fee6-115">用於識別此租使用者識別碼的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="8fee6-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="8fee6-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="8fee6-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="8fee6-117">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="8fee6-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="8fee6-118">允許的值：</span><span class="sxs-lookup"><span data-stu-id="8fee6-118">Allowed values:</span></span> <br/>  <span data-ttu-id="8fee6-119">00000000-0000-0000-0000-000000000000-企業</span><span class="sxs-lookup"><span data-stu-id="8fee6-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="8fee6-120">00000000-0000-0000-0000-000000000001-同盟</span><span class="sxs-lookup"><span data-stu-id="8fee6-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="8fee6-121">00000000-0000-0000-0000-000000000002-匿名</span><span class="sxs-lookup"><span data-stu-id="8fee6-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="8fee6-122">00000000-0000-0000-0000-000000000003-公用 IM 連線能力</span><span class="sxs-lookup"><span data-stu-id="8fee6-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

