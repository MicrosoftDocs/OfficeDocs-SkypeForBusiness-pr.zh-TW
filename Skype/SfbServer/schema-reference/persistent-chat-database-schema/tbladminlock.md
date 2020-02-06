---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含執行某些系統管理員命令所需的管理員鎖。
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814691"
---
# <a name="tbladminlock"></a><span data-ttu-id="71f21-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="71f21-103">tblAdminLock</span></span>
 
<span data-ttu-id="71f21-104">tblAdminLock 包含執行某些系統管理員命令所需的管理員鎖。</span><span class="sxs-lookup"><span data-stu-id="71f21-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="71f21-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="71f21-105">**Columns**</span></span>

|<span data-ttu-id="71f21-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="71f21-106">**Column**</span></span>|<span data-ttu-id="71f21-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="71f21-107">**Type**</span></span>|<span data-ttu-id="71f21-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="71f21-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71f21-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="71f21-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="71f21-110">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="71f21-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="71f21-111">[鎖定到期日] 和 [時間]。</span><span class="sxs-lookup"><span data-stu-id="71f21-111">Lock expiration date and time.</span></span> <span data-ttu-id="71f21-112">擁有者可以定期延伸此值。</span><span class="sxs-lookup"><span data-stu-id="71f21-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="71f21-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="71f21-113">lockServerID</span></span>  <br/> |<span data-ttu-id="71f21-114">int，not null</span><span class="sxs-lookup"><span data-stu-id="71f21-114">int, not null</span></span>  <br/> |<span data-ttu-id="71f21-115">擁有鎖定的伺服器 ID。</span><span class="sxs-lookup"><span data-stu-id="71f21-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="71f21-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="71f21-116">lockActorID</span></span>  <br/> |<span data-ttu-id="71f21-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="71f21-117">int, not null</span></span>  <br/> |<span data-ttu-id="71f21-118">擁有鎖定之主體的 ID。</span><span class="sxs-lookup"><span data-stu-id="71f21-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

