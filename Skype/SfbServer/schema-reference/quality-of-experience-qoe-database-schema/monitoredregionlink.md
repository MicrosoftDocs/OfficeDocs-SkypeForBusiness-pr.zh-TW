---
title: MonitoredRegionLink 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 資料表是支援資料表。 每筆記錄代表兩個國家/地區之間的一個連結。
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192662"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="c353b-104">MonitoredRegionLink 表格</span><span class="sxs-lookup"><span data-stu-id="c353b-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="c353b-105">MonitoredRegionLink 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="c353b-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="c353b-106">每筆記錄代表兩個國家/地區之間的一個連結。</span><span class="sxs-lookup"><span data-stu-id="c353b-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="c353b-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c353b-107">**Column**</span></span>|<span data-ttu-id="c353b-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c353b-108">**Data Type**</span></span>|<span data-ttu-id="c353b-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="c353b-109">**Key/Index**</span></span>|<span data-ttu-id="c353b-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c353b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c353b-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="c353b-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="c353b-112">int</span><span class="sxs-lookup"><span data-stu-id="c353b-112">int</span></span>  <br/> |<span data-ttu-id="c353b-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="c353b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c353b-114">從[Region 資料表](region.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="c353b-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="c353b-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="c353b-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="c353b-116">int</span><span class="sxs-lookup"><span data-stu-id="c353b-116">int</span></span>  <br/> |<span data-ttu-id="c353b-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="c353b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c353b-118">從[Region 資料表](region.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="c353b-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

