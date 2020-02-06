---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含 Active Directory 網域服務的變更，這些變更尚未經過後續的 Active Directory 同步處理步驟使用。
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814681"
---
# <a name="tbladupdates"></a><span data-ttu-id="3195e-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="3195e-103">tblADUpdates</span></span>
 
<span data-ttu-id="3195e-104">tblADUpdates 包含 Active Directory 網域服務的變更，這些變更尚未經過後續的 Active Directory 同步處理步驟使用。</span><span class="sxs-lookup"><span data-stu-id="3195e-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="3195e-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="3195e-105">**Columns**</span></span>

|<span data-ttu-id="3195e-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="3195e-106">**Column**</span></span>|<span data-ttu-id="3195e-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="3195e-107">**Type**</span></span>|<span data-ttu-id="3195e-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="3195e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3195e-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="3195e-109">prinGuid</span></span>  <br/> |<span data-ttu-id="3195e-110">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="3195e-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="3195e-111">已變更之物件的主要 GUID。</span><span class="sxs-lookup"><span data-stu-id="3195e-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="3195e-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="3195e-112">prinADPath</span></span>  <br/> |<span data-ttu-id="3195e-113">Nvarchar （384），not null</span><span class="sxs-lookup"><span data-stu-id="3195e-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="3195e-114">物件的判別名。</span><span class="sxs-lookup"><span data-stu-id="3195e-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="3195e-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="3195e-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="3195e-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="3195e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="3195e-117">如果物件至少有一個屬性已變更，則為 True。</span><span class="sxs-lookup"><span data-stu-id="3195e-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="3195e-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="3195e-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="3195e-119">bit、not null</span><span class="sxs-lookup"><span data-stu-id="3195e-119">bit, not null</span></span>  <br/> |<span data-ttu-id="3195e-120">如果成員資格變更，則為 True。</span><span class="sxs-lookup"><span data-stu-id="3195e-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="3195e-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="3195e-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="3195e-122">bit、not null</span><span class="sxs-lookup"><span data-stu-id="3195e-122">bit, not null</span></span>  <br/> |<span data-ttu-id="3195e-123">不使用。</span><span class="sxs-lookup"><span data-stu-id="3195e-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="3195e-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="3195e-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="3195e-125">bit、not null</span><span class="sxs-lookup"><span data-stu-id="3195e-125">bit, not null</span></span>  <br/> |<span data-ttu-id="3195e-126">如果已刪除物件，則為 True。</span><span class="sxs-lookup"><span data-stu-id="3195e-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="3195e-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="3195e-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="3195e-128">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="3195e-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="3195e-129">插入列的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="3195e-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

