---
title: 商務用 Skype Server 2015 中的 [閘道] 表格
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: '[閘道] 資料表是支援表格。 每個記錄都儲存一個閘道的相關資訊，這些資訊包含在資料庫中有記錄的公用交換電話網絡（PSTN）通話中。'
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815161"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="79cf2-104">商務用 Skype Server 2015 中的 [閘道] 表格</span><span class="sxs-lookup"><span data-stu-id="79cf2-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="79cf2-105">[閘道] 資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="79cf2-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="79cf2-106">每個記錄都儲存一個閘道的相關資訊，這些資訊包含在資料庫中有記錄的公用交換電話網絡（PSTN）通話中。</span><span class="sxs-lookup"><span data-stu-id="79cf2-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="79cf2-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="79cf2-107">**Column**</span></span>|<span data-ttu-id="79cf2-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="79cf2-108">**Data Type**</span></span>|<span data-ttu-id="79cf2-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="79cf2-109">**Key/Index**</span></span>|<span data-ttu-id="79cf2-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="79cf2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="79cf2-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="79cf2-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="79cf2-112">int</span><span class="sxs-lookup"><span data-stu-id="79cf2-112">int</span></span>  <br/> |<span data-ttu-id="79cf2-113">首選</span><span class="sxs-lookup"><span data-stu-id="79cf2-113">Primary</span></span>  <br/> |<span data-ttu-id="79cf2-114">識別此閘道的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="79cf2-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="79cf2-115">**關**</span><span class="sxs-lookup"><span data-stu-id="79cf2-115">**Gateway**</span></span> <br/> |<span data-ttu-id="79cf2-116">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="79cf2-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="79cf2-117">閘道名稱。</span><span class="sxs-lookup"><span data-stu-id="79cf2-117">Gateway name.</span></span>  <br/> |
   

