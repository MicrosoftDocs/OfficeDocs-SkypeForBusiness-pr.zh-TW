---
title: 商務用 Skype Server 中的位置表格2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每筆記錄代表緊急通話中參照的一個位置，例如 E9-1-1 通話。
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821513"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="09c5f-103">商務用 Skype Server 中的位置表格2015</span><span class="sxs-lookup"><span data-stu-id="09c5f-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="09c5f-104">每筆記錄代表緊急通話中參照的一個位置，例如 E9-1-1 通話。</span><span class="sxs-lookup"><span data-stu-id="09c5f-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="09c5f-105">**欄**</span><span class="sxs-lookup"><span data-stu-id="09c5f-105">**Column**</span></span>|<span data-ttu-id="09c5f-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="09c5f-106">**Data Type**</span></span>|<span data-ttu-id="09c5f-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="09c5f-107">**Key/Index**</span></span>|<span data-ttu-id="09c5f-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="09c5f-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09c5f-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="09c5f-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="09c5f-110">datetime</span><span class="sxs-lookup"><span data-stu-id="09c5f-110">datetime</span></span>  <br/> |<span data-ttu-id="09c5f-111">主要，外部</span><span class="sxs-lookup"><span data-stu-id="09c5f-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="09c5f-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="09c5f-112">Time of session request.</span></span> <span data-ttu-id="09c5f-113">其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="09c5f-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="09c5f-114">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。</span><span class="sxs-lookup"><span data-stu-id="09c5f-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="09c5f-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="09c5f-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="09c5f-116">int</span><span class="sxs-lookup"><span data-stu-id="09c5f-116">int</span></span>  <br/> |<span data-ttu-id="09c5f-117">主要，外部</span><span class="sxs-lookup"><span data-stu-id="09c5f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="09c5f-118">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="09c5f-118">ID number to identify the session.</span></span> <span data-ttu-id="09c5f-119">會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="09c5f-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="09c5f-120">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。</span><span class="sxs-lookup"><span data-stu-id="09c5f-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="09c5f-121">**位置**</span><span class="sxs-lookup"><span data-stu-id="09c5f-121">**Location**</span></span> <br/> |<span data-ttu-id="09c5f-122">Nvarchar (max) </span><span class="sxs-lookup"><span data-stu-id="09c5f-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="09c5f-123">緊急電話的位置。</span><span class="sxs-lookup"><span data-stu-id="09c5f-123">Location of emergency call.</span></span>  <br/> |
   

