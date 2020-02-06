---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含使用者的用戶端喜好設定。 這通常是由 Lync 2013 舊版用戶端使用。
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814551"
---
# <a name="tblpreference"></a><span data-ttu-id="2f9b0-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="2f9b0-104">tblPreference</span></span>

<span data-ttu-id="2f9b0-105">tblPreference 包含使用者的用戶端喜好設定。</span><span class="sxs-lookup"><span data-stu-id="2f9b0-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="2f9b0-106">這通常是由 Lync 2013 舊版用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="2f9b0-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="2f9b0-107">**分欄**</span><span class="sxs-lookup"><span data-stu-id="2f9b0-107">**Columns**</span></span>


| <span data-ttu-id="2f9b0-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="2f9b0-108">**Column**</span></span>            | <span data-ttu-id="2f9b0-109">**類型**</span><span class="sxs-lookup"><span data-stu-id="2f9b0-109">**Type**</span></span>                        | <span data-ttu-id="2f9b0-110">**說明**</span><span class="sxs-lookup"><span data-stu-id="2f9b0-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="2f9b0-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="2f9b0-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="2f9b0-112">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="2f9b0-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="2f9b0-113">具有以下格式的標籤： \<使用者 sip uri\></span><span class="sxs-lookup"><span data-stu-id="2f9b0-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="2f9b0-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="2f9b0-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="2f9b0-115">int，not null</span><span class="sxs-lookup"><span data-stu-id="2f9b0-115">int, not null</span></span>  <br/>            | <span data-ttu-id="2f9b0-116">用於進行版本設定的順序編號（每個標籤）。</span><span class="sxs-lookup"><span data-stu-id="2f9b0-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="2f9b0-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="2f9b0-117">prefContent</span></span>  <br/>    | <span data-ttu-id="2f9b0-118">Nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="2f9b0-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="2f9b0-119">已編碼的內容。</span><span class="sxs-lookup"><span data-stu-id="2f9b0-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="2f9b0-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="2f9b0-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="2f9b0-121">int，not null</span><span class="sxs-lookup"><span data-stu-id="2f9b0-121">int, not null</span></span>  <br/>            | <span data-ttu-id="2f9b0-122">更新喜好設定的主體 ID。</span><span class="sxs-lookup"><span data-stu-id="2f9b0-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="2f9b0-123">**機碼**</span><span class="sxs-lookup"><span data-stu-id="2f9b0-123">**Key**</span></span>

|<span data-ttu-id="2f9b0-124">**左欄**</span><span class="sxs-lookup"><span data-stu-id="2f9b0-124">**Column**</span></span>|<span data-ttu-id="2f9b0-125">**說明**</span><span class="sxs-lookup"><span data-stu-id="2f9b0-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2f9b0-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="2f9b0-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="2f9b0-127">主鍵。</span><span class="sxs-lookup"><span data-stu-id="2f9b0-127">Primary key.</span></span>  <br/> |


