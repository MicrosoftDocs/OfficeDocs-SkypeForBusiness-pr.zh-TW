---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含目前的輕量型目錄存取通訊協定 (LDAP) 同步處理 Cookie。
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814753"
---
# <a name="tbladcookie"></a><span data-ttu-id="0bcbb-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="0bcbb-103">tblADCookie</span></span>
 
<span data-ttu-id="0bcbb-104">tblADCookie 包含目前的輕量型目錄存取通訊協定 (LDAP) 同步處理 Cookie。</span><span class="sxs-lookup"><span data-stu-id="0bcbb-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="0bcbb-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="0bcbb-105">**Columns**</span></span>

|<span data-ttu-id="0bcbb-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="0bcbb-106">**Column**</span></span>|<span data-ttu-id="0bcbb-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="0bcbb-107">**Type**</span></span>|<span data-ttu-id="0bcbb-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="0bcbb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0bcbb-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0bcbb-109">prinGuid</span></span>  <br/> |<span data-ttu-id="0bcbb-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="0bcbb-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="0bcbb-111">受監控網域的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="0bcbb-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="0bcbb-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="0bcbb-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="0bcbb-113">nvarchar(255)</span><span class="sxs-lookup"><span data-stu-id="0bcbb-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="0bcbb-114">用於 Active Directory 網域服務同步處理的目前網域控制站 (FQDN) 的完整功能變數名稱。具有資訊性值。</span><span class="sxs-lookup"><span data-stu-id="0bcbb-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="0bcbb-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="0bcbb-115">adcContent</span></span>  <br/> |<span data-ttu-id="0bcbb-116">影像 (二進位)</span><span class="sxs-lookup"><span data-stu-id="0bcbb-116">image (binary)</span></span>  <br/> |<span data-ttu-id="0bcbb-117">Active Directory 同步處理 Cookie。</span><span class="sxs-lookup"><span data-stu-id="0bcbb-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="0bcbb-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="0bcbb-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="0bcbb-119">datetime</span><span class="sxs-lookup"><span data-stu-id="0bcbb-119">datetime</span></span>  <br/> |<span data-ttu-id="0bcbb-120">含有列更新時間的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="0bcbb-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="0bcbb-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="0bcbb-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="0bcbb-122">datetime</span><span class="sxs-lookup"><span data-stu-id="0bcbb-122">datetime</span></span>  <br/> |<span data-ttu-id="0bcbb-p101">鎖定列以進行變更的時間。這是軟體聯鎖機制的一部分，可確保一次僅有一個聊天服務會進行 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="0bcbb-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="0bcbb-125">**Keys**</span><span class="sxs-lookup"><span data-stu-id="0bcbb-125">**Keys**</span></span>

|<span data-ttu-id="0bcbb-126">**欄 (s)**</span><span class="sxs-lookup"><span data-stu-id="0bcbb-126">**Column(s)**</span></span>|<span data-ttu-id="0bcbb-127">**描述**</span><span class="sxs-lookup"><span data-stu-id="0bcbb-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0bcbb-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0bcbb-128">prinGuid</span></span>  <br/> |<span data-ttu-id="0bcbb-129">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="0bcbb-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0bcbb-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0bcbb-130">prinGuid</span></span>  <br/> |<span data-ttu-id="0bcbb-131">在 Principal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="0bcbb-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

