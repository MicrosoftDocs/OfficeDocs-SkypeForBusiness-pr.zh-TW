---
title: 商務用 Skype Server 2015 中的 [裝置] 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: '[裝置] 資料表是支援資料表。 每筆記錄儲存一個裝置（電話機）的相關資訊。'
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815281"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a1444-104">商務用 Skype Server 2015 中的 [裝置] 表格</span><span class="sxs-lookup"><span data-stu-id="a1444-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a1444-105">[裝置] 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="a1444-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="a1444-106">每筆記錄儲存一個裝置（電話機）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a1444-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="a1444-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a1444-107">**Column**</span></span>|<span data-ttu-id="a1444-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a1444-108">**Data Type**</span></span>|<span data-ttu-id="a1444-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="a1444-109">**Key/Index**</span></span>|<span data-ttu-id="a1444-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a1444-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a1444-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="a1444-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="a1444-112">int</span><span class="sxs-lookup"><span data-stu-id="a1444-112">int</span></span>  <br/> |<span data-ttu-id="a1444-113">首選</span><span class="sxs-lookup"><span data-stu-id="a1444-113">Primary</span></span>  <br/> |<span data-ttu-id="a1444-114">識別這個硬體版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a1444-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="a1444-115">**[Manufacturerid**</span><span class="sxs-lookup"><span data-stu-id="a1444-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="a1444-116">int</span><span class="sxs-lookup"><span data-stu-id="a1444-116">int</span></span>  <br/> |<span data-ttu-id="a1444-117">外</span><span class="sxs-lookup"><span data-stu-id="a1444-117">Foreign</span></span>  <br/> |<span data-ttu-id="a1444-118">此裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="a1444-118">Manufacturer of this device.</span></span> <span data-ttu-id="a1444-119">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](manufacturers.md)的 [製造商] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a1444-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a1444-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="a1444-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="a1444-121">int</span><span class="sxs-lookup"><span data-stu-id="a1444-121">int</span></span>  <br/> |<span data-ttu-id="a1444-122">外</span><span class="sxs-lookup"><span data-stu-id="a1444-122">Foreign</span></span>  <br/> |<span data-ttu-id="a1444-123">此裝置的硬體版本。</span><span class="sxs-lookup"><span data-stu-id="a1444-123">Hardware version of this device.</span></span> <span data-ttu-id="a1444-124">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](hardwareversions.md)的 [HardwareVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a1444-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a1444-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="a1444-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="a1444-126">Bigint</span><span class="sxs-lookup"><span data-stu-id="a1444-126">bigint</span></span>  <br/> ||<span data-ttu-id="a1444-127">MAC 位址</span><span class="sxs-lookup"><span data-stu-id="a1444-127">MAC Address</span></span>  <br/> |
   

