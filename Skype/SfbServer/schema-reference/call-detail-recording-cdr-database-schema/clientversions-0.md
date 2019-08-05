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
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。 該視圖中的每一筆記錄代表一個用戶端版本。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192899"
---
# <a name="clientversions-view"></a><span data-ttu-id="c2df1-105">ClientVersions 視圖</span><span class="sxs-lookup"><span data-stu-id="c2df1-105">ClientVersions view</span></span>
 
<span data-ttu-id="c2df1-106">ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。</span><span class="sxs-lookup"><span data-stu-id="c2df1-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c2df1-107">該視圖中的每一筆記錄代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="c2df1-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="c2df1-108">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="c2df1-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2df1-109">某些欄可能有多個記錄。</span><span class="sxs-lookup"><span data-stu-id="c2df1-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="c2df1-110">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c2df1-110">**Column**</span></span>|<span data-ttu-id="c2df1-111">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c2df1-111">**Data Type**</span></span>|<span data-ttu-id="c2df1-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c2df1-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2df1-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="c2df1-113">**VersionId**</span></span> <br/> |<span data-ttu-id="c2df1-114">int</span><span class="sxs-lookup"><span data-stu-id="c2df1-114">int</span></span>  <br/> |<span data-ttu-id="c2df1-115">標識此用戶端類型與版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="c2df1-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="c2df1-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="c2df1-116">**Version**</span></span> <br/> |<span data-ttu-id="c2df1-117">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2df1-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2df1-118">代表使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="c2df1-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="c2df1-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="c2df1-119">**ClientType**</span></span> <br/> |<span data-ttu-id="c2df1-120">int</span><span class="sxs-lookup"><span data-stu-id="c2df1-120">int</span></span>  <br/> |<span data-ttu-id="c2df1-121">用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="c2df1-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="c2df1-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="c2df1-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="c2df1-123">Nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c2df1-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="c2df1-124">用戶端所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="c2df1-124">Category that the client belongs to.</span></span> <span data-ttu-id="c2df1-125">例如, 用戶端 Conferencing_Attendant_ 1.0 屬於 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="c2df1-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

