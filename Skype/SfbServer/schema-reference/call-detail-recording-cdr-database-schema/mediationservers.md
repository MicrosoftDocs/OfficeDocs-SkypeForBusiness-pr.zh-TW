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
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 資料表是支援資料表。 每個記錄都儲存在資料庫中有記錄的通話中所涉及之一個中繼伺服器的相關資訊。
ms.openlocfilehash: a79c7c1d81f220e034e63263ef8dbf81a13d4024
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192821"
---
# <a name="mediationservers-table"></a><span data-ttu-id="182c2-104">MediationServers 表格</span><span class="sxs-lookup"><span data-stu-id="182c2-104">MediationServers table</span></span>
 
<span data-ttu-id="182c2-105">MediationServers 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="182c2-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="182c2-106">每個記錄都儲存在資料庫中有記錄的通話中所涉及之一個中繼伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="182c2-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="182c2-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="182c2-107">**Column**</span></span>|<span data-ttu-id="182c2-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="182c2-108">**Data Type**</span></span>|<span data-ttu-id="182c2-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="182c2-109">**Key/Index**</span></span>|<span data-ttu-id="182c2-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="182c2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="182c2-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="182c2-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="182c2-112">int</span><span class="sxs-lookup"><span data-stu-id="182c2-112">int</span></span>  <br/> |<span data-ttu-id="182c2-113">首選</span><span class="sxs-lookup"><span data-stu-id="182c2-113">Primary</span></span>  <br/> |<span data-ttu-id="182c2-114">標識此中繼伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="182c2-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="182c2-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="182c2-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="182c2-116">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="182c2-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="182c2-117">中繼伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="182c2-117">Mediation Server name.</span></span>  <br/> |
   

