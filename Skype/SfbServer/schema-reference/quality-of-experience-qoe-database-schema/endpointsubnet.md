---
title: EndpointSubnet 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet 資料表是支援資料表。 每個記錄代表一個從端點捕獲的子網。
ms.openlocfilehash: b8a8e62178919da72082f99acad7798f3935a5ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192674"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="19540-104">EndpointSubnet 表格</span><span class="sxs-lookup"><span data-stu-id="19540-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="19540-105">EndpointSubnet 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="19540-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="19540-106">每個記錄代表一個從端點捕獲的子網。</span><span class="sxs-lookup"><span data-stu-id="19540-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="19540-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="19540-107">**Column**</span></span>|<span data-ttu-id="19540-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="19540-108">**Data Type**</span></span>|<span data-ttu-id="19540-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="19540-109">**Key/Index**</span></span>|<span data-ttu-id="19540-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="19540-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="19540-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="19540-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="19540-112">int</span><span class="sxs-lookup"><span data-stu-id="19540-112">int</span></span>  <br/> |<span data-ttu-id="19540-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="19540-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="19540-114">子網的整數表示。</span><span class="sxs-lookup"><span data-stu-id="19540-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="19540-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="19540-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="19540-116">datetime</span><span class="sxs-lookup"><span data-stu-id="19540-116">datetime</span></span>  <br/> ||<span data-ttu-id="19540-117">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="19540-117">For internal use only.</span></span>  <br/> |
   

