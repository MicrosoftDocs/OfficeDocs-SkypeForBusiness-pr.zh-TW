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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含尚未由後續 Active Directory 網域服務同步處理步驟處理的群組成員資格變更（新增和移除的成員）。
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814071"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="c1dfc-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="c1dfc-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="c1dfc-104">tblPrincipalMemberDifference 包含尚未由後續 Active Directory 網域服務同步處理步驟處理的群組成員資格變更（新增和移除的成員）。</span><span class="sxs-lookup"><span data-stu-id="c1dfc-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="c1dfc-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="c1dfc-105">**Columns**</span></span>

|<span data-ttu-id="c1dfc-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c1dfc-106">**Column**</span></span>|<span data-ttu-id="c1dfc-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="c1dfc-107">**Type**</span></span>|<span data-ttu-id="c1dfc-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="c1dfc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c1dfc-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c1dfc-109">prinGuid</span></span>  <br/> |<span data-ttu-id="c1dfc-110">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="c1dfc-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="c1dfc-111">已變更之群組的主要 GUID。</span><span class="sxs-lookup"><span data-stu-id="c1dfc-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="c1dfc-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="c1dfc-112">memberADPath</span></span>  <br/> |<span data-ttu-id="c1dfc-113">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="c1dfc-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="c1dfc-114">成員的判別名。</span><span class="sxs-lookup"><span data-stu-id="c1dfc-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="c1dfc-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="c1dfc-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="c1dfc-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="c1dfc-116">bit, not null</span></span>  <br/> |<span data-ttu-id="c1dfc-117">如果成員已新增，則為 False。</span><span class="sxs-lookup"><span data-stu-id="c1dfc-117">False if the member was added.</span></span> <span data-ttu-id="c1dfc-118">如果成員已移除，則為 True。</span><span class="sxs-lookup"><span data-stu-id="c1dfc-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="c1dfc-119">**機碼**</span><span class="sxs-lookup"><span data-stu-id="c1dfc-119">**Key**</span></span>

|<span data-ttu-id="c1dfc-120">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c1dfc-120">**Column**</span></span>|<span data-ttu-id="c1dfc-121">**說明**</span><span class="sxs-lookup"><span data-stu-id="c1dfc-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1dfc-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="c1dfc-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="c1dfc-123">主鍵。</span><span class="sxs-lookup"><span data-stu-id="c1dfc-123">Primary key.</span></span>  <br/> |
   

