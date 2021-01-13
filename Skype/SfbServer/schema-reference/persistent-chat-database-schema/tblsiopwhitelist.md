---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可與節點相關聯的註冊增益集清單。
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831483"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="4ed8c-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="4ed8c-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="4ed8c-104">tblSiopWhiteList 是可與節點相關聯的註冊增益集清單。</span><span class="sxs-lookup"><span data-stu-id="4ed8c-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="4ed8c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="4ed8c-105">**Columns**</span></span>

|<span data-ttu-id="4ed8c-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="4ed8c-106">**Column**</span></span>|<span data-ttu-id="4ed8c-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="4ed8c-107">**Type**</span></span>|<span data-ttu-id="4ed8c-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="4ed8c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ed8c-109">siopID</span><span class="sxs-lookup"><span data-stu-id="4ed8c-109">siopID</span></span>  <br/> |<span data-ttu-id="4ed8c-110">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="4ed8c-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="4ed8c-111">增益集的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4ed8c-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="4ed8c-112">siopName</span><span class="sxs-lookup"><span data-stu-id="4ed8c-112">siopName</span></span>  <br/> |<span data-ttu-id="4ed8c-113">nvarchar (50)，非 null</span><span class="sxs-lookup"><span data-stu-id="4ed8c-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="4ed8c-114">增益集的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="4ed8c-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="4ed8c-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="4ed8c-115">siopUrl</span></span>  <br/> |<span data-ttu-id="4ed8c-116">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="4ed8c-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="4ed8c-117">增益集的 URL。</span><span class="sxs-lookup"><span data-stu-id="4ed8c-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="4ed8c-118">**Key**</span><span class="sxs-lookup"><span data-stu-id="4ed8c-118">**Key**</span></span>

|<span data-ttu-id="4ed8c-119">**欄**</span><span class="sxs-lookup"><span data-stu-id="4ed8c-119">**Column**</span></span>|<span data-ttu-id="4ed8c-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="4ed8c-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4ed8c-121">siopID</span><span class="sxs-lookup"><span data-stu-id="4ed8c-121">siopID</span></span>  <br/> |<span data-ttu-id="4ed8c-122">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="4ed8c-122">Primary key.</span></span>  <br/> |
   

