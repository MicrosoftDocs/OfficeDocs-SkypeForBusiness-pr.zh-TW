---
title: MediationServers 表格
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
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 資料表是支援資料表。 每個記錄都儲存在資料庫中有記錄的通話中所涉及之一個中繼伺服器的相關資訊。
ms.openlocfilehash: 74c1095044bd9bb7183202d115236eba863c62da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815021"
---
# <a name="mediationservers-table"></a><span data-ttu-id="9f618-104">MediationServers 表格</span><span class="sxs-lookup"><span data-stu-id="9f618-104">MediationServers table</span></span>
 
<span data-ttu-id="9f618-105">MediationServers 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="9f618-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="9f618-106">每個記錄都儲存在資料庫中有記錄的通話中所涉及之一個中繼伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9f618-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="9f618-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="9f618-107">**Column**</span></span>|<span data-ttu-id="9f618-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="9f618-108">**Data Type**</span></span>|<span data-ttu-id="9f618-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="9f618-109">**Key/Index**</span></span>|<span data-ttu-id="9f618-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="9f618-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9f618-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="9f618-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="9f618-112">int</span><span class="sxs-lookup"><span data-stu-id="9f618-112">int</span></span>  <br/> |<span data-ttu-id="9f618-113">首選</span><span class="sxs-lookup"><span data-stu-id="9f618-113">Primary</span></span>  <br/> |<span data-ttu-id="9f618-114">標識此中繼伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="9f618-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="9f618-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="9f618-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="9f618-116">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="9f618-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="9f618-117">中繼伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="9f618-117">Mediation Server name.</span></span>  <br/> |
   

