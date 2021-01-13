---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含後續 Active Directory 同步步驟尚未處理的 Active Directory 網域服務變更。
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821383"
---
# <a name="tbladupdates"></a><span data-ttu-id="02315-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="02315-103">tblADUpdates</span></span>
 
<span data-ttu-id="02315-104">tblADUpdates 包含後續 Active Directory 同步步驟尚未處理的 Active Directory 網域服務變更。</span><span class="sxs-lookup"><span data-stu-id="02315-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="02315-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="02315-105">**Columns**</span></span>

|<span data-ttu-id="02315-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="02315-106">**Column**</span></span>|<span data-ttu-id="02315-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="02315-107">**Type**</span></span>|<span data-ttu-id="02315-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="02315-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="02315-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="02315-109">prinGuid</span></span>  <br/> |<span data-ttu-id="02315-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="02315-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="02315-111">已變更之物件的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="02315-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="02315-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="02315-112">prinADPath</span></span>  <br/> |<span data-ttu-id="02315-113">Nvarchar (384) ，非 null</span><span class="sxs-lookup"><span data-stu-id="02315-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="02315-114">物件的辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="02315-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="02315-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="02315-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="02315-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="02315-116">bit, not null</span></span>  <br/> |<span data-ttu-id="02315-117">True 是表示如果物件的至少一個屬性已變更。</span><span class="sxs-lookup"><span data-stu-id="02315-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="02315-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="02315-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="02315-119">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="02315-119">bit, not null</span></span>  <br/> |<span data-ttu-id="02315-120">True 是表示如果成員資格變更。</span><span class="sxs-lookup"><span data-stu-id="02315-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="02315-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="02315-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="02315-122">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="02315-122">bit, not null</span></span>  <br/> |<span data-ttu-id="02315-123">不會使用。</span><span class="sxs-lookup"><span data-stu-id="02315-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="02315-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="02315-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="02315-125">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="02315-125">bit, not null</span></span>  <br/> |<span data-ttu-id="02315-126">True 是表示如果物件已刪除。</span><span class="sxs-lookup"><span data-stu-id="02315-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="02315-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="02315-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="02315-128">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="02315-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="02315-129">插入列時的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="02315-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

