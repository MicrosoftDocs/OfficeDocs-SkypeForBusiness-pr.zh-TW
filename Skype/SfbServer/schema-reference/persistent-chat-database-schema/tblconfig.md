---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久聊天伺服器不支援的設定，一列。
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809733"
---
# <a name="tblconfig"></a><span data-ttu-id="e97ce-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="e97ce-103">tblConfig</span></span>
 
<span data-ttu-id="e97ce-104">tblConfig 包含一些持久聊天伺服器不支援的設定，一列。</span><span class="sxs-lookup"><span data-stu-id="e97ce-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="e97ce-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e97ce-105">**Columns**</span></span>

|<span data-ttu-id="e97ce-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="e97ce-106">**Column**</span></span>|<span data-ttu-id="e97ce-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="e97ce-107">**Type**</span></span>|<span data-ttu-id="e97ce-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="e97ce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e97ce-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="e97ce-109">configLabel</span></span>  <br/> |<span data-ttu-id="e97ce-110">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="e97ce-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="e97ce-111">包含「集區」。</span><span class="sxs-lookup"><span data-stu-id="e97ce-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="e97ce-112">configContent</span><span class="sxs-lookup"><span data-stu-id="e97ce-112">configContent</span></span>  <br/> |<span data-ttu-id="e97ce-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="e97ce-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="e97ce-114">設定內容。</span><span class="sxs-lookup"><span data-stu-id="e97ce-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="e97ce-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="e97ce-115">configPoolID</span></span>  <br/> |<span data-ttu-id="e97ce-116">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="e97ce-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="e97ce-117">資料庫執行個體的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e97ce-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="e97ce-118">**Key**</span><span class="sxs-lookup"><span data-stu-id="e97ce-118">**Key**</span></span>

|<span data-ttu-id="e97ce-119">**欄**</span><span class="sxs-lookup"><span data-stu-id="e97ce-119">**Column**</span></span>|<span data-ttu-id="e97ce-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="e97ce-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e97ce-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="e97ce-121">configLabel</span></span>  <br/> |<span data-ttu-id="e97ce-122">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e97ce-122">Primary key.</span></span>  <br/> |
   

