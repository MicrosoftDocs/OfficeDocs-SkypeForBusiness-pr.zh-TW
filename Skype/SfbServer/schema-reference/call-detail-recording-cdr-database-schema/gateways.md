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
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: '[閘道] 資料表是支援表格。 每個記錄都儲存一個閘道的相關資訊, 這些資訊包含在資料庫中有記錄的公用交換電話網絡 (PSTN) 通話中。'
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192850"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d6bdb-104">商務用 Skype Server 2015 中的 [閘道] 表格</span><span class="sxs-lookup"><span data-stu-id="d6bdb-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d6bdb-105">[閘道] 資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="d6bdb-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="d6bdb-106">每個記錄都儲存一個閘道的相關資訊, 這些資訊包含在資料庫中有記錄的公用交換電話網絡 (PSTN) 通話中。</span><span class="sxs-lookup"><span data-stu-id="d6bdb-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="d6bdb-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="d6bdb-107">**Column**</span></span>|<span data-ttu-id="d6bdb-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="d6bdb-108">**Data Type**</span></span>|<span data-ttu-id="d6bdb-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="d6bdb-109">**Key/Index**</span></span>|<span data-ttu-id="d6bdb-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d6bdb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d6bdb-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="d6bdb-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="d6bdb-112">int</span><span class="sxs-lookup"><span data-stu-id="d6bdb-112">int</span></span>  <br/> |<span data-ttu-id="d6bdb-113">首選</span><span class="sxs-lookup"><span data-stu-id="d6bdb-113">Primary</span></span>  <br/> |<span data-ttu-id="d6bdb-114">識別此閘道的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="d6bdb-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="d6bdb-115">**關**</span><span class="sxs-lookup"><span data-stu-id="d6bdb-115">**Gateway**</span></span> <br/> |<span data-ttu-id="d6bdb-116">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d6bdb-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="d6bdb-117">閘道名稱。</span><span class="sxs-lookup"><span data-stu-id="d6bdb-117">Gateway name.</span></span>  <br/> |
   

