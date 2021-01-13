---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含的群組成員資格變更 (新增及移除的成員，) 後來的 Active Directory 網域服務同步步驟尚未處理。
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809703"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="a7d2f-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="a7d2f-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="a7d2f-104">tblPrincipalMemberDifference 包含的群組成員資格變更 (新增及移除的成員，) 後來的 Active Directory 網域服務同步步驟尚未處理。</span><span class="sxs-lookup"><span data-stu-id="a7d2f-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="a7d2f-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="a7d2f-105">**Columns**</span></span>

|<span data-ttu-id="a7d2f-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="a7d2f-106">**Column**</span></span>|<span data-ttu-id="a7d2f-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="a7d2f-107">**Type**</span></span>|<span data-ttu-id="a7d2f-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="a7d2f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7d2f-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a7d2f-109">prinGuid</span></span>  <br/> |<span data-ttu-id="a7d2f-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="a7d2f-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a7d2f-111">已變更群組的主體 GUID。</span><span class="sxs-lookup"><span data-stu-id="a7d2f-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="a7d2f-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="a7d2f-112">memberADPath</span></span>  <br/> |<span data-ttu-id="a7d2f-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a7d2f-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="a7d2f-114">成員的辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="a7d2f-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="a7d2f-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="a7d2f-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="a7d2f-116">bit，非 null</span><span class="sxs-lookup"><span data-stu-id="a7d2f-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a7d2f-p101">False 表示已新增成員；True 表示已移除成員。</span><span class="sxs-lookup"><span data-stu-id="a7d2f-p101">False if the member was added. True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="a7d2f-119">**Key**</span><span class="sxs-lookup"><span data-stu-id="a7d2f-119">**Key**</span></span>

|<span data-ttu-id="a7d2f-120">**欄**</span><span class="sxs-lookup"><span data-stu-id="a7d2f-120">**Column**</span></span>|<span data-ttu-id="a7d2f-121">**描述**</span><span class="sxs-lookup"><span data-stu-id="a7d2f-121">**Description**</span></span>|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |<span data-ttu-id="a7d2f-122">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="a7d2f-122">Primary key.</span></span>  <br/> |
   

