---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含無法讀取的隸屬關係（通常是由於 Active Directory 網域服務存取錯誤）。
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812011"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="b10c8-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="b10c8-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="b10c8-104">tblSkippedAffiliations 包含無法讀取的隸屬關係（通常是由於 Active Directory 網域服務存取錯誤）。</span><span class="sxs-lookup"><span data-stu-id="b10c8-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="b10c8-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="b10c8-105">**Columns**</span></span>

|<span data-ttu-id="b10c8-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b10c8-106">**Column**</span></span>|<span data-ttu-id="b10c8-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="b10c8-107">**Type**</span></span>|<span data-ttu-id="b10c8-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="b10c8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b10c8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b10c8-109">prinID</span></span>  <br/> |<span data-ttu-id="b10c8-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="b10c8-110">int, not null</span></span>  <br/> |<span data-ttu-id="b10c8-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="b10c8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b10c8-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="b10c8-112">affDescription</span></span>  <br/> |<span data-ttu-id="b10c8-113">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="b10c8-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b10c8-114">標識隸屬關係的字串。</span><span class="sxs-lookup"><span data-stu-id="b10c8-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="b10c8-115">格式為： guid： _{0}_ uri： _{1}_> 識別碼：_{2}_</span><span class="sxs-lookup"><span data-stu-id="b10c8-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="b10c8-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="b10c8-116">updatedBy</span></span>  <br/> |<span data-ttu-id="b10c8-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="b10c8-117">int, not null</span></span>  <br/> |<span data-ttu-id="b10c8-118">更新此列之主體的 ID。</span><span class="sxs-lookup"><span data-stu-id="b10c8-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="b10c8-119">因為 Active Directory 同步處理是這些專案的唯一來源，所以它永遠是1（系統使用者）。</span><span class="sxs-lookup"><span data-stu-id="b10c8-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="b10c8-120">**鍵**</span><span class="sxs-lookup"><span data-stu-id="b10c8-120">**Keys**</span></span>

|<span data-ttu-id="b10c8-121">**欄（s）**</span><span class="sxs-lookup"><span data-stu-id="b10c8-121">**Column(s)**</span></span>|<span data-ttu-id="b10c8-122">**說明**</span><span class="sxs-lookup"><span data-stu-id="b10c8-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b10c8-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="b10c8-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="b10c8-124">主鍵。</span><span class="sxs-lookup"><span data-stu-id="b10c8-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b10c8-125">prinID</span><span class="sxs-lookup"><span data-stu-id="b10c8-125">prinID</span></span>  <br/> |<span data-ttu-id="b10c8-126">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="b10c8-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

