---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含目前的輕型目錄存取通訊協定 (LDAP) 同步處理 cookie。
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192759"
---
# <a name="tbladcookie"></a><span data-ttu-id="6bac2-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="6bac2-103">tblADCookie</span></span>
 
<span data-ttu-id="6bac2-104">tblADCookie 包含目前的輕型目錄存取通訊協定 (LDAP) 同步處理 cookie。</span><span class="sxs-lookup"><span data-stu-id="6bac2-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="6bac2-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="6bac2-105">**Columns**</span></span>

|<span data-ttu-id="6bac2-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="6bac2-106">**Column**</span></span>|<span data-ttu-id="6bac2-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="6bac2-107">**Type**</span></span>|<span data-ttu-id="6bac2-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="6bac2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6bac2-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6bac2-109">prinGuid</span></span>  <br/> |<span data-ttu-id="6bac2-110">GUID, 不是 null</span><span class="sxs-lookup"><span data-stu-id="6bac2-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="6bac2-111">受監視之網域的主要 GUID。</span><span class="sxs-lookup"><span data-stu-id="6bac2-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="6bac2-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="6bac2-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="6bac2-113">Nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="6bac2-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="6bac2-114">用於 Active Directory 網域服務同步處理之目前網網域控制站的完整功能變數名稱 (FQDN)。有資訊值。</span><span class="sxs-lookup"><span data-stu-id="6bac2-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="6bac2-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="6bac2-115">adcContent</span></span>  <br/> |<span data-ttu-id="6bac2-116">image (二進位)</span><span class="sxs-lookup"><span data-stu-id="6bac2-116">image (binary)</span></span>  <br/> |<span data-ttu-id="6bac2-117">Active Directory 同步處理 cookie。</span><span class="sxs-lookup"><span data-stu-id="6bac2-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="6bac2-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="6bac2-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="6bac2-119">datetime</span><span class="sxs-lookup"><span data-stu-id="6bac2-119">datetime</span></span>  <br/> |<span data-ttu-id="6bac2-120">含有資料列更新時間的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="6bac2-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="6bac2-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="6bac2-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="6bac2-122">datetime</span><span class="sxs-lookup"><span data-stu-id="6bac2-122">datetime</span></span>  <br/> |<span data-ttu-id="6bac2-123">[時間], 直到列鎖定變更為止。</span><span class="sxs-lookup"><span data-stu-id="6bac2-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="6bac2-124">這是軟體互鎖機制的一部分, 可確保一次只有其中一個聊天服務進行 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="6bac2-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="6bac2-125">**鍵**</span><span class="sxs-lookup"><span data-stu-id="6bac2-125">**Keys**</span></span>

|<span data-ttu-id="6bac2-126">**欄 (s)**</span><span class="sxs-lookup"><span data-stu-id="6bac2-126">**Column(s)**</span></span>|<span data-ttu-id="6bac2-127">**說明**</span><span class="sxs-lookup"><span data-stu-id="6bac2-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6bac2-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6bac2-128">prinGuid</span></span>  <br/> |<span data-ttu-id="6bac2-129">主鍵。</span><span class="sxs-lookup"><span data-stu-id="6bac2-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6bac2-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="6bac2-130">prinGuid</span></span>  <br/> |<span data-ttu-id="6bac2-131">PrinGuid 表格中的 [查閱] 外鍵。</span><span class="sxs-lookup"><span data-stu-id="6bac2-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

