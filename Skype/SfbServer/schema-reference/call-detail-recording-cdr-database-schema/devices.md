---
title: 商務用 Skype Server 中的裝置表格2015
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
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 表格是一種支援資料表。 每筆記錄儲存一部裝置 (電話機) 的資訊。
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831813"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="aa240-104">商務用 Skype Server 中的裝置表格2015</span><span class="sxs-lookup"><span data-stu-id="aa240-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aa240-105">Devices 表格是一種支援資料表。</span><span class="sxs-lookup"><span data-stu-id="aa240-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="aa240-106">每筆記錄儲存一部裝置 (電話機) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="aa240-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="aa240-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="aa240-107">**Column**</span></span>|<span data-ttu-id="aa240-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="aa240-108">**Data Type**</span></span>|<span data-ttu-id="aa240-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="aa240-109">**Key/Index**</span></span>|<span data-ttu-id="aa240-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="aa240-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa240-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="aa240-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="aa240-112">int</span><span class="sxs-lookup"><span data-stu-id="aa240-112">int</span></span>  <br/> |<span data-ttu-id="aa240-113">主要</span><span class="sxs-lookup"><span data-stu-id="aa240-113">Primary</span></span>  <br/> |<span data-ttu-id="aa240-114">用於識別此硬體版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="aa240-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="aa240-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="aa240-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="aa240-116">int</span><span class="sxs-lookup"><span data-stu-id="aa240-116">int</span></span>  <br/> |<span data-ttu-id="aa240-117">Foreign</span><span class="sxs-lookup"><span data-stu-id="aa240-117">Foreign</span></span>  <br/> |<span data-ttu-id="aa240-118">此裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="aa240-118">Manufacturer of this device.</span></span> <span data-ttu-id="aa240-119">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的製造商表格](manufacturers.md) 。</span><span class="sxs-lookup"><span data-stu-id="aa240-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="aa240-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="aa240-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="aa240-121">int</span><span class="sxs-lookup"><span data-stu-id="aa240-121">int</span></span>  <br/> |<span data-ttu-id="aa240-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="aa240-122">Foreign</span></span>  <br/> |<span data-ttu-id="aa240-123">此裝置的硬體版本。</span><span class="sxs-lookup"><span data-stu-id="aa240-123">Hardware version of this device.</span></span> <span data-ttu-id="aa240-124">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的 HardwareVersions 表格](hardwareversions.md) 。</span><span class="sxs-lookup"><span data-stu-id="aa240-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="aa240-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="aa240-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="aa240-126">Bigint</span><span class="sxs-lookup"><span data-stu-id="aa240-126">bigint</span></span>  <br/> ||<span data-ttu-id="aa240-127">MAC 位址</span><span class="sxs-lookup"><span data-stu-id="aa240-127">MAC Address</span></span>  <br/> |
   

