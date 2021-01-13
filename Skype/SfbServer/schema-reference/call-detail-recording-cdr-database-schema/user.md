---
title: 使用者視圖
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 使用者檢視會儲存在資料庫中有記錄之通話或工作階段中所涉及的使用者相關資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831693"
---
# <a name="user-view"></a><span data-ttu-id="77757-104">使用者視圖</span><span class="sxs-lookup"><span data-stu-id="77757-104">User view</span></span>
 
<span data-ttu-id="77757-105">使用者檢視會儲存在資料庫中有記錄之通話或工作階段中所涉及的使用者相關資訊。</span><span class="sxs-lookup"><span data-stu-id="77757-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="77757-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="77757-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="77757-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="77757-107">**Column**</span></span>|<span data-ttu-id="77757-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="77757-108">**Data Type**</span></span>|<span data-ttu-id="77757-109">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="77757-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77757-110">UserId</span><span class="sxs-lookup"><span data-stu-id="77757-110">UserId</span></span>  <br/> |<span data-ttu-id="77757-111">int</span><span class="sxs-lookup"><span data-stu-id="77757-111">int</span></span>  <br/> |<span data-ttu-id="77757-112">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="77757-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="77757-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="77757-113">UserUri</span></span>  <br/> |<span data-ttu-id="77757-114">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="77757-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="77757-115">使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="77757-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="77757-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="77757-116">TenantKey</span></span>  <br/> |<span data-ttu-id="77757-117">唯一</span><span class="sxs-lookup"><span data-stu-id="77757-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="77757-118">使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="77757-118">Tenant of user.</span></span> <span data-ttu-id="77757-119">如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。</span><span class="sxs-lookup"><span data-stu-id="77757-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="77757-120">UriType</span><span class="sxs-lookup"><span data-stu-id="77757-120">UriType</span></span>  <br/> |<span data-ttu-id="77757-121">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="77757-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="77757-122">使用者 URI 的類型。</span><span class="sxs-lookup"><span data-stu-id="77757-122">Type of user URI.</span></span> <span data-ttu-id="77757-123">如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。</span><span class="sxs-lookup"><span data-stu-id="77757-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

