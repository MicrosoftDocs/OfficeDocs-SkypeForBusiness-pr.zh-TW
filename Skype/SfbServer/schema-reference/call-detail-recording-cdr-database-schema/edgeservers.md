---
title: 商務用 Skype Server 2015 中的 EdgeServers 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 資料表是支援資料表。 每個記錄都儲存在資料庫中有記錄的通話中所涉及之一台邊緣伺服器的相關資訊。
ms.openlocfilehash: a78acd3b6297bbef3348ef87047c8cb7f0893231
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192870"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="25b46-104">商務用 Skype Server 2015 中的 EdgeServers 表格</span><span class="sxs-lookup"><span data-stu-id="25b46-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="25b46-105">EdgeServers 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="25b46-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="25b46-106">每個記錄都儲存在資料庫中有記錄的通話中所涉及之一台邊緣伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="25b46-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="25b46-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="25b46-107">**Column**</span></span>|<span data-ttu-id="25b46-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="25b46-108">**Data Type**</span></span>|<span data-ttu-id="25b46-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="25b46-109">**Key/Index**</span></span>|<span data-ttu-id="25b46-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="25b46-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="25b46-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="25b46-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="25b46-112">int</span><span class="sxs-lookup"><span data-stu-id="25b46-112">int</span></span>  <br/> |<span data-ttu-id="25b46-113">首選</span><span class="sxs-lookup"><span data-stu-id="25b46-113">Primary</span></span>  <br/> |<span data-ttu-id="25b46-114">標識此 Edge 伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="25b46-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="25b46-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="25b46-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="25b46-116">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="25b46-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="25b46-117">Edge 伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="25b46-117">Edge Server name.</span></span>  <br/> |
   

