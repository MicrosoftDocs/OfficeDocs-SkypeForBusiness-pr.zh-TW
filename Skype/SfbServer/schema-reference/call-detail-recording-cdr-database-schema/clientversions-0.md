---
title: ClientVersions 視圖
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。 該視圖中的每一筆記錄代表一個用戶端版本。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815411"
---
# <a name="clientversions-view"></a><span data-ttu-id="5f3d9-105">ClientVersions 視圖</span><span class="sxs-lookup"><span data-stu-id="5f3d9-105">ClientVersions view</span></span>
 
<span data-ttu-id="5f3d9-106">ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。</span><span class="sxs-lookup"><span data-stu-id="5f3d9-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="5f3d9-107">該視圖中的每一筆記錄代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="5f3d9-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="5f3d9-108">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="5f3d9-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f3d9-109">某些欄可能有多個記錄。</span><span class="sxs-lookup"><span data-stu-id="5f3d9-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="5f3d9-110">**左欄**</span><span class="sxs-lookup"><span data-stu-id="5f3d9-110">**Column**</span></span>|<span data-ttu-id="5f3d9-111">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="5f3d9-111">**Data Type**</span></span>|<span data-ttu-id="5f3d9-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="5f3d9-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f3d9-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="5f3d9-113">**VersionId**</span></span> <br/> |<span data-ttu-id="5f3d9-114">int</span><span class="sxs-lookup"><span data-stu-id="5f3d9-114">int</span></span>  <br/> |<span data-ttu-id="5f3d9-115">標識此用戶端類型與版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="5f3d9-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="5f3d9-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="5f3d9-116">**Version**</span></span> <br/> |<span data-ttu-id="5f3d9-117">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="5f3d9-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5f3d9-118">代表使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="5f3d9-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="5f3d9-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="5f3d9-119">**ClientType**</span></span> <br/> |<span data-ttu-id="5f3d9-120">int</span><span class="sxs-lookup"><span data-stu-id="5f3d9-120">int</span></span>  <br/> |<span data-ttu-id="5f3d9-121">用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="5f3d9-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="5f3d9-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="5f3d9-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="5f3d9-123">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="5f3d9-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="5f3d9-124">用戶端所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="5f3d9-124">Category that the client belongs to.</span></span> <span data-ttu-id="5f3d9-125">例如，用戶端 Conferencing_Attendant_1 .0 屬於 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="5f3d9-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

