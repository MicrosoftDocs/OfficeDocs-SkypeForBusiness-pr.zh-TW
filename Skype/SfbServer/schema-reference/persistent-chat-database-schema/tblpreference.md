---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 包含使用者的用戶端喜好設定。 這通常是 Lync 2013 之前的用戶端使用。
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815903"
---
# <a name="tblpreference"></a><span data-ttu-id="5f617-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="5f617-104">tblPreference</span></span>

<span data-ttu-id="5f617-105">tblPreference 包含使用者的用戶端喜好設定。</span><span class="sxs-lookup"><span data-stu-id="5f617-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="5f617-106">這通常是 Lync 2013 之前的用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="5f617-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="5f617-107">**Columns**</span><span class="sxs-lookup"><span data-stu-id="5f617-107">**Columns**</span></span>


| <span data-ttu-id="5f617-108">**欄**</span><span class="sxs-lookup"><span data-stu-id="5f617-108">**Column**</span></span>            | <span data-ttu-id="5f617-109">**類型**</span><span class="sxs-lookup"><span data-stu-id="5f617-109">**Type**</span></span>                        | <span data-ttu-id="5f617-110">**描述**</span><span class="sxs-lookup"><span data-stu-id="5f617-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="5f617-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="5f617-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="5f617-112">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="5f617-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="5f617-113">標籤，格式如下： \<user sip uri\></span><span class="sxs-lookup"><span data-stu-id="5f617-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="5f617-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="5f617-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="5f617-115">int，非 null</span><span class="sxs-lookup"><span data-stu-id="5f617-115">int, not null</span></span>  <br/>            | <span data-ttu-id="5f617-116">每個標籤的序數位 (，供版本設定之用) 。</span><span class="sxs-lookup"><span data-stu-id="5f617-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="5f617-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="5f617-117">prefContent</span></span>  <br/>    | <span data-ttu-id="5f617-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5f617-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="5f617-119">編碼內容。</span><span class="sxs-lookup"><span data-stu-id="5f617-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="5f617-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="5f617-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="5f617-121">int，非 null</span><span class="sxs-lookup"><span data-stu-id="5f617-121">int, not null</span></span>  <br/>            | <span data-ttu-id="5f617-122">更新首選項的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="5f617-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="5f617-123">**Key**</span><span class="sxs-lookup"><span data-stu-id="5f617-123">**Key**</span></span>

|<span data-ttu-id="5f617-124">**欄**</span><span class="sxs-lookup"><span data-stu-id="5f617-124">**Column**</span></span>|<span data-ttu-id="5f617-125">**描述**</span><span class="sxs-lookup"><span data-stu-id="5f617-125">**Description**</span></span>|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |<span data-ttu-id="5f617-126">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="5f617-126">Primary key.</span></span>  <br/> |


