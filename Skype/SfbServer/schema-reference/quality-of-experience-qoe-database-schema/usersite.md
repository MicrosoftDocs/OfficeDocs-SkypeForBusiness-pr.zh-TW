---
title: UserSite 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 資料表是支援資料表。 每個記錄代表 [網路設定] 中定義的一個使用者網站。
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192616"
---
# <a name="usersite-table"></a><span data-ttu-id="ea387-104">UserSite 表格</span><span class="sxs-lookup"><span data-stu-id="ea387-104">UserSite table</span></span>
 
<span data-ttu-id="ea387-105">UserSite 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="ea387-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="ea387-106">每個記錄代表 [網路設定] 中定義的一個使用者網站。</span><span class="sxs-lookup"><span data-stu-id="ea387-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="ea387-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="ea387-107">**Column**</span></span>|<span data-ttu-id="ea387-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="ea387-108">**Data Type**</span></span>|<span data-ttu-id="ea387-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="ea387-109">**Key/Index**</span></span>|<span data-ttu-id="ea387-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="ea387-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ea387-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="ea387-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="ea387-112">int</span><span class="sxs-lookup"><span data-stu-id="ea387-112">int</span></span>  <br/> |<span data-ttu-id="ea387-113">首選</span><span class="sxs-lookup"><span data-stu-id="ea387-113">Primary</span></span>  <br/> |<span data-ttu-id="ea387-114">識別使用者網站的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="ea387-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="ea387-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="ea387-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="ea387-116">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="ea387-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="ea387-117">唯一</span><span class="sxs-lookup"><span data-stu-id="ea387-117">Unique</span></span>  <br/> |<span data-ttu-id="ea387-118">使用者網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="ea387-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="ea387-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="ea387-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="ea387-120">int</span><span class="sxs-lookup"><span data-stu-id="ea387-120">int</span></span>  <br/> |<span data-ttu-id="ea387-121">外</span><span class="sxs-lookup"><span data-stu-id="ea387-121">Foreign</span></span>  <br/> |<span data-ttu-id="ea387-122">從[Region 資料表](region.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="ea387-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

