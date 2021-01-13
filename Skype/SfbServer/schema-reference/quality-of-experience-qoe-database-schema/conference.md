---
title: 會議表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 會議表格是支援表格。 每筆記錄代表一部會議或點對點工作階段。
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802783"
---
# <a name="conference-table"></a><span data-ttu-id="d2660-104">會議表格</span><span class="sxs-lookup"><span data-stu-id="d2660-104">Conference table</span></span>
 
<span data-ttu-id="d2660-p102">會議表格是一種支援資料表，其中的每一項記錄都代表一個會議或對等工作階段。</span><span class="sxs-lookup"><span data-stu-id="d2660-p102">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="d2660-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="d2660-107">**Column**</span></span>|<span data-ttu-id="d2660-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="d2660-108">**Data Type**</span></span>|<span data-ttu-id="d2660-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="d2660-109">**Key/Index**</span></span>|<span data-ttu-id="d2660-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d2660-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d2660-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="d2660-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="d2660-112">int</span><span class="sxs-lookup"><span data-stu-id="d2660-112">int</span></span>  <br/> |<span data-ttu-id="d2660-113">主要</span><span class="sxs-lookup"><span data-stu-id="d2660-113">Primary</span></span>  <br/> |<span data-ttu-id="d2660-114">用於識別此會議記錄的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="d2660-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="d2660-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="d2660-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="d2660-116">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d2660-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d2660-117">unique</span><span class="sxs-lookup"><span data-stu-id="d2660-117">unique</span></span>  <br/> |<span data-ttu-id="d2660-118">會議 URI (若為會議)，或 DialogID (若為點對點工作階段)。</span><span class="sxs-lookup"><span data-stu-id="d2660-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="d2660-119">**校驗**</span><span class="sxs-lookup"><span data-stu-id="d2660-119">**Checksum**</span></span> <br/> |<span data-ttu-id="d2660-120">int</span><span class="sxs-lookup"><span data-stu-id="d2660-120">int</span></span>  <br/> |<span data-ttu-id="d2660-121">index</span><span class="sxs-lookup"><span data-stu-id="d2660-121">index</span></span>  <br/> |<span data-ttu-id="d2660-p103">會議 URI 的總和檢查碼。僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="d2660-p103">Checksum of the conference URI. This is used internally.</span></span>  <br/> |
|<span data-ttu-id="d2660-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d2660-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d2660-125">datetime</span><span class="sxs-lookup"><span data-stu-id="d2660-125">datetime</span></span>  <br/> ||<span data-ttu-id="d2660-126">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="d2660-126">For internal use only.</span></span>  <br/> |
   

