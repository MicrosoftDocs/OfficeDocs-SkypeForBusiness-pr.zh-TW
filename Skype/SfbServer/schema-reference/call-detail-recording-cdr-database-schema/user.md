---
title: 使用者視圖
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: '[使用者] 視圖儲存已參與通話的使用者相關資訊，或在資料庫中有記錄的會話。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814831"
---
# <a name="user-view"></a><span data-ttu-id="c374b-104">使用者視圖</span><span class="sxs-lookup"><span data-stu-id="c374b-104">User view</span></span>
 
<span data-ttu-id="c374b-105">[使用者] 視圖儲存已參與通話的使用者相關資訊，或在資料庫中有記錄的會話。</span><span class="sxs-lookup"><span data-stu-id="c374b-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="c374b-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="c374b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c374b-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c374b-107">**Column**</span></span>|<span data-ttu-id="c374b-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c374b-108">**Data Type**</span></span>|<span data-ttu-id="c374b-109">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c374b-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c374b-110">UserId</span><span class="sxs-lookup"><span data-stu-id="c374b-110">UserId</span></span>  <br/> |<span data-ttu-id="c374b-111">int</span><span class="sxs-lookup"><span data-stu-id="c374b-111">int</span></span>  <br/> |<span data-ttu-id="c374b-112">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="c374b-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="c374b-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="c374b-113">UserUri</span></span>  <br/> |<span data-ttu-id="c374b-114">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="c374b-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c374b-115">使用者的 Uri。</span><span class="sxs-lookup"><span data-stu-id="c374b-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="c374b-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="c374b-116">TenantKey</span></span>  <br/> |<span data-ttu-id="c374b-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c374b-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="c374b-118">使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="c374b-118">Tenant of user.</span></span> <span data-ttu-id="c374b-119">如需詳細資訊，請參閱[承租人資料表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="c374b-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c374b-120">UriType</span><span class="sxs-lookup"><span data-stu-id="c374b-120">UriType</span></span>  <br/> |<span data-ttu-id="c374b-121">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="c374b-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c374b-122">使用者 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="c374b-122">Type of user URI.</span></span> <span data-ttu-id="c374b-123">如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="c374b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

