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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: EdgeServers 資料表是支援資料表。 每個記錄都儲存在資料庫中有記錄的通話中所涉及之一台邊緣伺服器的相關資訊。
ms.openlocfilehash: 7a1621e3416b6cff48c430e7bc2e45057ecb3e14
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815261"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d472f-104">商務用 Skype Server 2015 中的 EdgeServers 表格</span><span class="sxs-lookup"><span data-stu-id="d472f-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d472f-105">EdgeServers 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="d472f-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="d472f-106">每個記錄都儲存在資料庫中有記錄的通話中所涉及之一台邊緣伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d472f-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="d472f-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="d472f-107">**Column**</span></span>|<span data-ttu-id="d472f-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="d472f-108">**Data Type**</span></span>|<span data-ttu-id="d472f-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="d472f-109">**Key/Index**</span></span>|<span data-ttu-id="d472f-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d472f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d472f-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="d472f-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="d472f-112">int</span><span class="sxs-lookup"><span data-stu-id="d472f-112">int</span></span>  <br/> |<span data-ttu-id="d472f-113">首選</span><span class="sxs-lookup"><span data-stu-id="d472f-113">Primary</span></span>  <br/> |<span data-ttu-id="d472f-114">標識此 Edge 伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="d472f-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="d472f-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="d472f-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="d472f-116">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d472f-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="d472f-117">Edge 伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="d472f-117">Edge Server name.</span></span>  <br/> |
   

