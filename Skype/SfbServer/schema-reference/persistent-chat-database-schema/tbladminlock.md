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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含執行某些系統管理員命令所需的管理員鎖。
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192756"
---
# <a name="tbladminlock"></a><span data-ttu-id="b61a4-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="b61a4-103">tblAdminLock</span></span>
 
<span data-ttu-id="b61a4-104">tblAdminLock 包含執行某些系統管理員命令所需的管理員鎖。</span><span class="sxs-lookup"><span data-stu-id="b61a4-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="b61a4-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="b61a4-105">**Columns**</span></span>

|<span data-ttu-id="b61a4-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b61a4-106">**Column**</span></span>|<span data-ttu-id="b61a4-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="b61a4-107">**Type**</span></span>|<span data-ttu-id="b61a4-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="b61a4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b61a4-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="b61a4-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="b61a4-110">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="b61a4-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="b61a4-111">[鎖定到期日] 和 [時間]。</span><span class="sxs-lookup"><span data-stu-id="b61a4-111">Lock expiration date and time.</span></span> <span data-ttu-id="b61a4-112">擁有者可以定期延伸此值。</span><span class="sxs-lookup"><span data-stu-id="b61a4-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="b61a4-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="b61a4-113">lockServerID</span></span>  <br/> |<span data-ttu-id="b61a4-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="b61a4-114">int, not null</span></span>  <br/> |<span data-ttu-id="b61a4-115">擁有鎖定的伺服器 ID。</span><span class="sxs-lookup"><span data-stu-id="b61a4-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="b61a4-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="b61a4-116">lockActorID</span></span>  <br/> |<span data-ttu-id="b61a4-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="b61a4-117">int, not null</span></span>  <br/> |<span data-ttu-id="b61a4-118">擁有鎖定之主體的 ID。</span><span class="sxs-lookup"><span data-stu-id="b61a4-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

