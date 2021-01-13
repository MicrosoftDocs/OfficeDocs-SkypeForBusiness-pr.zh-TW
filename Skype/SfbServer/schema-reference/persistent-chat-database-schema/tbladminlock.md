---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 表格包含執行某些系統管理員命令所需的系統管理員鎖定。
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809883"
---
# <a name="tbladminlock"></a><span data-ttu-id="0ce2f-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="0ce2f-103">tblAdminLock</span></span>
 
<span data-ttu-id="0ce2f-104">tblAdminLock 表格包含執行某些系統管理員命令所需的系統管理員鎖定。</span><span class="sxs-lookup"><span data-stu-id="0ce2f-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="0ce2f-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="0ce2f-105">**Columns**</span></span>

|<span data-ttu-id="0ce2f-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="0ce2f-106">**Column**</span></span>|<span data-ttu-id="0ce2f-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="0ce2f-107">**Type**</span></span>|<span data-ttu-id="0ce2f-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="0ce2f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0ce2f-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="0ce2f-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="0ce2f-110">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="0ce2f-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="0ce2f-p101">鎖定到期的日期和時間。擁有者可定期延長這個值。</span><span class="sxs-lookup"><span data-stu-id="0ce2f-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="0ce2f-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="0ce2f-113">lockServerID</span></span>  <br/> |<span data-ttu-id="0ce2f-114">int，非 null</span><span class="sxs-lookup"><span data-stu-id="0ce2f-114">int, not null</span></span>  <br/> |<span data-ttu-id="0ce2f-115">掌握鎖定之伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="0ce2f-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="0ce2f-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="0ce2f-116">lockActorID</span></span>  <br/> |<span data-ttu-id="0ce2f-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="0ce2f-117">int, not null</span></span>  <br/> |<span data-ttu-id="0ce2f-118">掌握鎖定之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="0ce2f-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

