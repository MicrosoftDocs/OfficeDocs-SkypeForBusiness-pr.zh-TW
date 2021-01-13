---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含無法讀取的隸屬 (，通常是因為 Active Directory 網域服務存取錯誤) 。
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831423"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="e7deb-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="e7deb-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="e7deb-104">tblSkippedAffiliations 包含無法讀取的隸屬 (，通常是因為 Active Directory 網域服務存取錯誤) 。</span><span class="sxs-lookup"><span data-stu-id="e7deb-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="e7deb-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e7deb-105">**Columns**</span></span>

|<span data-ttu-id="e7deb-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="e7deb-106">**Column**</span></span>|<span data-ttu-id="e7deb-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="e7deb-107">**Type**</span></span>|<span data-ttu-id="e7deb-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="e7deb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e7deb-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="e7deb-109">prinID</span></span>  <br/> |<span data-ttu-id="e7deb-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e7deb-110">int, not null</span></span>  <br/> |<span data-ttu-id="e7deb-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="e7deb-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e7deb-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="e7deb-112">affDescription</span></span>  <br/> |<span data-ttu-id="e7deb-113">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="e7deb-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e7deb-114">識別關係的字串。</span><span class="sxs-lookup"><span data-stu-id="e7deb-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="e7deb-115">格式為： guid：  _{0}_ uri： _{1}_> 識別碼：  _{2}_</span><span class="sxs-lookup"><span data-stu-id="e7deb-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="e7deb-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e7deb-116">updatedBy</span></span>  <br/> |<span data-ttu-id="e7deb-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e7deb-117">int, not null</span></span>  <br/> |<span data-ttu-id="e7deb-p101">上次更新此列之主體的識別碼。其一律為 1 (系統使用者) 因為 Active Directory 同步處理是這些項目的唯一來源。</span><span class="sxs-lookup"><span data-stu-id="e7deb-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="e7deb-120">**Keys**</span><span class="sxs-lookup"><span data-stu-id="e7deb-120">**Keys**</span></span>

|<span data-ttu-id="e7deb-121">**欄 (s)**</span><span class="sxs-lookup"><span data-stu-id="e7deb-121">**Column(s)**</span></span>|<span data-ttu-id="e7deb-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="e7deb-122">**Description**</span></span>|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |<span data-ttu-id="e7deb-123">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e7deb-123">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e7deb-124">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="e7deb-124">prinID</span></span>  <br/> |<span data-ttu-id="e7deb-125">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e7deb-125">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

