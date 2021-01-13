---
title: ClientVersions view
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions view 儲存已參與資料庫中記錄之會話的各種用戶端類型和版本資訊。 視圖中的每一筆記錄都代表一個用戶端版本。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813353"
---
# <a name="clientversions-view"></a><span data-ttu-id="1dde3-105">ClientVersions view</span><span class="sxs-lookup"><span data-stu-id="1dde3-105">ClientVersions view</span></span>
 
<span data-ttu-id="1dde3-106">ClientVersions view 儲存已參與資料庫中記錄之會話的各種用戶端類型和版本資訊。</span><span class="sxs-lookup"><span data-stu-id="1dde3-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="1dde3-107">視圖中的每一筆記錄都代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="1dde3-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="1dde3-108">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1dde3-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dde3-109">某些欄可能會有多筆記錄。</span><span class="sxs-lookup"><span data-stu-id="1dde3-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="1dde3-110">**欄**</span><span class="sxs-lookup"><span data-stu-id="1dde3-110">**Column**</span></span>|<span data-ttu-id="1dde3-111">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1dde3-111">**Data Type**</span></span>|<span data-ttu-id="1dde3-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="1dde3-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1dde3-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="1dde3-113">**VersionId**</span></span> <br/> |<span data-ttu-id="1dde3-114">int</span><span class="sxs-lookup"><span data-stu-id="1dde3-114">int</span></span>  <br/> |<span data-ttu-id="1dde3-115">用於識別此用戶端類型及版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="1dde3-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="1dde3-116">**版本**</span><span class="sxs-lookup"><span data-stu-id="1dde3-116">**Version**</span></span> <br/> |<span data-ttu-id="1dde3-117">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="1dde3-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1dde3-118">代表使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="1dde3-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="1dde3-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="1dde3-119">**ClientType**</span></span> <br/> |<span data-ttu-id="1dde3-120">int</span><span class="sxs-lookup"><span data-stu-id="1dde3-120">int</span></span>  <br/> |<span data-ttu-id="1dde3-121">用戶端的類型。</span><span class="sxs-lookup"><span data-stu-id="1dde3-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="1dde3-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="1dde3-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="1dde3-123">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="1dde3-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="1dde3-124">用戶端所屬的類別。</span><span class="sxs-lookup"><span data-stu-id="1dde3-124">Category that the client belongs to.</span></span> <span data-ttu-id="1dde3-125">例如，用戶端 Conferencing_Attendant_1 .0 屬於 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="1dde3-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

