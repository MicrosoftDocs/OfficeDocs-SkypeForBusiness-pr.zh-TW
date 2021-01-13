---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主體成員資格。
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831593"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="ee0a6-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="ee0a6-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="ee0a6-104">tblPrincipalMembers 包含主體成員資格。</span><span class="sxs-lookup"><span data-stu-id="ee0a6-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="ee0a6-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="ee0a6-105">**Columns**</span></span>

|<span data-ttu-id="ee0a6-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="ee0a6-106">**Column**</span></span>|<span data-ttu-id="ee0a6-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="ee0a6-107">**Type**</span></span>|<span data-ttu-id="ee0a6-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="ee0a6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee0a6-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ee0a6-109">prinID</span></span>  <br/> |<span data-ttu-id="ee0a6-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="ee0a6-110">int, not null</span></span>  <br/> |<span data-ttu-id="ee0a6-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="ee0a6-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ee0a6-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="ee0a6-112">memberADPath</span></span>  <br/> |<span data-ttu-id="ee0a6-113">Nvarchar (384) ，非 null</span><span class="sxs-lookup"><span data-stu-id="ee0a6-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="ee0a6-114">成員的辨識名稱。</span><span class="sxs-lookup"><span data-stu-id="ee0a6-114">Distinguished name of a member.</span></span> <span data-ttu-id="ee0a6-115">成員不一定要是 tblPrincipal table) 中的主體 (。</span><span class="sxs-lookup"><span data-stu-id="ee0a6-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="ee0a6-116">**Keys**</span><span class="sxs-lookup"><span data-stu-id="ee0a6-116">**Keys**</span></span>

|<span data-ttu-id="ee0a6-117">**欄**</span><span class="sxs-lookup"><span data-stu-id="ee0a6-117">**Column**</span></span>|<span data-ttu-id="ee0a6-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="ee0a6-118">**Description**</span></span>|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |<span data-ttu-id="ee0a6-119">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="ee0a6-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ee0a6-120">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ee0a6-120">prinID</span></span>  <br/> |<span data-ttu-id="ee0a6-121">在 tblPrincipal.prinID 中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="ee0a6-121">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

