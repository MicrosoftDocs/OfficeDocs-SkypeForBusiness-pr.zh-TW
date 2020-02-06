---
title: Subnet 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 子網資料表是支援表格。 每個記錄代表 [網路設定] 中定義的一個子網。
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805201"
---
# <a name="subnet-table"></a><span data-ttu-id="5d71a-104">Subnet 表格</span><span class="sxs-lookup"><span data-stu-id="5d71a-104">Subnet table</span></span>
 
<span data-ttu-id="5d71a-105">子網資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="5d71a-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="5d71a-106">每個記錄代表 [網路設定] 中定義的一個子網。</span><span class="sxs-lookup"><span data-stu-id="5d71a-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="5d71a-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="5d71a-107">**Column**</span></span>|<span data-ttu-id="5d71a-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="5d71a-108">**Data Type**</span></span>|<span data-ttu-id="5d71a-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="5d71a-109">**Key/Index**</span></span>|<span data-ttu-id="5d71a-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="5d71a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5d71a-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="5d71a-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="5d71a-112">int</span><span class="sxs-lookup"><span data-stu-id="5d71a-112">int</span></span>  <br/> |<span data-ttu-id="5d71a-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="5d71a-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5d71a-114">子網 IP 的整數表示。</span><span class="sxs-lookup"><span data-stu-id="5d71a-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="5d71a-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="5d71a-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="5d71a-116">int</span><span class="sxs-lookup"><span data-stu-id="5d71a-116">int</span></span>  <br/> ||<span data-ttu-id="5d71a-117">子網路遮罩。</span><span class="sxs-lookup"><span data-stu-id="5d71a-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="5d71a-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="5d71a-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="5d71a-119">int</span><span class="sxs-lookup"><span data-stu-id="5d71a-119">int</span></span>  <br/> |<span data-ttu-id="5d71a-120">外</span><span class="sxs-lookup"><span data-stu-id="5d71a-120">Foreign</span></span>  <br/> |<span data-ttu-id="5d71a-121">從[UserSite 資料表](usersite.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="5d71a-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="5d71a-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="5d71a-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="5d71a-123">Nvarchar （512）</span><span class="sxs-lookup"><span data-stu-id="5d71a-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="5d71a-124">子網的描述。</span><span class="sxs-lookup"><span data-stu-id="5d71a-124">The description for the subnet.</span></span>  <br/> |
   

