---
title: Device 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 資料表是一個支援資料表, 可儲存各種捕獲或轉譯裝置的相關資訊。 資料表中的每一筆記錄代表一個裝置。
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192682"
---
# <a name="device-table"></a><span data-ttu-id="46e0a-104">Device 表格</span><span class="sxs-lookup"><span data-stu-id="46e0a-104">Device table</span></span>
 
<span data-ttu-id="46e0a-105">Device 資料表是一個支援資料表, 可儲存各種捕獲或轉譯裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="46e0a-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="46e0a-106">資料表中的每一筆記錄代表一個裝置。</span><span class="sxs-lookup"><span data-stu-id="46e0a-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="46e0a-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="46e0a-107">**Column**</span></span>|<span data-ttu-id="46e0a-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="46e0a-108">**Data Type**</span></span>|<span data-ttu-id="46e0a-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="46e0a-109">**Key/Index**</span></span>|<span data-ttu-id="46e0a-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="46e0a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46e0a-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="46e0a-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="46e0a-112">int</span><span class="sxs-lookup"><span data-stu-id="46e0a-112">int</span></span>  <br/> |<span data-ttu-id="46e0a-113">首選</span><span class="sxs-lookup"><span data-stu-id="46e0a-113">Primary</span></span>  <br/> |<span data-ttu-id="46e0a-114">標識此裝置的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="46e0a-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="46e0a-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="46e0a-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="46e0a-116">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="46e0a-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="46e0a-117">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="46e0a-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="46e0a-118">裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="46e0a-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="46e0a-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="46e0a-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="46e0a-120">稍微</span><span class="sxs-lookup"><span data-stu-id="46e0a-120">bit</span></span>  <br/> |<span data-ttu-id="46e0a-121">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="46e0a-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="46e0a-122">裝置類型。</span><span class="sxs-lookup"><span data-stu-id="46e0a-122">Device type.</span></span> <span data-ttu-id="46e0a-123">1是擷取裝置, 0 是轉譯裝置。</span><span class="sxs-lookup"><span data-stu-id="46e0a-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

