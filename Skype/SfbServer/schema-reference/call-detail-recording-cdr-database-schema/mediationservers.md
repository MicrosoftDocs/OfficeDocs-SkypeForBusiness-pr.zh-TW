---
title: MediationServers 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 表格是支援的表格。 每筆記錄都儲存在具有資料庫中記錄之通話所涉及的一個轉送伺服器的相關資訊。
ms.openlocfilehash: e498409087ee5cf41b32b29ec5f66a147290e1ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814763"
---
# <a name="mediationservers-table"></a><span data-ttu-id="bd9bc-104">MediationServers 表格</span><span class="sxs-lookup"><span data-stu-id="bd9bc-104">MediationServers table</span></span>
 
<span data-ttu-id="bd9bc-105">MediationServers 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="bd9bc-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="bd9bc-106">每筆記錄都儲存在具有資料庫中記錄之通話所涉及的一個轉送伺服器的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bd9bc-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="bd9bc-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="bd9bc-107">**Column**</span></span>|<span data-ttu-id="bd9bc-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bd9bc-108">**Data Type**</span></span>|<span data-ttu-id="bd9bc-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="bd9bc-109">**Key/Index**</span></span>|<span data-ttu-id="bd9bc-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="bd9bc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd9bc-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="bd9bc-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="bd9bc-112">int</span><span class="sxs-lookup"><span data-stu-id="bd9bc-112">int</span></span>  <br/> |<span data-ttu-id="bd9bc-113">主要</span><span class="sxs-lookup"><span data-stu-id="bd9bc-113">Primary</span></span>  <br/> |<span data-ttu-id="bd9bc-114">用於識別此轉送伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="bd9bc-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="bd9bc-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="bd9bc-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="bd9bc-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="bd9bc-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="bd9bc-117">轉送伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="bd9bc-117">Mediation Server name.</span></span>  <br/> |
   

