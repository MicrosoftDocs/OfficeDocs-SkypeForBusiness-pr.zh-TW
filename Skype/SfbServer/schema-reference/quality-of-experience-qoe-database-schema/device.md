---
title: 裝置表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 表是一種支援資料表，可儲存各種捕獲或呈現裝置的相關資訊。 資料表中的每一筆記錄都代表一個裝置。
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814743"
---
# <a name="device-table"></a><span data-ttu-id="a6352-104">裝置表格</span><span class="sxs-lookup"><span data-stu-id="a6352-104">Device table</span></span>
 
<span data-ttu-id="a6352-105">Device 表是一種支援資料表，可儲存各種捕獲或呈現裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a6352-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="a6352-106">資料表中的每一筆記錄都代表一個裝置。</span><span class="sxs-lookup"><span data-stu-id="a6352-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="a6352-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="a6352-107">**Column**</span></span>|<span data-ttu-id="a6352-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a6352-108">**Data Type**</span></span>|<span data-ttu-id="a6352-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="a6352-109">**Key/Index**</span></span>|<span data-ttu-id="a6352-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a6352-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a6352-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="a6352-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="a6352-112">int</span><span class="sxs-lookup"><span data-stu-id="a6352-112">int</span></span>  <br/> |<span data-ttu-id="a6352-113">主要</span><span class="sxs-lookup"><span data-stu-id="a6352-113">Primary</span></span>  <br/> |<span data-ttu-id="a6352-114">用於識別此裝置的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a6352-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="a6352-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="a6352-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="a6352-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a6352-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a6352-117">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="a6352-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="a6352-118">裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a6352-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="a6352-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="a6352-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="a6352-120">位</span><span class="sxs-lookup"><span data-stu-id="a6352-120">bit</span></span>  <br/> |<span data-ttu-id="a6352-121">DeviceName + DeviceType 是唯一的</span><span class="sxs-lookup"><span data-stu-id="a6352-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="a6352-122">裝置類型。</span><span class="sxs-lookup"><span data-stu-id="a6352-122">Device type.</span></span> <span data-ttu-id="a6352-123">1是捕獲裝置，0代表呈現裝置。</span><span class="sxs-lookup"><span data-stu-id="a6352-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

