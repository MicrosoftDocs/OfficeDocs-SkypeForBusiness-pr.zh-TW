---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主體成員資格。
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813941"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="f7220-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="f7220-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="f7220-104">tblPrincipalMembers 包含主體成員資格。</span><span class="sxs-lookup"><span data-stu-id="f7220-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="f7220-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="f7220-105">**Columns**</span></span>

|<span data-ttu-id="f7220-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="f7220-106">**Column**</span></span>|<span data-ttu-id="f7220-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="f7220-107">**Type**</span></span>|<span data-ttu-id="f7220-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="f7220-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7220-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f7220-109">prinID</span></span>  <br/> |<span data-ttu-id="f7220-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="f7220-110">int, not null</span></span>  <br/> |<span data-ttu-id="f7220-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="f7220-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f7220-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="f7220-112">memberADPath</span></span>  <br/> |<span data-ttu-id="f7220-113">Nvarchar （384），not null</span><span class="sxs-lookup"><span data-stu-id="f7220-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="f7220-114">成員的判別名。</span><span class="sxs-lookup"><span data-stu-id="f7220-114">Distinguished name of a member.</span></span> <span data-ttu-id="f7220-115">成員不一定要是 principal （在 tblPrincipal 資料表中）。</span><span class="sxs-lookup"><span data-stu-id="f7220-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="f7220-116">**鍵**</span><span class="sxs-lookup"><span data-stu-id="f7220-116">**Keys**</span></span>

|<span data-ttu-id="f7220-117">**左欄**</span><span class="sxs-lookup"><span data-stu-id="f7220-117">**Column**</span></span>|<span data-ttu-id="f7220-118">**說明**</span><span class="sxs-lookup"><span data-stu-id="f7220-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f7220-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="f7220-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="f7220-120">主鍵。</span><span class="sxs-lookup"><span data-stu-id="f7220-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f7220-121">prinID</span><span class="sxs-lookup"><span data-stu-id="f7220-121">prinID</span></span>  <br/> |<span data-ttu-id="f7220-122">在 tblPrincipal 中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="f7220-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

