---
title: MonitoredRegionLink 表格
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 表格是支援的表格。 每筆記錄代表兩個國家/地區之間的一個連結。
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806343"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="ee33b-104">MonitoredRegionLink 表格</span><span class="sxs-lookup"><span data-stu-id="ee33b-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="ee33b-105">MonitoredRegionLink 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="ee33b-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="ee33b-106">每筆記錄代表兩個國家/地區之間的一個連結。</span><span class="sxs-lookup"><span data-stu-id="ee33b-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="ee33b-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="ee33b-107">**Column**</span></span>|<span data-ttu-id="ee33b-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="ee33b-108">**Data Type**</span></span>|<span data-ttu-id="ee33b-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="ee33b-109">**Key/Index**</span></span>|<span data-ttu-id="ee33b-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="ee33b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee33b-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="ee33b-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="ee33b-112">int</span><span class="sxs-lookup"><span data-stu-id="ee33b-112">int</span></span>  <br/> |<span data-ttu-id="ee33b-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="ee33b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ee33b-114">從 [地區表](region.md)參考。</span><span class="sxs-lookup"><span data-stu-id="ee33b-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="ee33b-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="ee33b-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="ee33b-116">int</span><span class="sxs-lookup"><span data-stu-id="ee33b-116">int</span></span>  <br/> |<span data-ttu-id="ee33b-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="ee33b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ee33b-118">從 [地區表](region.md)參考。</span><span class="sxs-lookup"><span data-stu-id="ee33b-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

