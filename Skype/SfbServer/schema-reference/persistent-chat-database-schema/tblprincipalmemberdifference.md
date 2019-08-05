---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含尚未由後續 Active Directory 網域服務同步處理步驟處理的群組成員資格變更 (新增和移除的成員)。
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192722"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="582af-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="582af-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="582af-104">tblPrincipalMemberDifference 包含尚未由後續 Active Directory 網域服務同步處理步驟處理的群組成員資格變更 (新增和移除的成員)。</span><span class="sxs-lookup"><span data-stu-id="582af-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="582af-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="582af-105">**Columns**</span></span>

|<span data-ttu-id="582af-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="582af-106">**Column**</span></span>|<span data-ttu-id="582af-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="582af-107">**Type**</span></span>|<span data-ttu-id="582af-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="582af-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="582af-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="582af-109">prinGuid</span></span>  <br/> |<span data-ttu-id="582af-110">GUID, 不是 null</span><span class="sxs-lookup"><span data-stu-id="582af-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="582af-111">已變更之群組的主要 GUID。</span><span class="sxs-lookup"><span data-stu-id="582af-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="582af-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="582af-112">memberADPath</span></span>  <br/> |<span data-ttu-id="582af-113">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="582af-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="582af-114">成員的判別名。</span><span class="sxs-lookup"><span data-stu-id="582af-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="582af-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="582af-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="582af-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="582af-116">bit, not null</span></span>  <br/> |<span data-ttu-id="582af-117">如果成員已新增, 則為 False。</span><span class="sxs-lookup"><span data-stu-id="582af-117">False if the member was added.</span></span> <span data-ttu-id="582af-118">如果成員已移除, 則為 True。</span><span class="sxs-lookup"><span data-stu-id="582af-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="582af-119">**快速鍵**</span><span class="sxs-lookup"><span data-stu-id="582af-119">**Key**</span></span>

|<span data-ttu-id="582af-120">**左欄**</span><span class="sxs-lookup"><span data-stu-id="582af-120">**Column**</span></span>|<span data-ttu-id="582af-121">**說明**</span><span class="sxs-lookup"><span data-stu-id="582af-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="582af-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="582af-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="582af-123">主鍵。</span><span class="sxs-lookup"><span data-stu-id="582af-123">Primary key.</span></span>  <br/> |
   

